Webhooks
========

Basecamp can notify your application through webhooks when something is changed.
A webhook consists of a payload URL to be called, which must be HTTPS, and a list of types that'll trigger calls.

Basecamp will attempt to call the payload URL up to 10 times before deactivating the webhook. The duration between attempts
will grow exponentially longer to give your service time to recover. Basecamp will only consider a HTTP status code in
the 2xx range to be a successful response. We will not follow a 3xx redirect.

A webhook can be subscribed to updates from the types detailed below. The default is to subscribe to all of them.

Endpoints:

- Comment
- Client::Approval::Response
- Client::Forward
- Client::Reply
- CloudFile
- Document
- GoogleDocument
- Inbox::Forward
- Kanban::Card
- Kanban::Step
- Message
- Question
- Question::Answer
- Schedule::Entry
- Todo
- Todolist
- Upload
- Vault

Note that chat isn't amongst the options. Check our [chat bot API][1] for that. Also, `CloudFile` type corresponds to files linked from any cloud provider different from Google Drive (which has its separate `GoogleDocument` type). 

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
    "title": "Welcome to Basecamp!",
    "inherits_status": true,
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

As you'll note, the recording format is the basic generic format that all other content endpoints share, with the addition of a `content` field. This format won't include as many details about the recording as other specific endpoints return. For example, for a [todo][2], this won't include fields such as `description`, `completed` or `assignees`.

The payload for copy/move events will also include some details on the copied recording under `"copy"`. For example:
```json
{
   "id":1479523571,
   "kind":"todo_copied",
   "details":{
      "copy_id":981721240
   },
   "created_at":"2018-03-23T10:19:33.908+01:00",
   "copy":{
      "id":981721240,
      "url":"https://3.basecampapi.com/195539477/buckets/2085958499/todos/981721240.json",
      "app_url":"https://3.basecamp.com/195539477/buckets/2085958499/todos/981721240",
      "bucket":{
         "id":2085958499,
      }
   },
   "recording":{
      "id":968814335,
      "status":"active",
      "created_at":"2018-03-16T12:17:04.938+01:00",
      "updated_at":"2018-03-19T09:31:12.753+01:00",
      "title":"Go cutting edge: iOS8 and Android 4.5 only",
      "inherits_status": true,
      "type":"Todo",
      "url":"https://3.basecampapi.com/195539477/buckets/68833643212/todos/968814335.json",
      "app_url":"https://3.basecamp.com/195539477/buckets/68833643212/todos/968814335",
      "bookmark_url":"https://3.basecampapi.com/195539477/my/bookmarks/BAh7CEkiCGdpZAY6BkVUSSItZ2lkOi8vYmMzL1JlY29yZGluZy85Njg4MTQzMzU_ZXhwaXJlc19pbgY7AFRJIgxwdXJwb3NlBjsAVEkiDXJlYWRhYmxlBjsAVEkiD2V4cGlyZXNfYXQGOwBUMA==--9c496c78316f7ff7c52fbbbc957f198efd1c338c.json",
      "parent":{
         "id":968814030,
         "title": "Strategy ideas",
         "type":"Todolist",
         "url":"https://3.basecampapi.com/195539477/buckets/68833643212/todolists/968814030.json",
         "app_url":"https://3.basecamp.com/195539477/buckets/68833643212/todolists/968814030"
      },
      "bucket":{
         "id":68833643212,
         "name":"The Leto Laptop",
         "type":"Project"
      },
      "creator": {
        "id": 1049715915,
        "attachable_sgid": "BAh7CEkiCGdpZAY6BkVUSSIrZ2lkOi8vYmMzL1BlcnNvbi8xMDQ5NzE1OTE1P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg9hdHRhY2hhYmxlBjsAVEkiD2V4cGlyZXNfYXQGOwBUMA==--5f103c46d4f123f0068fcd0192a0f7fea7f26193",
        "name": "Annie Bryan",
        "email_address": "annie@honchodesign.com",
        "personable_type": "User",
        "title": "Central Markets Manager",
        "bio": "To open a store is easy, to keep it open is an art",
        "created_at": "2018-02-14T17:02:25.043Z",
        "updated_at": "2018-02-14T17:02:25.043Z",
        "admin": false,
        "owner": false,
        "time_zone": "America/Chicago",
        "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBMtkkT4=--e609ef146e39f9ca5e4bb7242fdfd50aec4c3b3f/avatar-64-x4",
        "company": {
          "id": 1033447817,
          "name": "Honcho Design"
        }
      },
      "content":"Go cutting edge: iOS8 and Android 4.5 only"
   },
  "creator": {
    "id": 1049715915,
    "attachable_sgid": "BAh7CEkiCGdpZAY6BkVUSSIrZ2lkOi8vYmMzL1BlcnNvbi8xMDQ5NzE1OTE1P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg9hdHRhY2hhYmxlBjsAVEkiD2V4cGlyZXNfYXQGOwBUMA==--5f103c46d4f123f0068fcd0192a0f7fea7f26193",
    "name": "Annie Bryan",
    "email_address": "annie@honchodesign.com",
    "personable_type": "User",
    "title": "Central Markets Manager",
    "bio": "To open a store is easy, to keep it open is an art",
    "created_at": "2018-02-14T17:02:25.043Z",
    "updated_at": "2018-02-14T17:02:25.043Z",
    "admin": false,
    "owner": false,
    "time_zone": "America/Chicago",
    "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBMtkkT4=--e609ef146e39f9ca5e4bb7242fdfd50aec4c3b3f/avatar-64-x4",
    "company": {
      "id": 1033447817,
      "name": "Honcho Design"
    }
  }
}
```

After sending the payload, Basecamp will record the interaction with your application as a delivery record that can be introspected for debugging.
The delivery record includes the full request and response that occurred for that specific event relay.

##### Events triggering webhooks

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

###### Status propagation to children recordings

Starting the 1st of July 2024, Basecamp won't notify of changes that are automatically propagated to children's recordings. For example, when archiving a todolist, all its contained todos and comments within each todo will get archived too. In this case, Basecamp will only notify the status change on the parent todolist, not on each of the contained items.

###### Endpoints

- [Get webhooks](#get-webhooks)
- [Get a webhook](#get-a-webhook)
- [Create a webhook](#create-a-webhook)
- [Update a webhook](#update-a-webhook)
- [Destroy a webhook](#destroy-a-webhook)

**Note:** client users aren't allowed to perform any of the webhook related actions, so calling these endpoints while being authenticated with a client user will get a `403 Forbidden` response. 

Get webhooks
------------

* `GET /buckets/1/webhooks.json` will return all the webhooks from the basecamp with an ID of `1`.

###### Example JSON Response
```json
[
  {
    "id": 9007199254741202,
    "active": true,
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
<!-- START GET /buckets/1/webhooks/3.json -->
```json
{
"id": 9007199254741202,
"active": true,
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
          "title": "Add Leto folks to Basecamp",
          "inherits_status": true,
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
<!-- END GET /buckets/1/webhooks/3.json -->
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

[1]: https://github.com/basecamp/bc3-api/blob/master/sections/chatbots.md
[2]: https://github.com/basecamp/bc3-api/blob/master/sections/todos.md#get-a-to-do
