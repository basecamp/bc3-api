To-dos
======

Endpoints:

- [Get to-dos](#get-to-do)
- [Get a to-do](#get-a-to-do)
- [Create a to-do](#create-a-to-do)
- [Update a to-do](#update-a-to-do)
- [Complete a to-do](#complete-a-to-do)
- [Uncomplete a to-do](#uncomplete-a-to-do)
- [Move a to-do](#move-a-to-do)
- [Trash a to-do][1]

Get to-dos
----------

* `GET /buckets/1/todolists/3/todos.json` will return a [paginated list][2] of active to-dos in the Basecamp with an ID of `1` and the to-do list with ID of `3`.

###### Example JSON Response

``` json
[
  {
    "id": 9007199254741208,
    "created_at": "2016-02-24T16:27:28.313-06:00",
    "updated_at": "2016-02-09T22:20:46.519-06:00",
    "status": "active",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958496/todos/9007199254741209",
    "content": "Nicole vs. Dan",
    "description_html": "<div>It is time!</div>",
    "description_text": "It is time!",
    "starts_on": null,
    "due_on": null,
    "completed": false,
    "comments_count": 0,
    "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7CEkiCGdpZAY6BkVUSSI0Z2lkOi8vYmMzL1JlY29yZGluZy85MDA3MTk5MjU0NzQxMjA5P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg1yZWFkYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--fe49818bda5455af0f5655bd729df58acfdf7f3b",
    "subscription_url": "https://3.basecampapi.com/195539477/buckets/2085958496/recordings/9007199254741209/subscription",
    "assignees": [
      {
        "id": 1007299150,
        "name": "Nicole Katz",
        "email_address": "nicole@honchodesign.com",
        "avatar_url": "https://3.basecamp-assets.com/195539477/people/BAhpBE4qCjw=--b544b6a710bd76020abc076fc041895954025116/avatar-64-x4"
      }
    ],
    "type": "Todo",
    "creator": {
      "id": 1007299155,
      "name": "Brian Jenks",
      "email_address": "brian@honchodesign.com",
      "avatar_url": "https://3.basecamp-assets.com/195539477/people/BAhpBFMqCjw=--edcad0d274229690f2ff2d8e53e033fb0d04491e/avatar-64-x4"
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
      "id": 9007199254741204,
      "title": "Ping pong tournament",
      "url": "https://3.basecampapi.com/195539477/buckets/2085958496/todolists/9007199254741203"
    }
  }
]
```

###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/todolists/3/todos.json
```


Get a to-do
-----------

* `GET /buckets/1/todos/2.json` will return the to-do with an ID of `2` in the Basecamp with an ID of `1`.

Nesting under the to-do lists resource is not necessary for this endpoint.

###### Example JSON Response

``` json
{
  "id": 9007199254741204,
  "created_at": "2016-02-24T14:25:28.313-06:00",
  "updated_at": "2016-02-09T15:09:16.785-06:00",
  "status": "active",
  "url": "https://3.basecampapi.com/195539477/buckets/2085958496/todos/9007199254741205",
  "content": "Lillie vs. Charles",
  "description_html": null,
  "description_text": null,
  "starts_on": null,
  "due_on": null,
  "completed": false,
  "comments_count": 0,
  "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7CEkiCGdpZAY6BkVUSSI0Z2lkOi8vYmMzL1JlY29yZGluZy85MDA3MTk5MjU0NzQxMjA1P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg1yZWFkYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--b7261cb370f0f26a8acff00a0fea2745f8491b8c",
  "subscription_url": "https://3.basecampapi.com/195539477/buckets/2085958496/recordings/9007199254741205/subscription",
  "assignees": [
    {
      "id": 1007299163,
      "name": "Lillie McKenzie",
      "email_address": "lillie@honchodesign.com",
      "avatar_url": "https://3.basecamp-assets.com/195539477/people/BAhpBFsqCjw=--5b11ef4df711ccffeae93405a32a97d7daac0cd4/avatar-64-x4"
    }
  ],
  "type": "Todo",
  "creator": {
    "id": 1007299155,
    "name": "Brian Jenks",
    "email_address": "brian@honchodesign.com",
    "avatar_url": "https://3.basecamp-assets.com/195539477/people/BAhpBFMqCjw=--edcad0d274229690f2ff2d8e53e033fb0d04491e/avatar-64-x4"
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
    "id": 9007199254741204,
    "title": "Ping pong tournament",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958496/todolists/9007199254741203"
  }
}
```

###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/todos/2.json
```


Create a to-do
--------------

* `POST /buckets/1/todolists/3/todos.json` creates a to-do in the Basecamp with ID `1` and under the to-do list with an ID of `3`.

**Required parameters**: `content` for what the to-do is for.

_Optional parameters_:

* `description_html` - containing information about the to-do. See our [Rich content][3] guide for what HTML tags allowed.
* `assignee_ids` - an array of people that will be assigned to this to-do. Please see the [Get people]() endpoints to retrieve them.
* `notify` - when set to `true`, will notify the assignees about being assigned.
* `due_on` - a date when the to-do should be completed.
* `starts_on` - allows the to-do to run from this date to the `due_on` date.

This endpoint will return `201 Created` with the current JSON representation of the to-do if the creation was a success. See the [Get a to-do](#get-a-to-do) endpoint for more info on the payload.

###### Example JSON Request

``` json
{
  "name": "Program it",
  "description_html": "<div><em>Try that new language!</em></div>",
  "due_on": "2016-05-01"
}
```

###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -H "Content-Type: application/json" \
  -d '{"name":"Program it","description_html":"<div><em>Try that new language!</em></div>","due_on":"2016-05-01"}' \
  https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/todolists/3/todos.json
```


Update a to-do
--------------

* `PUT /buckets/1/todos/2.json` allows changing the name and description of the to-do with an ID of `2` in the Basecamp with ID `1`.

Nesting under the to-do list resource is not necessary for this endpoint.

This endpoint will return `200 OK` with the current JSON representation of the to-do if the update was a success. See the [Get a to-do](#get-a-to-do) endpoint for more info on the payload.

###### Example JSON Request

``` json
{
  "name": "Whiteboard it",
  "description_html": "<div><strong>Maybe plan it out first.</strong></div>"
}
```

###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -H "Content-Type: application/json" \
  -d '{"name":"Whiteboard it","description_html":"<div><strong>Maybe plan it out first.</strong></div>"}' -X PUT \
  https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/todos/2.json
```


Complete a to-do
----------------

* `POST /buckets/1/todos/2/completion.json` will mark the to-do with an ID of `2` in the Basecamp with ID `1` as completed.

This endpoint will return `204 No Content` if successful. No parameters are required.

###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -H "Content-Type: application/json" -X POST \
  https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/todos/2/completion.json
```


Uncomplete a to-do
------------------

* `DELETE /buckets/1/todos/2/completion.json` will mark the to-do with an ID of `2` in the Basecamp with ID `1` as uncompleted.

This endpoint will return `204 No Content` if successful. No parameters are required.

###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -H "Content-Type: application/json" -X DELETE \
  https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/todos/2/completion.json
```


Move a to-do
------------

* `PUT /buckets/1/todos/2/position.json` allows changing the position of the to-do with an ID of `2` in the Basecamp with ID `1`.

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
  https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/todos/2/position.json
```


[1]: https://github.com/basecamp/bc3-api/blob/master/sections/recordings.md#trash-a-recording
[2]: https://github.com/basecamp/bc3-api/blob/master/README.md#pagination
[3]: https://github.com/basecamp/bc3-api/blob/master/README.md#rich-content
