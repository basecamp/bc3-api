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
    "id": 9007199254741064,
    "created_at": "2016-01-27T12:41:33.975-06:00",
    "updated_at": "2016-01-27T12:41:33.975-06:00",
    "status": "active",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958496/comments/9007199254741063",
    "content_html": "I just want to echo what just about everyone already said. This is a big one for us, and I can't wait to get going. I'll be spinning up the project shortly!",
    "content_text": "I just want to echo what just about everyone already said. This is a big one for us, and I can't wait to get going. I'll be spinning up the project shortly!",
    "type": "Comment",
    "creator": {
      "id": 1007299145,
      "name": "Annie Bryan",
      "email_address": "annie@honchodesign.com",
      "avatar_url": "https://3.basecamp-assets.com/195539477/people/BAhpBEkqCjw=--7e8e5d9e90e4898faee5f69e72def9e58da85fbe/avatar-64-x4"
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
      "id": 9007199254741052,
      "title": "We won Leto!",
      "url": "https://3.basecampapi.com/195539477/buckets/2085958496/messages/9007199254741053"
    }
  },
  ...
]
```

###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/recordings/3/comments.json
```


Get a comment
-------------

* `GET /buckets/1/comments/2.json` will return the comment with an ID of `2` in the Basecamp with an ID of `1`.

###### Example JSON Response

``` json
{
  "id": 9007199254741054,
  "created_at": "2016-01-27T11:31:31.734-06:00",
  "updated_at": "2016-01-27T11:31:31.734-06:00",
  "status": "active",
  "url": "https://3.basecampapi.com/195539477/buckets/2085958496/comments/9007199254741054",
  "content_html": "Yeah! Great job everyone! Super excited to get going!",
  "content_text": "Yeah! Great job everyone! Super excited to get going!",
  "type": "Comment",
  "creator": {
    "id": 1007299153,
    "name": "Andrew Wong",
    "email_address": "andrew@honchodesign.com",
    "avatar_url": "https://3.basecamp-assets.com/195539477/people/BAhpBFEqCjw=--f4f91a8c888e425d0d557f8f27d70dfb6f68505e/avatar-64-x4"
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
    "id": 9007199254741052,
    "title": "We won Leto!",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958496/messages/9007199254741053"
  }
}
```

###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/comment/2.json
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
  https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/recordings/3/comments.json
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
  https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/messages/2.json
```


[recordings]: https://github.com/basecamp/bc3-api/blob/master/sections/recordings.md#recordings
[messages]:   https://github.com/basecamp/bc3-api/blob/master/sections/messages.md#messages
[todolists]:  https://github.com/basecamp/bc3-api/blob/master/sections/todolists.md#todolists
[todos]:      https://github.com/basecamp/bc3-api/blob/master/sections/todos.md#todos
[trash]:      https://github.com/basecamp/bc3-api/blob/master/sections/recordings.md#trash-a-recording
[pagination]: https://github.com/basecamp/bc3-api/blob/master/README.md#pagination
[rich]:       https://github.com/basecamp/bc3-api/blob/master/README.md#rich-content
