Webhooks
========

Basecamp can notify your application when something is changed through webhooks.
A webhook consists of a payload URL to be called, which must be HTTPS, and a list of types that'll trigger calls.

Basecamp will attempt to call the payload URL up to 10 times before deactivating the webhook. The duration between attempts
will grow exponentially longer to give your service time to recover. Basecamp will only consider a HTTP status code in
the 2xx range to be a successful response. We will not follow a 3xx redirect.

A webhook can be subscribed to updates from the types detailed below. The default is to subscribe to all of them:

- Comment
- Document
- GoogleDocument
- Message
- Question
- Question::Answer
- Inbox::Forward
- Schedule::Entry
- Todo
- Todolist
- Upload

(Note that chat isn't amongst the options. We will be providing a chat bot API separately soon.)

Whenever an event is created for any of the types that webhook was created to match, Basecamp will call your payload URL.
All payloads follow the same JSON format:

```json
{
  "id": 9007199254741210,
  "kind": "message_created",
  "details": { "notified_recipient_ids": [1007299144] },
  "created_at": "2016-06-08T19:00:41.933Z",
  "recording": {
    "id": 9007199254741622,
    "status": "active",
    "created_at": "2016-07-20T00:21:41.446Z",
    "updated_at": "2016-07-19T21:29:08.739Z",
    "type": "Message",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958498/messages/9007199254741622.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958498/messages/9007199254741622",
    "comments_count": 1,
    "comments_url": "https://3.basecampapi.com/195539477/buckets/2085958498/recordings/9007199254741622/comments.json",
    "parent": {
      "id": 9007199254741434,
      "title": "Message Board",
      "type": "Message::Board",
      "url": "https://3.basecampapi.com/195539477/buckets/2085958498/message_boards/9007199254741434.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958498/message_boards/9007199254741434"
    },
    "bucket": {
      "id": 2085958498,
      "name": "The Leto Laptop",
      "type": "Project"
    },
    "creator": {
      "id": 1007299165,
      "attachable_sgid": "BAh7CEkiCGdpZAY6BkVUSSIrZ2lkOi8vYmMzL1BlcnNvbi8xMDA3Mjk5MTY1P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg9hdHRhY2hhYmxlBjsAVEkiD2V4cGlyZXNfYXQGOwBUMA==--c28a27d0c490353fc1a5c2a50ce8eda0fae07370",
      "name": "Matt Donahue",
      "email_address": "matt@honchodesign.com",
      "personable_type": "User",
      "title": "Global Data Strategist",
      "bio": null,
      "created_at": "2016-07-19T21:27:47.654Z",
      "updated_at": "2016-07-19T21:27:47.654Z",
      "admin": false,
      "owner": false,
      "time_zone": "America/Chicago",
      "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBF0qCjw=--21513efb0cf6f64f7a0720b2c56ac6145ae6680c/avatar-64-x4"
    },
    "title": "Welcome to Basecamp!",
    "content": "<div>Hey all, here are some high res shots of the laptop hardware that we can use. These are not public yet, so be careful with how you share them. We don't want any leaks at all with these images.</div>"
  },
  "creator": {
    "id": 1007299165,
    "attachable_sgid": "BAh7CEkiCGdpZAY6BkVUSSIrZ2lkOi8vYmMzL1BlcnNvbi8xMDA3Mjk5MTY1P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg9hdHRhY2hhYmxlBjsAVEkiD2V4cGlyZXNfYXQGOwBUMA==--c28a27d0c490353fc1a5c2a50ce8eda0fae07370",
    "name": "Matt Donahue",
    "email_address": "matt@honchodesign.com",
    "personable_type": "User",
    "title": "Global Data Strategist",
    "bio": null,
    "created_at": "2016-07-19T21:27:47.654Z",
    "updated_at": "2016-07-19T21:27:47.654Z",
    "admin": false,
    "owner": false,
    "time_zone": "America/Chicago",
    "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBF0qCjw=--21513efb0cf6f64f7a0720b2c56ac6145ae6680c/avatar-64-x4"
  }
}
```

As you'll note, the recording format is the basic generic format that all other content endpoints share, with the addition of a title and content field.

After sending the payload, Basecamp will record the interaction with your application as a delivery record that can be introspected for debugging.
The delivery record includes the full request and response that occurred for that specific event relay.

Basecamp will send the following lifecycle events for all types, here using message as an example:

- message_created / message_active
- message_title_updated / message_content_updated
- message_copied / message_inserted
- message_archived / message_unarchived
- message_trashed / message_untrashed
- message_deleted

There are also a handful of shared operations around the types that pertain to all types, again using message as an example:

- message_subscribers_changed
- message_publicized

Comments added on any recording will trigger the following event:

- comment_created

Additionally, some types have unique events. They are as follows:

Todos:

- todo_completed
- todo_uncompleted

Questions:

- question_paused
- question_resumed

Endpoints:

- [Get webhooks](#get-webhooks)
- [Get a webhook](#get-a-webhook)
- [Create a webhook](#create-a-webhook)
- [Update a webhook](#update-a-webhook)
- [Destroy a webhook](#destroy-a-webhook)

Get webhooks
------------

* `GET /buckets/1/webhooks.json` will return all the webhooks from the basecamp with an ID of `1`.

###### Example JSON Response
```json
[
  {
    "id": 9007199254741202,
    "active": "true",
    "created_at": "2016-06-08T19:00:41.933Z",
    "updated_at": "2016-07-19T16:47:00.621Z",
    "payload_url": "https://example.com/endpoint",
    "types": [ "all" ],
    "url": "https://3.basecampapi.com/195539477/buckets/2085958498/webhooks/9007199254741202.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958498/webhooks/9007199254741202"
  },
  {
    "id": 9007199254741203,
    "active": "false",
    "created_at": "2016-06-08T19:00:41.933Z",
    "updated_at": "2016-07-19T16:47:00.621Z",
    "payload_url": "https://example.com/another/endpoint",
    "types": [ "Todo", "Todolist" ],
    "url": "https://3.basecampapi.com/195539477/buckets/2085958498/webhooks/9007199254741203.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958498/webhooks/9007199254741203"
  }  
]
```
###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/webhooks.json
```

Get a webhook
-------------

* `GET /buckets/1/webhooks/3.json` will return the webhook with an ID of `3` in the project with ID `1`.

The recent deliveries array will contain the 25 most recent delivery exchanges, sorted with the most recent first.

###### Example JSON Response
```json
{
"id": 9007199254741202,
"active": "true",
"created_at": "2016-06-08T19:00:41.933Z",
"updated_at": "2016-07-19T16:47:00.621Z",
"payload_url": "https://example.com/endpoint",
"types": [ "all" ],
"url": "https://3.basecampapi.com/195539477/buckets/2085958498/webhooks/9007199254741202.json",
"app_url": "https://3.basecamp.com/195539477/buckets/2085958498/webhooks/9007199254741202",
"recent_deliveries": [
  {
    "id": 2,
    "created_at": "2016-08-26T18:36:09.988Z",
    "request": {
      "headers": {
        "Content-Type": "application/json",
        "User-Agent": "Basecamp3 Webhook",
        "X-Request-Id": "d9ba7dae-2ee0-4a89-bace-b7bbbe1a30d9"
      },
      "body": {
        "id": 9007199254741828,
        "kind": "todo_completed",
        "details": { },
        "created_at": "2016-08-26T13:36:07.345-05:00",
        "recording": {
          "id": 9007199254741036,
          "status": "active",
          "created_at": "2016-08-05T15:02:19.588-05:00",
          "updated_at": "2016-08-26T13:36:07.340-05:00",
          "type": "Todo",
          "url": "http://bc3-api.dev/195539477/buckets/2085958495/todos/9007199254741036.json",
          "app_url": "http://bc3.dev/195539477/buckets/2085958495/todos/9007199254741036",
          "parent": {
            "id": 9007199254741034,
            "title": "Project stuff",
            "type": "Todolist",
            "url": "http://bc3-api.dev/195539477/buckets/2085958495/todolists/9007199254741034.json",
            "app_url": "http://bc3.dev/195539477/buckets/2085958495/todolists/9007199254741034"
          },
          "bucket": {
            "id": 2085958495,
            "name": "Annie's Corner",
            "type": "Project"
          },
          "title": "Add Leto folks to Basecamp",
          "content": "Add Leto folks to Basecamp"
        }
      }
    },
    "response": {
      "code": 200,
      "headers": {
        "Content-Type": "text/html;charset=utf-8",
        "Content-Length": "0"
      },
      "message": "OK",
      "body": ""
    }
  }
]
}
```
###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/webhooks/3.json
```

Create a webhook
----------------

* `POST /buckets/1/webhooks.json` creates a webhook in the project with ID `1`.

**Required parameters**: `payload_url` for the HTTPS url that Basecamp should call.
_Optional parameters_: `types` as an array of types, options given in the introduction.

This endpoint will return `201 Created` with the current JSON representation of the vault if the creation was a success. See the [Get a webhook](#get-a-webhook) endpoint for more info on the payload.

###### Example JSON Request

``` json
{
  "payload_url": "https://example.com/endpoint",
  "types": [ "Todo", "Todolist" ]
}
```

###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -H "Content-Type: application/json" \
  -d '{"payload_url":"https://example.com/endpoint","types":["Todo","Todolist"]}' \
  https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/webhooks.json
```

Update a webhook
----------------

* `PUT /buckets/1/webhooks/3.json` allows changing the payload url and types of the webhook with an ID of `3` in the project with ID `1`.

**Required parameters**: `payload_url` for the HTTPS url that Basecamp will call.
_Optional parameters_: `types` as an array of types, options given in the introduction. `active` as a boolean whether this webhook should be matching.

This endpoint will return `200 OK` with the current JSON representation of the webhook if the update was a success. See the [Get a webhook](#get-a-webhook) endpoint for more info on the payload.

###### Example JSON Request

``` json
{
  "payload_url": "https://example.com/endpoint",
  "types": ["Todo", "Todolist"],
  "active": true
}
```

###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -H "Content-Type: application/json" \
  -d '{"payload_url":"https://example.com/endpoint","types":["Todo","Todolist"],"active":true}' -X PUT \
  https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/webhooks/3.json
```

Destroy a webhook
-----------------

* `DELETE /buckets/1/webhooks/3.json` will delete the webhook with an ID of `3` in the project with ID `1`.

This endpoint will return `204 No Content` if the destroy was a success.

###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -X DELETE \
  https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/webhooks/3.json
```
