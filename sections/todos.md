To-dos
======

Endpoints:

- [Get to-dos](#get-to-dos)
- [Get a to-do](#get-a-to-do)
- [Create a to-do](#create-a-to-do)
- [Update a to-do](#update-a-to-do)
- [Complete a to-do](#complete-a-to-do)
- [Uncomplete a to-do](#uncomplete-a-to-do)
- [Reposition a to-do](#move-a-to-do)
- [Trash a to-do][1]

Get to-dos
----------

* `GET /buckets/1/todolists/3/todos.json` will return a [paginated list][2] of active to-dos in the Basecamp with an ID of `1` and the to-do list with ID of `3`.

_Optional query parameters_:

* `status` - when set to `archived` or `trashed`, will return archived or trashed to-dos that are in this list
* `completed` - when set to `true`, will only return to-dos that were completed. Can be combined with the `status` parameter too.

###### Example JSON Response
<!-- START GET /buckets/1/todolists/3/todos.json -->
```json
[
  {
    "id": 9007199254741613,
    "status": "active",
    "created_at": "2016-07-27T04:01:06.221Z",
    "updated_at": "2016-07-27T04:01:06.221Z",
    "type": "Todo",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958498/todos/9007199254741613.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958498/todos/9007199254741613",
    "comments_count": 0,
    "comments_url": "https://3.basecampapi.com/195539477/buckets/2085958498/recordings/9007199254741613/comments.json",
    "bucket": {
      "id": 2085958498,
      "type": "Project"
    },
    "parent": {
      "id": 9007199254741612,
      "type": "Todolist",
      "url": "https://3.basecampapi.com/195539477/buckets/2085958498/todolists/9007199254741612.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958498/todolists/9007199254741612"
    },
    "creator": {
      "id": 1007299144,
      "name": "Annie Bryan",
      "email_address": "annie@honchodesign.com",
      "personable_type": "User",
      "title": "Central Markets Manager",
      "created_at": "2016-07-08T02:16:07.615Z",
      "updated_at": "2016-07-08T02:16:07.615Z",
      "admin": false,
      "owner": false,
      "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBEgqCjw=--8266bb0507508f3d46050d57b65924d5e2a005f3/avatar-64-x4",
      "company": {
        "id": 1033447817,
        "name": "Honcho Design"
      }
    },
    "description_html": null,
    "description_text": null,
    "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7CEkiCGdpZAY6BkVUSSI0Z2lkOi8vYmMzL1JlY29yZGluZy85MDA3MTk5MjU0NzQxNjEzP2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg1yZWFkYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--0235c827eabaffecd5c75a7846e988fdec5a95a4.json",
    "subscription_url": "https://3.basecampapi.com/195539477/buckets/2085958498/recordings/9007199254741613/subscription.json",
    "content": "Go cutting edge: iOS8 and Android 4.5 only",
    "starts_on": null,
    "due_on": null,
    "completed": false,
    "completion_url": "https://3.basecampapi.com/195539477/buckets/2085958498/todos/9007199254741613/completion.json",
    "assignees": [

    ]
  }
]
```
<!-- END GET /buckets/1/todolists/3/todos.json -->
###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/todolists/3/todos.json
```


Get a to-do
-----------

* `GET /buckets/1/todos/2.json` will return the to-do with an ID of `2` in the Basecamp with an ID of `1`.

Nesting under the to-do lists resource is not necessary for this endpoint.

###### Example JSON Response
<!-- START GET /buckets/1/todos/2.json -->
```json
{
  "id": 9007199254741617,
  "status": "active",
  "created_at": "2016-07-27T05:14:06.221Z",
  "updated_at": "2016-07-27T05:14:06.221Z",
  "type": "Todo",
  "url": "https://3.basecampapi.com/195539477/buckets/2085958498/todos/9007199254741617.json",
  "app_url": "https://3.basecamp.com/195539477/buckets/2085958498/todos/9007199254741617",
  "comments_count": 0,
  "comments_url": "https://3.basecampapi.com/195539477/buckets/2085958498/recordings/9007199254741617/comments.json",
  "bucket": {
    "id": 2085958498,
    "type": "Project"
  },
  "parent": {
    "id": 9007199254741612,
    "type": "Todolist",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958498/todolists/9007199254741612.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958498/todolists/9007199254741612"
  },
  "creator": {
    "id": 1007299144,
    "name": "Annie Bryan",
    "email_address": "annie@honchodesign.com",
    "personable_type": "User",
    "title": "Central Markets Manager",
    "created_at": "2016-07-08T02:16:07.615Z",
    "updated_at": "2016-07-08T02:16:07.615Z",
    "admin": false,
    "owner": false,
    "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBEgqCjw=--8266bb0507508f3d46050d57b65924d5e2a005f3/avatar-64-x4",
    "company": {
      "id": 1033447817,
      "name": "Honcho Design"
    }
  },
  "description_html": null,
  "description_text": null,
  "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7CEkiCGdpZAY6BkVUSSI0Z2lkOi8vYmMzL1JlY29yZGluZy85MDA3MTk5MjU0NzQxNjE3P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg1yZWFkYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--6893ffc69d6c1a00220b470cf1a7ae4e60b73ae0.json",
  "subscription_url": "https://3.basecampapi.com/195539477/buckets/2085958498/recordings/9007199254741617/subscription.json",
  "content": "Get frequent (daily?) client feedback",
  "starts_on": null,
  "due_on": null,
  "completed": false,
  "completion_url": "https://3.basecampapi.com/195539477/buckets/2085958498/todos/9007199254741617/completion.json",
  "assignees": [

  ]
}
```
<!-- END GET /buckets/1/todos/2.json -->
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
* `assignee_ids` - an array of people that will be assigned to this to-do. Please see the [Get people][4] endpoints to retrieve them.
* `notify` - when set to `true`, will notify the assignees about being assigned.
* `due_on` - a date when the to-do should be completed.
* `starts_on` - allows the to-do to run from this date to the `due_on` date.

This endpoint will return `201 Created` with the current JSON representation of the to-do if the creation was a success. See the [Get a to-do](#get-a-to-do) endpoint for more info on the payload.

###### Example JSON Request

``` json
{
  "content": "Program it",
  "description_html": "<div><em>Try that new language!</em></div>",
  "due_on": "2016-05-01"
}
```

###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -H "Content-Type: application/json" \
  -d '{"content":"Program it","description_html":"<div><em>Try that new language!</em></div>","due_on":"2016-05-01"}' \
  https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/todolists/3/todos.json
```


Update a to-do
--------------

* `PUT /buckets/1/todos/2.json` allows changing the to-do with an ID of `2` in the Basecamp with ID `1`.

This endpoint will return `200 OK` with the current JSON representation of the to-do if the update was a success. See the [Get a to-do](#get-a-to-do) endpoint for more info on the payload.

**Required parameters**: Pass all existing parameters in addition to those being updated. For example, to update the to-do's `content` from [Create a to-do](#create-a-todo):

###### Example JSON Request

``` json
{
  "content": "Only changing content! Passing the rest to preserve them.",
  "description_html": "<div><em>Try that new language!</em></div>",
  "due_on": "2016-05-01"
}
```

###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -H "Content-Type: application/json" \
  -d '{"content":"Only changing content! Passing the rest to preserve them.","description_html":"<div><em>Try that new language!</em></div>","due_on":"2016-05-01"}' -X PUT \
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


Reposition a to-do
------------------

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
[4]: https://github.com/basecamp/bc3-api/blob/master/sections/people.md#get-all-people
