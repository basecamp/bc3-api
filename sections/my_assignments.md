My assignments
===============

Endpoints for retrieving the current user's assignments, including active assignments split by priority, completed assignments, and due assignments filtered by time scope.

Each assignment includes its content, type, bucket, parent, assignees, due dates, completion status, and any child assignments (e.g. card steps nested under their parent card).

**Note:** These endpoints return the full result set and are not paginated.

Endpoints:

- [Get assignments](#get-assignments)
- [Get completed assignments](#get-completed-assignments)
- [Get due assignments](#get-due-assignments)


Get assignments
---------------

* `GET /my/assignments.json` will return the current user's active assignments grouped into `priorities` and `non_priorities`. Card table steps are normalized to their parent card, with steps included as `children`.

###### Example JSON Response
<!-- START GET /my/assignments.json -->
```json
{
  "priorities": [
    {
      "id": 9007199254741623,
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958504/todos/9007199254741623",
      "content": "Program the flux capacitor",
      "starts_on": null,
      "due_on": "2026-03-15",
      "bucket": {
        "id": 2085958504,
        "name": "The Leto Laptop",
        "app_url": "https://3.basecamp.com/195539477/buckets/2085958504"
      },
      "completed": false,
      "type": "todo",
      "assignees": [
        {
          "id": 1049715913,
          "name": "Victor Cooper",
          "avatar_url": "https://3.basecampapi.com/195539477/people/BAhpBMlkkT4=--5fe7b70fbee7a7f0e2e1e19df7579e5d880c753d/avatar"
        }
      ],
      "comments_count": 0,
      "has_description": false,
      "priority_recording_id": 9007199254741700,
      "parent": {
        "id": 9007199254741601,
        "title": "Development tasks",
        "app_url": "https://3.basecamp.com/195539477/buckets/2085958504/todolists/9007199254741601"
      },
      "children": []
    }
  ],
  "non_priorities": [
    {
      "id": 9007199254741650,
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958504/todos/9007199254741650",
      "content": "Design the landing page",
      "starts_on": null,
      "due_on": null,
      "bucket": {
        "id": 2085958504,
        "name": "The Leto Laptop",
        "app_url": "https://3.basecamp.com/195539477/buckets/2085958504"
      },
      "completed": false,
      "type": "todo",
      "assignees": [
        {
          "id": 1049715913,
          "name": "Victor Cooper",
          "avatar_url": "https://3.basecampapi.com/195539477/people/BAhpBMlkkT4=--5fe7b70fbee7a7f0e2e1e19df7579e5d880c753d/avatar"
        }
      ],
      "comments_count": 2,
      "has_description": true,
      "parent": {
        "id": 9007199254741601,
        "title": "Development tasks",
        "app_url": "https://3.basecamp.com/195539477/buckets/2085958504/todolists/9007199254741601"
      },
      "children": []
    }
  ]
}
```
<!-- END GET /my/assignments.json -->

Assignments with card table steps are normalized so the parent card appears as the top-level item with its steps nested as `children`. Priority items include a `priority_recording_id` field.

###### Copy as cURL

```shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/my/assignments.json
```


Get completed assignments
-------------------------

* `GET /my/assignments/completed.json` will return the current user's completed assignments. Archived and trashed recordings are excluded.

###### Example JSON Response
<!-- START GET /my/assignments/completed.json -->
```json
[
  {
    "id": 9007199254741623,
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958504/todos/9007199254741623",
    "content": "Program the flux capacitor",
    "starts_on": null,
    "due_on": "2026-03-15",
    "bucket": {
      "id": 2085958504,
      "name": "The Leto Laptop",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958504"
    },
    "completed": true,
    "type": "todo",
    "assignees": [
      {
        "id": 1049715913,
        "name": "Victor Cooper",
        "avatar_url": "https://3.basecampapi.com/195539477/people/BAhpBMlkkT4=--5fe7b70fbee7a7f0e2e1e19df7579e5d880c753d/avatar"
      }
    ],
    "comments_count": 0,
    "has_description": false,
    "parent": {
      "id": 9007199254741601,
      "title": "Development tasks",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958504/todolists/9007199254741601"
    },
    "children": []
  }
]
```
<!-- END GET /my/assignments/completed.json -->

###### Copy as cURL

```shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/my/assignments/completed.json
```


Get due assignments
-------------------

* `GET /my/assignments/due.json` will return the current user's assignments filtered by due date scope. Defaults to `overdue` when no scope is provided.

_Optional parameters_:

* `scope` - filter by due date range. Valid options: `overdue`, `due_today`, `due_tomorrow`, `due_later_this_week`, `due_next_week`, `due_later`.

Providing an invalid `scope` returns `400 Bad Request` with an error listing the valid options:

```json
{
  "error": "Invalid scope 'invalid'. Valid options: overdue, due_today, due_tomorrow, due_later_this_week, due_next_week, due_later"
}
```

###### Example JSON Response
<!-- START GET /my/assignments/due.json -->
```json
[
  {
    "id": 9007199254741623,
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958504/todos/9007199254741623",
    "content": "Program the flux capacitor",
    "starts_on": null,
    "due_on": "2026-03-10",
    "bucket": {
      "id": 2085958504,
      "name": "The Leto Laptop",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958504"
    },
    "completed": false,
    "type": "todo",
    "assignees": [
      {
        "id": 1049715913,
        "name": "Victor Cooper",
        "avatar_url": "https://3.basecampapi.com/195539477/people/BAhpBMlkkT4=--5fe7b70fbee7a7f0e2e1e19df7579e5d880c753d/avatar"
      }
    ],
    "comments_count": 0,
    "has_description": false,
    "parent": {
      "id": 9007199254741601,
      "title": "Development tasks",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958504/todolists/9007199254741601"
    },
    "children": []
  }
]
```
<!-- END GET /my/assignments/due.json -->

###### Copy as cURL

```shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/my/assignments/due.json?scope=overdue
```
