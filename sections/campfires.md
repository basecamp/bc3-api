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
    "created_at": "2016-04-10T03:43:39.958Z",
    "updated_at": "2016-07-07T02:58:50.967Z",
    "bucket_path": "/195539477/buckets/2085958496",
    "type": "Chat::Transcript",
    "comments_count": 0,
    "url": "https://3.basecampapi.com/195539477/buckets/2085958496/chats/9007199254741043.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958496/chats/9007199254741043",
    "creator": {
      "id": 1007299143,
      "name": "Victor Cooper",
      "email_address": "victor@honchodesign.com",
      "personable_type": "User",
      "title": null,
      "created_at": "2016-07-07T02:58:31.022Z",
      "updated_at": "2016-07-07T02:58:35.795Z",
      "admin": true,
      "owner": true,
      "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBEcqCjw=--c632b967cec296b87363a697a67a87f9cc1e5b45/avatar-64-x4",
      "company": {
        "id": 1033447817,
        "name": "Honcho Design"
      }
    },
    "bucket": {
      "id": 1042979250,
      "account_id": 1009501286,
      "name": "Honcho Design Newsroom",
      "description": "Let's talk about the company!",
      "created_at": "2016-04-07T02:58:39.958Z",
      "updated_at": "2016-04-07T02:58:39.958Z",
      "creator_id": 1007299143,
      "client_company_id": null
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
  "created_at": "2016-04-10T03:43:39.958Z",
  "updated_at": "2016-07-07T02:58:50.967Z",
  "bucket_path": "/195539477/buckets/2085958496",
  "type": "Chat::Transcript",
  "comments_count": 0,
  "url": "https://3.basecampapi.com/195539477/buckets/2085958496/chats/9007199254741043.json",
  "app_url": "https://3.basecamp.com/195539477/buckets/2085958496/chats/9007199254741043",
  "creator": {
    "id": 1007299143,
    "name": "Victor Cooper",
    "email_address": "victor@honchodesign.com",
    "personable_type": "User",
    "title": null,
    "created_at": "2016-07-07T02:58:31.022Z",
    "updated_at": "2016-07-07T02:58:35.795Z",
    "admin": true,
    "owner": true,
    "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBEcqCjw=--c632b967cec296b87363a697a67a87f9cc1e5b45/avatar-64-x4",
    "company": {
      "id": 1033447817,
      "name": "Honcho Design"
    }
  },
  "bucket": {
    "id": 1042979250,
    "account_id": 1009501286,
    "name": "Honcho Design Newsroom",
    "description": "Let's talk about the company!",
    "created_at": "2016-04-07T02:58:39.958Z",
    "updated_at": "2016-04-07T02:58:39.958Z",
    "creator_id": 1007299143,
    "client_company_id": null
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
    "created_at": "2016-04-12T18:13:39.958Z",
    "updated_at": "2016-04-12T18:13:39.958Z",
    "bucket_path": "/195539477/buckets/2085958496",
    "type": "Chat::Lines::Text",
    "comments_count": 0,
    "url": "https://3.basecampapi.com/195539477/buckets/2085958496/chats/9007199254741043/lines/9007199254741125.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958496/chats/9007199254741043@9007199254741125",
    "creator": {
      "id": 1007299165,
      "name": "Matt Donahue",
      "email_address": "matt@honchodesign.com",
      "personable_type": "User",
      "title": "Global Data Strategist",
      "created_at": "2016-07-07T02:58:34.592Z",
      "updated_at": "2016-07-07T02:58:34.592Z",
      "admin": false,
      "owner": false,
      "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBF0qCjw=--21513efb0cf6f64f7a0720b2c56ac6145ae6680c/avatar-64-x4"
    },
    "bucket": {
      "id": 1042979250,
      "account_id": 1009501286,
      "name": "Honcho Design Newsroom",
      "description": "Let's talk about the company!",
      "created_at": "2016-04-07T02:58:39.958Z",
      "updated_at": "2016-04-07T02:58:39.958Z",
      "creator_id": 1007299143,
      "client_company_id": null
    },
    "parent": {
      "id": 9007199254741043,
      "title": "Campfire",
      "url": "https://3.basecampapi.com/195539477/buckets/2085958496/chats/9007199254741043.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958496/chats/9007199254741043"
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
  "created_at": "2016-04-10T04:01:39.958Z",
  "updated_at": "2016-04-10T04:01:39.958Z",
  "bucket_path": "/195539477/buckets/2085958496",
  "type": "Chat::Lines::Text",
  "comments_count": 0,
  "url": "https://3.basecampapi.com/195539477/buckets/2085958496/chats/9007199254741043/lines/9007199254741076.json",
  "app_url": "https://3.basecamp.com/195539477/buckets/2085958496/chats/9007199254741043@9007199254741076",
  "creator": {
    "id": 1007299143,
    "name": "Victor Cooper",
    "email_address": "victor@honchodesign.com",
    "personable_type": "User",
    "title": null,
    "created_at": "2016-07-07T02:58:31.022Z",
    "updated_at": "2016-07-07T02:58:35.795Z",
    "admin": true,
    "owner": true,
    "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBEcqCjw=--c632b967cec296b87363a697a67a87f9cc1e5b45/avatar-64-x4",
    "company": {
      "id": 1033447817,
      "name": "Honcho Design"
    }
  },
  "bucket": {
    "id": 1042979250,
    "account_id": 1009501286,
    "name": "Honcho Design Newsroom",
    "description": "Let's talk about the company!",
    "created_at": "2016-04-07T02:58:39.958Z",
    "updated_at": "2016-04-07T02:58:39.958Z",
    "creator_id": 1007299143,
    "client_company_id": null
  },
  "parent": {
    "id": 9007199254741043,
    "title": "Campfire",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958496/chats/9007199254741043.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958496/chats/9007199254741043"
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
