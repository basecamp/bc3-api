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

* `GET /buckets/1/webhooks.json` will return all the webhooks for the project with an ID of `1`.

###### Example JSON Response
<!-- START GET /buckets/1/webhooks.json -->
```json
[
  {
    "id": 1051369971,
    "active": true,
    "created_at": "2026-01-31T08:38:45.916Z",
    "updated_at": "2026-01-31T08:38:45.916Z",
    "payload_url": "https://example.com/endpoint",
    "types": [
      "all"
    ],
    "url": "https://3.basecampapi.com/195539477/buckets/2085958504/webhooks/1051369971.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958504/webhooks/1051369971"
  }
]
```
<!-- END GET /buckets/1/webhooks.json -->
###### Copy as cURL

```shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/webhooks.json
```

Get a webhook
-------------

* `GET /webhooks/3.json` will return the webhook with an ID of `3`.

The recent deliveries array will contain the 25 most recent delivery exchanges, sorted with the most recent first.

###### Example JSON Response
<!-- START GET /webhooks/3.json -->
```json
{
  "id": 1051369971,
  "active": true,
  "created_at": "2026-01-31T08:38:45.916Z",
  "updated_at": "2026-01-31T08:38:45.916Z",
  "payload_url": "https://example.com/endpoint",
  "types": [
    "all"
  ],
  "url": "https://3.basecampapi.com/195539477/buckets/2085958504/webhooks/1051369971.json",
  "app_url": "https://3.basecamp.com/195539477/buckets/2085958504/webhooks/1051369971",
  "recent_deliveries": [
    {
      "id": 627138748,
      "created_at": "2026-02-06T22:45:25.539Z",
      "request": {
        "headers": {
          "Content-Type": "application/json",
          "User-Agent": "Basecamp3 Webhook",
          "X-Request-Id": "dbbd29a0-d95e-4f1c-b42a-9175d2eec13a"
        },
        "body": {
          "id": 1071915830,
          "kind": "timesheet_entry_deleted",
          "details": {
            "status_was": "active"
          },
          "created_at": "2026-02-06T16:45:24.441-06:00",
          "recording": {
            "id": 1069480063,
            "status": "deleted",
            "visible_to_clients": false,
            "created_at": "2026-02-06T16:45:23.220-06:00",
            "updated_at": "2026-02-06T16:45:24.420-06:00",
            "title": "Timesheet entry",
            "inherits_status": false,
            "type": "Timesheet::Entry",
            "url": "https://3.basecampapi.com/195539477/projects/2085958504/timesheet/entries/1069480063.json",
            "app_url": "http://3.basecamp.localhost:4001/195539477/projects/2085958504/timesheet/entries/1069480063",
            "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiLmdpZDovL2JjMy9SZWNvcmRpbmcvMTA2OTQ4MDA2Mz9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg1yZWFkYWJsZQY7AFQ=--26abeb4c635676c566ca512ea6606d069f7392e0.json",
            "parent": {
              "id": 1069479406,
              "title": "We won Leto!",
              "type": "Message",
              "url": "https://3.basecampapi.com/195539477/buckets/2085958504/messages/1069479406.json",
              "app_url": "http://3.basecamp.localhost:4001/195539477/buckets/2085958504/messages/1069479406"
            },
            "bucket": {
              "id": 2085958504,
              "name": "The Leto Laptop",
              "type": "Project"
            },
            "creator": {
              "id": 1049715913,
              "attachable_sgid": "BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiK2dpZDovL2JjMy9QZXJzb24vMTA0OTcxNTkxMz9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg9hdHRhY2hhYmxlBjsAVA==--e627c45e6b34e08862da23906862412620e4d5d9",
              "name": "Victor Cooper",
              "email_address": "victor@honchodesign.com",
              "personable_type": "User",
              "title": "Chief Strategist",
              "bio": "Don’t let your dreams be dreams",
              "location": "Chicago, IL",
              "created_at": "2026-01-31T02:29:28.365-06:00",
              "updated_at": "2026-01-31T02:29:32.599-06:00",
              "admin": true,
              "owner": true,
              "client": false,
              "employee": true,
              "time_zone": "America/Chicago",
              "avatar_url": "http://bc3-cdn.3.basecamp.localhost:4001/195539477/people/BAhpBMlkkT4=--5fe7b70fbee7a7f0e2e1e19df7579e5d880c753d/avatar?v=1",
              "company": {
                "id": 1033447817,
                "name": "Honcho Design"
              },
              "can_ping": true,
              "can_manage_projects": true,
              "can_manage_people": true,
              "can_access_timesheet": true,
              "can_access_hill_charts": true
            },
            "content": null
          },
          "creator": {
            "id": 1049715913,
            "attachable_sgid": "BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiK2dpZDovL2JjMy9QZXJzb24vMTA0OTcxNTkxMz9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg9hdHRhY2hhYmxlBjsAVA==--e627c45e6b34e08862da23906862412620e4d5d9",
            "name": "Victor Cooper",
            "email_address": "victor@honchodesign.com",
            "personable_type": "User",
            "title": "Chief Strategist",
            "bio": "Don’t let your dreams be dreams",
            "location": "Chicago, IL",
            "created_at": "2026-01-31T02:29:28.365-06:00",
            "updated_at": "2026-01-31T02:29:32.599-06:00",
            "admin": true,
            "owner": true,
            "client": false,
            "employee": true,
            "time_zone": "America/Chicago",
            "avatar_url": "http://bc3-cdn.3.basecamp.localhost:4001/195539477/people/BAhpBMlkkT4=--5fe7b70fbee7a7f0e2e1e19df7579e5d880c753d/avatar?v=1",
            "company": {
              "id": 1033447817,
              "name": "Honcho Design"
            },
            "can_ping": true,
            "can_manage_projects": true,
            "can_manage_people": true,
            "can_access_timesheet": true,
            "can_access_hill_charts": true
          }
        }
      },
      "response": {
        "error": "#<OpenSSL::SSL::SSLError: SSL_connect returned=1 errno=0 peeraddr=[2606:4700::6812:1a78]:443 state=error: certificate verify failed (unable to get certificate CRL)>"
      }
    },
    {
      "id": 627138747,
      "created_at": "2026-02-06T22:45:25.120Z",
      "request": {
        "headers": {
          "Content-Type": "application/json",
          "User-Agent": "Basecamp3 Webhook",
          "X-Request-Id": "ac687907-7d62-4fc3-94bd-e6cb50524c67"
        },
        "body": {
          "id": 1071915828,
          "kind": "timesheet_entry_description_changed",
          "details": {},
          "created_at": "2026-02-06T16:45:24.005-06:00",
          "recording": {
            "id": 1069480063,
            "status": "deleted",
            "visible_to_clients": false,
            "created_at": "2026-02-06T16:45:23.220-06:00",
            "updated_at": "2026-02-06T16:45:24.420-06:00",
            "title": "Timesheet entry",
            "inherits_status": false,
            "type": "Timesheet::Entry",
            "url": "https://3.basecampapi.com/195539477/projects/2085958504/timesheet/entries/1069480063.json",
            "app_url": "http://3.basecamp.localhost:4001/195539477/projects/2085958504/timesheet/entries/1069480063",
            "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiLmdpZDovL2JjMy9SZWNvcmRpbmcvMTA2OTQ4MDA2Mz9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg1yZWFkYWJsZQY7AFQ=--26abeb4c635676c566ca512ea6606d069f7392e0.json",
            "parent": {
              "id": 1069479406,
              "title": "We won Leto!",
              "type": "Message",
              "url": "https://3.basecampapi.com/195539477/buckets/2085958504/messages/1069479406.json",
              "app_url": "http://3.basecamp.localhost:4001/195539477/buckets/2085958504/messages/1069479406"
            },
            "bucket": {
              "id": 2085958504,
              "name": "The Leto Laptop",
              "type": "Project"
            },
            "creator": {
              "id": 1049715913,
              "attachable_sgid": "BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiK2dpZDovL2JjMy9QZXJzb24vMTA0OTcxNTkxMz9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg9hdHRhY2hhYmxlBjsAVA==--e627c45e6b34e08862da23906862412620e4d5d9",
              "name": "Victor Cooper",
              "email_address": "victor@honchodesign.com",
              "personable_type": "User",
              "title": "Chief Strategist",
              "bio": "Don’t let your dreams be dreams",
              "location": "Chicago, IL",
              "created_at": "2026-01-31T02:29:28.365-06:00",
              "updated_at": "2026-01-31T02:29:32.599-06:00",
              "admin": true,
              "owner": true,
              "client": false,
              "employee": true,
              "time_zone": "America/Chicago",
              "avatar_url": "http://bc3-cdn.3.basecamp.localhost:4001/195539477/people/BAhpBMlkkT4=--5fe7b70fbee7a7f0e2e1e19df7579e5d880c753d/avatar?v=1",
              "company": {
                "id": 1033447817,
                "name": "Honcho Design"
              },
              "can_ping": true,
              "can_manage_projects": true,
              "can_manage_people": true,
              "can_access_timesheet": true,
              "can_access_hill_charts": true
            },
            "content": null
          },
          "creator": {
            "id": 1049715913,
            "attachable_sgid": "BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiK2dpZDovL2JjMy9QZXJzb24vMTA0OTcxNTkxMz9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg9hdHRhY2hhYmxlBjsAVA==--e627c45e6b34e08862da23906862412620e4d5d9",
            "name": "Victor Cooper",
            "email_address": "victor@honchodesign.com",
            "personable_type": "User",
            "title": "Chief Strategist",
            "bio": "Don’t let your dreams be dreams",
            "location": "Chicago, IL",
            "created_at": "2026-01-31T02:29:28.365-06:00",
            "updated_at": "2026-01-31T02:29:32.599-06:00",
            "admin": true,
            "owner": true,
            "client": false,
            "employee": true,
            "time_zone": "America/Chicago",
            "avatar_url": "http://bc3-cdn.3.basecamp.localhost:4001/195539477/people/BAhpBMlkkT4=--5fe7b70fbee7a7f0e2e1e19df7579e5d880c753d/avatar?v=1",
            "company": {
              "id": 1033447817,
              "name": "Honcho Design"
            },
            "can_ping": true,
            "can_manage_projects": true,
            "can_manage_people": true,
            "can_access_timesheet": true,
            "can_access_hill_charts": true
          }
        }
      },
      "response": {
        "error": "#<OpenSSL::SSL::SSLError: SSL_connect returned=1 errno=0 peeraddr=[2606:4700::6812:1a78]:443 state=error: certificate verify failed (unable to get certificate CRL)>"
      }
    },
    {
      "id": 627138746,
      "created_at": "2026-02-06T22:45:25.116Z",
      "request": {
        "headers": {
          "Content-Type": "application/json",
          "User-Agent": "Basecamp3 Webhook",
          "X-Request-Id": "8c7a92f1-472a-4a7d-bc14-c99c3b3cd031"
        },
        "body": {
          "id": 1071915829,
          "kind": "timesheet_entry_hours_changed",
          "details": {},
          "created_at": "2026-02-06T16:45:24.009-06:00",
          "recording": {
            "id": 1069480063,
            "status": "deleted",
            "visible_to_clients": false,
            "created_at": "2026-02-06T16:45:23.220-06:00",
            "updated_at": "2026-02-06T16:45:24.420-06:00",
            "title": "Timesheet entry",
            "inherits_status": false,
            "type": "Timesheet::Entry",
            "url": "https://3.basecampapi.com/195539477/projects/2085958504/timesheet/entries/1069480063.json",
            "app_url": "http://3.basecamp.localhost:4001/195539477/projects/2085958504/timesheet/entries/1069480063",
            "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiLmdpZDovL2JjMy9SZWNvcmRpbmcvMTA2OTQ4MDA2Mz9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg1yZWFkYWJsZQY7AFQ=--26abeb4c635676c566ca512ea6606d069f7392e0.json",
            "parent": {
              "id": 1069479406,
              "title": "We won Leto!",
              "type": "Message",
              "url": "https://3.basecampapi.com/195539477/buckets/2085958504/messages/1069479406.json",
              "app_url": "http://3.basecamp.localhost:4001/195539477/buckets/2085958504/messages/1069479406"
            },
            "bucket": {
              "id": 2085958504,
              "name": "The Leto Laptop",
              "type": "Project"
            },
            "creator": {
              "id": 1049715913,
              "attachable_sgid": "BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiK2dpZDovL2JjMy9QZXJzb24vMTA0OTcxNTkxMz9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg9hdHRhY2hhYmxlBjsAVA==--e627c45e6b34e08862da23906862412620e4d5d9",
              "name": "Victor Cooper",
              "email_address": "victor@honchodesign.com",
              "personable_type": "User",
              "title": "Chief Strategist",
              "bio": "Don’t let your dreams be dreams",
              "location": "Chicago, IL",
              "created_at": "2026-01-31T02:29:28.365-06:00",
              "updated_at": "2026-01-31T02:29:32.599-06:00",
              "admin": true,
              "owner": true,
              "client": false,
              "employee": true,
              "time_zone": "America/Chicago",
              "avatar_url": "http://bc3-cdn.3.basecamp.localhost:4001/195539477/people/BAhpBMlkkT4=--5fe7b70fbee7a7f0e2e1e19df7579e5d880c753d/avatar?v=1",
              "company": {
                "id": 1033447817,
                "name": "Honcho Design"
              },
              "can_ping": true,
              "can_manage_projects": true,
              "can_manage_people": true,
              "can_access_timesheet": true,
              "can_access_hill_charts": true
            },
            "content": null
          },
          "creator": {
            "id": 1049715913,
            "attachable_sgid": "BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiK2dpZDovL2JjMy9QZXJzb24vMTA0OTcxNTkxMz9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg9hdHRhY2hhYmxlBjsAVA==--e627c45e6b34e08862da23906862412620e4d5d9",
            "name": "Victor Cooper",
            "email_address": "victor@honchodesign.com",
            "personable_type": "User",
            "title": "Chief Strategist",
            "bio": "Don’t let your dreams be dreams",
            "location": "Chicago, IL",
            "created_at": "2026-01-31T02:29:28.365-06:00",
            "updated_at": "2026-01-31T02:29:32.599-06:00",
            "admin": true,
            "owner": true,
            "client": false,
            "employee": true,
            "time_zone": "America/Chicago",
            "avatar_url": "http://bc3-cdn.3.basecamp.localhost:4001/195539477/people/BAhpBMlkkT4=--5fe7b70fbee7a7f0e2e1e19df7579e5d880c753d/avatar?v=1",
            "company": {
              "id": 1033447817,
              "name": "Honcho Design"
            },
            "can_ping": true,
            "can_manage_projects": true,
            "can_manage_people": true,
            "can_access_timesheet": true,
            "can_access_hill_charts": true
          }
        }
      },
      "response": {
        "error": "#<OpenSSL::SSL::SSLError: SSL_connect returned=1 errno=0 peeraddr=[2606:4700::6812:1a78]:443 state=error: certificate verify failed (unable to get certificate CRL)>"
      }
    },
    {
      "id": 627138745,
      "created_at": "2026-02-06T22:45:24.302Z",
      "request": {
        "headers": {
          "Content-Type": "application/json",
          "User-Agent": "Basecamp3 Webhook",
          "X-Request-Id": "a26ce21e-0e0d-4ea4-b250-b680ef55ceb9"
        },
        "body": {
          "id": 1071915827,
          "kind": "timesheet_entry_created",
          "details": {},
          "created_at": "2026-02-06T16:45:23.227-06:00",
          "recording": {
            "id": 1069480063,
            "status": "active",
            "visible_to_clients": false,
            "created_at": "2026-02-06T16:45:23.220-06:00",
            "updated_at": "2026-02-06T16:45:23.995-06:00",
            "title": "Timesheet entry",
            "inherits_status": true,
            "type": "Timesheet::Entry",
            "url": "https://3.basecampapi.com/195539477/projects/2085958504/timesheet/entries/1069480063.json",
            "app_url": "http://3.basecamp.localhost:4001/195539477/projects/2085958504/timesheet/entries/1069480063",
            "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiLmdpZDovL2JjMy9SZWNvcmRpbmcvMTA2OTQ4MDA2Mz9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg1yZWFkYWJsZQY7AFQ=--26abeb4c635676c566ca512ea6606d069f7392e0.json",
            "parent": {
              "id": 1069479406,
              "title": "We won Leto!",
              "type": "Message",
              "url": "https://3.basecampapi.com/195539477/buckets/2085958504/messages/1069479406.json",
              "app_url": "http://3.basecamp.localhost:4001/195539477/buckets/2085958504/messages/1069479406"
            },
            "bucket": {
              "id": 2085958504,
              "name": "The Leto Laptop",
              "type": "Project"
            },
            "creator": {
              "id": 1049715913,
              "attachable_sgid": "BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiK2dpZDovL2JjMy9QZXJzb24vMTA0OTcxNTkxMz9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg9hdHRhY2hhYmxlBjsAVA==--e627c45e6b34e08862da23906862412620e4d5d9",
              "name": "Victor Cooper",
              "email_address": "victor@honchodesign.com",
              "personable_type": "User",
              "title": "Chief Strategist",
              "bio": "Don’t let your dreams be dreams",
              "location": "Chicago, IL",
              "created_at": "2026-01-31T02:29:28.365-06:00",
              "updated_at": "2026-01-31T02:29:32.599-06:00",
              "admin": true,
              "owner": true,
              "client": false,
              "employee": true,
              "time_zone": "America/Chicago",
              "avatar_url": "http://bc3-cdn.3.basecamp.localhost:4001/195539477/people/BAhpBMlkkT4=--5fe7b70fbee7a7f0e2e1e19df7579e5d880c753d/avatar?v=1",
              "company": {
                "id": 1033447817,
                "name": "Honcho Design"
              },
              "can_ping": true,
              "can_manage_projects": true,
              "can_manage_people": true,
              "can_access_timesheet": true,
              "can_access_hill_charts": true
            },
            "content": null
          },
          "creator": {
            "id": 1049715913,
            "attachable_sgid": "BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiK2dpZDovL2JjMy9QZXJzb24vMTA0OTcxNTkxMz9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg9hdHRhY2hhYmxlBjsAVA==--e627c45e6b34e08862da23906862412620e4d5d9",
            "name": "Victor Cooper",
            "email_address": "victor@honchodesign.com",
            "personable_type": "User",
            "title": "Chief Strategist",
            "bio": "Don’t let your dreams be dreams",
            "location": "Chicago, IL",
            "created_at": "2026-01-31T02:29:28.365-06:00",
            "updated_at": "2026-01-31T02:29:32.599-06:00",
            "admin": true,
            "owner": true,
            "client": false,
            "employee": true,
            "time_zone": "America/Chicago",
            "avatar_url": "http://bc3-cdn.3.basecamp.localhost:4001/195539477/people/BAhpBMlkkT4=--5fe7b70fbee7a7f0e2e1e19df7579e5d880c753d/avatar?v=1",
            "company": {
              "id": 1033447817,
              "name": "Honcho Design"
            },
            "can_ping": true,
            "can_manage_projects": true,
            "can_manage_people": true,
            "can_access_timesheet": true,
            "can_access_hill_charts": true
          }
        }
      },
      "response": {
        "error": "#<OpenSSL::SSL::SSLError: SSL_connect returned=1 errno=0 peeraddr=[2606:4700::6812:1a78]:443 state=error: certificate verify failed (unable to get certificate CRL)>"
      }
    },
    {
      "id": 627138744,
      "created_at": "2026-02-06T22:44:45.584Z",
      "request": {
        "headers": {
          "Content-Type": "application/json",
          "User-Agent": "Basecamp3 Webhook",
          "X-Request-Id": "cfac79dd-48ea-4bd8-9d0f-1aff003781e4"
        },
        "body": {
          "id": 1071915799,
          "kind": "timesheet_entry_deleted",
          "details": {
            "status_was": "active"
          },
          "created_at": "2026-02-06T16:44:44.452-06:00",
          "recording": {
            "id": 1069480038,
            "status": "deleted",
            "visible_to_clients": false,
            "created_at": "2026-02-06T16:44:43.002-06:00",
            "updated_at": "2026-02-06T16:44:44.413-06:00",
            "title": "Timesheet entry",
            "inherits_status": false,
            "type": "Timesheet::Entry",
            "url": "https://3.basecampapi.com/195539477/projects/2085958504/timesheet/entries/1069480038.json",
            "app_url": "http://3.basecamp.localhost:4001/195539477/projects/2085958504/timesheet/entries/1069480038",
            "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiLmdpZDovL2JjMy9SZWNvcmRpbmcvMTA2OTQ4MDAzOD9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg1yZWFkYWJsZQY7AFQ=--f81229c0afbfed60f6e03184f50f919ee2527277.json",
            "parent": {
              "id": 1069479406,
              "title": "We won Leto!",
              "type": "Message",
              "url": "https://3.basecampapi.com/195539477/buckets/2085958504/messages/1069479406.json",
              "app_url": "http://3.basecamp.localhost:4001/195539477/buckets/2085958504/messages/1069479406"
            },
            "bucket": {
              "id": 2085958504,
              "name": "The Leto Laptop",
              "type": "Project"
            },
            "creator": {
              "id": 1049715913,
              "attachable_sgid": "BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiK2dpZDovL2JjMy9QZXJzb24vMTA0OTcxNTkxMz9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg9hdHRhY2hhYmxlBjsAVA==--e627c45e6b34e08862da23906862412620e4d5d9",
              "name": "Victor Cooper",
              "email_address": "victor@honchodesign.com",
              "personable_type": "User",
              "title": "Chief Strategist",
              "bio": "Don’t let your dreams be dreams",
              "location": "Chicago, IL",
              "created_at": "2026-01-31T02:29:28.365-06:00",
              "updated_at": "2026-01-31T02:29:32.599-06:00",
              "admin": true,
              "owner": true,
              "client": false,
              "employee": true,
              "time_zone": "America/Chicago",
              "avatar_url": "http://bc3-cdn.3.basecamp.localhost:4001/195539477/people/BAhpBMlkkT4=--5fe7b70fbee7a7f0e2e1e19df7579e5d880c753d/avatar?v=1",
              "company": {
                "id": 1033447817,
                "name": "Honcho Design"
              },
              "can_ping": true,
              "can_manage_projects": true,
              "can_manage_people": true,
              "can_access_timesheet": true,
              "can_access_hill_charts": true
            },
            "content": null
          },
          "creator": {
            "id": 1049715913,
            "attachable_sgid": "BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiK2dpZDovL2JjMy9QZXJzb24vMTA0OTcxNTkxMz9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg9hdHRhY2hhYmxlBjsAVA==--e627c45e6b34e08862da23906862412620e4d5d9",
            "name": "Victor Cooper",
            "email_address": "victor@honchodesign.com",
            "personable_type": "User",
            "title": "Chief Strategist",
            "bio": "Don’t let your dreams be dreams",
            "location": "Chicago, IL",
            "created_at": "2026-01-31T02:29:28.365-06:00",
            "updated_at": "2026-01-31T02:29:32.599-06:00",
            "admin": true,
            "owner": true,
            "client": false,
            "employee": true,
            "time_zone": "America/Chicago",
            "avatar_url": "http://bc3-cdn.3.basecamp.localhost:4001/195539477/people/BAhpBMlkkT4=--5fe7b70fbee7a7f0e2e1e19df7579e5d880c753d/avatar?v=1",
            "company": {
              "id": 1033447817,
              "name": "Honcho Design"
            },
            "can_ping": true,
            "can_manage_projects": true,
            "can_manage_people": true,
            "can_access_timesheet": true,
            "can_access_hill_charts": true
          }
        }
      },
      "response": {
        "error": "#<OpenSSL::SSL::SSLError: SSL_connect returned=1 errno=0 peeraddr=[2606:4700::6812:1b78]:443 state=error: certificate verify failed (unable to get certificate CRL)>"
      }
    },
    {
      "id": 627138743,
      "created_at": "2026-02-06T22:44:45.111Z",
      "request": {
        "headers": {
          "Content-Type": "application/json",
          "User-Agent": "Basecamp3 Webhook",
          "X-Request-Id": "e30f1cb4-0d9c-4ae1-b4dd-8737676c1a0b"
        },
        "body": {
          "id": 1071915798,
          "kind": "timesheet_entry_hours_changed",
          "details": {},
          "created_at": "2026-02-06T16:44:43.999-06:00",
          "recording": {
            "id": 1069480038,
            "status": "deleted",
            "visible_to_clients": false,
            "created_at": "2026-02-06T16:44:43.002-06:00",
            "updated_at": "2026-02-06T16:44:44.413-06:00",
            "title": "Timesheet entry",
            "inherits_status": false,
            "type": "Timesheet::Entry",
            "url": "https://3.basecampapi.com/195539477/projects/2085958504/timesheet/entries/1069480038.json",
            "app_url": "http://3.basecamp.localhost:4001/195539477/projects/2085958504/timesheet/entries/1069480038",
            "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiLmdpZDovL2JjMy9SZWNvcmRpbmcvMTA2OTQ4MDAzOD9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg1yZWFkYWJsZQY7AFQ=--f81229c0afbfed60f6e03184f50f919ee2527277.json",
            "parent": {
              "id": 1069479406,
              "title": "We won Leto!",
              "type": "Message",
              "url": "https://3.basecampapi.com/195539477/buckets/2085958504/messages/1069479406.json",
              "app_url": "http://3.basecamp.localhost:4001/195539477/buckets/2085958504/messages/1069479406"
            },
            "bucket": {
              "id": 2085958504,
              "name": "The Leto Laptop",
              "type": "Project"
            },
            "creator": {
              "id": 1049715913,
              "attachable_sgid": "BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiK2dpZDovL2JjMy9QZXJzb24vMTA0OTcxNTkxMz9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg9hdHRhY2hhYmxlBjsAVA==--e627c45e6b34e08862da23906862412620e4d5d9",
              "name": "Victor Cooper",
              "email_address": "victor@honchodesign.com",
              "personable_type": "User",
              "title": "Chief Strategist",
              "bio": "Don’t let your dreams be dreams",
              "location": "Chicago, IL",
              "created_at": "2026-01-31T02:29:28.365-06:00",
              "updated_at": "2026-01-31T02:29:32.599-06:00",
              "admin": true,
              "owner": true,
              "client": false,
              "employee": true,
              "time_zone": "America/Chicago",
              "avatar_url": "http://bc3-cdn.3.basecamp.localhost:4001/195539477/people/BAhpBMlkkT4=--5fe7b70fbee7a7f0e2e1e19df7579e5d880c753d/avatar?v=1",
              "company": {
                "id": 1033447817,
                "name": "Honcho Design"
              },
              "can_ping": true,
              "can_manage_projects": true,
              "can_manage_people": true,
              "can_access_timesheet": true,
              "can_access_hill_charts": true
            },
            "content": null
          },
          "creator": {
            "id": 1049715913,
            "attachable_sgid": "BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiK2dpZDovL2JjMy9QZXJzb24vMTA0OTcxNTkxMz9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg9hdHRhY2hhYmxlBjsAVA==--e627c45e6b34e08862da23906862412620e4d5d9",
            "name": "Victor Cooper",
            "email_address": "victor@honchodesign.com",
            "personable_type": "User",
            "title": "Chief Strategist",
            "bio": "Don’t let your dreams be dreams",
            "location": "Chicago, IL",
            "created_at": "2026-01-31T02:29:28.365-06:00",
            "updated_at": "2026-01-31T02:29:32.599-06:00",
            "admin": true,
            "owner": true,
            "client": false,
            "employee": true,
            "time_zone": "America/Chicago",
            "avatar_url": "http://bc3-cdn.3.basecamp.localhost:4001/195539477/people/BAhpBMlkkT4=--5fe7b70fbee7a7f0e2e1e19df7579e5d880c753d/avatar?v=1",
            "company": {
              "id": 1033447817,
              "name": "Honcho Design"
            },
            "can_ping": true,
            "can_manage_projects": true,
            "can_manage_people": true,
            "can_access_timesheet": true,
            "can_access_hill_charts": true
          }
        }
      },
      "response": {
        "error": "#<OpenSSL::SSL::SSLError: SSL_connect returned=1 errno=0 peeraddr=[2606:4700::6812:1b78]:443 state=error: certificate verify failed (unable to get certificate CRL)>"
      }
    },
    {
      "id": 627138742,
      "created_at": "2026-02-06T22:44:45.093Z",
      "request": {
        "headers": {
          "Content-Type": "application/json",
          "User-Agent": "Basecamp3 Webhook",
          "X-Request-Id": "8c638ca9-ab89-4f1f-a4c6-d068cda95bc7"
        },
        "body": {
          "id": 1071915797,
          "kind": "timesheet_entry_description_changed",
          "details": {},
          "created_at": "2026-02-06T16:44:43.994-06:00",
          "recording": {
            "id": 1069480038,
            "status": "deleted",
            "visible_to_clients": false,
            "created_at": "2026-02-06T16:44:43.002-06:00",
            "updated_at": "2026-02-06T16:44:44.413-06:00",
            "title": "Timesheet entry",
            "inherits_status": false,
            "type": "Timesheet::Entry",
            "url": "https://3.basecampapi.com/195539477/projects/2085958504/timesheet/entries/1069480038.json",
            "app_url": "http://3.basecamp.localhost:4001/195539477/projects/2085958504/timesheet/entries/1069480038",
            "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiLmdpZDovL2JjMy9SZWNvcmRpbmcvMTA2OTQ4MDAzOD9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg1yZWFkYWJsZQY7AFQ=--f81229c0afbfed60f6e03184f50f919ee2527277.json",
            "parent": {
              "id": 1069479406,
              "title": "We won Leto!",
              "type": "Message",
              "url": "https://3.basecampapi.com/195539477/buckets/2085958504/messages/1069479406.json",
              "app_url": "http://3.basecamp.localhost:4001/195539477/buckets/2085958504/messages/1069479406"
            },
            "bucket": {
              "id": 2085958504,
              "name": "The Leto Laptop",
              "type": "Project"
            },
            "creator": {
              "id": 1049715913,
              "attachable_sgid": "BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiK2dpZDovL2JjMy9QZXJzb24vMTA0OTcxNTkxMz9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg9hdHRhY2hhYmxlBjsAVA==--e627c45e6b34e08862da23906862412620e4d5d9",
              "name": "Victor Cooper",
              "email_address": "victor@honchodesign.com",
              "personable_type": "User",
              "title": "Chief Strategist",
              "bio": "Don’t let your dreams be dreams",
              "location": "Chicago, IL",
              "created_at": "2026-01-31T02:29:28.365-06:00",
              "updated_at": "2026-01-31T02:29:32.599-06:00",
              "admin": true,
              "owner": true,
              "client": false,
              "employee": true,
              "time_zone": "America/Chicago",
              "avatar_url": "http://bc3-cdn.3.basecamp.localhost:4001/195539477/people/BAhpBMlkkT4=--5fe7b70fbee7a7f0e2e1e19df7579e5d880c753d/avatar?v=1",
              "company": {
                "id": 1033447817,
                "name": "Honcho Design"
              },
              "can_ping": true,
              "can_manage_projects": true,
              "can_manage_people": true,
              "can_access_timesheet": true,
              "can_access_hill_charts": true
            },
            "content": null
          },
          "creator": {
            "id": 1049715913,
            "attachable_sgid": "BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiK2dpZDovL2JjMy9QZXJzb24vMTA0OTcxNTkxMz9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg9hdHRhY2hhYmxlBjsAVA==--e627c45e6b34e08862da23906862412620e4d5d9",
            "name": "Victor Cooper",
            "email_address": "victor@honchodesign.com",
            "personable_type": "User",
            "title": "Chief Strategist",
            "bio": "Don’t let your dreams be dreams",
            "location": "Chicago, IL",
            "created_at": "2026-01-31T02:29:28.365-06:00",
            "updated_at": "2026-01-31T02:29:32.599-06:00",
            "admin": true,
            "owner": true,
            "client": false,
            "employee": true,
            "time_zone": "America/Chicago",
            "avatar_url": "http://bc3-cdn.3.basecamp.localhost:4001/195539477/people/BAhpBMlkkT4=--5fe7b70fbee7a7f0e2e1e19df7579e5d880c753d/avatar?v=1",
            "company": {
              "id": 1033447817,
              "name": "Honcho Design"
            },
            "can_ping": true,
            "can_manage_projects": true,
            "can_manage_people": true,
            "can_access_timesheet": true,
            "can_access_hill_charts": true
          }
        }
      },
      "response": {
        "error": "#<OpenSSL::SSL::SSLError: SSL_connect returned=1 errno=0 peeraddr=[2606:4700::6812:1b78]:443 state=error: certificate verify failed (unable to get certificate CRL)>"
      }
    },
    {
      "id": 627138741,
      "created_at": "2026-02-06T22:44:44.426Z",
      "request": {
        "headers": {
          "Content-Type": "application/json",
          "User-Agent": "Basecamp3 Webhook",
          "X-Request-Id": "c62b8ade-b086-4385-bf79-ca8f8a56b387"
        },
        "body": {
          "id": 1071915796,
          "kind": "timesheet_entry_created",
          "details": {},
          "created_at": "2026-02-06T16:44:43.053-06:00",
          "recording": {
            "id": 1069480038,
            "status": "active",
            "visible_to_clients": false,
            "created_at": "2026-02-06T16:44:43.002-06:00",
            "updated_at": "2026-02-06T16:44:43.968-06:00",
            "title": "Timesheet entry",
            "inherits_status": true,
            "type": "Timesheet::Entry",
            "url": "https://3.basecampapi.com/195539477/projects/2085958504/timesheet/entries/1069480038.json",
            "app_url": "https://3.basecamp.com/195539477/projects/2085958504/timesheet/entries/1069480038",
            "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiLmdpZDovL2JjMy9SZWNvcmRpbmcvMTA2OTQ4MDAzOD9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg1yZWFkYWJsZQY7AFQ=--f81229c0afbfed60f6e03184f50f919ee2527277.json",
            "parent": {
              "id": 1069479406,
              "title": "We won Leto!",
              "type": "Message",
              "url": "https://3.basecampapi.com/195539477/buckets/2085958504/messages/1069479406.json",
              "app_url": "https://3.basecamp.com/195539477/buckets/2085958504/messages/1069479406"
            },
            "bucket": {
              "id": 2085958504,
              "name": "The Leto Laptop",
              "type": "Project"
            },
            "creator": {
              "id": 1049715913,
              "attachable_sgid": "BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiK2dpZDovL2JjMy9QZXJzb24vMTA0OTcxNTkxMz9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg9hdHRhY2hhYmxlBjsAVA==--e627c45e6b34e08862da23906862412620e4d5d9",
              "name": "Victor Cooper",
              "email_address": "victor@honchodesign.com",
              "personable_type": "User",
              "title": "Chief Strategist",
              "bio": "Don’t let your dreams be dreams",
              "location": "Chicago, IL",
              "created_at": "2026-01-31T02:29:28.365-06:00",
              "updated_at": "2026-01-31T02:29:32.599-06:00",
              "admin": true,
              "owner": true,
              "client": false,
              "employee": true,
              "time_zone": "America/Chicago",
              "avatar_url": "https://3.basecampapi.com/195539477/people/BAhpBMlkkT4=--5fe7b70fbee7a7f0e2e1e19df7579e5d880c753d/avatar?v=1",
              "company": {
                "id": 1033447817,
                "name": "Honcho Design"
              },
              "can_ping": true,
              "can_manage_projects": true,
              "can_manage_people": true,
              "can_access_timesheet": true,
              "can_access_hill_charts": true
            },
            "content": null
          },
          "creator": {
            "id": 1049715913,
            "attachable_sgid": "BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiK2dpZDovL2JjMy9QZXJzb24vMTA0OTcxNTkxMz9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg9hdHRhY2hhYmxlBjsAVA==--e627c45e6b34e08862da23906862412620e4d5d9",
            "name": "Victor Cooper",
            "email_address": "victor@honchodesign.com",
            "personable_type": "User",
            "title": "Chief Strategist",
            "bio": "Don’t let your dreams be dreams",
            "location": "Chicago, IL",
            "created_at": "2026-01-31T02:29:28.365-06:00",
            "updated_at": "2026-01-31T02:29:32.599-06:00",
            "admin": true,
            "owner": true,
            "client": false,
            "employee": true,
            "time_zone": "America/Chicago",
            "avatar_url": "https://3.basecampapi.com/195539477/people/BAhpBMlkkT4=--5fe7b70fbee7a7f0e2e1e19df7579e5d880c753d/avatar?v=1",
            "company": {
              "id": 1033447817,
              "name": "Honcho Design"
            },
            "can_ping": true,
            "can_manage_projects": true,
            "can_manage_people": true,
            "can_access_timesheet": true,
            "can_access_hill_charts": true
          }
        }
      },
      "response": {
        "error": "#<OpenSSL::SSL::SSLError: SSL_connect returned=1 errno=0 peeraddr=[2606:4700::6812:1b78]:443 state=error: certificate verify failed (unable to get certificate CRL)>"
      }
    },
    {
      "id": 627138740,
      "created_at": "2026-02-06T22:19:55.732Z",
      "request": {
        "headers": {
          "Content-Type": "application/json",
          "User-Agent": "Basecamp3 Webhook",
          "X-Request-Id": "bf67274e-1a54-407f-96a7-0ee3637416e0"
        },
        "body": {
          "id": 1071915795,
          "kind": "message_subscribers_changed",
          "details": {
            "added_person_ids": [
              1049715939
            ],
            "removed_person_ids": [
              1049715913
            ]
          },
          "created_at": "2026-02-06T16:19:54.663-06:00",
          "recording": {
            "id": 1069479406,
            "status": "active",
            "visible_to_clients": false,
            "created_at": "2025-12-18T17:30:00.000-06:00",
            "updated_at": "2026-02-06T16:19:54.659-06:00",
            "title": "We won Leto!",
            "inherits_status": true,
            "type": "Message",
            "url": "https://3.basecampapi.com/195539477/buckets/2085958504/messages/1069479406.json",
            "app_url": "http://3.basecamp.localhost:4001/195539477/buckets/2085958504/messages/1069479406",
            "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiLmdpZDovL2JjMy9SZWNvcmRpbmcvMTA2OTQ3OTQwNj9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg1yZWFkYWJsZQY7AFQ=--309e0fbab86893aaaf279f01f2a0795c56716aeb.json",
            "subscription_url": "https://3.basecampapi.com/195539477/buckets/2085958504/recordings/1069479406/subscription.json",
            "parent": {
              "id": 1069479392,
              "title": "Message Board",
              "type": "Message::Board",
              "url": "https://3.basecampapi.com/195539477/buckets/2085958504/message_boards/1069479392.json",
              "app_url": "http://3.basecamp.localhost:4001/195539477/buckets/2085958504/message_boards/1069479392"
            },
            "bucket": {
              "id": 2085958504,
              "name": "The Leto Laptop",
              "type": "Project"
            },
            "creator": {
              "id": 1049715913,
              "attachable_sgid": "BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiK2dpZDovL2JjMy9QZXJzb24vMTA0OTcxNTkxMz9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg9hdHRhY2hhYmxlBjsAVA==--e627c45e6b34e08862da23906862412620e4d5d9",
              "name": "Victor Cooper",
              "email_address": "victor@honchodesign.com",
              "personable_type": "User",
              "title": "Chief Strategist",
              "bio": "Don’t let your dreams be dreams",
              "location": "Chicago, IL",
              "created_at": "2026-01-31T02:29:28.365-06:00",
              "updated_at": "2026-01-31T02:29:32.599-06:00",
              "admin": true,
              "owner": true,
              "client": false,
              "employee": true,
              "time_zone": "America/Chicago",
              "avatar_url": "http://bc3-cdn.3.basecamp.localhost:4001/195539477/people/BAhpBMlkkT4=--5fe7b70fbee7a7f0e2e1e19df7579e5d880c753d/avatar?v=1",
              "company": {
                "id": 1033447817,
                "name": "Honcho Design"
              },
              "can_ping": true,
              "can_manage_projects": true,
              "can_manage_people": true,
              "can_access_timesheet": true,
              "can_access_hill_charts": true
            },
            "content": "Hey guys,<br><br>We won the Leto account! This is huge for us, it really marks a turning point for the company.<br><br>As you know we've been pursuing bigger clients in the consumer space, but we've done so carefully. We've never been about getting the biggest clients - those are easy to get. We've been trying to get the best clients for us - ones that will challenge us, grow us, make us better, and ultimately giving us a platform to show how awesome you guys all are. And now we have that!<br><br>A big congrats to everyone who worked so hard to make this happen, and now the fun really begins. Most of the pitch team will stay on as leading members of the first project, the Leto Microsite.<br><br>Again, great job everyone, and let's go kick some more butt!<br><br>-Victor<br>"
          },
          "creator": {
            "id": 1049715913,
            "attachable_sgid": "BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiK2dpZDovL2JjMy9QZXJzb24vMTA0OTcxNTkxMz9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg9hdHRhY2hhYmxlBjsAVA==--e627c45e6b34e08862da23906862412620e4d5d9",
            "name": "Victor Cooper",
            "email_address": "victor@honchodesign.com",
            "personable_type": "User",
            "title": "Chief Strategist",
            "bio": "Don’t let your dreams be dreams",
            "location": "Chicago, IL",
            "created_at": "2026-01-31T02:29:28.365-06:00",
            "updated_at": "2026-01-31T02:29:32.599-06:00",
            "admin": true,
            "owner": true,
            "client": false,
            "employee": true,
            "time_zone": "America/Chicago",
            "avatar_url": "http://bc3-cdn.3.basecamp.localhost:4001/195539477/people/BAhpBMlkkT4=--5fe7b70fbee7a7f0e2e1e19df7579e5d880c753d/avatar?v=1",
            "company": {
              "id": 1033447817,
              "name": "Honcho Design"
            },
            "can_ping": true,
            "can_manage_projects": true,
            "can_manage_people": true,
            "can_access_timesheet": true,
            "can_access_hill_charts": true
          }
        }
      },
      "response": {
        "error": "#<OpenSSL::SSL::SSLError: SSL_connect returned=1 errno=0 peeraddr=[2606:4700::6812:1a78]:443 state=error: certificate verify failed (unable to get certificate CRL)>"
      }
    },
    {
      "id": 627138739,
      "created_at": "2026-02-06T22:19:48.150Z",
      "request": {
        "headers": {
          "Content-Type": "application/json",
          "User-Agent": "Basecamp3 Webhook",
          "X-Request-Id": "9dbc96b0-b8e7-4c73-877b-69ee3c1ddda9"
        },
        "body": {
          "id": 1071915793,
          "kind": "todo_uncompleted",
          "details": {},
          "created_at": "2026-02-06T16:19:46.800-06:00",
          "recording": {
            "id": 1069479576,
            "status": "active",
            "visible_to_clients": false,
            "created_at": "2026-01-15T01:20:00.000-06:00",
            "updated_at": "2026-02-06T16:19:46.799-06:00",
            "title": "Clear and simple UI",
            "inherits_status": true,
            "type": "Todo",
            "url": "https://3.basecampapi.com/195539477/buckets/2085958504/todos/1069479576.json",
            "app_url": "http://3.basecamp.localhost:4001/195539477/buckets/2085958504/todos/1069479576",
            "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiLmdpZDovL2JjMy9SZWNvcmRpbmcvMTA2OTQ3OTU3Nj9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg1yZWFkYWJsZQY7AFQ=--11a40c121978ed499b97e8c9ed0d3bfc8632df41.json",
            "subscription_url": "https://3.basecampapi.com/195539477/buckets/2085958504/recordings/1069479576/subscription.json",
            "position": 3,
            "parent": {
              "id": 1069479573,
              "title": "Strategy ideas",
              "type": "Todolist",
              "url": "https://3.basecampapi.com/195539477/buckets/2085958504/todolists/1069479573.json",
              "app_url": "http://3.basecamp.localhost:4001/195539477/buckets/2085958504/todolists/1069479573"
            },
            "bucket": {
              "id": 2085958504,
              "name": "The Leto Laptop",
              "type": "Project"
            },
            "creator": {
              "id": 1049715938,
              "attachable_sgid": "BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiK2dpZDovL2JjMy9QZXJzb24vMTA0OTcxNTkzOD9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg9hdHRhY2hhYmxlBjsAVA==--4ccc567a0a3b10e354bca909b704637b601f0b16",
              "name": "Annie Bryan",
              "email_address": "annie@honchodesign.com",
              "personable_type": "User",
              "title": "Central Markets Manager",
              "bio": "To open a store is easy, to keep it open is an art",
              "location": null,
              "created_at": "2026-01-31T02:29:42.795-06:00",
              "updated_at": "2026-01-31T02:29:42.795-06:00",
              "admin": false,
              "owner": false,
              "client": false,
              "employee": true,
              "time_zone": "America/Chicago",
              "avatar_url": "http://bc3-cdn.3.basecamp.localhost:4001/195539477/people/BAhpBOJkkT4=--732a71fbd28ec10d9bf4466abd3588a8bea40bdb/avatar?v=1",
              "company": {
                "id": 1033447817,
                "name": "Honcho Design"
              },
              "can_ping": true,
              "can_manage_projects": true,
              "can_manage_people": true,
              "can_access_timesheet": true,
              "can_access_hill_charts": true
            },
            "content": "Clear and simple UI"
          },
          "creator": {
            "id": 1049715930,
            "attachable_sgid": "BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiK2dpZDovL2JjMy9QZXJzb24vMTA0OTcxNTkzMD9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg9hdHRhY2hhYmxlBjsAVA==--322099b137f9e0b6bc944b5b9fe7a2692da94814",
            "name": "Sharon Bradford",
            "email_address": "sharon@honchodesign.com",
            "personable_type": "User",
            "title": "Principal Branding Administrator",
            "bio": null,
            "location": null,
            "created_at": "2026-01-31T02:29:40.859-06:00",
            "updated_at": "2026-01-31T02:29:40.859-06:00",
            "admin": false,
            "owner": false,
            "client": false,
            "employee": false,
            "time_zone": "America/Chicago",
            "avatar_url": "http://bc3-cdn.3.basecamp.localhost:4001/195539477/people/BAhpBNpkkT4=--789594e5e542ab99e467a51c9dec0a9035abc0e0/avatar?v=1",
            "can_ping": true,
            "can_manage_projects": true,
            "can_manage_people": true,
            "can_access_timesheet": true,
            "can_access_hill_charts": true
          }
        }
      },
      "response": {
        "error": "#<OpenSSL::SSL::SSLError: SSL_connect returned=1 errno=0 peeraddr=[2606:4700::6812:1a78]:443 state=error: certificate verify failed (unable to get certificate CRL)>"
      }
    },
    {
      "id": 627138738,
      "created_at": "2026-02-06T22:19:47.616Z",
      "request": {
        "headers": {
          "Content-Type": "application/json",
          "User-Agent": "Basecamp3 Webhook",
          "X-Request-Id": "d055d5a8-6805-4d92-a53d-fdb05b84a906"
        },
        "body": {
          "id": 1071915792,
          "kind": "todo_completed",
          "details": {
            "notified_recipient_ids": [
              1049715938
            ]
          },
          "created_at": "2026-02-06T16:19:46.349-06:00",
          "recording": {
            "id": 1069479576,
            "status": "active",
            "visible_to_clients": false,
            "created_at": "2026-01-15T01:20:00.000-06:00",
            "updated_at": "2026-02-06T16:19:46.799-06:00",
            "title": "Clear and simple UI",
            "inherits_status": true,
            "type": "Todo",
            "url": "https://3.basecampapi.com/195539477/buckets/2085958504/todos/1069479576.json",
            "app_url": "http://3.basecamp.localhost:4001/195539477/buckets/2085958504/todos/1069479576",
            "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiLmdpZDovL2JjMy9SZWNvcmRpbmcvMTA2OTQ3OTU3Nj9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg1yZWFkYWJsZQY7AFQ=--11a40c121978ed499b97e8c9ed0d3bfc8632df41.json",
            "subscription_url": "https://3.basecampapi.com/195539477/buckets/2085958504/recordings/1069479576/subscription.json",
            "position": 3,
            "parent": {
              "id": 1069479573,
              "title": "Strategy ideas",
              "type": "Todolist",
              "url": "https://3.basecampapi.com/195539477/buckets/2085958504/todolists/1069479573.json",
              "app_url": "http://3.basecamp.localhost:4001/195539477/buckets/2085958504/todolists/1069479573"
            },
            "bucket": {
              "id": 2085958504,
              "name": "The Leto Laptop",
              "type": "Project"
            },
            "creator": {
              "id": 1049715938,
              "attachable_sgid": "BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiK2dpZDovL2JjMy9QZXJzb24vMTA0OTcxNTkzOD9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg9hdHRhY2hhYmxlBjsAVA==--4ccc567a0a3b10e354bca909b704637b601f0b16",
              "name": "Annie Bryan",
              "email_address": "annie@honchodesign.com",
              "personable_type": "User",
              "title": "Central Markets Manager",
              "bio": "To open a store is easy, to keep it open is an art",
              "location": null,
              "created_at": "2026-01-31T02:29:42.795-06:00",
              "updated_at": "2026-01-31T02:29:42.795-06:00",
              "admin": false,
              "owner": false,
              "client": false,
              "employee": true,
              "time_zone": "America/Chicago",
              "avatar_url": "http://bc3-cdn.3.basecamp.localhost:4001/195539477/people/BAhpBOJkkT4=--732a71fbd28ec10d9bf4466abd3588a8bea40bdb/avatar?v=1",
              "company": {
                "id": 1033447817,
                "name": "Honcho Design"
              },
              "can_ping": true,
              "can_manage_projects": true,
              "can_manage_people": true,
              "can_access_timesheet": true,
              "can_access_hill_charts": true
            },
            "content": "Clear and simple UI"
          },
          "creator": {
            "id": 1049715930,
            "attachable_sgid": "BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiK2dpZDovL2JjMy9QZXJzb24vMTA0OTcxNTkzMD9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg9hdHRhY2hhYmxlBjsAVA==--322099b137f9e0b6bc944b5b9fe7a2692da94814",
            "name": "Sharon Bradford",
            "email_address": "sharon@honchodesign.com",
            "personable_type": "User",
            "title": "Principal Branding Administrator",
            "bio": null,
            "location": null,
            "created_at": "2026-01-31T02:29:40.859-06:00",
            "updated_at": "2026-01-31T02:29:40.859-06:00",
            "admin": false,
            "owner": false,
            "client": false,
            "employee": false,
            "time_zone": "America/Chicago",
            "avatar_url": "http://bc3-cdn.3.basecamp.localhost:4001/195539477/people/BAhpBNpkkT4=--789594e5e542ab99e467a51c9dec0a9035abc0e0/avatar?v=1",
            "can_ping": true,
            "can_manage_projects": true,
            "can_manage_people": true,
            "can_access_timesheet": true,
            "can_access_hill_charts": true
          }
        }
      },
      "response": {
        "error": "#<OpenSSL::SSL::SSLError: SSL_connect returned=1 errno=0 peeraddr=[2606:4700::6812:1a78]:443 state=error: certificate verify failed (unable to get certificate CRL)>"
      }
    },
    {
      "id": 627138737,
      "created_at": "2026-02-06T22:19:01.265Z",
      "request": {
        "headers": {
          "Content-Type": "application/json",
          "User-Agent": "Basecamp3 Webhook",
          "X-Request-Id": "28f1e5bd-c22f-47b5-96d5-dd39b83c2f61"
        },
        "body": {
          "id": 1071915758,
          "kind": "timesheet_entry_deleted",
          "details": {
            "status_was": "active"
          },
          "created_at": "2026-02-06T16:18:59.726-06:00",
          "recording": {
            "id": 1069480010,
            "status": "deleted",
            "visible_to_clients": false,
            "created_at": "2026-02-06T16:18:58.419-06:00",
            "updated_at": "2026-02-06T16:18:59.658-06:00",
            "title": "Timesheet entry",
            "inherits_status": false,
            "type": "Timesheet::Entry",
            "url": "https://3.basecampapi.com/195539477/projects/2085958504/timesheet/entries/1069480010.json",
            "app_url": "http://3.basecamp.localhost:4001/195539477/projects/2085958504/timesheet/entries/1069480010",
            "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiLmdpZDovL2JjMy9SZWNvcmRpbmcvMTA2OTQ4MDAxMD9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg1yZWFkYWJsZQY7AFQ=--6c3c632b2583ccb4836fc8bc1b9e55370fc2456c.json",
            "parent": {
              "id": 1069479406,
              "title": "We won Leto!",
              "type": "Message",
              "url": "https://3.basecampapi.com/195539477/buckets/2085958504/messages/1069479406.json",
              "app_url": "http://3.basecamp.localhost:4001/195539477/buckets/2085958504/messages/1069479406"
            },
            "bucket": {
              "id": 2085958504,
              "name": "The Leto Laptop",
              "type": "Project"
            },
            "creator": {
              "id": 1049715913,
              "attachable_sgid": "BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiK2dpZDovL2JjMy9QZXJzb24vMTA0OTcxNTkxMz9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg9hdHRhY2hhYmxlBjsAVA==--e627c45e6b34e08862da23906862412620e4d5d9",
              "name": "Victor Cooper",
              "email_address": "victor@honchodesign.com",
              "personable_type": "User",
              "title": "Chief Strategist",
              "bio": "Don’t let your dreams be dreams",
              "location": "Chicago, IL",
              "created_at": "2026-01-31T02:29:28.365-06:00",
              "updated_at": "2026-01-31T02:29:32.599-06:00",
              "admin": true,
              "owner": true,
              "client": false,
              "employee": true,
              "time_zone": "America/Chicago",
              "avatar_url": "http://bc3-cdn.3.basecamp.localhost:4001/195539477/people/BAhpBMlkkT4=--5fe7b70fbee7a7f0e2e1e19df7579e5d880c753d/avatar?v=1",
              "company": {
                "id": 1033447817,
                "name": "Honcho Design"
              },
              "can_ping": true,
              "can_manage_projects": true,
              "can_manage_people": true,
              "can_access_timesheet": true,
              "can_access_hill_charts": true
            },
            "content": null
          },
          "creator": {
            "id": 1049715913,
            "attachable_sgid": "BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiK2dpZDovL2JjMy9QZXJzb24vMTA0OTcxNTkxMz9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg9hdHRhY2hhYmxlBjsAVA==--e627c45e6b34e08862da23906862412620e4d5d9",
            "name": "Victor Cooper",
            "email_address": "victor@honchodesign.com",
            "personable_type": "User",
            "title": "Chief Strategist",
            "bio": "Don’t let your dreams be dreams",
            "location": "Chicago, IL",
            "created_at": "2026-01-31T02:29:28.365-06:00",
            "updated_at": "2026-01-31T02:29:32.599-06:00",
            "admin": true,
            "owner": true,
            "client": false,
            "employee": true,
            "time_zone": "America/Chicago",
            "avatar_url": "http://bc3-cdn.3.basecamp.localhost:4001/195539477/people/BAhpBMlkkT4=--5fe7b70fbee7a7f0e2e1e19df7579e5d880c753d/avatar?v=1",
            "company": {
              "id": 1033447817,
              "name": "Honcho Design"
            },
            "can_ping": true,
            "can_manage_projects": true,
            "can_manage_people": true,
            "can_access_timesheet": true,
            "can_access_hill_charts": true
          }
        }
      },
      "response": {
        "error": "#<OpenSSL::SSL::SSLError: SSL_connect returned=1 errno=0 peeraddr=[2606:4700::6812:1a78]:443 state=error: certificate verify failed (unable to get certificate CRL)>"
      }
    },
    {
      "id": 627138736,
      "created_at": "2026-02-06T22:19:00.414Z",
      "request": {
        "headers": {
          "Content-Type": "application/json",
          "User-Agent": "Basecamp3 Webhook",
          "X-Request-Id": "e77b491d-6fab-4ab0-9be2-5a711ed54db0"
        },
        "body": {
          "id": 1071915757,
          "kind": "timesheet_entry_hours_changed",
          "details": {},
          "created_at": "2026-02-06T16:18:59.298-06:00",
          "recording": {
            "id": 1069480010,
            "status": "deleted",
            "visible_to_clients": false,
            "created_at": "2026-02-06T16:18:58.419-06:00",
            "updated_at": "2026-02-06T16:18:59.658-06:00",
            "title": "Timesheet entry",
            "inherits_status": false,
            "type": "Timesheet::Entry",
            "url": "https://3.basecampapi.com/195539477/projects/2085958504/timesheet/entries/1069480010.json",
            "app_url": "http://3.basecamp.localhost:4001/195539477/projects/2085958504/timesheet/entries/1069480010",
            "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiLmdpZDovL2JjMy9SZWNvcmRpbmcvMTA2OTQ4MDAxMD9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg1yZWFkYWJsZQY7AFQ=--6c3c632b2583ccb4836fc8bc1b9e55370fc2456c.json",
            "parent": {
              "id": 1069479406,
              "title": "We won Leto!",
              "type": "Message",
              "url": "https://3.basecampapi.com/195539477/buckets/2085958504/messages/1069479406.json",
              "app_url": "http://3.basecamp.localhost:4001/195539477/buckets/2085958504/messages/1069479406"
            },
            "bucket": {
              "id": 2085958504,
              "name": "The Leto Laptop",
              "type": "Project"
            },
            "creator": {
              "id": 1049715913,
              "attachable_sgid": "BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiK2dpZDovL2JjMy9QZXJzb24vMTA0OTcxNTkxMz9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg9hdHRhY2hhYmxlBjsAVA==--e627c45e6b34e08862da23906862412620e4d5d9",
              "name": "Victor Cooper",
              "email_address": "victor@honchodesign.com",
              "personable_type": "User",
              "title": "Chief Strategist",
              "bio": "Don’t let your dreams be dreams",
              "location": "Chicago, IL",
              "created_at": "2026-01-31T02:29:28.365-06:00",
              "updated_at": "2026-01-31T02:29:32.599-06:00",
              "admin": true,
              "owner": true,
              "client": false,
              "employee": true,
              "time_zone": "America/Chicago",
              "avatar_url": "http://bc3-cdn.3.basecamp.localhost:4001/195539477/people/BAhpBMlkkT4=--5fe7b70fbee7a7f0e2e1e19df7579e5d880c753d/avatar?v=1",
              "company": {
                "id": 1033447817,
                "name": "Honcho Design"
              },
              "can_ping": true,
              "can_manage_projects": true,
              "can_manage_people": true,
              "can_access_timesheet": true,
              "can_access_hill_charts": true
            },
            "content": null
          },
          "creator": {
            "id": 1049715913,
            "attachable_sgid": "BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiK2dpZDovL2JjMy9QZXJzb24vMTA0OTcxNTkxMz9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg9hdHRhY2hhYmxlBjsAVA==--e627c45e6b34e08862da23906862412620e4d5d9",
            "name": "Victor Cooper",
            "email_address": "victor@honchodesign.com",
            "personable_type": "User",
            "title": "Chief Strategist",
            "bio": "Don’t let your dreams be dreams",
            "location": "Chicago, IL",
            "created_at": "2026-01-31T02:29:28.365-06:00",
            "updated_at": "2026-01-31T02:29:32.599-06:00",
            "admin": true,
            "owner": true,
            "client": false,
            "employee": true,
            "time_zone": "America/Chicago",
            "avatar_url": "http://bc3-cdn.3.basecamp.localhost:4001/195539477/people/BAhpBMlkkT4=--5fe7b70fbee7a7f0e2e1e19df7579e5d880c753d/avatar?v=1",
            "company": {
              "id": 1033447817,
              "name": "Honcho Design"
            },
            "can_ping": true,
            "can_manage_projects": true,
            "can_manage_people": true,
            "can_access_timesheet": true,
            "can_access_hill_charts": true
          }
        }
      },
      "response": {
        "error": "#<OpenSSL::SSL::SSLError: SSL_connect returned=1 errno=0 peeraddr=[2606:4700::6812:1a78]:443 state=error: certificate verify failed (unable to get certificate CRL)>"
      }
    },
    {
      "id": 627138735,
      "created_at": "2026-02-06T22:19:00.391Z",
      "request": {
        "headers": {
          "Content-Type": "application/json",
          "User-Agent": "Basecamp3 Webhook",
          "X-Request-Id": "ce42867a-7f88-461f-a2c0-64f91fc2622b"
        },
        "body": {
          "id": 1071915756,
          "kind": "timesheet_entry_description_changed",
          "details": {},
          "created_at": "2026-02-06T16:18:59.292-06:00",
          "recording": {
            "id": 1069480010,
            "status": "deleted",
            "visible_to_clients": false,
            "created_at": "2026-02-06T16:18:58.419-06:00",
            "updated_at": "2026-02-06T16:18:59.658-06:00",
            "title": "Timesheet entry",
            "inherits_status": false,
            "type": "Timesheet::Entry",
            "url": "https://3.basecampapi.com/195539477/projects/2085958504/timesheet/entries/1069480010.json",
            "app_url": "http://3.basecamp.localhost:4001/195539477/projects/2085958504/timesheet/entries/1069480010",
            "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiLmdpZDovL2JjMy9SZWNvcmRpbmcvMTA2OTQ4MDAxMD9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg1yZWFkYWJsZQY7AFQ=--6c3c632b2583ccb4836fc8bc1b9e55370fc2456c.json",
            "parent": {
              "id": 1069479406,
              "title": "We won Leto!",
              "type": "Message",
              "url": "https://3.basecampapi.com/195539477/buckets/2085958504/messages/1069479406.json",
              "app_url": "http://3.basecamp.localhost:4001/195539477/buckets/2085958504/messages/1069479406"
            },
            "bucket": {
              "id": 2085958504,
              "name": "The Leto Laptop",
              "type": "Project"
            },
            "creator": {
              "id": 1049715913,
              "attachable_sgid": "BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiK2dpZDovL2JjMy9QZXJzb24vMTA0OTcxNTkxMz9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg9hdHRhY2hhYmxlBjsAVA==--e627c45e6b34e08862da23906862412620e4d5d9",
              "name": "Victor Cooper",
              "email_address": "victor@honchodesign.com",
              "personable_type": "User",
              "title": "Chief Strategist",
              "bio": "Don’t let your dreams be dreams",
              "location": "Chicago, IL",
              "created_at": "2026-01-31T02:29:28.365-06:00",
              "updated_at": "2026-01-31T02:29:32.599-06:00",
              "admin": true,
              "owner": true,
              "client": false,
              "employee": true,
              "time_zone": "America/Chicago",
              "avatar_url": "http://bc3-cdn.3.basecamp.localhost:4001/195539477/people/BAhpBMlkkT4=--5fe7b70fbee7a7f0e2e1e19df7579e5d880c753d/avatar?v=1",
              "company": {
                "id": 1033447817,
                "name": "Honcho Design"
              },
              "can_ping": true,
              "can_manage_projects": true,
              "can_manage_people": true,
              "can_access_timesheet": true,
              "can_access_hill_charts": true
            },
            "content": null
          },
          "creator": {
            "id": 1049715913,
            "attachable_sgid": "BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiK2dpZDovL2JjMy9QZXJzb24vMTA0OTcxNTkxMz9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg9hdHRhY2hhYmxlBjsAVA==--e627c45e6b34e08862da23906862412620e4d5d9",
            "name": "Victor Cooper",
            "email_address": "victor@honchodesign.com",
            "personable_type": "User",
            "title": "Chief Strategist",
            "bio": "Don’t let your dreams be dreams",
            "location": "Chicago, IL",
            "created_at": "2026-01-31T02:29:28.365-06:00",
            "updated_at": "2026-01-31T02:29:32.599-06:00",
            "admin": true,
            "owner": true,
            "client": false,
            "employee": true,
            "time_zone": "America/Chicago",
            "avatar_url": "http://bc3-cdn.3.basecamp.localhost:4001/195539477/people/BAhpBMlkkT4=--5fe7b70fbee7a7f0e2e1e19df7579e5d880c753d/avatar?v=1",
            "company": {
              "id": 1033447817,
              "name": "Honcho Design"
            },
            "can_ping": true,
            "can_manage_projects": true,
            "can_manage_people": true,
            "can_access_timesheet": true,
            "can_access_hill_charts": true
          }
        }
      },
      "response": {
        "error": "#<OpenSSL::SSL::SSLError: SSL_connect returned=1 errno=0 peeraddr=[2606:4700::6812:1a78]:443 state=error: certificate verify failed (unable to get certificate CRL)>"
      }
    },
    {
      "id": 627138734,
      "created_at": "2026-02-06T22:18:59.649Z",
      "request": {
        "headers": {
          "Content-Type": "application/json",
          "User-Agent": "Basecamp3 Webhook",
          "X-Request-Id": "5af0876d-96d4-41c6-b29c-a0984736e4b2"
        },
        "body": {
          "id": 1071915755,
          "kind": "timesheet_entry_created",
          "details": {},
          "created_at": "2026-02-06T16:18:58.462-06:00",
          "recording": {
            "id": 1069480010,
            "status": "active",
            "visible_to_clients": false,
            "created_at": "2026-02-06T16:18:58.419-06:00",
            "updated_at": "2026-02-06T16:18:59.271-06:00",
            "title": "Timesheet entry",
            "inherits_status": true,
            "type": "Timesheet::Entry",
            "url": "https://3.basecampapi.com/195539477/projects/2085958504/timesheet/entries/1069480010.json",
            "app_url": "http://3.basecamp.localhost:4001/195539477/projects/2085958504/timesheet/entries/1069480010",
            "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiLmdpZDovL2JjMy9SZWNvcmRpbmcvMTA2OTQ4MDAxMD9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg1yZWFkYWJsZQY7AFQ=--6c3c632b2583ccb4836fc8bc1b9e55370fc2456c.json",
            "parent": {
              "id": 1069479406,
              "title": "We won Leto!",
              "type": "Message",
              "url": "https://3.basecampapi.com/195539477/buckets/2085958504/messages/1069479406.json",
              "app_url": "http://3.basecamp.localhost:4001/195539477/buckets/2085958504/messages/1069479406"
            },
            "bucket": {
              "id": 2085958504,
              "name": "The Leto Laptop",
              "type": "Project"
            },
            "creator": {
              "id": 1049715913,
              "attachable_sgid": "BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiK2dpZDovL2JjMy9QZXJzb24vMTA0OTcxNTkxMz9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg9hdHRhY2hhYmxlBjsAVA==--e627c45e6b34e08862da23906862412620e4d5d9",
              "name": "Victor Cooper",
              "email_address": "victor@honchodesign.com",
              "personable_type": "User",
              "title": "Chief Strategist",
              "bio": "Don’t let your dreams be dreams",
              "location": "Chicago, IL",
              "created_at": "2026-01-31T02:29:28.365-06:00",
              "updated_at": "2026-01-31T02:29:32.599-06:00",
              "admin": true,
              "owner": true,
              "client": false,
              "employee": true,
              "time_zone": "America/Chicago",
              "avatar_url": "http://bc3-cdn.3.basecamp.localhost:4001/195539477/people/BAhpBMlkkT4=--5fe7b70fbee7a7f0e2e1e19df7579e5d880c753d/avatar?v=1",
              "company": {
                "id": 1033447817,
                "name": "Honcho Design"
              },
              "can_ping": true,
              "can_manage_projects": true,
              "can_manage_people": true,
              "can_access_timesheet": true,
              "can_access_hill_charts": true
            },
            "content": null
          },
          "creator": {
            "id": 1049715913,
            "attachable_sgid": "BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiK2dpZDovL2JjMy9QZXJzb24vMTA0OTcxNTkxMz9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg9hdHRhY2hhYmxlBjsAVA==--e627c45e6b34e08862da23906862412620e4d5d9",
            "name": "Victor Cooper",
            "email_address": "victor@honchodesign.com",
            "personable_type": "User",
            "title": "Chief Strategist",
            "bio": "Don’t let your dreams be dreams",
            "location": "Chicago, IL",
            "created_at": "2026-01-31T02:29:28.365-06:00",
            "updated_at": "2026-01-31T02:29:32.599-06:00",
            "admin": true,
            "owner": true,
            "client": false,
            "employee": true,
            "time_zone": "America/Chicago",
            "avatar_url": "http://bc3-cdn.3.basecamp.localhost:4001/195539477/people/BAhpBMlkkT4=--5fe7b70fbee7a7f0e2e1e19df7579e5d880c753d/avatar?v=1",
            "company": {
              "id": 1033447817,
              "name": "Honcho Design"
            },
            "can_ping": true,
            "can_manage_projects": true,
            "can_manage_people": true,
            "can_access_timesheet": true,
            "can_access_hill_charts": true
          }
        }
      },
      "response": {
        "error": "#<OpenSSL::SSL::SSLError: SSL_connect returned=1 errno=0 peeraddr=[2606:4700::6812:1a78]:443 state=error: certificate verify failed (unable to get certificate CRL)>"
      }
    },
    {
      "id": 627138733,
      "created_at": "2026-02-06T21:44:50.696Z",
      "request": {
        "headers": {
          "Content-Type": "application/json",
          "User-Agent": "Basecamp3 Webhook",
          "X-Request-Id": "befe9275-110a-4a4b-89a7-f32812079f32"
        },
        "body": {
          "id": 1071915753,
          "kind": "todo_uncompleted",
          "details": {},
          "created_at": "2026-02-06T15:44:49.092-06:00",
          "recording": {
            "id": 1069479576,
            "status": "active",
            "visible_to_clients": false,
            "created_at": "2026-01-15T01:20:00.000-06:00",
            "updated_at": "2026-02-06T15:44:49.091-06:00",
            "title": "Clear and simple UI",
            "inherits_status": true,
            "type": "Todo",
            "url": "https://3.basecampapi.com/195539477/buckets/2085958504/todos/1069479576.json",
            "app_url": "http://3.basecamp.localhost:4001/195539477/buckets/2085958504/todos/1069479576",
            "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiLmdpZDovL2JjMy9SZWNvcmRpbmcvMTA2OTQ3OTU3Nj9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg1yZWFkYWJsZQY7AFQ=--11a40c121978ed499b97e8c9ed0d3bfc8632df41.json",
            "subscription_url": "https://3.basecampapi.com/195539477/buckets/2085958504/recordings/1069479576/subscription.json",
            "position": 3,
            "parent": {
              "id": 1069479573,
              "title": "Strategy ideas",
              "type": "Todolist",
              "url": "https://3.basecampapi.com/195539477/buckets/2085958504/todolists/1069479573.json",
              "app_url": "http://3.basecamp.localhost:4001/195539477/buckets/2085958504/todolists/1069479573"
            },
            "bucket": {
              "id": 2085958504,
              "name": "The Leto Laptop",
              "type": "Project"
            },
            "creator": {
              "id": 1049715938,
              "attachable_sgid": "BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiK2dpZDovL2JjMy9QZXJzb24vMTA0OTcxNTkzOD9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg9hdHRhY2hhYmxlBjsAVA==--4ccc567a0a3b10e354bca909b704637b601f0b16",
              "name": "Annie Bryan",
              "email_address": "annie@honchodesign.com",
              "personable_type": "User",
              "title": "Central Markets Manager",
              "bio": "To open a store is easy, to keep it open is an art",
              "location": null,
              "created_at": "2026-01-31T02:29:42.795-06:00",
              "updated_at": "2026-01-31T02:29:42.795-06:00",
              "admin": false,
              "owner": false,
              "client": false,
              "employee": true,
              "time_zone": "America/Chicago",
              "avatar_url": "http://bc3-cdn.3.basecamp.localhost:4001/195539477/people/BAhpBOJkkT4=--732a71fbd28ec10d9bf4466abd3588a8bea40bdb/avatar?v=1",
              "company": {
                "id": 1033447817,
                "name": "Honcho Design"
              },
              "can_ping": true,
              "can_manage_projects": true,
              "can_manage_people": true,
              "can_access_timesheet": true,
              "can_access_hill_charts": true
            },
            "content": "Clear and simple UI"
          },
          "creator": {
            "id": 1049715930,
            "attachable_sgid": "BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiK2dpZDovL2JjMy9QZXJzb24vMTA0OTcxNTkzMD9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg9hdHRhY2hhYmxlBjsAVA==--322099b137f9e0b6bc944b5b9fe7a2692da94814",
            "name": "Sharon Bradford",
            "email_address": "sharon@honchodesign.com",
            "personable_type": "User",
            "title": "Principal Branding Administrator",
            "bio": null,
            "location": null,
            "created_at": "2026-01-31T02:29:40.859-06:00",
            "updated_at": "2026-01-31T02:29:40.859-06:00",
            "admin": false,
            "owner": false,
            "client": false,
            "employee": false,
            "time_zone": "America/Chicago",
            "avatar_url": "http://bc3-cdn.3.basecamp.localhost:4001/195539477/people/BAhpBNpkkT4=--789594e5e542ab99e467a51c9dec0a9035abc0e0/avatar?v=1",
            "can_ping": true,
            "can_manage_projects": true,
            "can_manage_people": true,
            "can_access_timesheet": true,
            "can_access_hill_charts": true
          }
        }
      },
      "response": {
        "error": "#<OpenSSL::SSL::SSLError: SSL_connect returned=1 errno=0 peeraddr=[2606:4700::6812:1b78]:443 state=error: certificate verify failed (unable to get certificate CRL)>"
      }
    },
    {
      "id": 627138732,
      "created_at": "2026-02-06T21:44:50.185Z",
      "request": {
        "headers": {
          "Content-Type": "application/json",
          "User-Agent": "Basecamp3 Webhook",
          "X-Request-Id": "5d5a155e-d5a2-44e5-abf9-ce062c11a0fc"
        },
        "body": {
          "id": 1071915752,
          "kind": "todo_completed",
          "details": {
            "notified_recipient_ids": [
              1049715938
            ]
          },
          "created_at": "2026-02-06T15:44:48.563-06:00",
          "recording": {
            "id": 1069479576,
            "status": "active",
            "visible_to_clients": false,
            "created_at": "2026-01-15T01:20:00.000-06:00",
            "updated_at": "2026-02-06T15:44:49.091-06:00",
            "title": "Clear and simple UI",
            "inherits_status": true,
            "type": "Todo",
            "url": "https://3.basecampapi.com/195539477/buckets/2085958504/todos/1069479576.json",
            "app_url": "http://3.basecamp.localhost:4001/195539477/buckets/2085958504/todos/1069479576",
            "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiLmdpZDovL2JjMy9SZWNvcmRpbmcvMTA2OTQ3OTU3Nj9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg1yZWFkYWJsZQY7AFQ=--11a40c121978ed499b97e8c9ed0d3bfc8632df41.json",
            "subscription_url": "https://3.basecampapi.com/195539477/buckets/2085958504/recordings/1069479576/subscription.json",
            "position": 3,
            "parent": {
              "id": 1069479573,
              "title": "Strategy ideas",
              "type": "Todolist",
              "url": "https://3.basecampapi.com/195539477/buckets/2085958504/todolists/1069479573.json",
              "app_url": "http://3.basecamp.localhost:4001/195539477/buckets/2085958504/todolists/1069479573"
            },
            "bucket": {
              "id": 2085958504,
              "name": "The Leto Laptop",
              "type": "Project"
            },
            "creator": {
              "id": 1049715938,
              "attachable_sgid": "BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiK2dpZDovL2JjMy9QZXJzb24vMTA0OTcxNTkzOD9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg9hdHRhY2hhYmxlBjsAVA==--4ccc567a0a3b10e354bca909b704637b601f0b16",
              "name": "Annie Bryan",
              "email_address": "annie@honchodesign.com",
              "personable_type": "User",
              "title": "Central Markets Manager",
              "bio": "To open a store is easy, to keep it open is an art",
              "location": null,
              "created_at": "2026-01-31T02:29:42.795-06:00",
              "updated_at": "2026-01-31T02:29:42.795-06:00",
              "admin": false,
              "owner": false,
              "client": false,
              "employee": true,
              "time_zone": "America/Chicago",
              "avatar_url": "http://bc3-cdn.3.basecamp.localhost:4001/195539477/people/BAhpBOJkkT4=--732a71fbd28ec10d9bf4466abd3588a8bea40bdb/avatar?v=1",
              "company": {
                "id": 1033447817,
                "name": "Honcho Design"
              },
              "can_ping": true,
              "can_manage_projects": true,
              "can_manage_people": true,
              "can_access_timesheet": true,
              "can_access_hill_charts": true
            },
            "content": "Clear and simple UI"
          },
          "creator": {
            "id": 1049715930,
            "attachable_sgid": "BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiK2dpZDovL2JjMy9QZXJzb24vMTA0OTcxNTkzMD9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg9hdHRhY2hhYmxlBjsAVA==--322099b137f9e0b6bc944b5b9fe7a2692da94814",
            "name": "Sharon Bradford",
            "email_address": "sharon@honchodesign.com",
            "personable_type": "User",
            "title": "Principal Branding Administrator",
            "bio": null,
            "location": null,
            "created_at": "2026-01-31T02:29:40.859-06:00",
            "updated_at": "2026-01-31T02:29:40.859-06:00",
            "admin": false,
            "owner": false,
            "client": false,
            "employee": false,
            "time_zone": "America/Chicago",
            "avatar_url": "http://bc3-cdn.3.basecamp.localhost:4001/195539477/people/BAhpBNpkkT4=--789594e5e542ab99e467a51c9dec0a9035abc0e0/avatar?v=1",
            "can_ping": true,
            "can_manage_projects": true,
            "can_manage_people": true,
            "can_access_timesheet": true,
            "can_access_hill_charts": true
          }
        }
      },
      "response": {
        "error": "#<OpenSSL::SSL::SSLError: SSL_connect returned=1 errno=0 peeraddr=[2606:4700::6812:1b78]:443 state=error: certificate verify failed (unable to get certificate CRL)>"
      }
    },
    {
      "id": 627138731,
      "created_at": "2026-02-05T17:52:20.374Z",
      "request": {
        "headers": {
          "Content-Type": "application/json",
          "User-Agent": "Basecamp3 Webhook",
          "X-Request-Id": "27aa4448-55f3-4c8b-bc38-68c7757d48ce"
        },
        "body": {
          "id": 1071915747,
          "kind": "timesheet_entry_deleted",
          "details": {
            "status_was": "active"
          },
          "created_at": "2026-02-05T11:52:19.257-06:00",
          "recording": {
            "id": 1069480006,
            "status": "deleted",
            "visible_to_clients": false,
            "created_at": "2026-02-05T11:52:17.927-06:00",
            "updated_at": "2026-02-05T11:52:19.247-06:00",
            "title": "Timesheet entry",
            "inherits_status": false,
            "type": "Timesheet::Entry",
            "url": "https://3.basecampapi.com/195539477/projects/2085958504/timesheet/entries/1069480006.json",
            "app_url": "http://3.basecamp.localhost:4001/195539477/projects/2085958504/timesheet/entries/1069480006",
            "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiLmdpZDovL2JjMy9SZWNvcmRpbmcvMTA2OTQ4MDAwNj9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg1yZWFkYWJsZQY7AFQ=--fb54ed5cfeb5d73c50db5363971d2b9d166c6996.json",
            "parent": {
              "id": 1069479406,
              "title": "We won Leto!",
              "type": "Message",
              "url": "https://3.basecampapi.com/195539477/buckets/2085958504/messages/1069479406.json",
              "app_url": "http://3.basecamp.localhost:4001/195539477/buckets/2085958504/messages/1069479406"
            },
            "bucket": {
              "id": 2085958504,
              "name": "The Leto Laptop",
              "type": "Project"
            },
            "creator": {
              "id": 1049715913,
              "attachable_sgid": "BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiK2dpZDovL2JjMy9QZXJzb24vMTA0OTcxNTkxMz9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg9hdHRhY2hhYmxlBjsAVA==--e627c45e6b34e08862da23906862412620e4d5d9",
              "name": "Victor Cooper",
              "email_address": "victor@honchodesign.com",
              "personable_type": "User",
              "title": "Chief Strategist",
              "bio": "Don’t let your dreams be dreams",
              "location": "Chicago, IL",
              "created_at": "2026-01-31T02:29:28.365-06:00",
              "updated_at": "2026-01-31T02:29:32.599-06:00",
              "admin": true,
              "owner": true,
              "client": false,
              "employee": true,
              "time_zone": "America/Chicago",
              "avatar_url": "http://bc3-cdn.3.basecamp.localhost:4001/195539477/people/BAhpBMlkkT4=--5fe7b70fbee7a7f0e2e1e19df7579e5d880c753d/avatar?v=1",
              "company": {
                "id": 1033447817,
                "name": "Honcho Design"
              },
              "can_ping": true,
              "can_manage_projects": true,
              "can_manage_people": true,
              "can_access_timesheet": true,
              "can_access_hill_charts": true
            },
            "content": null
          },
          "creator": {
            "id": 1049715913,
            "attachable_sgid": "BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiK2dpZDovL2JjMy9QZXJzb24vMTA0OTcxNTkxMz9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg9hdHRhY2hhYmxlBjsAVA==--e627c45e6b34e08862da23906862412620e4d5d9",
            "name": "Victor Cooper",
            "email_address": "victor@honchodesign.com",
            "personable_type": "User",
            "title": "Chief Strategist",
            "bio": "Don’t let your dreams be dreams",
            "location": "Chicago, IL",
            "created_at": "2026-01-31T02:29:28.365-06:00",
            "updated_at": "2026-01-31T02:29:32.599-06:00",
            "admin": true,
            "owner": true,
            "client": false,
            "employee": true,
            "time_zone": "America/Chicago",
            "avatar_url": "http://bc3-cdn.3.basecamp.localhost:4001/195539477/people/BAhpBMlkkT4=--5fe7b70fbee7a7f0e2e1e19df7579e5d880c753d/avatar?v=1",
            "company": {
              "id": 1033447817,
              "name": "Honcho Design"
            },
            "can_ping": true,
            "can_manage_projects": true,
            "can_manage_people": true,
            "can_access_timesheet": true,
            "can_access_hill_charts": true
          }
        }
      },
      "response": {
        "error": "#<OpenSSL::SSL::SSLError: SSL_connect returned=1 errno=0 peeraddr=[2606:4700::6812:1b78]:443 state=error: certificate verify failed (unable to get certificate CRL)>"
      }
    },
    {
      "id": 627138730,
      "created_at": "2026-02-05T17:52:19.990Z",
      "request": {
        "headers": {
          "Content-Type": "application/json",
          "User-Agent": "Basecamp3 Webhook",
          "X-Request-Id": "6a3ff982-313e-479b-9bcf-a1ab4e3e9ada"
        },
        "body": {
          "id": 1071915746,
          "kind": "timesheet_entry_hours_changed",
          "details": {},
          "created_at": "2026-02-05T11:52:18.837-06:00",
          "recording": {
            "id": 1069480006,
            "status": "deleted",
            "visible_to_clients": false,
            "created_at": "2026-02-05T11:52:17.927-06:00",
            "updated_at": "2026-02-05T11:52:19.247-06:00",
            "title": "Timesheet entry",
            "inherits_status": false,
            "type": "Timesheet::Entry",
            "url": "https://3.basecampapi.com/195539477/projects/2085958504/timesheet/entries/1069480006.json",
            "app_url": "http://3.basecamp.localhost:4001/195539477/projects/2085958504/timesheet/entries/1069480006",
            "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiLmdpZDovL2JjMy9SZWNvcmRpbmcvMTA2OTQ4MDAwNj9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg1yZWFkYWJsZQY7AFQ=--fb54ed5cfeb5d73c50db5363971d2b9d166c6996.json",
            "parent": {
              "id": 1069479406,
              "title": "We won Leto!",
              "type": "Message",
              "url": "https://3.basecampapi.com/195539477/buckets/2085958504/messages/1069479406.json",
              "app_url": "http://3.basecamp.localhost:4001/195539477/buckets/2085958504/messages/1069479406"
            },
            "bucket": {
              "id": 2085958504,
              "name": "The Leto Laptop",
              "type": "Project"
            },
            "creator": {
              "id": 1049715913,
              "attachable_sgid": "BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiK2dpZDovL2JjMy9QZXJzb24vMTA0OTcxNTkxMz9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg9hdHRhY2hhYmxlBjsAVA==--e627c45e6b34e08862da23906862412620e4d5d9",
              "name": "Victor Cooper",
              "email_address": "victor@honchodesign.com",
              "personable_type": "User",
              "title": "Chief Strategist",
              "bio": "Don’t let your dreams be dreams",
              "location": "Chicago, IL",
              "created_at": "2026-01-31T02:29:28.365-06:00",
              "updated_at": "2026-01-31T02:29:32.599-06:00",
              "admin": true,
              "owner": true,
              "client": false,
              "employee": true,
              "time_zone": "America/Chicago",
              "avatar_url": "http://bc3-cdn.3.basecamp.localhost:4001/195539477/people/BAhpBMlkkT4=--5fe7b70fbee7a7f0e2e1e19df7579e5d880c753d/avatar?v=1",
              "company": {
                "id": 1033447817,
                "name": "Honcho Design"
              },
              "can_ping": true,
              "can_manage_projects": true,
              "can_manage_people": true,
              "can_access_timesheet": true,
              "can_access_hill_charts": true
            },
            "content": null
          },
          "creator": {
            "id": 1049715913,
            "attachable_sgid": "BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiK2dpZDovL2JjMy9QZXJzb24vMTA0OTcxNTkxMz9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg9hdHRhY2hhYmxlBjsAVA==--e627c45e6b34e08862da23906862412620e4d5d9",
            "name": "Victor Cooper",
            "email_address": "victor@honchodesign.com",
            "personable_type": "User",
            "title": "Chief Strategist",
            "bio": "Don’t let your dreams be dreams",
            "location": "Chicago, IL",
            "created_at": "2026-01-31T02:29:28.365-06:00",
            "updated_at": "2026-01-31T02:29:32.599-06:00",
            "admin": true,
            "owner": true,
            "client": false,
            "employee": true,
            "time_zone": "America/Chicago",
            "avatar_url": "http://bc3-cdn.3.basecamp.localhost:4001/195539477/people/BAhpBMlkkT4=--5fe7b70fbee7a7f0e2e1e19df7579e5d880c753d/avatar?v=1",
            "company": {
              "id": 1033447817,
              "name": "Honcho Design"
            },
            "can_ping": true,
            "can_manage_projects": true,
            "can_manage_people": true,
            "can_access_timesheet": true,
            "can_access_hill_charts": true
          }
        }
      },
      "response": {
        "error": "#<OpenSSL::SSL::SSLError: SSL_connect returned=1 errno=0 peeraddr=[2606:4700::6812:1b78]:443 state=error: certificate verify failed (unable to get certificate CRL)>"
      }
    },
    {
      "id": 627138729,
      "created_at": "2026-02-05T17:52:19.966Z",
      "request": {
        "headers": {
          "Content-Type": "application/json",
          "User-Agent": "Basecamp3 Webhook",
          "X-Request-Id": "2b8a1e86-0390-4c62-96f3-a0d12dda5b2a"
        },
        "body": {
          "id": 1071915745,
          "kind": "timesheet_entry_description_changed",
          "details": {},
          "created_at": "2026-02-05T11:52:18.831-06:00",
          "recording": {
            "id": 1069480006,
            "status": "deleted",
            "visible_to_clients": false,
            "created_at": "2026-02-05T11:52:17.927-06:00",
            "updated_at": "2026-02-05T11:52:19.247-06:00",
            "title": "Timesheet entry",
            "inherits_status": false,
            "type": "Timesheet::Entry",
            "url": "https://3.basecampapi.com/195539477/projects/2085958504/timesheet/entries/1069480006.json",
            "app_url": "http://3.basecamp.localhost:4001/195539477/projects/2085958504/timesheet/entries/1069480006",
            "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiLmdpZDovL2JjMy9SZWNvcmRpbmcvMTA2OTQ4MDAwNj9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg1yZWFkYWJsZQY7AFQ=--fb54ed5cfeb5d73c50db5363971d2b9d166c6996.json",
            "parent": {
              "id": 1069479406,
              "title": "We won Leto!",
              "type": "Message",
              "url": "https://3.basecampapi.com/195539477/buckets/2085958504/messages/1069479406.json",
              "app_url": "http://3.basecamp.localhost:4001/195539477/buckets/2085958504/messages/1069479406"
            },
            "bucket": {
              "id": 2085958504,
              "name": "The Leto Laptop",
              "type": "Project"
            },
            "creator": {
              "id": 1049715913,
              "attachable_sgid": "BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiK2dpZDovL2JjMy9QZXJzb24vMTA0OTcxNTkxMz9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg9hdHRhY2hhYmxlBjsAVA==--e627c45e6b34e08862da23906862412620e4d5d9",
              "name": "Victor Cooper",
              "email_address": "victor@honchodesign.com",
              "personable_type": "User",
              "title": "Chief Strategist",
              "bio": "Don’t let your dreams be dreams",
              "location": "Chicago, IL",
              "created_at": "2026-01-31T02:29:28.365-06:00",
              "updated_at": "2026-01-31T02:29:32.599-06:00",
              "admin": true,
              "owner": true,
              "client": false,
              "employee": true,
              "time_zone": "America/Chicago",
              "avatar_url": "http://bc3-cdn.3.basecamp.localhost:4001/195539477/people/BAhpBMlkkT4=--5fe7b70fbee7a7f0e2e1e19df7579e5d880c753d/avatar?v=1",
              "company": {
                "id": 1033447817,
                "name": "Honcho Design"
              },
              "can_ping": true,
              "can_manage_projects": true,
              "can_manage_people": true,
              "can_access_timesheet": true,
              "can_access_hill_charts": true
            },
            "content": null
          },
          "creator": {
            "id": 1049715913,
            "attachable_sgid": "BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiK2dpZDovL2JjMy9QZXJzb24vMTA0OTcxNTkxMz9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg9hdHRhY2hhYmxlBjsAVA==--e627c45e6b34e08862da23906862412620e4d5d9",
            "name": "Victor Cooper",
            "email_address": "victor@honchodesign.com",
            "personable_type": "User",
            "title": "Chief Strategist",
            "bio": "Don’t let your dreams be dreams",
            "location": "Chicago, IL",
            "created_at": "2026-01-31T02:29:28.365-06:00",
            "updated_at": "2026-01-31T02:29:32.599-06:00",
            "admin": true,
            "owner": true,
            "client": false,
            "employee": true,
            "time_zone": "America/Chicago",
            "avatar_url": "http://bc3-cdn.3.basecamp.localhost:4001/195539477/people/BAhpBMlkkT4=--5fe7b70fbee7a7f0e2e1e19df7579e5d880c753d/avatar?v=1",
            "company": {
              "id": 1033447817,
              "name": "Honcho Design"
            },
            "can_ping": true,
            "can_manage_projects": true,
            "can_manage_people": true,
            "can_access_timesheet": true,
            "can_access_hill_charts": true
          }
        }
      },
      "response": {
        "error": "#<OpenSSL::SSL::SSLError: SSL_connect returned=1 errno=0 peeraddr=[2606:4700::6812:1b78]:443 state=error: certificate verify failed (unable to get certificate CRL)>"
      }
    },
    {
      "id": 627138728,
      "created_at": "2026-02-05T17:52:19.058Z",
      "request": {
        "headers": {
          "Content-Type": "application/json",
          "User-Agent": "Basecamp3 Webhook",
          "X-Request-Id": "fbef5c60-d35d-4205-9285-cd571fda706e"
        },
        "body": {
          "id": 1071915744,
          "kind": "timesheet_entry_created",
          "details": {},
          "created_at": "2026-02-05T11:52:17.943-06:00",
          "recording": {
            "id": 1069480006,
            "status": "active",
            "visible_to_clients": false,
            "created_at": "2026-02-05T11:52:17.927-06:00",
            "updated_at": "2026-02-05T11:52:18.813-06:00",
            "title": "Timesheet entry",
            "inherits_status": true,
            "type": "Timesheet::Entry",
            "url": "https://3.basecampapi.com/195539477/projects/2085958504/timesheet/entries/1069480006.json",
            "app_url": "http://3.basecamp.localhost:4001/195539477/projects/2085958504/timesheet/entries/1069480006",
            "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiLmdpZDovL2JjMy9SZWNvcmRpbmcvMTA2OTQ4MDAwNj9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg1yZWFkYWJsZQY7AFQ=--fb54ed5cfeb5d73c50db5363971d2b9d166c6996.json",
            "parent": {
              "id": 1069479406,
              "title": "We won Leto!",
              "type": "Message",
              "url": "https://3.basecampapi.com/195539477/buckets/2085958504/messages/1069479406.json",
              "app_url": "http://3.basecamp.localhost:4001/195539477/buckets/2085958504/messages/1069479406"
            },
            "bucket": {
              "id": 2085958504,
              "name": "The Leto Laptop",
              "type": "Project"
            },
            "creator": {
              "id": 1049715913,
              "attachable_sgid": "BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiK2dpZDovL2JjMy9QZXJzb24vMTA0OTcxNTkxMz9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg9hdHRhY2hhYmxlBjsAVA==--e627c45e6b34e08862da23906862412620e4d5d9",
              "name": "Victor Cooper",
              "email_address": "victor@honchodesign.com",
              "personable_type": "User",
              "title": "Chief Strategist",
              "bio": "Don’t let your dreams be dreams",
              "location": "Chicago, IL",
              "created_at": "2026-01-31T02:29:28.365-06:00",
              "updated_at": "2026-01-31T02:29:32.599-06:00",
              "admin": true,
              "owner": true,
              "client": false,
              "employee": true,
              "time_zone": "America/Chicago",
              "avatar_url": "http://bc3-cdn.3.basecamp.localhost:4001/195539477/people/BAhpBMlkkT4=--5fe7b70fbee7a7f0e2e1e19df7579e5d880c753d/avatar?v=1",
              "company": {
                "id": 1033447817,
                "name": "Honcho Design"
              },
              "can_ping": true,
              "can_manage_projects": true,
              "can_manage_people": true,
              "can_access_timesheet": true,
              "can_access_hill_charts": true
            },
            "content": null
          },
          "creator": {
            "id": 1049715913,
            "attachable_sgid": "BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiK2dpZDovL2JjMy9QZXJzb24vMTA0OTcxNTkxMz9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg9hdHRhY2hhYmxlBjsAVA==--e627c45e6b34e08862da23906862412620e4d5d9",
            "name": "Victor Cooper",
            "email_address": "victor@honchodesign.com",
            "personable_type": "User",
            "title": "Chief Strategist",
            "bio": "Don’t let your dreams be dreams",
            "location": "Chicago, IL",
            "created_at": "2026-01-31T02:29:28.365-06:00",
            "updated_at": "2026-01-31T02:29:32.599-06:00",
            "admin": true,
            "owner": true,
            "client": false,
            "employee": true,
            "time_zone": "America/Chicago",
            "avatar_url": "http://bc3-cdn.3.basecamp.localhost:4001/195539477/people/BAhpBMlkkT4=--5fe7b70fbee7a7f0e2e1e19df7579e5d880c753d/avatar?v=1",
            "company": {
              "id": 1033447817,
              "name": "Honcho Design"
            },
            "can_ping": true,
            "can_manage_projects": true,
            "can_manage_people": true,
            "can_access_timesheet": true,
            "can_access_hill_charts": true
          }
        }
      },
      "response": {
        "error": "#<OpenSSL::SSL::SSLError: SSL_connect returned=1 errno=0 peeraddr=[2606:4700::6812:1b78]:443 state=error: certificate verify failed (unable to get certificate CRL)>"
      }
    },
    {
      "id": 627138727,
      "created_at": "2026-02-05T17:51:57.514Z",
      "request": {
        "headers": {
          "Content-Type": "application/json",
          "User-Agent": "Basecamp3 Webhook",
          "X-Request-Id": "7addf072-3318-4400-8171-f657aac36bf9"
        },
        "body": {
          "id": 1071915743,
          "kind": "timesheet_entry_deleted",
          "details": {
            "status_was": "active"
          },
          "created_at": "2026-02-05T11:51:56.397-06:00",
          "recording": {
            "id": 1069480005,
            "status": "deleted",
            "visible_to_clients": false,
            "created_at": "2026-02-05T11:51:54.954-06:00",
            "updated_at": "2026-02-05T11:51:56.345-06:00",
            "title": "Timesheet entry",
            "inherits_status": false,
            "type": "Timesheet::Entry",
            "url": "https://3.basecampapi.com/195539477/projects/2085958504/timesheet/entries/1069480005.json",
            "app_url": "http://3.basecamp.localhost:4001/195539477/projects/2085958504/timesheet/entries/1069480005",
            "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiLmdpZDovL2JjMy9SZWNvcmRpbmcvMTA2OTQ4MDAwNT9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg1yZWFkYWJsZQY7AFQ=--46b319a6552eaa798919835a57a19a2350f6c363.json",
            "parent": {
              "id": 1069479406,
              "title": "We won Leto!",
              "type": "Message",
              "url": "https://3.basecampapi.com/195539477/buckets/2085958504/messages/1069479406.json",
              "app_url": "http://3.basecamp.localhost:4001/195539477/buckets/2085958504/messages/1069479406"
            },
            "bucket": {
              "id": 2085958504,
              "name": "The Leto Laptop",
              "type": "Project"
            },
            "creator": {
              "id": 1049715913,
              "attachable_sgid": "BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiK2dpZDovL2JjMy9QZXJzb24vMTA0OTcxNTkxMz9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg9hdHRhY2hhYmxlBjsAVA==--e627c45e6b34e08862da23906862412620e4d5d9",
              "name": "Victor Cooper",
              "email_address": "victor@honchodesign.com",
              "personable_type": "User",
              "title": "Chief Strategist",
              "bio": "Don’t let your dreams be dreams",
              "location": "Chicago, IL",
              "created_at": "2026-01-31T02:29:28.365-06:00",
              "updated_at": "2026-01-31T02:29:32.599-06:00",
              "admin": true,
              "owner": true,
              "client": false,
              "employee": true,
              "time_zone": "America/Chicago",
              "avatar_url": "http://bc3-cdn.3.basecamp.localhost:4001/195539477/people/BAhpBMlkkT4=--5fe7b70fbee7a7f0e2e1e19df7579e5d880c753d/avatar?v=1",
              "company": {
                "id": 1033447817,
                "name": "Honcho Design"
              },
              "can_ping": true,
              "can_manage_projects": true,
              "can_manage_people": true,
              "can_access_timesheet": true,
              "can_access_hill_charts": true
            },
            "content": null
          },
          "creator": {
            "id": 1049715913,
            "attachable_sgid": "BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiK2dpZDovL2JjMy9QZXJzb24vMTA0OTcxNTkxMz9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg9hdHRhY2hhYmxlBjsAVA==--e627c45e6b34e08862da23906862412620e4d5d9",
            "name": "Victor Cooper",
            "email_address": "victor@honchodesign.com",
            "personable_type": "User",
            "title": "Chief Strategist",
            "bio": "Don’t let your dreams be dreams",
            "location": "Chicago, IL",
            "created_at": "2026-01-31T02:29:28.365-06:00",
            "updated_at": "2026-01-31T02:29:32.599-06:00",
            "admin": true,
            "owner": true,
            "client": false,
            "employee": true,
            "time_zone": "America/Chicago",
            "avatar_url": "http://bc3-cdn.3.basecamp.localhost:4001/195539477/people/BAhpBMlkkT4=--5fe7b70fbee7a7f0e2e1e19df7579e5d880c753d/avatar?v=1",
            "company": {
              "id": 1033447817,
              "name": "Honcho Design"
            },
            "can_ping": true,
            "can_manage_projects": true,
            "can_manage_people": true,
            "can_access_timesheet": true,
            "can_access_hill_charts": true
          }
        }
      },
      "response": {
        "error": "#<OpenSSL::SSL::SSLError: SSL_connect returned=1 errno=0 peeraddr=[2606:4700::6812:1b78]:443 state=error: certificate verify failed (unable to get certificate CRL)>"
      }
    },
    {
      "id": 627138726,
      "created_at": "2026-02-05T17:51:56.998Z",
      "request": {
        "headers": {
          "Content-Type": "application/json",
          "User-Agent": "Basecamp3 Webhook",
          "X-Request-Id": "b3421c1e-5516-4f9a-a1ba-16220f98690c"
        },
        "body": {
          "id": 1071915742,
          "kind": "timesheet_entry_hours_changed",
          "details": {},
          "created_at": "2026-02-05T11:51:55.907-06:00",
          "recording": {
            "id": 1069480005,
            "status": "deleted",
            "visible_to_clients": false,
            "created_at": "2026-02-05T11:51:54.954-06:00",
            "updated_at": "2026-02-05T11:51:56.345-06:00",
            "title": "Timesheet entry",
            "inherits_status": false,
            "type": "Timesheet::Entry",
            "url": "https://3.basecampapi.com/195539477/projects/2085958504/timesheet/entries/1069480005.json",
            "app_url": "http://3.basecamp.localhost:4001/195539477/projects/2085958504/timesheet/entries/1069480005",
            "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiLmdpZDovL2JjMy9SZWNvcmRpbmcvMTA2OTQ4MDAwNT9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg1yZWFkYWJsZQY7AFQ=--46b319a6552eaa798919835a57a19a2350f6c363.json",
            "parent": {
              "id": 1069479406,
              "title": "We won Leto!",
              "type": "Message",
              "url": "https://3.basecampapi.com/195539477/buckets/2085958504/messages/1069479406.json",
              "app_url": "http://3.basecamp.localhost:4001/195539477/buckets/2085958504/messages/1069479406"
            },
            "bucket": {
              "id": 2085958504,
              "name": "The Leto Laptop",
              "type": "Project"
            },
            "creator": {
              "id": 1049715913,
              "attachable_sgid": "BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiK2dpZDovL2JjMy9QZXJzb24vMTA0OTcxNTkxMz9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg9hdHRhY2hhYmxlBjsAVA==--e627c45e6b34e08862da23906862412620e4d5d9",
              "name": "Victor Cooper",
              "email_address": "victor@honchodesign.com",
              "personable_type": "User",
              "title": "Chief Strategist",
              "bio": "Don’t let your dreams be dreams",
              "location": "Chicago, IL",
              "created_at": "2026-01-31T02:29:28.365-06:00",
              "updated_at": "2026-01-31T02:29:32.599-06:00",
              "admin": true,
              "owner": true,
              "client": false,
              "employee": true,
              "time_zone": "America/Chicago",
              "avatar_url": "http://bc3-cdn.3.basecamp.localhost:4001/195539477/people/BAhpBMlkkT4=--5fe7b70fbee7a7f0e2e1e19df7579e5d880c753d/avatar?v=1",
              "company": {
                "id": 1033447817,
                "name": "Honcho Design"
              },
              "can_ping": true,
              "can_manage_projects": true,
              "can_manage_people": true,
              "can_access_timesheet": true,
              "can_access_hill_charts": true
            },
            "content": null
          },
          "creator": {
            "id": 1049715913,
            "attachable_sgid": "BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiK2dpZDovL2JjMy9QZXJzb24vMTA0OTcxNTkxMz9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg9hdHRhY2hhYmxlBjsAVA==--e627c45e6b34e08862da23906862412620e4d5d9",
            "name": "Victor Cooper",
            "email_address": "victor@honchodesign.com",
            "personable_type": "User",
            "title": "Chief Strategist",
            "bio": "Don’t let your dreams be dreams",
            "location": "Chicago, IL",
            "created_at": "2026-01-31T02:29:28.365-06:00",
            "updated_at": "2026-01-31T02:29:32.599-06:00",
            "admin": true,
            "owner": true,
            "client": false,
            "employee": true,
            "time_zone": "America/Chicago",
            "avatar_url": "http://bc3-cdn.3.basecamp.localhost:4001/195539477/people/BAhpBMlkkT4=--5fe7b70fbee7a7f0e2e1e19df7579e5d880c753d/avatar?v=1",
            "company": {
              "id": 1033447817,
              "name": "Honcho Design"
            },
            "can_ping": true,
            "can_manage_projects": true,
            "can_manage_people": true,
            "can_access_timesheet": true,
            "can_access_hill_charts": true
          }
        }
      },
      "response": {
        "error": "#<OpenSSL::SSL::SSLError: SSL_connect returned=1 errno=0 peeraddr=[2606:4700::6812:1b78]:443 state=error: certificate verify failed (unable to get certificate CRL)>"
      }
    },
    {
      "id": 627138725,
      "created_at": "2026-02-05T17:51:56.987Z",
      "request": {
        "headers": {
          "Content-Type": "application/json",
          "User-Agent": "Basecamp3 Webhook",
          "X-Request-Id": "d11f05e4-17cd-46ef-b299-74891285c1ea"
        },
        "body": {
          "id": 1071915741,
          "kind": "timesheet_entry_description_changed",
          "details": {},
          "created_at": "2026-02-05T11:51:55.895-06:00",
          "recording": {
            "id": 1069480005,
            "status": "deleted",
            "visible_to_clients": false,
            "created_at": "2026-02-05T11:51:54.954-06:00",
            "updated_at": "2026-02-05T11:51:56.345-06:00",
            "title": "Timesheet entry",
            "inherits_status": false,
            "type": "Timesheet::Entry",
            "url": "https://3.basecampapi.com/195539477/projects/2085958504/timesheet/entries/1069480005.json",
            "app_url": "http://3.basecamp.localhost:4001/195539477/projects/2085958504/timesheet/entries/1069480005",
            "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiLmdpZDovL2JjMy9SZWNvcmRpbmcvMTA2OTQ4MDAwNT9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg1yZWFkYWJsZQY7AFQ=--46b319a6552eaa798919835a57a19a2350f6c363.json",
            "parent": {
              "id": 1069479406,
              "title": "We won Leto!",
              "type": "Message",
              "url": "https://3.basecampapi.com/195539477/buckets/2085958504/messages/1069479406.json",
              "app_url": "http://3.basecamp.localhost:4001/195539477/buckets/2085958504/messages/1069479406"
            },
            "bucket": {
              "id": 2085958504,
              "name": "The Leto Laptop",
              "type": "Project"
            },
            "creator": {
              "id": 1049715913,
              "attachable_sgid": "BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiK2dpZDovL2JjMy9QZXJzb24vMTA0OTcxNTkxMz9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg9hdHRhY2hhYmxlBjsAVA==--e627c45e6b34e08862da23906862412620e4d5d9",
              "name": "Victor Cooper",
              "email_address": "victor@honchodesign.com",
              "personable_type": "User",
              "title": "Chief Strategist",
              "bio": "Don’t let your dreams be dreams",
              "location": "Chicago, IL",
              "created_at": "2026-01-31T02:29:28.365-06:00",
              "updated_at": "2026-01-31T02:29:32.599-06:00",
              "admin": true,
              "owner": true,
              "client": false,
              "employee": true,
              "time_zone": "America/Chicago",
              "avatar_url": "http://bc3-cdn.3.basecamp.localhost:4001/195539477/people/BAhpBMlkkT4=--5fe7b70fbee7a7f0e2e1e19df7579e5d880c753d/avatar?v=1",
              "company": {
                "id": 1033447817,
                "name": "Honcho Design"
              },
              "can_ping": true,
              "can_manage_projects": true,
              "can_manage_people": true,
              "can_access_timesheet": true,
              "can_access_hill_charts": true
            },
            "content": null
          },
          "creator": {
            "id": 1049715913,
            "attachable_sgid": "BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiK2dpZDovL2JjMy9QZXJzb24vMTA0OTcxNTkxMz9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg9hdHRhY2hhYmxlBjsAVA==--e627c45e6b34e08862da23906862412620e4d5d9",
            "name": "Victor Cooper",
            "email_address": "victor@honchodesign.com",
            "personable_type": "User",
            "title": "Chief Strategist",
            "bio": "Don’t let your dreams be dreams",
            "location": "Chicago, IL",
            "created_at": "2026-01-31T02:29:28.365-06:00",
            "updated_at": "2026-01-31T02:29:32.599-06:00",
            "admin": true,
            "owner": true,
            "client": false,
            "employee": true,
            "time_zone": "America/Chicago",
            "avatar_url": "http://bc3-cdn.3.basecamp.localhost:4001/195539477/people/BAhpBMlkkT4=--5fe7b70fbee7a7f0e2e1e19df7579e5d880c753d/avatar?v=1",
            "company": {
              "id": 1033447817,
              "name": "Honcho Design"
            },
            "can_ping": true,
            "can_manage_projects": true,
            "can_manage_people": true,
            "can_access_timesheet": true,
            "can_access_hill_charts": true
          }
        }
      },
      "response": {
        "error": "#<OpenSSL::SSL::SSLError: SSL_connect returned=1 errno=0 peeraddr=[2606:4700::6812:1b78]:443 state=error: certificate verify failed (unable to get certificate CRL)>"
      }
    },
    {
      "id": 627138724,
      "created_at": "2026-02-05T17:51:56.138Z",
      "request": {
        "headers": {
          "Content-Type": "application/json",
          "User-Agent": "Basecamp3 Webhook",
          "X-Request-Id": "541c6b73-d6e8-41a0-bb0a-3311e9163539"
        },
        "body": {
          "id": 1071915740,
          "kind": "timesheet_entry_created",
          "details": {},
          "created_at": "2026-02-05T11:51:54.977-06:00",
          "recording": {
            "id": 1069480005,
            "status": "active",
            "visible_to_clients": false,
            "created_at": "2026-02-05T11:51:54.954-06:00",
            "updated_at": "2026-02-05T11:51:55.885-06:00",
            "title": "Timesheet entry",
            "inherits_status": true,
            "type": "Timesheet::Entry",
            "url": "https://3.basecampapi.com/195539477/projects/2085958504/timesheet/entries/1069480005.json",
            "app_url": "http://3.basecamp.localhost:4001/195539477/projects/2085958504/timesheet/entries/1069480005",
            "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiLmdpZDovL2JjMy9SZWNvcmRpbmcvMTA2OTQ4MDAwNT9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg1yZWFkYWJsZQY7AFQ=--46b319a6552eaa798919835a57a19a2350f6c363.json",
            "parent": {
              "id": 1069479406,
              "title": "We won Leto!",
              "type": "Message",
              "url": "https://3.basecampapi.com/195539477/buckets/2085958504/messages/1069479406.json",
              "app_url": "http://3.basecamp.localhost:4001/195539477/buckets/2085958504/messages/1069479406"
            },
            "bucket": {
              "id": 2085958504,
              "name": "The Leto Laptop",
              "type": "Project"
            },
            "creator": {
              "id": 1049715913,
              "attachable_sgid": "BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiK2dpZDovL2JjMy9QZXJzb24vMTA0OTcxNTkxMz9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg9hdHRhY2hhYmxlBjsAVA==--e627c45e6b34e08862da23906862412620e4d5d9",
              "name": "Victor Cooper",
              "email_address": "victor@honchodesign.com",
              "personable_type": "User",
              "title": "Chief Strategist",
              "bio": "Don’t let your dreams be dreams",
              "location": "Chicago, IL",
              "created_at": "2026-01-31T02:29:28.365-06:00",
              "updated_at": "2026-01-31T02:29:32.599-06:00",
              "admin": true,
              "owner": true,
              "client": false,
              "employee": true,
              "time_zone": "America/Chicago",
              "avatar_url": "http://bc3-cdn.3.basecamp.localhost:4001/195539477/people/BAhpBMlkkT4=--5fe7b70fbee7a7f0e2e1e19df7579e5d880c753d/avatar?v=1",
              "company": {
                "id": 1033447817,
                "name": "Honcho Design"
              },
              "can_ping": true,
              "can_manage_projects": true,
              "can_manage_people": true,
              "can_access_timesheet": true,
              "can_access_hill_charts": true
            },
            "content": null
          },
          "creator": {
            "id": 1049715913,
            "attachable_sgid": "BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiK2dpZDovL2JjMy9QZXJzb24vMTA0OTcxNTkxMz9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg9hdHRhY2hhYmxlBjsAVA==--e627c45e6b34e08862da23906862412620e4d5d9",
            "name": "Victor Cooper",
            "email_address": "victor@honchodesign.com",
            "personable_type": "User",
            "title": "Chief Strategist",
            "bio": "Don’t let your dreams be dreams",
            "location": "Chicago, IL",
            "created_at": "2026-01-31T02:29:28.365-06:00",
            "updated_at": "2026-01-31T02:29:32.599-06:00",
            "admin": true,
            "owner": true,
            "client": false,
            "employee": true,
            "time_zone": "America/Chicago",
            "avatar_url": "http://bc3-cdn.3.basecamp.localhost:4001/195539477/people/BAhpBMlkkT4=--5fe7b70fbee7a7f0e2e1e19df7579e5d880c753d/avatar?v=1",
            "company": {
              "id": 1033447817,
              "name": "Honcho Design"
            },
            "can_ping": true,
            "can_manage_projects": true,
            "can_manage_people": true,
            "can_access_timesheet": true,
            "can_access_hill_charts": true
          }
        }
      },
      "response": {
        "error": "#<OpenSSL::SSL::SSLError: SSL_connect returned=1 errno=0 peeraddr=[2606:4700::6812:1b78]:443 state=error: certificate verify failed (unable to get certificate CRL)>"
      }
    }
  ]
}
```
<!-- END GET /webhooks/3.json -->
###### Copy as cURL

```shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/webhooks/3.json
```

Create a webhook
----------------

* `POST /buckets/1/webhooks.json` creates a webhook in the project with an ID of `1`.

**Required parameters**: `payload_url` for the HTTPS url that Basecamp should call.
_Optional parameters_: `types` as an array of types, options given in the introduction.

This endpoint will return `201 Created` with the current JSON representation of the webhook if the creation was a success. See the [Get a webhook](#get-a-webhook) endpoint for more info on the payload.

This endpoint will return `400 Bad Request` if the payload URL is not a valid HTTPS URL or other validation errors occur. It will return `507 Insufficient Storage` if the account has reached its webhook limit.

###### Example JSON Request

```json
{
  "payload_url": "https://example.com/endpoint",
  "types": [ "Todo", "Todolist" ]
}
```

###### Copy as cURL

```shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -H "Content-Type: application/json" \
  -d '{"payload_url":"https://example.com/endpoint","types":["Todo","Todolist"]}' \
  https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/webhooks.json
```

Update a webhook
----------------

* `PUT /webhooks/3.json` allows changing the payload url and types of the webhook with an ID of `3`.

**Required parameters**: `payload_url` for the HTTPS url that Basecamp will call.
_Optional parameters_: `types` as an array of types, options given in the introduction. `active` as a boolean whether this webhook should be matching.

This endpoint will return `200 OK` with the current JSON representation of the webhook if the update was a success. See the [Get a webhook](#get-a-webhook) endpoint for more info on the payload.

This endpoint will return `400 Bad Request` if the payload URL is not a valid HTTPS URL or other validation errors occur.

###### Example JSON Request

```json
{
  "payload_url": "https://example.com/endpoint",
  "types": ["Todo", "Todolist"],
  "active": true
}
```

###### Copy as cURL

```shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -H "Content-Type: application/json" \
  -d '{"payload_url":"https://example.com/endpoint","types":["Todo","Todolist"],"active":true}' -X PUT \
  https://3.basecampapi.com/$ACCOUNT_ID/webhooks/3.json
```

Destroy a webhook
-----------------

* `DELETE /webhooks/3.json` will delete the webhook with an ID of `3`.

This endpoint will return `204 No Content` if the destroy was a success.

###### Copy as cURL

```shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -X DELETE \
  https://3.basecampapi.com/$ACCOUNT_ID/webhooks/3.json
```


Legacy project-scoped routes
-----------------------------

The following project-scoped routes are still supported and will remain available, but flat routes above are the canonical form for new integrations.

* `GET /buckets/1/webhooks/3.json` → [Get a webhook](#get-a-webhook)
* `PUT /buckets/1/webhooks/3.json` → [Update a webhook](#update-a-webhook)
* `DELETE /buckets/1/webhooks/3.json` → [Destroy a webhook](#destroy-a-webhook)

[1]: https://github.com/basecamp/bc3-api/blob/master/sections/chatbots.md
[2]: https://github.com/basecamp/bc3-api/blob/master/sections/todos.md#get-a-to-do
