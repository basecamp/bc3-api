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
    "id": 1069479100,
    "status": "active",
    "visible_to_clients": false,
    "created_at": "2022-10-21T10:24:24.930Z",
    "updated_at": "2022-11-22T08:23:38.003Z",
    "title": "Group A",
    "inherits_status": true,
    "type": "Todolist",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958497/todolists/1069479100.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958497/todolists/1069479100",
    "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7CEkiCGdpZAY6BkVUSSIuZ2lkOi8vYmMzL1JlY29yZGluZy8xMDY5NDc5MTAwP2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg1yZWFkYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--7925d04412570c8f9576fa5ead98f77b9d48640c.json",
    "subscription_url": "https://3.basecampapi.com/195539477/buckets/2085958497/recordings/1069479100/subscription.json",
    "comments_count": 0,
    "comments_url": "https://3.basecampapi.com/195539477/buckets/2085958497/recordings/1069479100/comments.json",
    "position": 1,
    "parent": {
      "id": 1069479099,
      "title": "Ping pong tournament",
      "type": "Todolist",
      "url": "https://3.basecampapi.com/195539477/buckets/2085958497/todolists/1069479099.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958497/todolists/1069479099"
    },
    "bucket": {
      "id": 2085958497,
      "name": "Honcho Design Newsroom",
      "type": "Project"
    },
    "creator": {
      "id": 1049715925,
      "attachable_sgid": "BAh7CEkiCGdpZAY6BkVUSSIrZ2lkOi8vYmMzL1BlcnNvbi8xMDQ5NzE1OTI1P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg9hdHRhY2hhYmxlBjsAVEkiD2V4cGlyZXNfYXQGOwBUMA==--6a81661a78620c3dfbd47bd56f73be4a144efb77",
      "name": "Brian Jenks",
      "email_address": "brian@honchodesign.com",
      "personable_type": "User",
      "title": "International Branding Liason",
      "bio": null,
      "location": null,
      "created_at": "2022-11-22T08:23:22.042Z",
      "updated_at": "2022-11-22T08:23:22.042Z",
      "admin": false,
      "owner": false,
      "client": false,
      "employee": false,
      "time_zone": "Etc/UTC",
      "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBNVkkT4=--d1d91cb4e7b2a143d18329cd4e8ec4d65fbda939/avatar?v=1",
      "can_manage_projects": true,
      "can_manage_people": true
    },
    "description": "",
    "completed": false,
    "completed_ratio": "0/2",
    "name": "Group A",
    "todos_url": "https://3.basecampapi.com/195539477/buckets/2085958497/todolists/1069479100/todos.json",
    "group_position_url": "https://3.basecampapi.com/195539477/buckets/2085958497/todolists/groups/1069479100/position.json",
    "app_todos_url": "https://3.basecamp.com/195539477/buckets/2085958497/todolists/1069479100/todos"
  },
  {
    "id": 1069479103,
    "status": "active",
    "visible_to_clients": false,
    "created_at": "2022-10-21T08:56:24.930Z",
    "updated_at": "2022-11-22T08:23:38.283Z",
    "title": "Group B",
    "inherits_status": true,
    "type": "Todolist",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958497/todolists/1069479103.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958497/todolists/1069479103",
    "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7CEkiCGdpZAY6BkVUSSIuZ2lkOi8vYmMzL1JlY29yZGluZy8xMDY5NDc5MTAzP2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg1yZWFkYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--ef5ad3d44bdf9c717ea154529f49d7166f90c5fc.json",
    "subscription_url": "https://3.basecampapi.com/195539477/buckets/2085958497/recordings/1069479103/subscription.json",
    "comments_count": 0,
    "comments_url": "https://3.basecampapi.com/195539477/buckets/2085958497/recordings/1069479103/comments.json",
    "position": 2,
    "parent": {
      "id": 1069479099,
      "title": "Ping pong tournament",
      "type": "Todolist",
      "url": "https://3.basecampapi.com/195539477/buckets/2085958497/todolists/1069479099.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958497/todolists/1069479099"
    },
    "bucket": {
      "id": 2085958497,
      "name": "Honcho Design Newsroom",
      "type": "Project"
    },
    "creator": {
      "id": 1049715925,
      "attachable_sgid": "BAh7CEkiCGdpZAY6BkVUSSIrZ2lkOi8vYmMzL1BlcnNvbi8xMDQ5NzE1OTI1P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg9hdHRhY2hhYmxlBjsAVEkiD2V4cGlyZXNfYXQGOwBUMA==--6a81661a78620c3dfbd47bd56f73be4a144efb77",
      "name": "Brian Jenks",
      "email_address": "brian@honchodesign.com",
      "personable_type": "User",
      "title": "International Branding Liason",
      "bio": null,
      "location": null,
      "created_at": "2022-11-22T08:23:22.042Z",
      "updated_at": "2022-11-22T08:23:22.042Z",
      "admin": false,
      "owner": false,
      "client": false,
      "employee": false,
      "time_zone": "Etc/UTC",
      "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBNVkkT4=--d1d91cb4e7b2a143d18329cd4e8ec4d65fbda939/avatar?v=1",
      "can_manage_projects": true,
      "can_manage_people": true
    },
    "description": "",
    "completed": false,
    "completed_ratio": "0/2",
    "name": "Group B",
    "todos_url": "https://3.basecampapi.com/195539477/buckets/2085958497/todolists/1069479103/todos.json",
    "group_position_url": "https://3.basecampapi.com/195539477/buckets/2085958497/todolists/groups/1069479103/position.json",
    "app_todos_url": "https://3.basecamp.com/195539477/buckets/2085958497/todolists/1069479103/todos"
  }
]
```
<!-- END GET /buckets/1/todolists/2/groups.json -->
###### Copy as cURL

``` shell
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
  "id": 1069479100,
  "status": "active",
  "visible_to_clients": false,
  "created_at": "2022-10-21T10:24:24.930Z",
  "updated_at": "2022-11-22T08:23:38.003Z",
  "title": "Group A",
  "inherits_status": true,
  "type": "Todolist",
  "url": "https://3.basecampapi.com/195539477/buckets/2085958497/todolists/1069479100.json",
  "app_url": "https://3.basecamp.com/195539477/buckets/2085958497/todolists/1069479100",
  "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7CEkiCGdpZAY6BkVUSSIuZ2lkOi8vYmMzL1JlY29yZGluZy8xMDY5NDc5MTAwP2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg1yZWFkYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--7925d04412570c8f9576fa5ead98f77b9d48640c.json",
  "subscription_url": "https://3.basecampapi.com/195539477/buckets/2085958497/recordings/1069479100/subscription.json",
  "comments_count": 0,
  "comments_url": "https://3.basecampapi.com/195539477/buckets/2085958497/recordings/1069479100/comments.json",
  "position": 1,
  "parent": {
    "id": 1069479099,
    "title": "Ping pong tournament",
    "type": "Todolist",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958497/todolists/1069479099.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958497/todolists/1069479099"
  },
  "bucket": {
    "id": 2085958497,
    "name": "Honcho Design Newsroom",
    "type": "Project"
  },
  "creator": {
    "id": 1049715925,
    "attachable_sgid": "BAh7CEkiCGdpZAY6BkVUSSIrZ2lkOi8vYmMzL1BlcnNvbi8xMDQ5NzE1OTI1P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg9hdHRhY2hhYmxlBjsAVEkiD2V4cGlyZXNfYXQGOwBUMA==--6a81661a78620c3dfbd47bd56f73be4a144efb77",
    "name": "Brian Jenks",
    "email_address": "brian@honchodesign.com",
    "personable_type": "User",
    "title": "International Branding Liason",
    "bio": null,
    "location": null,
    "created_at": "2022-11-22T08:23:22.042Z",
    "updated_at": "2022-11-22T08:23:22.042Z",
    "admin": false,
    "owner": false,
    "client": false,
    "employee": false,
    "time_zone": "Etc/UTC",
    "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBNVkkT4=--d1d91cb4e7b2a143d18329cd4e8ec4d65fbda939/avatar?v=1",
    "can_manage_projects": true,
    "can_manage_people": true
  },
  "description": "",
  "completed": false,
  "completed_ratio": "0/2",
  "name": "Group A",
  "todos_url": "https://3.basecampapi.com/195539477/buckets/2085958497/todolists/1069479100/todos.json",
  "group_position_url": "https://3.basecampapi.com/195539477/buckets/2085958497/todolists/groups/1069479100/position.json",
  "app_todos_url": "https://3.basecamp.com/195539477/buckets/2085958497/todolists/1069479100/todos"
}
```
<!-- END GET /buckets/1/todolists/3.json -->

Create a to-do list group
-------------------------

* `POST /buckets/1/todolists/2/groups.json` creates a to-do group within the todolist with ID `2` in the project with id `1`.

**Required parameters**: `name` of the to-do list group.

This endpoint will return `201 Created` with the current JSON representation of the to-do list if the creation was a success. See the [Get a to-do list](#get-a-to-do-list) endpoint for more info on the payload.

###### Example JSON Request

``` json
{
  "name": "The Spencer Davis Group",
}
```

###### Copy as cURL

``` shell
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

``` json
{
  "position": 3
}
```

###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -H "Content-Type: application/json" \
  -d '{"position":3}' -X PUT \
  https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/todolists/groups/3/position.json
```

[pagination]: https://github.com/basecamp/bc3-api/blob/master/README.md#pagination
