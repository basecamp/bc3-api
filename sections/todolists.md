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

* `GET /buckets/1/todosets/3/todolists.json` will return a [paginated list][pagination] of active to-do lists in the Basecamp with an ID of `1` and the to-do set with ID of `3`.

To get the to-do set ID for a Basecamp, see the [Get to-do set][todoset] endpoint.

_Optional query parameters_:

* `status` - when set to `archived` or `trashed`, will return archived or trashed to-do lists that are in this to-do set.

###### Example JSON Response
<!-- START GET /buckets/1/todosets/3/todolists.json -->
```json
[
  {
    "id": 9007199254741612,
    "status": "active",
    "created_at": "2016-06-19T16:51:25.413-05:00",
    "updated_at": "2016-06-22T16:40:03.901-05:00",
    "bucket_path": "/195539477/buckets/2085958498",
    "type": "Todolist",
    "comments_count": 0,
    "url": "https://3.basecampapi.com/195539477/buckets/2085958498/todolists/9007199254741612.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958498/todolists/9007199254741612",
    "creator": {
      "id": 1007299144,
      "name": "Annie Bryan",
      "email_address": "annie@honchodesign.com",
      "personable_type": "User",
      "title": "Central Markets Manager",
      "created_at": "2016-06-22T16:37:57.022-05:00",
      "updated_at": "2016-06-22T16:37:57.022-05:00",
      "admin": false,
      "owner": false,
      "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBEgqCjw=--8266bb0507508f3d46050d57b65924d5e2a005f3/avatar-64-x4",
      "company": {
        "id": 1033447817,
        "name": "Honcho Design"
      }
    },
    "bucket": {
      "id": 1042979252,
      "account_id": 1009501286,
      "name": "The Leto Laptop",
      "description": "Laptop product launch.",
      "created_at": "2016-05-28T16:39:25.413-05:00",
      "updated_at": "2016-05-28T16:39:25.413-05:00",
      "creator_id": 1007299143,
      "client_company_id": null
    },
    "parent": {
      "id": 9007199254741435,
      "title": "To-dos",
      "url": "https://3.basecampapi.com/195539477/buckets/2085958498/todosets/9007199254741435.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958498/todosets/9007199254741435"
    },
    "description_html": null,
    "description_text": null,
    "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7CEkiCGdpZAY6BkVUSSI0Z2lkOi8vYmMzL1JlY29yZGluZy85MDA3MTk5MjU0NzQxNjEyP2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg1yZWFkYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--86ec6f857b01309e234a304fe0bcdab3839c53f4.json",
    "subscription_url": "https://3.basecampapi.com/195539477/buckets/2085958498/recordings/9007199254741612/subscription.json",
    "name": "Strategy ideas",
    "todos_url": "https://3.basecampapi.com/195539477/buckets/2085958498/todolists/9007199254741612/todos.json",
    "app_todos_url": "https://3.basecamp.com/195539477/buckets/2085958498/todolists/9007199254741612/todos"
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

* `GET /buckets/1/todolists/2.json` will return the to-do list with an ID of `2` in the Basecamp with an ID of `1`.

Note: Nesting under the to-do set resource is not necessary for this endpoint.

###### Example JSON Response
<!-- START GET /buckets/1/todolists/2.json -->
```json
{
  "id": 9007199254741461,
  "status": "active",
  "created_at": "2016-05-31T18:30:25.413-05:00",
  "updated_at": "2016-06-22T16:39:33.206-05:00",
  "bucket_path": "/195539477/buckets/2085958498",
  "type": "Todolist",
  "comments_count": 0,
  "url": "https://3.basecampapi.com/195539477/buckets/2085958498/todolists/9007199254741461.json",
  "app_url": "https://3.basecamp.com/195539477/buckets/2085958498/todolists/9007199254741461",
  "creator": {
    "id": 1007299152,
    "name": "Andrew Wong",
    "email_address": "andrew@honchodesign.com",
    "personable_type": "User",
    "title": "Senior Branding Strategist",
    "created_at": "2016-06-22T16:37:58.562-05:00",
    "updated_at": "2016-06-22T16:37:58.562-05:00",
    "admin": false,
    "owner": false,
    "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBFAqCjw=--0413da7be3ef98ba6e3274f859fb29fc38698edf/avatar-64-x4"
  },
  "bucket": {
    "id": 1042979252,
    "account_id": 1009501286,
    "name": "The Leto Laptop",
    "description": "Laptop product launch.",
    "created_at": "2016-05-28T16:39:25.413-05:00",
    "updated_at": "2016-05-28T16:39:25.413-05:00",
    "creator_id": 1007299143,
    "client_company_id": null
  },
  "parent": {
    "id": 9007199254741435,
    "title": "To-dos",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958498/todosets/9007199254741435.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958498/todosets/9007199254741435"
  },
  "description_html": null,
  "description_text": null,
  "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7CEkiCGdpZAY6BkVUSSI0Z2lkOi8vYmMzL1JlY29yZGluZy85MDA3MTk5MjU0NzQxNDYxP2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg1yZWFkYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--36b09454741fb7bec702606062a54a837bfaa750.json",
  "subscription_url": "https://3.basecampapi.com/195539477/buckets/2085958498/recordings/9007199254741461/subscription.json",
  "name": "Background and research",
  "todos_url": "https://3.basecampapi.com/195539477/buckets/2085958498/todolists/9007199254741461/todos.json",
  "app_todos_url": "https://3.basecamp.com/195539477/buckets/2085958498/todolists/9007199254741461/todos"
}
```
<!-- END GET /buckets/1/todolists/2.json -->
###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/todolists/2.json
```


Create a to-do list
-------------------

* `POST /buckets/1/todosets/3/todolists.json` creates a to-do list in the Basecamp with ID `1` and under the to-do set with an ID of `3`.

**Required parameters**: `name` of the to-do list.

_Optional parameters_: `description_html` containing information about the to-do list. See our [Rich content][rich] guide for what HTML tags are allowed.

This endpoint will return `201 Created` with the current JSON representation of the to-do list if the creation was a success. See the [Get a to-do list](#get-a-to-do-list) endpoint for more info on the payload.

###### Example JSON Request

``` json
{
  "name": "Launch",
  "description_html": "<div><em>Finish it!</em></div>"
}
```

###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -H "Content-Type: application/json" \
  -d '{"name":"Launch","description_html":"<div><em>Finish it!</em></div>"}' \
  https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/todosets/3/todolists.json
```


Update a to-do list
-------------------

* `PUT /buckets/1/todolists/2.json` allows changing the name and description of the to-do list with an ID of `2` in the Basecamp with ID `1`.

Nesting under the to-do set resource is not necessary for this endpoint. Clients may deliver `name` or `description_html` parameters, or both if necessary.

This endpoint will return `200 OK` with the current JSON representation of the to-do list if the update was a success. See the [Get a to-do list](#get-a-to-do-list) endpoint for more info on the payload.

###### Example JSON Request

``` json
{
  "name": "Relaunch",
  "description_html": "<div><strong>Try this again.</strong></div>"
}
```

###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -H "Content-Type: application/json" \
  -d '{"name":"Relaunch","description_html":"<div><strong>Try this again.</strong></div>"}' -X PUT \
  https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/todolists/2.json
```


[trash]: https://github.com/basecamp/bc3-api/blob/master/sections/recordings.md#trash-a-recording
[pagination]: https://github.com/basecamp/bc3-api/blob/master/README.md#pagination
[todoset]: https://github.com/basecamp/bc3-api/blob/master/sections/todosets.md#get-to-do-set
[todos]: https://github.com/basecamp/bc3-api/blob/master/sections/todos.md#to-dos
[rich]: https://github.com/basecamp/bc3-api/blob/master/README.md#rich-content
