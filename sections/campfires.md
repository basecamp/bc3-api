Campfires
=========

Endpoints:

- [Get Campfires](#get-campfires)
- [Get a Campfire](#get-a-campfire)
- [Get Campfire lines](#get-campfire-lines)
- [Get a Campfire line](#get-a-campfire-line)
- [Create a Campfire line](#create-a-campfire-line)
- [Delete a Campfire line](#delete-a-campfire-line)

Get Campfires
-------------

* `GET /chats.json` will return a [paginated list][pagination] of all active Campfires visible to the current user.

###### Example JSON Response
<!-- START GET /chats.json -->
```json
[
  {
    "id": 1069478933,
    "status": "active",
    "visible_to_clients": false,
    "created_at": "2022-08-25T10:04:24.930Z",
    "updated_at": "2022-11-22T08:23:30.837Z",
    "title": "Campfire",
    "inherits_status": true,
    "type": "Chat::Transcript",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958497/chats/1069478933.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958497/chats/1069478933",
    "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7CEkiCGdpZAY6BkVUSSIuZ2lkOi8vYmMzL1JlY29yZGluZy8xMDY5NDc4OTMzP2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg1yZWFkYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--f3045584f2792d1d77b9cf8dcaff57d9b0177e0b.json",
    "subscription_url": "https://3.basecampapi.com/195539477/buckets/2085958497/recordings/1069478933/subscription.json",
    "position": 4,
    "bucket": {
      "id": 2085958497,
      "name": "Honcho Design Newsroom",
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
    "topic": "Campfire",
    "lines_url": "https://3.basecampapi.com/195539477/buckets/2085958497/chats/1069478933/lines.json"
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

* `GET /buckets/1/chats/2.json` will return the Campfire with ID `2` in the project with ID `1`.

###### Example JSON Response
<!-- START GET /buckets/1/chats/2.json -->
```json
{
  "id": 1069478933,
  "status": "active",
  "visible_to_clients": false,
  "created_at": "2022-08-25T10:04:24.930Z",
  "updated_at": "2022-11-22T08:23:30.837Z",
  "title": "Campfire",
  "inherits_status": true,
  "type": "Chat::Transcript",
  "url": "https://3.basecampapi.com/195539477/buckets/2085958497/chats/1069478933.json",
  "app_url": "https://3.basecamp.com/195539477/buckets/2085958497/chats/1069478933",
  "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7CEkiCGdpZAY6BkVUSSIuZ2lkOi8vYmMzL1JlY29yZGluZy8xMDY5NDc4OTMzP2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg1yZWFkYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--f3045584f2792d1d77b9cf8dcaff57d9b0177e0b.json",
  "subscription_url": "https://3.basecampapi.com/195539477/buckets/2085958497/recordings/1069478933/subscription.json",
  "position": 4,
  "bucket": {
    "id": 2085958497,
    "name": "Honcho Design Newsroom",
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
  "topic": "Campfire",
  "lines_url": "https://3.basecampapi.com/195539477/buckets/2085958497/chats/1069478933/lines.json"
}
```
<!-- END GET /buckets/1/chats/2.json -->
###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/chats/2.json
```

Get Campfire lines
------------------

* `GET /buckets/1/chats/2/lines.json` will return a [paginated list][pagination] of Campfire lines of the Campfire with ID `2` in the project with ID `1`.

###### Example JSON Response
<!-- START GET /buckets/1/chats/2/lines.json -->
```json
[
  {
    "id": 1069479015,
    "status": "active",
    "visible_to_clients": false,
    "created_at": "2022-08-25T08:23:24.930Z",
    "updated_at": "2022-08-25T08:23:24.930Z",
    "title": "I'm hungry",
    "inherits_status": true,
    "type": "Chat::Lines::Text",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958497/chats/1069478933/lines/1069479015.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958497/chats/1069478933@1069479015",
    "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7CEkiCGdpZAY6BkVUSSIuZ2lkOi8vYmMzL1JlY29yZGluZy8xMDY5NDc5MDE1P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg1yZWFkYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--9d750749b82162ec684b4cf4747080694b766b8f.json",
    "parent": {
      "id": 1069478933,
      "title": "Campfire",
      "type": "Chat::Transcript",
      "url": "https://3.basecampapi.com/195539477/buckets/2085958497/chats/1069478933.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958497/chats/1069478933"
    },
    "bucket": {
      "id": 2085958497,
      "name": "Honcho Design Newsroom",
      "type": "Project"
    },
    "creator": {
      "id": 1049715936,
      "attachable_sgid": "BAh7CEkiCGdpZAY6BkVUSSIrZ2lkOi8vYmMzL1BlcnNvbi8xMDQ5NzE1OTM2P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg9hdHRhY2hhYmxlBjsAVEkiD2V4cGlyZXNfYXQGOwBUMA==--49bf4c17af8bc53bf5ecc54cfe98e24cc45aeaa0",
      "name": "Matt Donahue",
      "email_address": "matt@honchodesign.com",
      "personable_type": "User",
      "title": "Global Data Strategist",
      "bio": null,
      "location": null,
      "created_at": "2022-11-22T08:23:22.205Z",
      "updated_at": "2022-11-22T08:23:22.205Z",
      "admin": false,
      "owner": false,
      "client": false,
      "employee": false,
      "time_zone": "Etc/UTC",
      "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBOBkkT4=--78fb2ba7c3091268f41638ef90dee7dd32f395d6/avatar?v=1",
      "can_manage_projects": true,
      "can_manage_people": true
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

* `GET /buckets/1/chats/2/lines/3.json` will return the Campfire line with ID `3` in the Campfire with ID `2` in the project with ID `1`.

###### Example JSON Response
<!-- START GET /buckets/1/chats/2/lines/3.json -->
```json
{
  "id": 1069479001,
  "status": "active",
  "visible_to_clients": false,
  "created_at": "2022-08-25T08:23:24.930Z",
  "updated_at": "2022-08-25T08:23:24.930Z",
  "title": "👏 🎉",
  "inherits_status": true,
  "type": "Chat::Lines::Text",
  "url": "https://3.basecampapi.com/195539477/buckets/2085958497/chats/1069478933/lines/1069479001.json",
  "app_url": "https://3.basecamp.com/195539477/buckets/2085958497/chats/1069478933@1069479001",
  "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7CEkiCGdpZAY6BkVUSSIuZ2lkOi8vYmMzL1JlY29yZGluZy8xMDY5NDc5MDAxP2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg1yZWFkYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--c8a4576fc2f2c0fbf4a4015fc4f34128f4c20d42.json",
  "parent": {
    "id": 1069478933,
    "title": "Campfire",
    "type": "Chat::Transcript",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958497/chats/1069478933.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958497/chats/1069478933"
  },
  "bucket": {
    "id": 2085958497,
    "name": "Honcho Design Newsroom",
    "type": "Project"
  },
  "creator": {
    "id": 1049715922,
    "attachable_sgid": "BAh7CEkiCGdpZAY6BkVUSSIrZ2lkOi8vYmMzL1BlcnNvbi8xMDQ5NzE1OTIyP2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg9hdHRhY2hhYmxlBjsAVEkiD2V4cGlyZXNfYXQGOwBUMA==--90ea53b2b0ce32a96bcc6ef712c1fac0dbb0a0cd",
    "name": "Amy Rivera",
    "email_address": "amy@honchodesign.com",
    "personable_type": "User",
    "title": "Central Web Coordinator",
    "bio": "I never said most of the things I said",
    "location": null,
    "created_at": "2022-11-22T08:23:22.005Z",
    "updated_at": "2022-11-22T08:23:22.005Z",
    "admin": false,
    "owner": false,
    "client": false,
    "employee": false,
    "time_zone": "Etc/UTC",
    "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBNJkkT4=--6ef93d58440c2ed1fec4457e3eb5f09572e866a4/avatar?v=1",
    "can_manage_projects": true,
    "can_manage_people": true
  },
  "content": "👏 🎉"
}
```
<!-- END GET /buckets/1/chats/2/lines/3.json -->
###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/chats/2/lines/3.json
```

Create a Campfire line
----------------------

* `POST /buckets/1/chats/2/lines.json` creates a line in the Campfire with ID `2` in the project with ID `1`.

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

Delete a Campfire line
----------------------

* `DELETE /buckets/1/chats/2/lines/3.json` will delete the Campfire line with ID `3` in the Campfire with ID `2` in the project with ID `1`.

Returns `204 No Content` if successful.

###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/chats/2/lines/3.json
```

[pagination]: https://github.com/basecamp/bc3-api/blob/master/README.md#pagination
