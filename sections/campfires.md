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
    "id": 1069478985,
    "status": "active",
    "visible_to_clients": false,
    "created_at": "2026-01-31T08:29:58.785Z",
    "updated_at": "2026-01-31T08:30:23.083Z",
    "title": "Chat",
    "inherits_status": true,
    "type": "Chat::Transcript",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958502/chats/1069478985.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958502/chats/1069478985",
    "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiLmdpZDovL2JjMy9SZWNvcmRpbmcvMTA2OTQ3ODk4NT9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg1yZWFkYWJsZQY7AFQ=--f745f0a5dc8108b7f361e578d47b72ff974ed50e.json",
    "subscription_url": "https://3.basecampapi.com/195539477/buckets/2085958502/recordings/1069478985/subscription.json",
    "position": 4,
    "bucket": {
      "id": 2085958502,
      "name": "Honcho Design Newsroom",
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
    "topic": "Chat",
    "lines_url": "https://3.basecampapi.com/195539477/buckets/2085958502/chats/1069478985/lines.json"
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
  "id": 1069478985,
  "status": "active",
  "visible_to_clients": false,
  "created_at": "2026-01-31T08:29:58.785Z",
  "updated_at": "2026-01-31T08:30:23.083Z",
  "title": "Chat",
  "inherits_status": true,
  "type": "Chat::Transcript",
  "url": "https://3.basecampapi.com/195539477/buckets/2085958502/chats/1069478985.json",
  "app_url": "https://3.basecamp.com/195539477/buckets/2085958502/chats/1069478985",
  "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiLmdpZDovL2JjMy9SZWNvcmRpbmcvMTA2OTQ3ODk4NT9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg1yZWFkYWJsZQY7AFQ=--f745f0a5dc8108b7f361e578d47b72ff974ed50e.json",
  "subscription_url": "https://3.basecampapi.com/195539477/buckets/2085958502/recordings/1069478985/subscription.json",
  "position": 4,
  "bucket": {
    "id": 2085958502,
    "name": "Honcho Design Newsroom",
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
  "topic": "Chat",
  "lines_url": "https://3.basecampapi.com/195539477/buckets/2085958502/chats/1069478985/lines.json"
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
    "id": 1069479068,
    "status": "active",
    "visible_to_clients": false,
    "created_at": "2025-11-07T10:15:00.000Z",
    "updated_at": "2025-11-07T10:15:00.000Z",
    "title": "I'm hungry",
    "inherits_status": true,
    "type": "Chat::Lines::RichText",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958502/chats/1069478985/lines/1069479068.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958502/chats/1069478985@1069479068",
    "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiLmdpZDovL2JjMy9SZWNvcmRpbmcvMTA2OTQ3OTA2OD9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg1yZWFkYWJsZQY7AFQ=--ed75de023587361ebed66cce122997d56faeaa2e.json",
    "parent": {
      "id": 1069478985,
      "title": "Chat",
      "type": "Chat::Transcript",
      "url": "https://3.basecampapi.com/195539477/buckets/2085958502/chats/1069478985.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958502/chats/1069478985"
    },
    "bucket": {
      "id": 2085958502,
      "name": "Honcho Design Newsroom",
      "type": "Project"
    },
    "creator": {
      "id": 1049715929,
      "attachable_sgid": "BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiK2dpZDovL2JjMy9QZXJzb24vMTA0OTcxNTkyOT9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg9hdHRhY2hhYmxlBjsAVA==--d79103e78a10cd9f8ecda7470ea315674ac8a79a",
      "name": "Matt Donahue",
      "email_address": "matt@honchodesign.com",
      "personable_type": "User",
      "title": "Global Data Strategist",
      "bio": null,
      "location": null,
      "created_at": "2026-01-31T08:29:40.358Z",
      "updated_at": "2026-01-31T08:29:40.358Z",
      "admin": false,
      "owner": false,
      "client": false,
      "employee": false,
      "time_zone": "America/Chicago",
      "avatar_url": "https://3.basecampapi.com/195539477/people/BAhpBNlkkT4=--0f3c77d8c13069d514fd3f0ad694a67e426bad0f/avatar?v=1",
      "can_ping": true,
      "can_manage_projects": true,
      "can_manage_people": true,
      "can_access_timesheet": true,
      "can_access_hill_charts": true
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
  "id": 1069479054,
  "status": "active",
  "visible_to_clients": false,
  "created_at": "2025-11-07T03:12:00.000Z",
  "updated_at": "2025-11-07T03:12:00.000Z",
  "title": "👏 🎉",
  "inherits_status": true,
  "type": "Chat::Lines::RichText",
  "url": "https://3.basecampapi.com/195539477/buckets/2085958502/chats/1069478985/lines/1069479054.json",
  "app_url": "https://3.basecamp.com/195539477/buckets/2085958502/chats/1069478985@1069479054",
  "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiLmdpZDovL2JjMy9SZWNvcmRpbmcvMTA2OTQ3OTA1ND9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg1yZWFkYWJsZQY7AFQ=--bf7b55e226a9c3111e0a8639faa1012b4db18bb1.json",
  "parent": {
    "id": 1069478985,
    "title": "Chat",
    "type": "Chat::Transcript",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958502/chats/1069478985.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958502/chats/1069478985"
  },
  "bucket": {
    "id": 2085958502,
    "name": "Honcho Design Newsroom",
    "type": "Project"
  },
  "creator": {
    "id": 1049715915,
    "attachable_sgid": "BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiK2dpZDovL2JjMy9QZXJzb24vMTA0OTcxNTkxNT9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg9hdHRhY2hhYmxlBjsAVA==--56bb1f99675fd8fe08f93a706a5d2ddaa8412625",
    "name": "Amy Rivera",
    "email_address": "amy@honchodesign.com",
    "personable_type": "User",
    "title": "Central Web Coordinator",
    "bio": "I never said most of the things I said",
    "location": null,
    "created_at": "2026-01-31T08:29:32.987Z",
    "updated_at": "2026-01-31T08:29:32.987Z",
    "admin": false,
    "owner": false,
    "client": false,
    "employee": false,
    "time_zone": "America/Chicago",
    "avatar_url": "https://3.basecampapi.com/195539477/people/BAhpBMtkkT4=--9927c47a4cbee30a7f9aea667882496aba799149/avatar?v=1",
    "can_ping": true,
    "can_manage_projects": true,
    "can_manage_people": true,
    "can_access_timesheet": true,
    "can_access_hill_charts": true
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
