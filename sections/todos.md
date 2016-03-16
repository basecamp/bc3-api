To-dos
======

Endpoints:

- [Get to-dos](#get-to-do)
- [Get a to-do](#get-a-to-do)
- [Create a to-do](#create-a-to-do)
- [Update a to-do](#update-a-to-do)
- [Trash a to-do][1]

Get to-dos
----------

* `GET /buckets/1/todolists/3/todos.json` will return a [paginated list][2] of active to-dos in the Basecamp with an ID of `1` and the to-do list with ID of `3`.

###### Example JSON Response

``` json
[
  {
    "assignees": [
      {
        "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBEoqCjw=--19d80553ef84a88c19b6846fdd222c5c394b6dc4/avatar-64-x4",
        "email_address": "cheryl@honchodesign.com",
        "id": 1007299146,
        "name": "Cheryl Walters"
      }
    ],
    "bucket": {
      "account_id": 31989850,
      "client_company_id": null,
      "created_at": "2015-12-27T11:01:58.062-06:00",
      "creator_id": 1007299144,
      "description": "Looking for the best!",
      "id": 1042979251,
      "name": "Honcho Recruiting and Hiring",
      "updated_at": "2015-12-27T11:01:58.062-06:00"
    },
    "bucket_path": "/195539477/buckets/2085958497",
    "comments_count": 0,
    "completed": false,
    "completion_bucket_todo_path": "/195539477/buckets/2085958497/todos/9007199254741425/completion",
    "content": "Bruce Barnes",
    "created_at": "2016-02-15T15:43:58.062-06:00",
    "creator": {
      "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBEoqCjw=--19d80553ef84a88c19b6846fdd222c5c394b6dc4/avatar-64-x4",
      "email_address": "cheryl@honchodesign.com",
      "id": 1007299146,
      "name": "Cheryl Walters"
    },
    "description_text": null,
    "description_html": null,
    "due_on": null,
    "id": 9007199254741424,
    "parent": {
      "id": 9007199254741420,
      "title": "Accepted! 😀",
      "url": "https://3.basecamp.com/195539477/buckets/2085958497/todolists/9007199254741420"
    },
    "starts_on": null,
    "status": "active",
    "type": "Todo",
    "updated_at": "2016-02-11T09:49:38.059-06:00",
    "url": "https://3.basecamp.com/195539477/buckets/2085958497/todos/9007199254741425"
  },
  ...
]
```

###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecamp.com/$ACCOUNT_ID/buckets/1/todolists/3/todos.json
```


Get a to-do
-----------

* `GET /buckets/1/todos/2.json` will return the to-do with an ID of `2` in the Basecamp with an ID of `1`.

Nesting under the to-do lists resource is not necessary for this endpoint.

###### Example JSON Response

``` json
{
  "assignees": [
    {
      "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBF8qCjw=--213cf293338eeeb3865113763a0a63542a0ca73c/avatar-64-x4",
      "email_address": "sharon@honchodesign.com",
      "id": 1007299167,
      "name": "Sharon Bradford"
    }
  ],
  "bookmark_url": "https://3.basecamp.com/195539477/my/bookmarks/BAh7CEkiCGdpZAY6BkVUSSI0Z2lkOi8vYmMzL1JlY29yZGluZy85MDA3MTk5MjU0NzQxNjE1P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg1yZWFkYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--1aa203449a2e5e82749f5502fd53231a647989b8",
  "bucket": {
    "account_id": 31989850,
    "client_company_id": null,
    "created_at": "2016-01-02T11:02:32.048-06:00",
    "creator_id": 1007299144,
    "description": "Laptop product launch.",
    "id": 1042979252,
    "name": "The Leto Laptop",
    "updated_at": "2016-01-02T11:02:32.048-06:00"
  },
  "bucket_path": "/195539477/buckets/2085958498",
  "comments_count": 0,
  "completed": false,
  "completion_bucket_todo_path": "/195539477/buckets/2085958498/todos/9007199254741615/completion",
  "content": "Clear and simple UI",
  "created_at": "2016-02-15T15:02:32.048-06:00",
  "creator": {
    "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBEkqCjw=--7e8e5d9e90e4898faee5f69e72def9e58da85fbe/avatar-64-x4",
    "email_address": "annie@honchodesign.com",
    "id": 1007299145,
    "name": "Annie Bryan"
  },
  "description_text": "Important: We'll need to loop marketing in on this.",
  "description_html": "<div><em>Important:&nbsp;</em>We'll need to loop marketing in on this.</div>",
  "due_on": null,
  "id": 9007199254741616,
  "parent": {
    "id": 9007199254741612,
    "title": "Strategy ideas",
    "url": "https://3.basecamp.com/195539477/buckets/2085958498/todolists/9007199254741612"
  },
  "starts_on": null,
  "status": "active",
  "subscription_url": "https://3.basecamp.com/195539477/buckets/2085958498/recordings/9007199254741615/subscription",
  "type": "Todo",
  "updated_at": "2016-02-15T15:02:32.048-06:00",
  "url": "https://3.basecamp.com/195539477/buckets/2085958498/todos/9007199254741615"
}
```

###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecamp.com/$ACCOUNT_ID/buckets/1/todos/2.json
```


Create a to-do
--------------

* `POST /buckets/1/todolists/3/todos.json` creates a to-do in the Basecamp with ID `1` and under the to-do list with an ID of `3`.

**Required parameters**: `content` for what the to-do is for.

_Optional parameters_:

* `description_html` - containing information about the to-do. See our [Rich content][3] guide for what HTML tags allowed.
* `assignees` - an array of people that will be assigned to this to-do. Please see the [Get people][] endpoints to retrieve them.
* `notify` - when set to `true`, will notify the assignees about being assigned
* `due_on` - a date when the to-do should be completed
* `starts_on` - allows the to-do to run from this date to the `due_on` date

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
  https://3.basecamp.com/$ACCOUNT_ID/buckets/1/todolists/3/todos.json
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
  https://3.basecamp.com/$ACCOUNT_ID/buckets/1/todos/2.json
```


[1]: https://github.com/basecamp/bc3-api/blob/master/sections/recordings.md#trash-a-recording
[2]: https://github.com/basecamp/bc3-api/blob/master/README.md#pagination
[3]: https://github.com/basecamp/bc3-api/blob/master/README.md#rich-content
