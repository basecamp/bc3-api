To-do lists
===========

Endpoints:

- [Get to-do lists](#get-to-do-lists)
- [Get a to-do list](#get-a-to-do-list)
- [Create a to-do list](#create-a-to-do-list)
- [Update a to-do list](#update-a-to-do-list)
- [Trash a to-do list][1]

Get to-do lists
---------------

* `GET /buckets/1/todosets/3/todolists.json` will return a [paginated list][2] of active to-do lists in the Basecamp with an ID of `1` and the to-do set with ID of `3`.

To get the to-do set ID for a Basecamp, see the [Get to-do set][3] endpoint.

###### Example JSON Response

``` json
[
  {
    "id": 9007199254741064,
    "created_at": "2015-10-30T14:16:28.313-05:00",
    "updated_at": "2016-01-27T11:00:39.837-06:00",
    "status": "active",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958496/todolists/9007199254741064",
    "name": "Health benefits renewal",
    "description_html": null,
    "description_text": null,
    "comments_count": 0,
    "todos_url": "https://3.basecampapi.com/195539477/buckets/2085958496/todos.json",
    "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7CEkiCGdpZAY6BkVUSSI0Z2lkOi8vYmMzL1JlY29yZGluZy85MDA3MTk5MjU0NzQxMDY0P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg1yZWFkYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--be7fc7d856bd884e8ec8001bd362c45cb4c1e9f6",
    "subscription_url": "https://3.basecampapi.com/195539477/buckets/2085958496/recordings/9007199254741064/subscription",
    "type": "Todolist",
    "creator": {
      "id": 1007299146,
      "name": "Cheryl Walters",
      "email_address": "cheryl@honchodesign.com",
      "avatar_url": "https://3.basecamp-assets.com/195539477/people/BAhpBEoqCjw=--19d80553ef84a88c19b6846fdd222c5c394b6dc4/avatar-64-x4"
    },
    "bucket": {
      "id": 1042979250,
      "account_id": 31989850,
      "name": "Honcho Design Newsroom",
      "description": "Let's talk about the company!",
      "created_at": "2015-10-27T12:00:28.313-05:00",
      "updated_at": "2015-10-27T12:00:28.313-05:00",
      "creator_id": 1007299144,
      "client_company_id": null
    },
    "bucket_path": "/195539477/buckets/2085958496",
    "parent": {
      "id": 9007199254741044,
      "title": "To-dos",
      "url": "https://3.basecampapi.com/195539477/buckets/2085958496/todosets/9007199254741045"
    }
  },
  ...
]
```

###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/todosets/3/todolists.json
```


Get a to-do list
----------------

* `GET /buckets/1/todolists/2.json` will return the to-do list with an ID of `2` in the Basecamp with an ID of `1`.

Each to-do list payload includes the first 10 to-dos in the `todos` key. To retrieve more, see the [Get to-dos][4] endpoint. Nesting under the to-do set resource is not necessary for this endpoint.

###### Example JSON Response

``` json
{
  "id": 9007199254741234,
  "created_at": "2015-12-31T13:41:28.313-06:00",
  "updated_at": "2016-03-16T12:14:01.281-05:00",
  "status": "active",
  "url": "https://3.basecampapi.com/195539477/buckets/2085958496/todolists/9007199254741234",
  "name": "Meetup setup",
  "description_html": "<div>Let's&nbsp;<strong>finish</strong>&nbsp;this stuff!</div>",
  "description_text": "Let's finish this stuff!",
  "comments_count": 0,
  "todos_url": "https://3.basecampapi.com/195539477/buckets/2085958496/todos.json",
  "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7CEkiCGdpZAY6BkVUSSI0Z2lkOi8vYmMzL1JlY29yZGluZy85MDA3MTk5MjU0NzQxMjM0P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg1yZWFkYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--ceb1312e43bf42063c09d2679ac787d132dc6bff",
  "subscription_url": "https://3.basecampapi.com/195539477/buckets/2085958496/recordings/9007199254741234/subscription",
  "type": "Todolist",
  "creator": {
    "id": 1007299148,
    "name": "Jennifer Young",
    "email_address": "jennifer@honchodesign.com",
    "avatar_url": "https://3.basecamp-assets.com/195539477/people/BAhpBEwqCjw=--6d75c96cdfed6528797fe38d7b07ed9b8cc630c8/avatar-64-x4"
  },
  "bucket": {
    "id": 1042979250,
    "account_id": 31989850,
    "name": "Honcho Design Newsroom",
    "description": "Let's talk about the company!",
    "created_at": "2015-10-27T12:00:28.313-05:00",
    "updated_at": "2015-10-27T12:00:28.313-05:00",
    "creator_id": 1007299144,
    "client_company_id": null
  },
  "bucket_path": "/195539477/buckets/2085958496",
  "parent": {
    "id": 9007199254741044,
    "title": "To-dos",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958496/todosets/9007199254741045"
  }
}
```

###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/todolists/2.json
```


Create a to-do list
-------------------

* `POST /buckets/1/todosets/3/todolists.json` creates a to-do list in the Basecamp with ID `1` and under the to-do set with an ID of `3`.

**Required parameters**: `name` of the to-do list.

_Optional parameters_: `description_html` containing information about the to-do list. See our [Rich content][4] guide for what HTML tags are allowed.

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


[1]: https://github.com/basecamp/bc3-api/blob/master/sections/recordings.md#trash-a-recording
[2]: https://github.com/basecamp/bc3-api/blob/master/README.md#pagination
[3]: https://github.com/basecamp/bc3-api/blob/master/sections/todosets.md#get-to-do-set
[4]: https://github.com/basecamp/bc3-api/blob/master/sections/todos.md#to-dos
[5]: https://github.com/basecamp/bc3-api/blob/master/README.md#rich-content
