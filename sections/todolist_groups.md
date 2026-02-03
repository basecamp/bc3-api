To-do list groups
=================

Endpoints:

- [List to-do list groups](#list-to-do-list-groups)
- [Get a to-do list group](#get-to-do-list-group)
- [Create a to-do list group](#create-a-to-do-list-group)
- [Reposition a to-do list group](#reposition-a-to-do-list-group)

List to-do list groups
----------------------

* `GET /buckets/1/todolists/2/groups.json` will return a [paginated list][pagination] of active groups in the project with an ID of `1` and the to-do list with ID of `2`.

_Optional query parameters_:

* `status` - when set to `archived` or `trashed`, returns only archived or trashed to-do list groups within this to-do list.

###### Example JSON Response
<!-- START GET /buckets/1/todolists/2/groups.json -->
```json
[
  {
    "id": 1069479153,
    "status": "active",
    "visible_to_clients": false,
    "created_at": "2026-01-01T22:32:00.000Z",
    "updated_at": "2026-01-31T08:30:50.887Z",
    "title": "Group A",
    "inherits_status": true,
    "type": "Todolist",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958502/todolists/1069479153.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958502/todolists/1069479153",
    "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiLmdpZDovL2JjMy9SZWNvcmRpbmcvMTA2OTQ3OTE1Mz9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg1yZWFkYWJsZQY7AFQ=--a26b7fc6739381648d87196eaefbe0cfbf2746ef.json",
    "subscription_url": "https://3.basecampapi.com/195539477/buckets/2085958502/recordings/1069479153/subscription.json",
    "comments_count": 0,
    "comments_url": "https://3.basecampapi.com/195539477/buckets/2085958502/recordings/1069479153/comments.json",
    "position": 1,
    "parent": {
      "id": 1069479152,
      "title": "Ping pong tournament",
      "type": "Todolist",
      "url": "https://3.basecampapi.com/195539477/buckets/2085958502/todolists/1069479152.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958502/todolists/1069479152"
    },
    "bucket": {
      "id": 2085958502,
      "name": "Honcho Design Newsroom",
      "type": "Project"
    },
    "creator": {
      "id": 1049715918,
      "attachable_sgid": "BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiK2dpZDovL2JjMy9QZXJzb24vMTA0OTcxNTkxOD9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg9hdHRhY2hhYmxlBjsAVA==--d6212bd7e60bf63ea61797589b2638cbbf2d4ed7",
      "name": "Brian Jenks",
      "email_address": "brian@honchodesign.com",
      "personable_type": "User",
      "title": "International Branding Liason",
      "bio": null,
      "location": null,
      "created_at": "2026-01-31T08:29:34.525Z",
      "updated_at": "2026-01-31T08:29:34.525Z",
      "admin": false,
      "owner": false,
      "client": false,
      "employee": false,
      "time_zone": "America/Chicago",
      "avatar_url": "https://3.basecampapi.com/195539477/people/BAhpBM5kkT4=--50075f17f313c1198fb6f27e5d466327804dfd22/avatar?v=1",
      "can_ping": true,
      "can_manage_projects": true,
      "can_manage_people": true,
      "can_access_timesheet": true,
      "can_access_hill_charts": true
    },
    "description": "",
    "completed": false,
    "completed_ratio": "0/2",
    "name": "Group A",
    "color": null,
    "group_position_url": "https://3.basecampapi.com/195539477/buckets/2085958502/todolists/groups/1069479153/position.json",
    "todos_url": "https://3.basecampapi.com/195539477/buckets/2085958502/todolists/1069479153/todos.json",
    "app_todos_url": "https://3.basecamp.com/195539477/buckets/2085958502/todolists/1069479153/todos",
    "comments_app_url": "https://3.basecamp.com/195539477/buckets/2085958502/recordings/1069479153/comments"
  },
  {
    "id": 1069479156,
    "status": "active",
    "visible_to_clients": false,
    "created_at": "2026-01-01T22:58:00.000Z",
    "updated_at": "2026-01-31T08:30:51.823Z",
    "title": "Group B",
    "inherits_status": true,
    "type": "Todolist",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958502/todolists/1069479156.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958502/todolists/1069479156",
    "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiLmdpZDovL2JjMy9SZWNvcmRpbmcvMTA2OTQ3OTE1Nj9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg1yZWFkYWJsZQY7AFQ=--e0947e0fc5ec107b039a998e2f52ce75e86fdc32.json",
    "subscription_url": "https://3.basecampapi.com/195539477/buckets/2085958502/recordings/1069479156/subscription.json",
    "comments_count": 0,
    "comments_url": "https://3.basecampapi.com/195539477/buckets/2085958502/recordings/1069479156/comments.json",
    "position": 2,
    "parent": {
      "id": 1069479152,
      "title": "Ping pong tournament",
      "type": "Todolist",
      "url": "https://3.basecampapi.com/195539477/buckets/2085958502/todolists/1069479152.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958502/todolists/1069479152"
    },
    "bucket": {
      "id": 2085958502,
      "name": "Honcho Design Newsroom",
      "type": "Project"
    },
    "creator": {
      "id": 1049715918,
      "attachable_sgid": "BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiK2dpZDovL2JjMy9QZXJzb24vMTA0OTcxNTkxOD9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg9hdHRhY2hhYmxlBjsAVA==--d6212bd7e60bf63ea61797589b2638cbbf2d4ed7",
      "name": "Brian Jenks",
      "email_address": "brian@honchodesign.com",
      "personable_type": "User",
      "title": "International Branding Liason",
      "bio": null,
      "location": null,
      "created_at": "2026-01-31T08:29:34.525Z",
      "updated_at": "2026-01-31T08:29:34.525Z",
      "admin": false,
      "owner": false,
      "client": false,
      "employee": false,
      "time_zone": "America/Chicago",
      "avatar_url": "https://3.basecampapi.com/195539477/people/BAhpBM5kkT4=--50075f17f313c1198fb6f27e5d466327804dfd22/avatar?v=1",
      "can_ping": true,
      "can_manage_projects": true,
      "can_manage_people": true,
      "can_access_timesheet": true,
      "can_access_hill_charts": true
    },
    "description": "",
    "completed": false,
    "completed_ratio": "0/2",
    "name": "Group B",
    "color": null,
    "group_position_url": "https://3.basecampapi.com/195539477/buckets/2085958502/todolists/groups/1069479156/position.json",
    "todos_url": "https://3.basecampapi.com/195539477/buckets/2085958502/todolists/1069479156/todos.json",
    "app_todos_url": "https://3.basecamp.com/195539477/buckets/2085958502/todolists/1069479156/todos",
    "comments_app_url": "https://3.basecamp.com/195539477/buckets/2085958502/recordings/1069479156/comments"
  }
]
```
<!-- END GET /buckets/1/todolists/2/groups.json -->
###### Copy as cURL

```shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/todolists/2/groups.json
```

Get a to-do list group
----------------------

To-do list groups can be read in exactly the same way as to-do lists. The only difference is a top-level to-do list will
include a groups_url in its response, while a group will have a group_position_url

* `GET /buckets/1/todolists/3.json` will return the to-do list group with an ID of `3` in the project with an ID of `1`.

###### Example JSON Response
<!-- START GET /buckets/1/todolists/3.json -->
```json
{
  "id": 1069479153,
  "status": "active",
  "visible_to_clients": false,
  "created_at": "2026-01-01T22:32:00.000Z",
  "updated_at": "2026-01-31T08:30:50.887Z",
  "title": "Group A",
  "inherits_status": true,
  "type": "Todolist",
  "url": "https://3.basecampapi.com/195539477/buckets/2085958502/todolists/1069479153.json",
  "app_url": "https://3.basecamp.com/195539477/buckets/2085958502/todolists/1069479153",
  "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiLmdpZDovL2JjMy9SZWNvcmRpbmcvMTA2OTQ3OTE1Mz9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg1yZWFkYWJsZQY7AFQ=--a26b7fc6739381648d87196eaefbe0cfbf2746ef.json",
  "subscription_url": "https://3.basecampapi.com/195539477/buckets/2085958502/recordings/1069479153/subscription.json",
  "comments_count": 0,
  "comments_url": "https://3.basecampapi.com/195539477/buckets/2085958502/recordings/1069479153/comments.json",
  "position": 1,
  "parent": {
    "id": 1069479152,
    "title": "Ping pong tournament",
    "type": "Todolist",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958502/todolists/1069479152.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958502/todolists/1069479152"
  },
  "bucket": {
    "id": 2085958502,
    "name": "Honcho Design Newsroom",
    "type": "Project"
  },
  "creator": {
    "id": 1049715918,
    "attachable_sgid": "BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiK2dpZDovL2JjMy9QZXJzb24vMTA0OTcxNTkxOD9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg9hdHRhY2hhYmxlBjsAVA==--d6212bd7e60bf63ea61797589b2638cbbf2d4ed7",
    "name": "Brian Jenks",
    "email_address": "brian@honchodesign.com",
    "personable_type": "User",
    "title": "International Branding Liason",
    "bio": null,
    "location": null,
    "created_at": "2026-01-31T08:29:34.525Z",
    "updated_at": "2026-01-31T08:29:34.525Z",
    "admin": false,
    "owner": false,
    "client": false,
    "employee": false,
    "time_zone": "America/Chicago",
    "avatar_url": "https://3.basecampapi.com/195539477/people/BAhpBM5kkT4=--50075f17f313c1198fb6f27e5d466327804dfd22/avatar?v=1",
    "can_ping": true,
    "can_manage_projects": true,
    "can_manage_people": true,
    "can_access_timesheet": true,
    "can_access_hill_charts": true
  },
  "description": "",
  "completed": false,
  "completed_ratio": "0/2",
  "name": "Group A",
  "color": null,
  "group_position_url": "https://3.basecampapi.com/195539477/buckets/2085958502/todolists/groups/1069479153/position.json",
  "todos_url": "https://3.basecampapi.com/195539477/buckets/2085958502/todolists/1069479153/todos.json",
  "app_todos_url": "https://3.basecamp.com/195539477/buckets/2085958502/todolists/1069479153/todos",
  "comments_app_url": "https://3.basecamp.com/195539477/buckets/2085958502/recordings/1069479153/comments"
}
```
<!-- END GET /buckets/1/todolists/3.json -->

Create a to-do list group
-------------------------

* `POST /buckets/1/todolists/2/groups.json` creates a to-do group within the todolist with ID `2` in the project with id `1`.

**Required parameters**: `name` of the to-do list group.

_Optional parameters_:

* `color` - the color. Available values: `[ white red orange yellow green blue aqua purple gray pink brown ]`

This endpoint will return `201 Created` with the current JSON representation of the to-do list if the creation was a success. See the [Get a to-do list](#get-a-to-do-list) endpoint for more info on the payload.

###### Example JSON Request

```json
{
  "name": "The Spencer Davis Group",
}
```

###### Copy as cURL

```shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -H "Content-Type: application/json" \
  -d '{"name":"The Spencer Davis Group"}' \
  https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/todolists/2/groups.json
```

Reposition a to-do list group
-----------------------------

* `PUT /buckets/1/todolists/groups/3/position.json` allows changing the position of the to-do list group with an ID of `3` in the project with ID `1`.

**Required parameters**: `position` greater than or equal to one.

This endpoint will return `204 No Content` if the update was a success.

###### Example JSON Request

```json
{
  "position": 3
}
```

###### Copy as cURL

```shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -H "Content-Type: application/json" \
  -d '{"position":3}' -X PUT \
  https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/todolists/groups/3/position.json
```

[pagination]: https://github.com/basecamp/bc3-api/blob/master/README.md#pagination
