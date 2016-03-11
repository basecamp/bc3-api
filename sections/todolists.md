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
    "created_at": "2016-01-25T12:10:58.062-06:00",
    "creator": {
      "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBEoqCjw=--19d80553ef84a88c19b6846fdd222c5c394b6dc4/avatar-64-x4",
      "email_address": "cheryl@honchodesign.com",
      "id": 1007299146,
      "name": "Cheryl Walters"
    },
    "description": null,
    "id": 9007199254741428,
    "name": "Declined 😬",
    "parent": {
      "id": 9007199254741356,
      "title": "To-dos",
      "url": "https://3.basecamp.com/195539477/buckets/2085958497/todosets/9007199254741357"
    },
    "status": "active",
    "todos": [
      ...
    ],
    "todos_url": "https://3.basecamp.com/195539477/buckets/2085958497/todos.json",
    "type": "Todolist",
    "updated_at": "2016-03-10T14:30:02.761-06:00",
    "url": "https://3.basecamp.com/195539477/buckets/2085958497/todolists/9007199254741427"
  },
]
```

###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecamp.com/$ACCOUNT_ID/buckets/1/todosets/3/todolists.json
```


Get a to-do list
----------------

* `GET /buckets/1/todolists/2.json` will return the to-do list with an ID of `2` in the Basecamp with an ID of `1`.

Each to-do list payload includes the first 10 to-dos in the `todos` key. To retrieve more, see the [Get to-dos][4] endpoint. Nesting under the to-do set resource is not necessary for this endpoint.

###### Example JSON Response

``` json
{
  "bookmark_url": "https://3.basecamp.com/195539477/my/bookmarks/BAh7CEkiCGdpZAY6BkVUSSI0Z2lkOi8vYmMzL1JlY29yZGluZy85MDA3MTk5MjU0NzQxNDIwP2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg1yZWFkYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--29f41e960aaf8c1d46ac356fa4fed65c5d4786eb",
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
  "comments_count": 3,
  "created_at": "2016-01-21T13:40:58.062-06:00",
  "creator": {
    "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBEoqCjw=--19d80553ef84a88c19b6846fdd222c5c394b6dc4/avatar-64-x4",
    "email_address": "cheryl@honchodesign.com",
    "id": 1007299146,
    "name": "Cheryl Walters"
  },
  "description": null,
  "id": 9007199254741420,
  "name": "Accepted! 😀",
  "parent": {
    "id": 9007199254741356,
    "title": "To-dos",
    "url": "https://3.basecamp.com/195539477/buckets/2085958497/todosets/9007199254741357"
  },
  "status": "active",
  "subscription_url": "https://3.basecamp.com/195539477/buckets/2085958497/recordings/9007199254741420/subscription",
  "todos": [
    ...
  ],
  "todos_url": "https://3.basecamp.com/195539477/buckets/2085958497/todos.json",
  "type": "Todolist",
  "updated_at": "2016-02-11T09:49:53.804-06:00",
  "url": "https://3.basecamp.com/195539477/buckets/2085958497/todolists/9007199254741420"
}
```

###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecamp.com/$ACCOUNT_ID/buckets/1/todolists/2.json
```


Create a to-do list
-------------------

* `POST /buckets/1/todosets/3/todolists.json` creates a to-do list in the Basecamp with ID `1` and under the to-do set with an ID of `3`.

**Required parameters**: `name` of the to-do list.

_Optional parameters_: `description` containing information about the to-do list. See our [Rich content][4] guide for what HTML tags are allowed.

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
  https://3.basecamp.com/$ACCOUNT_ID/buckets/1/todosets/3/todolists.json
```


Update a to-do list
-------------------

* `PUT /buckets/1/todolists/2.json` allows changing the name and description of the to-do list with an ID of `2` in the Basecamp with ID `1`.

Nesting under the to-do set resource is not necessary for this endpoint. Clients may deliver `name` or `description` parameters, or both if necessary.

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
  https://3.basecamp.com/$ACCOUNT_ID/buckets/1/todolists/2.json
```


[1]: https://github.com/basecamp/bc3-api/blob/master/sections/recordings.md#trash-a-recording
[2]: https://github.com/basecamp/bc3-api/blob/master/README.md#pagination
[3]: https://github.com/basecamp/bc3-api/blob/master/sections/todosets.md#get-to-do-set
[4]: https://github.com/basecamp/bc3-api/blob/master/sections/todos.md#to-dos
[5]: https://github.com/basecamp/bc3-api/blob/master/README.md#rich-content
