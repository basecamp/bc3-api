Messages
========

Endpoints:

- [Get messages](#get-messages)
- [Get a message](#get-a-message)
- [Create a message](#create-a-message)
- [Update a message](#update-a-message)
- [Trash a message][1]

Get messages
------------

* `GET /buckets/1/message_boards/3/messages.json` will return a [paginated list][2] of active messages in the Basecamp with an ID of `1` and the message board with ID of `3`.

To get the message board ID for a Basecamp, see the [Get message board][3] endpoint.

###### Example JSON Response


``` json
[
  {
    "id": 9007199254741052,
    "created_at": "2015-10-30T13:55:28.313-05:00",
    "updated_at": "2016-01-27T11:00:34.131-06:00",
    "status": "active",
    "url": "https://3.basecamp.com/195539477/buckets/2085958496/messages/9007199254741053",
    "subject": "We won Leto!",
    "content_html": "Hey guys,\n\n  We won the Leto account! This is huge for us, it really marks a turning point for the company.\n\n  As you know we've been pursuing bigger clients in the consumer space, but we've done so carefully. We've never been about getting the biggest clients - those are easy to get. We've been trying to get the best clients for us - ones that will challenge us, grow us, make us better, and ultimately giving us a platform to show how awesome you guys all are. And now we have that!\n\n  A big congrats to everyone who worked so hard to make this happen, and now the fun really begins. Most of the pitch team will stay on as leading members of the first project, the Leto Microsite.\n\n  Again, great job everyone, and let's go kick some more butt!",
    "content_text": "Hey guys,\n\nWe won the Leto account! This is huge for us, it really marks a turning point for the company.\n\nAs you know we've been pursuing bigger clients in the consumer space, but we've done so carefully. We've never been about getting the biggest clients - those are easy to get. We've been trying to get the best clients for us - ones that will challenge us, grow us, make us better, and ultimately giving us a platform to show how awesome you guys all are. And now we have that!\n\nA big congrats to everyone who worked so hard to make this happen, and now the fun really begins. Most of the pitch team will stay on as leading members of the first project, the Leto Microsite.\n\nAgain, great job everyone, and let's go kick some more butt!",
    "comments_count": 10,
    "type": "Message",
    "creator": {
      "id": 1007299144,
      "name": "Victor Cooper",
      "email_address": "victor@honchodesign.com",
      "avatar_url": "https://3.basecamp-assets.com/195539477/people/BAhpBEgqCjw=--8266bb0507508f3d46050d57b65924d5e2a005f3/avatar-64-x4"
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
      "title": "Message Board",
      "url": "https://3.basecamp.com/195539477/buckets/2085958496/message_boards/9007199254741044"
    }
  },
  ...
]
```

###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecamp.com/$ACCOUNT_ID/buckets/1/message_boards/3/messages.json
```


Get a message
-------------

* `GET /buckets/1/messages/2.json` will return the message with an ID of `2` in the Basecamp with an ID of `1`.

###### Example JSON Response

``` json
{
  "id": 9007199254741872,
  "created_at": "2016-02-03T12:22:46.082-06:00",
  "updated_at": "2016-03-15T13:14:41.849-05:00",
  "status": "active",
  "url": "https://3.basecamp.com/195539477/buckets/2085958496/messages/9007199254741871",
  "subject": "Another one",
  "content_html": "<div>Welcome, Dave!</div>",
  "content_text": "Welcome, Dave!",
  "comments_count": 6,
  "type": "Message",
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
    "id": 9007199254741044,
    "title": "Message Board",
    "url": "https://3.basecamp.com/195539477/buckets/2085958496/message_boards/9007199254741044"
  }
}
```

Nesting under the message board resource is not necessary for this endpoint.

###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecamp.com/$ACCOUNT_ID/buckets/1/messages/2.json
```


Create a message
----------------

* `POST /buckets/1/message_boards/3/messages.json` publishes a message in the Basecamp with ID `1` and under the message board with an ID of `3`.

**Required parameters**: `subject` as the title of the message, and `status`, set to `active` to publish immediately.

_Optional parameters_: `content_html` as the body of the message. See our [Rich content][4] guide for what HTML tags are allowed.

Note: All people on a Basecamp are notified of the new message when it's posted. Changing who is subscribed is coming soon!

This endpoint will return `201 Created` with the current JSON representation of the message if the creation was a success. See the [Get a message](#get-a-message) endpoint for more info on the payload.

###### Example JSON Request

``` json
{
  "subject": "Kickoff",
  "content_html": "<div><strong>Welcome to Basecamp, everyone.</strong></div>",
  "status": "active"
}
```

###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -H "Content-Type: application/json" \
  -d '{"subject":"Kickoff","content_html":"<div><strong>Welcome to Basecamp, everyone.</strong></div>","status":"active"}' \
  https://3.basecamp.com/$ACCOUNT_ID/buckets/1/message_boards/3/messages.json
```


Update a message
----------------

* `PUT /buckets/1/messages/2.json` allows changing the subject and content of the message with an ID of `2` in the Basecamp with ID `1`.

Nesting under the message board resource is not necessary for this endpoint. Clients may deliver `subject` or `content_html` parameters, or both if necessary.

This endpoint will return `200 OK` with the current JSON representation of the message if the update was a success. See the [Get a message](#get-a-message) endpoint for more info on the payload.

###### Example JSON Request

``` json
{
  "subject": "Spin-down",
  "content_html": "<div><strong>Oops, we lost that client.</strong></div>"
}
```

###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -H "Content-Type: application/json" \
  -d '{"subject":"Spin-down","content_html":"<div><strong>Oops, we lost that client.</strong></div>"}' -X PUT \
  https://3.basecamp.com/$ACCOUNT_ID/buckets/1/messages/2.json
```


[1]: https://github.com/basecamp/bc3-api/blob/master/sections/recordings.md#trash-a-recording
[2]: https://github.com/basecamp/bc3-api/blob/master/README.md#pagination
[3]: https://github.com/basecamp/bc3-api/blob/master/sections/message_boards.md#message-boards
[4]: https://github.com/basecamp/bc3-api/blob/master/README.md#rich-content
