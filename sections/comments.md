Comments
========

Many [recordings][recordings] can be commented on, including:

- [Messages][messages]
- [To-do lists][todolists]
- [To-dos][todos]

Endpoints:

- [Get comments](#get-comments)
- [Get a comment](#get-a-comment)
- [Create a comment](#create-a-comment)
- [Update a comment](#update-a-comment)
- [Trash a comment][trash]

Get comments
------------

* `GET /buckets/1/recordings/3/comments.json` will return a [paginated list][pagination] of active comments in the Basecamp with an ID of `1` and the recording with ID of `3`.

###### Example JSON Response

``` json
[
  {
    "bucket": {
      "account_id": 31989850,
      "client_company_id": null,
      "created_at": "2016-03-01T10:20:40.146-06:00",
      "creator_id": 1007299144,
      "description": "2016-2017 Strategy",
      "id": 1042979260,
      "name": "Marketing Campaign for Xyz Corp",
      "updated_at": "2016-03-01T10:21:42.345-06:00"
    },
    "bucket_path": "/195539477/buckets/2085958506",
    "comments_count": 0,
    "content_text": "We're finished!",
    "content_html": "<div>We're finished!</div>",
    "created_at": "2016-03-07T10:12:35.411-06:00",
    "creator": {
      "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBEgqCjw=--8266bb0507508f3d46050d57b65924d5e2a005f3/avatar-64-x4",
      "email_address": "victor@honchodesign.com",
      "id": 1007299144,
      "name": "Victor Cooper"
    },
    "id": 9007199254743026,
    "parent": {
      "id": 9007199254743024,
      "title": "Kickoff",
      "url": "https://3.basecamp.com/195539477/buckets/2085958506/messages/9007199254743024"
    },
    "status": "active",
    "type": "Comment",
    "updated_at": "2016-03-07T10:12:41.372-06:00",
    "url": "https://3.basecamp.com/195539477/buckets/2085958506/comments/9007199254743026"
  },
  ...
]

```

###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecamp.com/$ACCOUNT_ID/buckets/1/recordings/3/comments.json
```


Get a comment
-------------

* `GET /buckets/1/comments/2.json` will return the comment with an ID of `2` in the Basecamp with an ID of `1`.

###### Example JSON Response

``` json
{
  "bucket": {
    "account_id": 31989850,
    "client_company_id": null,
    "created_at": "2015-10-27T12:00:28.313-05:00",
    "creator_id": 1007299144,
    "description": "Let's talk about the company!",
    "id": 1042979250,
    "name": "Honcho Design Newsroom",
    "updated_at": "2015-10-27T12:00:28.313-05:00"
  },
  "bucket_path": "/195539477/buckets/2085958496",
  "comments_count": 0,
  "content_text": "Can't wait to meet everyone for the first time. Been working with you guys for a while, but haven't met in person for so many of you. Can't wait!",
  "content_html": "<div>Can't wait to meet everyone for the first time. Been working with you guys for a while, but haven't met in person for so many of you. Can't wait!</div>",
  "created_at": "2016-01-27T11:33:28.988-06:00",
  "creator": {
    "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBE4qCjw=--b544b6a710bd76020abc076fc041895954025116/avatar-64-x4",
    "email_address": "nicole@honchodesign.com",
    "id": 1007299150,
    "name": "Nicole Katz"
  },
  "id": 9007199254741264,
  "parent": {
    "id": 9007199254741256,
    "title": "Next Quarterly meeting",
    "url": "https://3.basecamp.com/195539477/buckets/2085958496/messages/9007199254741256"
  },
  "status": "active",
  "type": "Comment",
  "updated_at": "2016-01-27T11:33:28.988-06:00",
  "url": "https://3.basecamp.com/195539477/buckets/2085958496/comments/9007199254741264"
}
```

###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecamp.com/$ACCOUNT_ID/buckets/1/comment/2.json
```


Create a comment
----------------

* `POST /buckets/1/recordings/3/comments.json` publishes a comment in the Basecamp with ID `1` and under the recording with an ID of `3`.

**Required parameters**: `content_html` as the body of the message. See our [Rich content][rich] guide for what HTML tags are allowed.

Note: All people who are subscribed to the recording will be notified when the comment is posted. Changing who is subscribed is coming soon!

This endpoint will return `201 Created` with the current JSON representation of the message if the creation was a success. See the [Get a comment](#get-a-comment) endpoint for more info on the payload. The `Location` header will contain a URL to the HTML version of the new comment.

###### Example JSON Request

``` json
{
  "content_html": "<div><em>Wow!</em> That is cool.</div>",
}
```

###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -H "Content-Type: application/json" \
  -d '{"content_html":"<div><em>Wow!</em> That is cool.</div>"}' \
  https://3.basecamp.com/$ACCOUNT_ID/buckets/1/recordings/3/comments.json
```


Update a comment
----------------

* `PUT /buckets/1/comments/2.json` allows changing content of the message with an ID of `2` in the Basecamp with ID `1`.

This endpoint will return `200 OK` with the current JSON representation of the message if the update was a success. See the [Get a comment](#get-a-comment) endpoint for more info on the payload. The `Location` header will contain a URL to the HTML version of the updated comment.

###### Example JSON Request

``` json
{
  "content_html": "<div><em>No way!</em> That isn't cool at all.</div>"
}
```

###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -H "Content-Type: application/json" \
  -d '{"content_html":"<div><em>No way!</em> That isn't cool at all.</div>"}' -X PUT \
  https://3.basecamp.com/$ACCOUNT_ID/buckets/1/messages/2.json
```


[recordings]: https://github.com/basecamp/bc3-api/blob/master/sections/recordings.md#recordings
[messages]:   https://github.com/basecamp/bc3-api/blob/master/sections/messages.md#messages
[todolists]:  https://github.com/basecamp/bc3-api/blob/master/sections/todolists.md#todolists
[todos]:      https://github.com/basecamp/bc3-api/blob/master/sections/todos.md#todos
[trash]:      https://github.com/basecamp/bc3-api/blob/master/sections/recordings.md#trash-a-recording
[pagination]: https://github.com/basecamp/bc3-api/blob/master/README.md#pagination
[rich]:       https://github.com/basecamp/bc3-api/blob/master/README.md#rich-content
