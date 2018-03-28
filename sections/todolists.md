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
    "id": 1046492039,
    "status": "active",
    "created_at": "2017-12-01T11:00:53.586Z",
    "updated_at": "2017-11-09T09:48:17.217Z",
    "title": "Strategy ideas",
    "inherits_status": true,
    "type": "Todolist",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958499/todolists/1046492039.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958499/todolists/1046492039",
    "comments_count": 0,
    "comments_url": "https://3.basecampapi.com/195539477/buckets/2085958499/recordings/1046492039/comments.json",
    "position": 1,
    "parent": {
      "id": 1046491863,
      "title": "To-dos",
      "type": "Todoset",
      "url": "https://3.basecampapi.com/195539477/buckets/2085958499/todosets/1046491863.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958499/todosets/1046491863"
    },
    "bucket": {
      "id": 2085958499,
      "name": "The Leto Laptop",
      "type": "Project"
    },
    "creator": {
      "id": 1049715915,
      "attachable_sgid": "BAh7CEkiCGdpZAY6BkVUSSIrZ2lkOi8vYmMzL1BlcnNvbi8xMDQ5NzE1OTE1P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg9hdHRhY2hhYmxlBjsAVEkiD2V4cGlyZXNfYXQGOwBUMA==--5f103c46d4f123f0068fcd0192a0f7fea7f26193",
      "name": "Annie Bryan",
      "email_address": "annie@honchodesign.com",
      "personable_type": "User",
      "title": "Central Markets Manager",
      "bio": "To open a store is easy, to keep it open is an art",
      "created_at": "2017-11-09T09:46:39.287Z",
      "updated_at": "2017-11-09T09:46:39.287Z",
      "admin": false,
      "owner": false,
      "time_zone": "America/Chicago",
      "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBMtkkT4=--e609ef146e39f9ca5e4bb7242fdfd50aec4c3b3f/avatar-64-x4",
      "company": {
        "id": 1033447817,
        "name": "Honcho Design"
      }
    },
    "description": "",
    "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7CEkiCGdpZAY6BkVUSSIuZ2lkOi8vYmMzL1JlY29yZGluZy8xMDQ2NDkyMDM5P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg1yZWFkYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--86725cce5d06ac1ebeb3ff3833e950a91815ec9c.json",
    "subscription_url": "https://3.basecampapi.com/195539477/buckets/2085958499/recordings/1046492039/subscription.json",
    "completed": false,
    "completed_ratio": "2/5",
    "name": "Strategy ideas",
    "todos_url": "https://3.basecampapi.com/195539477/buckets/2085958499/todolists/1046492039/todos.json",
    "groups_url": "https://3.basecampapi.com/195539477/buckets/2085958499/todolists/1046492039/groups.json",
    "app_todos_url": "https://3.basecamp.com/195539477/buckets/2085958499/todolists/1046492039/todos"
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
  "id": 1046491888,
  "status": "active",
  "created_at": "2017-11-12T10:35:53.586Z",
  "updated_at": "2017-11-09T09:47:57.585Z",
  "title": "Background and research",
  "inherits_status": true,
  "type": "Todolist",
  "url": "https://3.basecampapi.com/195539477/buckets/2085958499/todolists/1046491888.json",
  "app_url": "https://3.basecamp.com/195539477/buckets/2085958499/todolists/1046491888",
  "comments_count": 0,
  "comments_url": "https://3.basecampapi.com/195539477/buckets/2085958499/recordings/1046491888/comments.json",
  "position": 10,
  "parent": {
    "id": 1046491863,
    "title": "To-dos",
    "type": "Todoset",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958499/todosets/1046491863.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958499/todosets/1046491863"
  },
  "bucket": {
    "id": 2085958499,
    "name": "The Leto Laptop",
    "type": "Project"
  },
  "creator": {
    "id": 1049715923,
    "attachable_sgid": "BAh7CEkiCGdpZAY6BkVUSSIrZ2lkOi8vYmMzL1BlcnNvbi8xMDQ5NzE1OTIzP2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg9hdHRhY2hhYmxlBjsAVEkiD2V4cGlyZXNfYXQGOwBUMA==--0097e07e5ccce36073f440e82fb4af95d149923a",
    "name": "Andrew Wong",
    "email_address": "andrew@honchodesign.com",
    "personable_type": "User",
    "title": "Senior Branding Strategist",
    "bio": null,
    "created_at": "2017-11-09T09:46:39.990Z",
    "updated_at": "2017-11-09T09:46:39.990Z",
    "admin": false,
    "owner": false,
    "time_zone": "America/Chicago",
    "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBNNkkT4=--2d4c6d1c153687c71c54960854a6d672311b536e/avatar-64-x4"
  },
  "description": "",
  "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7CEkiCGdpZAY6BkVUSSIuZ2lkOi8vYmMzL1JlY29yZGluZy8xMDQ2NDkxODg4P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg1yZWFkYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--73828ccc551554287ab8958db2050a59696ff06c.json",
  "subscription_url": "https://3.basecampapi.com/195539477/buckets/2085958499/recordings/1046491888/subscription.json",
  "completed": false,
  "completed_ratio": "0/4",
  "name": "Background and research",
  "todos_url": "https://3.basecampapi.com/195539477/buckets/2085958499/todolists/1046491888/todos.json",
  "groups_url": "https://3.basecampapi.com/195539477/buckets/2085958499/todolists/1046491888/groups.json",
  "app_todos_url": "https://3.basecamp.com/195539477/buckets/2085958499/todolists/1046491888/todos"
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
