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
    "id": 1069479520,
    "status": "active",
    "visible_to_clients": false,
    "created_at": "2022-11-19T10:49:58.169Z",
    "updated_at": "2022-11-22T13:36:50.727Z",
    "title": "Strategy ideas",
    "inherits_status": true,
    "type": "Todolist",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958499/todolists/1069479520.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958499/todolists/1069479520",
    "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7CEkiCGdpZAY6BkVUSSIuZ2lkOi8vYmMzL1JlY29yZGluZy8xMDY5NDc5NTIwP2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg1yZWFkYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--24332fbdc81b06784de7e8f2b6c1e29021bbae58.json",
    "subscription_url": "https://3.basecampapi.com/195539477/buckets/2085958499/recordings/1069479520/subscription.json",
    "comments_count": 0,
    "comments_url": "https://3.basecampapi.com/195539477/buckets/2085958499/recordings/1069479520/comments.json",
    "position": 1,
    "parent": {
      "id": 1069479339,
      "title": "To-dos",
      "type": "Todoset",
      "url": "https://3.basecampapi.com/195539477/buckets/2085958499/todosets/1069479339.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958499/todosets/1069479339"
    },
    "bucket": {
      "id": 2085958499,
      "name": "The Leto Laptop",
      "type": "Project"
    },
    "creator": {
      "id": 1049715915,
      "attachable_sgid": "BAh7CEkiCGdpZAY6BkVUSSIrZ2lkOi8vYmMzL1BlcnNvbi8xMDQ5NzE1OTE1P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg9hdHRhY2hhYmxlBjsAVEkiD2V4cGlyZXNfYXQGOwBUMA==--aeb392ebf54ffd820e45f27add22bae3a8c7da56",
      "name": "Annie Bryan",
      "email_address": "annie@honchodesign.com",
      "personable_type": "User",
      "title": "Central Markets Manager",
      "bio": "To open a store is easy, to keep it open is an art",
      "location": null,
      "created_at": "2022-11-22T08:23:21.911Z",
      "updated_at": "2022-11-22T08:23:21.911Z",
      "admin": false,
      "owner": false,
      "client": false,
      "employee": true,
      "time_zone": "America/Chicago",
      "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBMtkkT4=--9927c47a4cbee30a7f9aea667882496aba799149/avatar?v=1",
      "company": {
        "id": 1033447817,
        "name": "Honcho Design"
      },
      "can_manage_projects": true,
      "can_manage_people": true
    },
    "description": "",
    "completed": false,
    "completed_ratio": "2/5",
    "name": "Strategy ideas",
    "todos_url": "https://3.basecampapi.com/195539477/buckets/2085958499/todolists/1069479520/todos.json",
    "groups_url": "https://3.basecampapi.com/195539477/buckets/2085958499/todolists/1069479520/groups.json",
    "app_todos_url": "https://3.basecamp.com/195539477/buckets/2085958499/todolists/1069479520/todos"
  }
]
```
<!-- END GET /buckets/1/todosets/3/todolists.json -->
###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/todosets/3/todolists.json
```


Get a to-do list
----------------

* `GET /buckets/1/todolists/2.json` will return the to-do list with an ID of `2` in the project with an ID of `1`.

###### Example JSON Response
<!-- START GET /buckets/1/todolists/2.json -->
```json
{
  "id": 1069479369,
  "status": "active",
  "visible_to_clients": false,
  "created_at": "2022-10-31T08:24:58.169Z",
  "updated_at": "2022-11-22T08:24:00.825Z",
  "title": "Background and research",
  "inherits_status": true,
  "type": "Todolist",
  "url": "https://3.basecampapi.com/195539477/buckets/2085958499/todolists/1069479369.json",
  "app_url": "https://3.basecamp.com/195539477/buckets/2085958499/todolists/1069479369",
  "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7CEkiCGdpZAY6BkVUSSIuZ2lkOi8vYmMzL1JlY29yZGluZy8xMDY5NDc5MzY5P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg1yZWFkYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--4b6309a7d4c2ec4c0ca573bd0caeedbcb3e49a2f.json",
  "subscription_url": "https://3.basecampapi.com/195539477/buckets/2085958499/recordings/1069479369/subscription.json",
  "comments_count": 0,
  "comments_url": "https://3.basecampapi.com/195539477/buckets/2085958499/recordings/1069479369/comments.json",
  "position": 10,
  "parent": {
    "id": 1069479339,
    "title": "To-dos",
    "type": "Todoset",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958499/todosets/1069479339.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958499/todosets/1069479339"
  },
  "bucket": {
    "id": 2085958499,
    "name": "The Leto Laptop",
    "type": "Project"
  },
  "creator": {
    "id": 1049715923,
    "attachable_sgid": "BAh7CEkiCGdpZAY6BkVUSSIrZ2lkOi8vYmMzL1BlcnNvbi8xMDQ5NzE1OTIzP2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg9hdHRhY2hhYmxlBjsAVEkiD2V4cGlyZXNfYXQGOwBUMA==--cc7313cd0fef7654f37f813c000bf892d80e2e2f",
    "name": "Andrew Wong",
    "email_address": "andrew@honchodesign.com",
    "personable_type": "User",
    "title": "Senior Branding Strategist",
    "bio": null,
    "location": null,
    "created_at": "2022-11-22T08:23:22.017Z",
    "updated_at": "2022-11-22T08:23:22.017Z",
    "admin": false,
    "owner": false,
    "client": false,
    "employee": false,
    "time_zone": "Etc/UTC",
    "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBNNkkT4=--e3c2676dde30e7c13f87642e3a3dd46ad657f731/avatar?v=1",
    "can_manage_projects": true,
    "can_manage_people": true
  },
  "description": "",
  "completed": false,
  "completed_ratio": "0/4",
  "name": "Background and research",
  "todos_url": "https://3.basecampapi.com/195539477/buckets/2085958499/todolists/1069479369/todos.json",
  "groups_url": "https://3.basecampapi.com/195539477/buckets/2085958499/todolists/1069479369/groups.json",
  "app_todos_url": "https://3.basecamp.com/195539477/buckets/2085958499/todolists/1069479369/todos"
}
```
<!-- END GET /buckets/1/todolists/2.json -->
###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/todolists/2.json
```


Create a to-do list
-------------------

* `POST /buckets/1/todosets/3/todolists.json` creates a to-do list in the project with ID `1` and under the to-do set with an ID of `3`.

**Required parameters**: `name` of the to-do list.

_Optional parameters_: `description` containing information about the to-do list. See our [Rich text guide][rich] for what HTML tags are allowed.

This endpoint will return `201 Created` with the current JSON representation of the to-do list if the creation was a success. See the [Get a to-do list](#get-a-to-do-list) endpoint for more info on the payload.

###### Example JSON Request

``` json
{
  "name": "Launch",
  "description": "<div><em>Finish it!</em></div>"
}
```

###### Copy as cURL

``` shell
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

``` json
{
  "name": "Relaunch",
  "description": "<div><strong>Try this again.</strong></div>"
}
```

###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -H "Content-Type: application/json" \
  -d '{"name":"Relaunch","description":"<div><strong>Try this again.</strong></div>"}' -X PUT \
  https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/todolists/2.json
```


[trash]: https://github.com/basecamp/bc3-api/blob/master/sections/recordings.md#trash-a-recording
[pagination]: https://github.com/basecamp/bc3-api/blob/master/README.md#pagination
[todoset]: https://github.com/basecamp/bc3-api/blob/master/sections/todosets.md#get-to-do-set
[todos]: https://github.com/basecamp/bc3-api/blob/master/sections/todos.md#to-dos
[rich]: https://github.com/basecamp/bc3-api/blob/master/sections/rich_text.md
