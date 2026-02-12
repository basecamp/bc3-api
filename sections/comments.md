Comments
========

To determine if a resource can be commented on, check for the presences of `comments_count` and `comments_url` attributes in its JSON response.

Endpoints:

- [Get comments](#get-comments)
- [Get a comment](#get-a-comment)
- [Create a comment](#create-a-comment)
- [Update a comment](#update-a-comment)
- [Trash a comment][trash]

Get comments
------------

* `GET /recordings/3/comments.json` will return a [paginated list][pagination] of active comments for the recording with ID of `3`.

###### Example JSON Response
<!-- START GET /recordings/3/comments.json -->
```json
[
  {
    "id": 1069479407,
    "status": "active",
    "visible_to_clients": false,
    "created_at": "2025-12-30T19:39:00.000Z",
    "updated_at": "2025-12-30T19:39:00.000Z",
    "title": "Re: We won Leto!",
    "inherits_status": true,
    "type": "Comment",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958504/comments/1069479407.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958504/messages/1069479406#__recording_1069479407",
    "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiLmdpZDovL2JjMy9SZWNvcmRpbmcvMTA2OTQ3OTQwNz9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg1yZWFkYWJsZQY7AFQ=--2d87c12332eb478cb125670282e0540a56500c87.json",
    "boosts_count": 0,
    "boosts_url": "https://3.basecampapi.com/195539477/buckets/2085958504/recordings/1069479407/boosts.json",
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
      "id": 1049715916,
      "attachable_sgid": "BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiK2dpZDovL2JjMy9QZXJzb24vMTA0OTcxNTkxNj9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg9hdHRhY2hhYmxlBjsAVA==--6414c77c0a206bc7d45987b8335318b768e8651f",
      "name": "Andrew Wong",
      "email_address": "andrew@honchodesign.com",
      "personable_type": "User",
      "title": "Senior Branding Strategist",
      "bio": null,
      "location": null,
      "created_at": "2026-02-12T06:08:51.481Z",
      "updated_at": "2026-02-12T06:08:51.481Z",
      "admin": false,
      "owner": false,
      "client": false,
      "employee": false,
      "time_zone": "America/Chicago",
      "avatar_url": "https://3.basecampapi.com/195539477/people/BAhpBMxkkT4=--0ea74d7e5d39ad2d120da79250b179b7e0b00c44/avatar?v=1",
      "can_ping": true,
      "can_manage_projects": true,
      "can_manage_people": true,
      "can_access_timesheet": false,
      "can_access_hill_charts": true
    },
    "content": "Yeah! Great job everyone! Super excited to get going!"
  }
]
```
<!-- END GET /recordings/3/comments.json -->
###### Copy as cURL

```shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/recordings/3/comments.json
```


Get a comment
-------------

* `GET /comments/2.json` will return the comment with an ID of `2`.

###### Example JSON Response
<!-- START GET /comments/2.json -->
```json
{
  "id": 1069479416,
  "status": "active",
  "visible_to_clients": false,
  "created_at": "2025-12-31T01:20:00.000Z",
  "updated_at": "2025-12-31T01:20:00.000Z",
  "title": "Re: We won Leto!",
  "inherits_status": true,
  "type": "Comment",
  "url": "https://3.basecampapi.com/195539477/buckets/2085958504/comments/1069479416.json",
  "app_url": "https://3.basecamp.com/195539477/buckets/2085958504/messages/1069479406#__recording_1069479416",
  "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiLmdpZDovL2JjMy9SZWNvcmRpbmcvMTA2OTQ3OTQxNj9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg1yZWFkYWJsZQY7AFQ=--cdd017a73b856e57fbc03bcaf209b104e458a3c9.json",
  "boosts_count": 0,
  "boosts_url": "https://3.basecampapi.com/195539477/buckets/2085958504/recordings/1069479416/boosts.json",
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
    "id": 1049715938,
    "attachable_sgid": "BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiK2dpZDovL2JjMy9QZXJzb24vMTA0OTcxNTkzOD9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg9hdHRhY2hhYmxlBjsAVA==--4ccc567a0a3b10e354bca909b704637b601f0b16",
    "name": "Annie Bryan",
    "email_address": "annie@honchodesign.com",
    "personable_type": "User",
    "title": "Central Markets Manager",
    "bio": "To open a store is easy, to keep it open is an art",
    "location": null,
    "created_at": "2026-02-12T06:08:57.340Z",
    "updated_at": "2026-02-12T06:08:57.340Z",
    "admin": false,
    "owner": false,
    "client": false,
    "employee": true,
    "time_zone": "America/Chicago",
    "avatar_url": "https://3.basecampapi.com/195539477/people/BAhpBOJkkT4=--732a71fbd28ec10d9bf4466abd3588a8bea40bdb/avatar?v=1",
    "company": {
      "id": 1033447817,
      "name": "Honcho Design"
    },
    "can_ping": true,
    "can_manage_projects": true,
    "can_manage_people": true,
    "can_access_timesheet": false,
    "can_access_hill_charts": true
  },
  "content": "I just want to echo what just about everyone already said. This is a big one for us, and I can't wait to get going. I'll be spinning up the project shortly!"
}
```
<!-- END GET /comments/2.json -->
###### Copy as cURL

```shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/comments/2.json
```


Create a comment
----------------

* `POST /recordings/3/comments.json` publishes a comment under the recording with an ID of `3`.

**Required parameters**: `content` as the body of the message. See our [Rich text guide][rich] for what HTML tags are allowed.

Note: All people who are subscribed to the recording will be notified when the comment is posted.

This endpoint will return `201 Created` with the current JSON representation of the message if the creation was a success. See the [Get a comment](#get-a-comment) endpoint for more info on the payload. The `Location` header will contain a URL to the HTML version of the new comment.

###### Example JSON Request

```json
{
  "content": "<div><em>Wow!</em> That is cool.</div>",
}
```

###### Copy as cURL

```shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -H "Content-Type: application/json" \
  -d '{"content":"<div><em>Wow!</em> That is cool.</div>"}' \
  https://3.basecampapi.com/$ACCOUNT_ID/recordings/3/comments.json
```


Update a comment
----------------

* `PUT /comments/2.json` allows changing content of the comment with an ID of `2`.

This endpoint will return `200 OK` with the current JSON representation of the message if the update was a success. See the [Get a comment](#get-a-comment) endpoint for more info on the payload. The `Location` header will contain a URL to the HTML version of the updated comment.

###### Example JSON Request

```json
{
  "content": "<div><em>No way!</em> That isn't cool at all.</div>"
}
```

###### Copy as cURL

```shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -H "Content-Type: application/json" \
  -d '{"content":"<div><em>No way!</em> That isn't cool at all.</div>"}' -X PUT \
  https://3.basecampapi.com/$ACCOUNT_ID/comments/2.json
```


Legacy project-scoped routes
-----------------------------

The following project-scoped routes are still supported and will remain available, but flat routes above are the canonical form for new integrations.

* `GET /buckets/1/recordings/3/comments.json` → [Get comments](#get-comments)
* `GET /buckets/1/comments/2.json` → [Get a comment](#get-a-comment)
* `POST /buckets/1/recordings/3/comments.json` → [Create a comment](#create-a-comment)
* `PUT /buckets/1/comments/2.json` → [Update a comment](#update-a-comment)

[recordings]: https://github.com/basecamp/bc3-api/blob/master/sections/recordings.md#recordings
[messages]:   https://github.com/basecamp/bc3-api/blob/master/sections/messages.md#messages
[todolists]:  https://github.com/basecamp/bc3-api/blob/master/sections/todolists.md#todolists
[todos]:      https://github.com/basecamp/bc3-api/blob/master/sections/todos.md#todos
[trash]:      https://github.com/basecamp/bc3-api/blob/master/sections/recordings.md#trash-a-recording
[pagination]: https://github.com/basecamp/bc3-api/blob/master/README.md#pagination
[rich]:       https://github.com/basecamp/bc3-api/blob/master/README.md#rich-text-content
