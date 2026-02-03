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
  "id": 1069479392,
  "status": "active",
  "visible_to_clients": false,
  "created_at": "2026-01-31T08:32:04.229Z",
  "updated_at": "2026-01-31T08:37:37.895Z",
  "title": "Message Board",
  "inherits_status": true,
  "type": "Message::Board",
  "url": "https://3.basecampapi.com/195539477/buckets/2085958504/message_boards/1069479392.json",
  "app_url": "https://3.basecamp.com/195539477/buckets/2085958504/message_boards/1069479392",
  "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiLmdpZDovL2JjMy9SZWNvcmRpbmcvMTA2OTQ3OTM5Mj9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg1yZWFkYWJsZQY7AFQ=--5b36411ed69f8efd9f978730efb236662fbb4bf0.json",
  "position": 1,
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
    "created_at": "2026-01-31T08:29:28.365Z",
    "updated_at": "2026-01-31T08:29:32.599Z",
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
  "messages_count": 9,
  "messages_url": "https://3.basecampapi.com/195539477/buckets/2085958504/message_boards/1069479392/messages.json",
  "app_messages_url": "https://3.basecamp.com/195539477/buckets/2085958504/message_boards/1069479392/messages"
}
```
<!-- END GET /buckets/1/message_boards/2.json -->
###### Copy as cURL

```shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/message_boards/2.json
```


[1]: https://github.com/basecamp/bc3-api/blob/master/sections/projects.md#get-a-project
[2]: https://github.com/basecamp/bc3-api/blob/master/sections/messages.md#get-messages
[3]: https://github.com/basecamp/bc3-api/blob/master/sections/recordings.md#trash-a-recording
