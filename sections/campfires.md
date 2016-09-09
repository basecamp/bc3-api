Campfires
=========

Endpoints:

- [Get Campfires](#get-campfires)
- [Get a Campfire](#get-a-campfire)
- [Get Campfire lines](#get-campfire-lines)
- [Get a Campfire line](#get-a-campfire-line)
- [Create a Campfire line](#create-a-campfire-line)

Get Campfires
-------------

* `GET /chats.json` will return a [paginated list][pagination] of all active Campfires visible to the current user.

###### Example JSON Response
<!-- START GET /chats.json -->
```json
[
  {
    "id": 9007199254741043,
    "status": "active",
    "created_at": "2016-04-22T18:23:41.933Z",
    "updated_at": "2016-07-19T16:46:50.302Z",
    "type": "Chat::Transcript",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958496/chats/9007199254741043.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958496/chats/9007199254741043",
    "bucket": {
      "id": 2085958496,
      "name": "Honcho Design Newsroom",
      "type": "Project"
    },
    "creator": {
      "id": 1007299143,
      "attachable_sgid": "BAh7CEkiCGdpZAY6BkVUSSIrZ2lkOi8vYmMzL1BlcnNvbi8xMDA3Mjk5MTQzP2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg9hdHRhY2hhYmxlBjsAVEkiD2V4cGlyZXNfYXQGOwBUMA==--919d2c8b11ff403eefcab9db42dd26846d0c3102",
      "name": "Victor Cooper",
      "email_address": "victor@honchodesign.com",
      "personable_type": "User",
      "title": null,
      "created_at": "2016-07-19T16:46:34.338Z",
      "updated_at": "2016-07-19T16:46:38.579Z",
      "admin": true,
      "owner": true,
      "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBEcqCjw=--c632b967cec296b87363a697a67a87f9cc1e5b45/avatar-64-x4",
      "company": {
        "id": 1033447817,
        "name": "Honcho Design"
      }
    },
    "topic": "Campfire",
    "lines_url": "https://3.basecampapi.com/195539477/buckets/2085958496/chats/9007199254741043/lines.json"
  }
]
```
<!-- END GET /chats.json -->
###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/chats.json
```

Get a Campfire
--------------

* `GET /buckets/1/chats/2.json` will return the Campfire with ID `2` in the Basecamp with ID `1`.

###### Example JSON Response
<!-- START GET /buckets/1/chats/2.json -->
```json
{
  "id": 9007199254741043,
  "status": "active",
  "created_at": "2016-04-22T18:23:41.933Z",
  "updated_at": "2016-07-19T16:46:50.302Z",
  "type": "Chat::Transcript",
  "url": "https://3.basecampapi.com/195539477/buckets/2085958496/chats/9007199254741043.json",
  "app_url": "https://3.basecamp.com/195539477/buckets/2085958496/chats/9007199254741043",
  "bucket": {
    "id": 2085958496,
    "name": "Honcho Design Newsroom",
    "type": "Project"
  },
  "creator": {
    "id": 1007299143,
    "attachable_sgid": "BAh7CEkiCGdpZAY6BkVUSSIrZ2lkOi8vYmMzL1BlcnNvbi8xMDA3Mjk5MTQzP2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg9hdHRhY2hhYmxlBjsAVEkiD2V4cGlyZXNfYXQGOwBUMA==--919d2c8b11ff403eefcab9db42dd26846d0c3102",
    "name": "Victor Cooper",
    "email_address": "victor@honchodesign.com",
    "personable_type": "User",
    "title": "Chief Strategist",
    "bio": "Don't let your dreams be dreams",
    "created_at": "2016-09-09T22:58:27.559Z",
    "updated_at": "2016-09-09T22:58:31.296Z",
    "admin": true,
    "owner": true,
    "time_zone": "America/Chicago",
    "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBEcqCjw=--c632b967cec296b87363a697a67a87f9cc1e5b45/avatar-64-x4",
    "company": {
      "id": 1033447817,
      "name": "Honcho Design"
    }
  },
  "topic": "Campfire",
  "lines_url": "https://3.basecampapi.com/195539477/buckets/2085958496/chats/9007199254741043/lines.json"
}
```
<!-- END GET /buckets/1/chats/2.json -->
###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/chats/2.json
```

Get Campfire lines
------------------

* `GET /buckets/1/chats/2/lines.json` will return a [paginated list][pagination] of Campfire lines of the Campfire with ID `2` in the Basecamp with ID `1`.

###### Example JSON Response
<!-- START GET /buckets/1/chats/2/lines.json -->
```json
[
  {
    "id": 9007199254741125,
    "status": "active",
    "created_at": "2016-04-25T21:30:41.933Z",
    "updated_at": "2016-04-25T21:30:41.933Z",
    "type": "Chat::Lines::Text",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958496/chats/9007199254741043/lines/9007199254741125.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958496/chats/9007199254741043@9007199254741125",
    "parent": {
      "id": 9007199254741043,
      "title": "Campfire",
      "type": "Chat::Transcript",
      "url": "https://3.basecampapi.com/195539477/buckets/2085958496/chats/9007199254741043.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958496/chats/9007199254741043"
    },
    "bucket": {
      "id": 2085958496,
      "name": "Honcho Design Newsroom",
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
      "created_at": "2016-09-09T22:58:29.925Z",
      "updated_at": "2016-09-09T22:58:29.925Z",
      "admin": false,
      "owner": false,
      "time_zone": "America/Chicago",
      "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBF0qCjw=--21513efb0cf6f64f7a0720b2c56ac6145ae6680c/avatar-64-x4"
    },
    "content": "I'm hungry"
  }
]
```
<!-- END GET /buckets/1/chats/2/lines.json -->
###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/chats/2/lines.json
```

Get a Campfire line
-------------------

* `GET /buckets/1/chats/2/lines/3.json` will return the Campfire line with ID `3` in the Campfire with ID `2` in the Basecamp with ID `1`.

###### Example JSON Response
<!-- START GET /buckets/1/chats/2/lines/3.json -->
```json
{
  "id": 9007199254741076,
  "status": "active",
  "created_at": "2016-04-22T18:04:41.933Z",
  "updated_at": "2016-04-22T18:04:41.933Z",
  "type": "Chat::Lines::Text",
  "url": "https://3.basecampapi.com/195539477/buckets/2085958496/chats/9007199254741043/lines/9007199254741076.json",
  "app_url": "https://3.basecamp.com/195539477/buckets/2085958496/chats/9007199254741043@9007199254741076",
  "parent": {
    "id": 9007199254741043,
    "title": "Campfire",
    "type": "Chat::Transcript",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958496/chats/9007199254741043.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958496/chats/9007199254741043"
  },
  "bucket": {
    "id": 2085958496,
    "name": "Honcho Design Newsroom",
    "type": "Project"
  },
  "creator": {
    "id": 1007299143,
    "attachable_sgid": "BAh7CEkiCGdpZAY6BkVUSSIrZ2lkOi8vYmMzL1BlcnNvbi8xMDA3Mjk5MTQzP2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg9hdHRhY2hhYmxlBjsAVEkiD2V4cGlyZXNfYXQGOwBUMA==--919d2c8b11ff403eefcab9db42dd26846d0c3102",
    "name": "Victor Cooper",
    "email_address": "victor@honchodesign.com",
    "personable_type": "User",
    "title": "Chief Strategist",
    "bio": "Don't let your dreams be dreams",
    "created_at": "2016-09-09T22:58:27.559Z",
    "updated_at": "2016-09-09T22:58:31.296Z",
    "admin": true,
    "owner": true,
    "time_zone": "America/Chicago",
    "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBEcqCjw=--c632b967cec296b87363a697a67a87f9cc1e5b45/avatar-64-x4",
    "company": {
      "id": 1033447817,
      "name": "Honcho Design"
    }
  },
  "content": "Hey all!"
}
```
<!-- END GET /buckets/1/chats/2/lines/3.json -->
###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/chats/2/lines/3.json
```

Create a Campfire line
----------------------

* `POST /buckets/1/chats/2/lines.json` creates a line in the Campfire with ID `2` in the Basecamp with ID `2`.

**Required parameters**: `content` as the plain text body for the Campfire line.

This endpoint will return `201 Created` with the current JSON representation of the line if the creation was a success. See the [Get a Campfire line](#get-a-campfire-line) endpoint for more info on the payload.

###### Example JSON Request

``` json
{
  "content": "Good morning"
}
```

###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -H "Content-Type: application/json" \
  -d '{"content":"Good morning"}' \
  https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/chats/2/lines.json
```

[pagination]: https://github.com/basecamp/bc3-api/blob/master/README.md#pagination
