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
    "id": 9007199254741623,
    "status": "active",
    "created_at": "2016-09-25T16:43:24.459Z",
    "updated_at": "2016-09-28T14:25:52.328Z",
    "type": "Todolist",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958498/todolists/9007199254741623.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958498/todolists/9007199254741623",
    "comments_count": 0,
    "comments_url": "https://3.basecampapi.com/195539477/buckets/2085958498/recordings/9007199254741623/comments.json",
    "parent": {
      "id": 9007199254741445,
      "title": "To-dos",
      "type": "Todoset",
      "url": "https://3.basecampapi.com/195539477/buckets/2085958498/todosets/9007199254741445.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958498/todosets/9007199254741445"
    },
    "bucket": {
      "id": 2085958498,
      "name": "The Leto Laptop",
      "type": "Project"
    },
    "creator": {
      "id": 1007299145,
      "attachable_sgid": "BAh7CEkiCGdpZAY6BkVUSSIrZ2lkOi8vYmMzL1BlcnNvbi8xMDA3Mjk5MTQ1P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg9hdHRhY2hhYmxlBjsAVEkiD2V4cGlyZXNfYXQGOwBUMA==--eabe63d5a75258e7be2ade823aa884b7fde00ab2",
      "name": "Annie Bryan",
      "email_address": "annie@honchodesign.com",
      "personable_type": "User",
      "title": "Central Markets Manager",
      "bio": "To open a store is easy, to keep it open is an art",
      "created_at": "2016-09-28T14:24:20.328Z",
      "updated_at": "2016-09-28T14:24:20.328Z",
      "admin": false,
      "owner": false,
      "time_zone": "America/Chicago",
      "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBEkqCjw=--7e8e5d9e90e4898faee5f69e72def9e58da85fbe/avatar-64-x4",
      "company": {
        "id": 1033447817,
        "name": "Honcho Design"
      }
    },
    "description": "",
    "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7CEkiCGdpZAY6BkVUSSI0Z2lkOi8vYmMzL1JlY29yZGluZy85MDA3MTk5MjU0NzQxNjIzP2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg1yZWFkYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--de56779a811888328888fdc44f88937d1bdf8603.json",
    "subscription_url": "https://3.basecampapi.com/195539477/buckets/2085958498/recordings/9007199254741623/subscription.json",
    "completed": false,
    "completed_ratio": "2/5",
    "name": "Strategy ideas",
    "todos_url": "https://3.basecampapi.com/195539477/buckets/2085958498/todolists/9007199254741623/todos.json",
    "app_todos_url": "https://3.basecamp.com/195539477/buckets/2085958498/todolists/9007199254741623/todos"
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
  "id": 9007199254741472,
  "status": "active",
  "created_at": "2016-09-06T16:32:24.459Z",
  "updated_at": "2016-09-28T14:25:29.867Z",
  "type": "Todolist",
  "url": "https://3.basecampapi.com/195539477/buckets/2085958498/todolists/9007199254741472.json",
  "app_url": "https://3.basecamp.com/195539477/buckets/2085958498/todolists/9007199254741472",
  "comments_count": 0,
  "comments_url": "https://3.basecampapi.com/195539477/buckets/2085958498/recordings/9007199254741472/comments.json",
  "parent": {
    "id": 9007199254741445,
    "title": "To-dos",
    "type": "Todoset",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958498/todosets/9007199254741445.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958498/todosets/9007199254741445"
  },
  "bucket": {
    "id": 2085958498,
    "name": "The Leto Laptop",
    "type": "Project"
  },
  "creator": {
    "id": 1007299153,
    "attachable_sgid": "BAh7CEkiCGdpZAY6BkVUSSIrZ2lkOi8vYmMzL1BlcnNvbi8xMDA3Mjk5MTUzP2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg9hdHRhY2hhYmxlBjsAVEkiD2V4cGlyZXNfYXQGOwBUMA==--45bdc7f0b8e14ef829adc08aadd1a2d32a964162",
    "name": "Andrew Wong",
    "email_address": "andrew@honchodesign.com",
    "personable_type": "User",
    "title": "Senior Branding Strategist",
    "bio": null,
    "created_at": "2016-09-28T14:24:21.078Z",
    "updated_at": "2016-09-28T14:24:21.078Z",
    "admin": false,
    "owner": false,
    "time_zone": "America/Chicago",
    "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBFEqCjw=--f4f91a8c888e425d0d557f8f27d70dfb6f68505e/avatar-64-x4"
  },
  "description": "",
  "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7CEkiCGdpZAY6BkVUSSI0Z2lkOi8vYmMzL1JlY29yZGluZy85MDA3MTk5MjU0NzQxNDcyP2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg1yZWFkYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--d84be0a9e68ce4fd5046e60c2a01f2e879ea2def.json",
  "subscription_url": "https://3.basecampapi.com/195539477/buckets/2085958498/recordings/9007199254741472/subscription.json",
  "completed": false,
  "completed_ratio": "0/4",
  "name": "Background and research",
  "todos_url": "https://3.basecampapi.com/195539477/buckets/2085958498/todolists/9007199254741472/todos.json",
  "app_todos_url": "https://3.basecamp.com/195539477/buckets/2085958498/todolists/9007199254741472/todos"
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
