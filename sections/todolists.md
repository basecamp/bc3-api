To-do lists
===========

Endpoints:

- [Get to-do lists](#get-to-do-lists)
- [Get a to-do list](#get-a-to-do-list)
- [Create a to-do list](#create-a-to-do-list)
- [Update a to-do list](#update-a-to-do-list)
- [Trash a to-do list][trash]

Get to-do lists
---------------

* `GET /buckets/1/todosets/3/todolists.json` will return a [paginated list][pagination] of active to-do lists in the project with an ID of `1` and the to-do set with ID of `3`.

To get the to-do set ID for a project, see the [Get to-do set][todoset] endpoint.

_Optional query parameters_:

* `status` - when set to `archived` or `trashed`, will return archived or trashed to-do lists that are in this to-do set.

###### Example JSON Response
<!-- START GET /buckets/1/todosets/3/todolists.json -->
```json
[
  {
    "id": 1069479573,
    "status": "active",
    "visible_to_clients": false,
    "created_at": "2026-01-15T05:50:00.000Z",
    "updated_at": "2026-02-01T02:53:47.036Z",
    "title": "Strategy ideas",
    "inherits_status": true,
    "type": "Todolist",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958504/todolists/1069479573.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958504/todolists/1069479573",
    "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiLmdpZDovL2JjMy9SZWNvcmRpbmcvMTA2OTQ3OTU3Mz9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg1yZWFkYWJsZQY7AFQ=--3edc00987d9016d2ac5115dabef3d1f0f1dacb64.json",
    "subscription_url": "https://3.basecampapi.com/195539477/buckets/2085958504/recordings/1069479573/subscription.json",
    "comments_count": 0,
    "comments_url": "https://3.basecampapi.com/195539477/buckets/2085958504/recordings/1069479573/comments.json",
    "boosts_count": 0,
    "boosts_url": "https://3.basecampapi.com/195539477/buckets/2085958504/recordings/1069479573/boosts.json",
    "position": 1,
    "parent": {
      "id": 1069479393,
      "title": "To-dos",
      "type": "Todoset",
      "url": "https://3.basecampapi.com/195539477/buckets/2085958504/todosets/1069479393.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958504/todosets/1069479393"
    },
    "bucket": {
      "id": 2085958504,
      "name": "The Leto Laptop",
      "type": "Project"
    },
    "creator": {
      "id": 1049715913,
      "attachable_sgid": "BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiK2dpZDovL2JjMy9QZXJzb24vMTA0OTcxNTkxMz9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg9hdHRhY2hhYmxlBjsAVA==--e627c45e6b34e08862da23906862412620e4d5d9",
      "name": "Victor Cooper",
      "email_address": "victor@honchodesign.com",
      "personable_type": "User",
      "title": "Chief Strategist",
      "bio": "Don’t let your dreams be dreams",
      "location": "Chicago, IL",
      "created_at": "2026-01-31T08:29:28.365Z",
      "updated_at": "2026-01-31T08:29:32.599Z",
      "admin": true,
      "owner": true,
      "client": false,
      "employee": true,
      "time_zone": "America/Chicago",
      "avatar_url": "https://3.basecampapi.com/195539477/people/BAhpBMlkkT4=--5fe7b70fbee7a7f0e2e1e19df7579e5d880c753d/avatar?v=1",
      "company": {
        "id": 1033447817,
        "name": "Honcho Design"
      },
      "can_ping": true,
      "can_manage_projects": true,
      "can_manage_people": true,
      "can_access_timesheet": true,
      "can_access_hill_charts": true
    },
    "description": "",
    "completed": false,
    "completed_ratio": "2/5",
    "name": "Strategy ideas",
    "color": null,
    "groups_url": "https://3.basecampapi.com/195539477/buckets/2085958504/todolists/1069479573/groups.json",
    "todos_url": "https://3.basecampapi.com/195539477/buckets/2085958504/todolists/1069479573/todos.json",
    "app_todos_url": "https://3.basecamp.com/195539477/buckets/2085958504/todolists/1069479573/todos",
    "comments_app_url": "https://3.basecamp.com/195539477/buckets/2085958504/recordings/1069479573/comments"
  }
]
```
<!-- END GET /buckets/1/todosets/3/todolists.json -->
###### Copy as cURL

```shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/todosets/3/todolists.json
```


Get a to-do list
----------------

* `GET /buckets/1/todolists/2.json` will return the to-do list with an ID of `2` in the project with an ID of `1`.

###### Example JSON Response
<!-- START GET /buckets/1/todolists/2.json -->
```json
{
  "id": 1069479424,
  "status": "active",
  "visible_to_clients": false,
  "created_at": "2025-12-20T18:09:00.000Z",
  "updated_at": "2026-01-31T08:32:13.249Z",
  "title": "Background and research",
  "inherits_status": true,
  "type": "Todolist",
  "url": "https://3.basecampapi.com/195539477/buckets/2085958504/todolists/1069479424.json",
  "app_url": "https://3.basecamp.com/195539477/buckets/2085958504/todolists/1069479424",
  "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiLmdpZDovL2JjMy9SZWNvcmRpbmcvMTA2OTQ3OTQyND9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg1yZWFkYWJsZQY7AFQ=--4fe2ce4602873b2bea4e9189685d5fa0ebf1c8da.json",
  "subscription_url": "https://3.basecampapi.com/195539477/buckets/2085958504/recordings/1069479424/subscription.json",
  "comments_count": 0,
  "comments_url": "https://3.basecampapi.com/195539477/buckets/2085958504/recordings/1069479424/comments.json",
  "boosts_count": 0,
  "boosts_url": "https://3.basecampapi.com/195539477/buckets/2085958504/recordings/1069479424/boosts.json",
  "position": 10,
  "parent": {
    "id": 1069479393,
    "title": "To-dos",
    "type": "Todoset",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958504/todosets/1069479393.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958504/todosets/1069479393"
  },
  "bucket": {
    "id": 2085958504,
    "name": "The Leto Laptop",
    "type": "Project"
  },
  "creator": {
    "id": 1049715913,
    "attachable_sgid": "BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiK2dpZDovL2JjMy9QZXJzb24vMTA0OTcxNTkxMz9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg9hdHRhY2hhYmxlBjsAVA==--e627c45e6b34e08862da23906862412620e4d5d9",
    "name": "Victor Cooper",
    "email_address": "victor@honchodesign.com",
    "personable_type": "User",
    "title": "Chief Strategist",
    "bio": "Don’t let your dreams be dreams",
    "location": "Chicago, IL",
    "created_at": "2026-01-31T08:29:28.365Z",
    "updated_at": "2026-01-31T08:29:32.599Z",
    "admin": true,
    "owner": true,
    "client": false,
    "employee": true,
    "time_zone": "America/Chicago",
    "avatar_url": "https://3.basecampapi.com/195539477/people/BAhpBMlkkT4=--5fe7b70fbee7a7f0e2e1e19df7579e5d880c753d/avatar?v=1",
    "company": {
      "id": 1033447817,
      "name": "Honcho Design"
    },
    "can_ping": true,
    "can_manage_projects": true,
    "can_manage_people": true,
    "can_access_timesheet": true,
    "can_access_hill_charts": true
  },
  "description": "",
  "completed": false,
  "completed_ratio": "0/4",
  "name": "Background and research",
  "color": null,
  "groups_url": "https://3.basecampapi.com/195539477/buckets/2085958504/todolists/1069479424/groups.json",
  "todos_url": "https://3.basecampapi.com/195539477/buckets/2085958504/todolists/1069479424/todos.json",
  "app_todos_url": "https://3.basecamp.com/195539477/buckets/2085958504/todolists/1069479424/todos",
  "comments_app_url": "https://3.basecamp.com/195539477/buckets/2085958504/recordings/1069479424/comments"
}
```
<!-- END GET /buckets/1/todolists/2.json -->
###### Copy as cURL

```shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/todolists/2.json
```


Create a to-do list
-------------------

* `POST /buckets/1/todosets/3/todolists.json` creates a to-do list in the project with ID `1` and under the to-do set with an ID of `3`.

**Required parameters**: `name` of the to-do list.

_Optional parameters_: `description` containing information about the to-do list. See our [Rich text guide][rich] for what HTML tags are allowed.

This endpoint will return `201 Created` with the current JSON representation of the to-do list if the creation was a success. See the [Get a to-do list](#get-a-to-do-list) endpoint for more info on the payload.

###### Example JSON Request

```json
{
  "name": "Launch",
  "description": "<div><em>Finish it!</em></div>"
}
```

###### Copy as cURL

```shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -H "Content-Type: application/json" \
  -d '{"name":"Launch","description":"<div><em>Finish it!</em></div>"}' \
  https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/todosets/3/todolists.json
```


Update a to-do list
-------------------

* `PUT /buckets/1/todolists/2.json` allows changing the name and description of the to-do list with an ID of `2` in the project with ID `1`.

This endpoint will return `200 OK` with the current JSON representation of the to-do list if the update was a success. See the [Get a to-do list](#get-a-to-do-list) endpoint for more info on the payload.

**Required parameters**: Pass all existing parameters in addition to those being updated. Omitting a parameter will clear its value.

* `name` of the to-do list. This one is always required, it can't be omitted as it can't be blank.

* `description` containing information about the to-do list. See our [Rich text guide][rich] for what HTML tags are allowed.

###### Example JSON Request

```json
{
  "name": "Relaunch",
  "description": "<div><strong>Try this again.</strong></div>"
}
```

###### Copy as cURL

```shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -H "Content-Type: application/json" \
  -d '{"name":"Relaunch","description":"<div><strong>Try this again.</strong></div>"}' -X PUT \
  https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/todolists/2.json
```


[trash]: https://github.com/basecamp/bc3-api/blob/master/sections/recordings.md#trash-a-recording
[pagination]: https://github.com/basecamp/bc3-api/blob/master/README.md#pagination
[todoset]: https://github.com/basecamp/bc3-api/blob/master/sections/todosets.md#get-to-do-set
[todos]: https://github.com/basecamp/bc3-api/blob/master/sections/todos.md#to-dos
[rich]: https://github.com/basecamp/bc3-api/blob/master/sections/rich_text.md
