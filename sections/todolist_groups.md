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
    "id": 1046491627,
    "status": "active",
    "created_at": "2018-01-08T09:55:44.413Z",
    "updated_at": "2017-11-09T09:47:27.006Z",
    "title": "Group A",
    "type": "Todolist",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958497/todolists/1046491627.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958497/todolists/1046491627",
    "comments_count": 0,
    "comments_url": "https://3.basecampapi.com/195539477/buckets/2085958497/recordings/1046491627/comments.json",
    "parent": {
      "id": 1046491626,
      "title": "Ping pong tournament",
      "type": "Todolist",
      "url": "https://3.basecampapi.com/195539477/buckets/2085958497/todolists/1046491626.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958497/todolists/1046491626"
    },
    "bucket": {
      "id": 2085958497,
      "name": "Honcho Design Newsroom",
      "type": "Project"
    },
    "creator": {
      "id": 1049715925,
      "attachable_sgid": "BAh7CEkiCGdpZAY6BkVUSSIrZ2lkOi8vYmMzL1BlcnNvbi8xMDQ5NzE1OTI1P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg9hdHRhY2hhYmxlBjsAVEkiD2V4cGlyZXNfYXQGOwBUMA==--989286d8ab050dfd694d5da58618282e737fb328",
      "name": "Brian Jenks",
      "email_address": "brian@honchodesign.com",
      "personable_type": "User",
      "title": "International Branding Liason",
      "bio": null,
      "created_at": "2017-11-09T09:46:40.155Z",
      "updated_at": "2017-11-09T09:46:40.155Z",
      "admin": false,
      "owner": false,
      "time_zone": "America/Chicago",
      "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBNVkkT4=--9ffc212c1029f86189a722cde9cb424cfe76f600/avatar-64-x4"
    },
    "description": "",
    "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7CEkiCGdpZAY6BkVUSSIuZ2lkOi8vYmMzL1JlY29yZGluZy8xMDQ2NDkxNjI3P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg1yZWFkYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--a535d70650057a8f98f9fd50e6a300691a34061f.json",
    "subscription_url": "https://3.basecampapi.com/195539477/buckets/2085958497/recordings/1046491627/subscription.json",
    "completed": false,
    "completed_ratio": "0/2",
    "name": "Group A",
    "todos_url": "https://3.basecampapi.com/195539477/buckets/2085958497/todolists/1046491627/todos.json",
    "group_position_url": "https://3.basecampapi.com/195539477/buckets/2085958497/todolists/groups/1046491627/position.json",
    "app_todos_url": "https://3.basecamp.com/195539477/buckets/2085958497/todolists/1046491627/todos"
  },
  {
    "id": 1046491630,
    "status": "active",
    "created_at": "2018-01-08T11:30:44.413Z",
    "updated_at": "2017-11-09T09:47:27.408Z",
    "title": "Group B",
    "type": "Todolist",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958497/todolists/1046491630.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958497/todolists/1046491630",
    "comments_count": 0,
    "comments_url": "https://3.basecampapi.com/195539477/buckets/2085958497/recordings/1046491630/comments.json",
    "parent": {
      "id": 1046491626,
      "title": "Ping pong tournament",
      "type": "Todolist",
      "url": "https://3.basecampapi.com/195539477/buckets/2085958497/todolists/1046491626.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958497/todolists/1046491626"
    },
    "bucket": {
      "id": 2085958497,
      "name": "Honcho Design Newsroom",
      "type": "Project"
    },
    "creator": {
      "id": 1049715925,
      "attachable_sgid": "BAh7CEkiCGdpZAY6BkVUSSIrZ2lkOi8vYmMzL1BlcnNvbi8xMDQ5NzE1OTI1P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg9hdHRhY2hhYmxlBjsAVEkiD2V4cGlyZXNfYXQGOwBUMA==--989286d8ab050dfd694d5da58618282e737fb328",
      "name": "Brian Jenks",
      "email_address": "brian@honchodesign.com",
      "personable_type": "User",
      "title": "International Branding Liason",
      "bio": null,
      "created_at": "2017-11-09T09:46:40.155Z",
      "updated_at": "2017-11-09T09:46:40.155Z",
      "admin": false,
      "owner": false,
      "time_zone": "America/Chicago",
      "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBNVkkT4=--9ffc212c1029f86189a722cde9cb424cfe76f600/avatar-64-x4"
    },
    "description": "",
    "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7CEkiCGdpZAY6BkVUSSIuZ2lkOi8vYmMzL1JlY29yZGluZy8xMDQ2NDkxNjMwP2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg1yZWFkYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--1998c70578debb55445290439d488cf4e5c2b40c.json",
    "subscription_url": "https://3.basecampapi.com/195539477/buckets/2085958497/recordings/1046491630/subscription.json",
    "completed": false,
    "completed_ratio": "0/2",
    "name": "Group B",
    "todos_url": "https://3.basecampapi.com/195539477/buckets/2085958497/todolists/1046491630/todos.json",
    "group_position_url": "https://3.basecampapi.com/195539477/buckets/2085958497/todolists/groups/1046491630/position.json",
    "app_todos_url": "https://3.basecamp.com/195539477/buckets/2085958497/todolists/1046491630/todos"
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
  "id": 1046491627,
  "status": "active",
  "created_at": "2018-01-08T09:55:44.413Z",
  "updated_at": "2017-11-09T09:47:27.006Z",
  "title": "Group A",
  "type": "Todolist",
  "url": "https://3.basecampapi.com/195539477/buckets/2085958497/todolists/1046491627.json",
  "app_url": "https://3.basecamp.com/195539477/buckets/2085958497/todolists/1046491627",
  "comments_count": 0,
  "comments_url": "https://3.basecampapi.com/195539477/buckets/2085958497/recordings/1046491627/comments.json",
  "parent": {
    "id": 1046491626,
    "title": "Ping pong tournament",
    "type": "Todolist",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958497/todolists/1046491626.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958497/todolists/1046491626"
  },
  "bucket": {
    "id": 2085958497,
    "name": "Honcho Design Newsroom",
    "type": "Project"
  },
  "creator": {
    "id": 1049715925,
    "attachable_sgid": "BAh7CEkiCGdpZAY6BkVUSSIrZ2lkOi8vYmMzL1BlcnNvbi8xMDQ5NzE1OTI1P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg9hdHRhY2hhYmxlBjsAVEkiD2V4cGlyZXNfYXQGOwBUMA==--989286d8ab050dfd694d5da58618282e737fb328",
    "name": "Brian Jenks",
    "email_address": "brian@honchodesign.com",
    "personable_type": "User",
    "title": "International Branding Liason",
    "bio": null,
    "created_at": "2017-11-09T09:46:40.155Z",
    "updated_at": "2017-11-09T09:46:40.155Z",
    "admin": false,
    "owner": false,
    "time_zone": "America/Chicago",
    "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBNVkkT4=--9ffc212c1029f86189a722cde9cb424cfe76f600/avatar-64-x4"
  },
  "description": "",
  "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7CEkiCGdpZAY6BkVUSSIuZ2lkOi8vYmMzL1JlY29yZGluZy8xMDQ2NDkxNjI3P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg1yZWFkYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--a535d70650057a8f98f9fd50e6a300691a34061f.json",
  "subscription_url": "https://3.basecampapi.com/195539477/buckets/2085958497/recordings/1046491627/subscription.json",
  "completed": false,
  "completed_ratio": "0/2",
  "name": "Group A",
  "todos_url": "https://3.basecampapi.com/195539477/buckets/2085958497/todolists/1046491627/todos.json",
  "group_position_url": "https://3.basecampapi.com/195539477/buckets/2085958497/todolists/groups/1046491627/position.json",
  "app_todos_url": "https://3.basecamp.com/195539477/buckets/2085958497/todolists/1046491627/todos"
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
