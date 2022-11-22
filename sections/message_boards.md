Message Boards
==============

All messages under a project are children of a Message Board resource.

Endpoints:

- [Get message board](#get-message-board)


Get message board
-----------------

* `GET /buckets/1/message_boards/2.json` will return the message board for the project with an ID of `1` and the message board ID of `2`.

To get the message board ID for a project, see the [Get a project][1] endpoint's `dock` payload. To retrieve its messages, see the [Get messages][2] endpoint.

###### Example JSON Response
<!-- START GET /buckets/1/message_boards/2.json -->
```json
{
  "id": 1069479338,
  "status": "active",
  "visible_to_clients": false,
  "created_at": "2022-11-22T08:23:58.186Z",
  "updated_at": "2022-11-22T17:53:36.294Z",
  "title": "Message Board",
  "inherits_status": true,
  "type": "Message::Board",
  "url": "https://3.basecampapi.com/195539477/buckets/2085958499/message_boards/1069479338.json",
  "app_url": "https://3.basecamp.com/195539477/buckets/2085958499/message_boards/1069479338",
  "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7CEkiCGdpZAY6BkVUSSIuZ2lkOi8vYmMzL1JlY29yZGluZy8xMDY5NDc5MzM4P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg1yZWFkYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--b1fc49d3c71b863b1635683193ce19eb723e7674.json",
  "position": 1,
  "bucket": {
    "id": 2085958499,
    "name": "The Leto Laptop",
    "type": "Project"
  },
  "creator": {
    "id": 1049715914,
    "attachable_sgid": "BAh7CEkiCGdpZAY6BkVUSSIrZ2lkOi8vYmMzL1BlcnNvbi8xMDQ5NzE1OTE0P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg9hdHRhY2hhYmxlBjsAVEkiD2V4cGlyZXNfYXQGOwBUMA==--ff006accb6e013cca785190fa38f42c091d24f1e",
    "name": "Victor Cooper",
    "email_address": "victor@honchodesign.com",
    "personable_type": "User",
    "title": "Chief Strategist",
    "bio": "Don’t let your dreams be dreams",
    "location": "Chicago, IL",
    "created_at": "2022-11-22T08:23:21.732Z",
    "updated_at": "2022-11-22T08:23:21.904Z",
    "admin": true,
    "owner": true,
    "client": false,
    "employee": true,
    "time_zone": "America/Chicago",
    "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBMpkkT4=--5520caeec1845b5090bbfc993ffe8eca8d138e14/avatar?v=1",
    "company": {
      "id": 1033447817,
      "name": "Honcho Design"
    },
    "can_manage_projects": true,
    "can_manage_people": true
  },
  "messages_count": 9,
  "messages_url": "https://3.basecampapi.com/195539477/buckets/2085958499/message_boards/1069479338/messages.json",
  "app_messages_url": "https://3.basecamp.com/195539477/buckets/2085958499/message_boards/1069479338/messages"
}
```
<!-- END GET /buckets/1/message_boards/2.json -->
###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/message_boards/2.json
```


[1]: https://github.com/basecamp/bc3-api/blob/master/sections/projects.md#get-a-project
[2]: https://github.com/basecamp/bc3-api/blob/master/sections/messages.md#get-messages
[3]: https://github.com/basecamp/bc3-api/blob/master/sections/recordings.md#trash-a-recording
