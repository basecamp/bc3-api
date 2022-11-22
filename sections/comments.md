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

* `GET /buckets/1/recordings/3/comments.json` will return a [paginated list][pagination] of active comments in the project with an ID of `1` and the recording with ID of `3`.

###### Example JSON Response
<!-- START GET /buckets/1/recordings/3/comments.json -->
```json
[
  {
    "id": 1069479352,
    "status": "active",
    "visible_to_clients": false,
    "created_at": "2022-10-29T10:32:58.169Z",
    "updated_at": "2022-10-29T10:32:58.169Z",
    "title": "Re: We won Leto!",
    "inherits_status": true,
    "type": "Comment",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958499/comments/1069479352.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958499/messages/1069479351#__recording_1069479352",
    "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7CEkiCGdpZAY6BkVUSSIuZ2lkOi8vYmMzL1JlY29yZGluZy8xMDY5NDc5MzUyP2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg1yZWFkYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--776378f4118807d7eea7c42ddd2a8ab6079b2788.json",
    "parent": {
      "id": 1069479351,
      "title": "We won Leto!",
      "type": "Message",
      "url": "https://3.basecampapi.com/195539477/buckets/2085958499/messages/1069479351.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958499/messages/1069479351"
    },
    "bucket": {
      "id": 2085958499,
      "name": "The Leto Laptop",
      "type": "Project"
    },
    "creator": {
      "id": 1049715923,
      "attachable_sgid": "BAh7CEkiCGdpZAY6BkVUSSIrZ2lkOi8vYmMzL1BlcnNvbi8xMDQ5NzE1OTIzP2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg9hdHRhY2hhYmxlBjsAVEkiD2V4cGlyZXNfYXQGOwBUMA==--cc7313cd0fef7654f37f813c000bf892d80e2e2f",
      "name": "Andrew Wong",
      "email_address": "andrew@honchodesign.com",
      "personable_type": "User",
      "title": "Senior Branding Strategist",
      "bio": null,
      "location": null,
      "created_at": "2022-11-22T08:23:22.017Z",
      "updated_at": "2022-11-22T08:23:22.017Z",
      "admin": false,
      "owner": false,
      "client": false,
      "employee": false,
      "time_zone": "Etc/UTC",
      "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBNNkkT4=--e3c2676dde30e7c13f87642e3a3dd46ad657f731/avatar?v=1",
      "can_manage_projects": true,
      "can_manage_people": true
    },
    "content": "<div>Yeah! Great job everyone! Super excited to get going!</div>"
  }
]
```
<!-- END GET /buckets/1/recordings/3/comments.json -->
###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/recordings/3/comments.json
```


Get a comment
-------------

* `GET /buckets/1/comments/2.json` will return the comment with an ID of `2` in the project with an ID of `1`.

###### Example JSON Response
<!-- START GET /buckets/1/comments/2.json -->
```json
{
  "id": 1069479361,
  "status": "active",
  "visible_to_clients": false,
  "created_at": "2022-10-30T01:01:58.169Z",
  "updated_at": "2022-10-30T01:01:58.169Z",
  "title": "Re: We won Leto!",
  "inherits_status": true,
  "type": "Comment",
  "url": "https://3.basecampapi.com/195539477/buckets/2085958499/comments/1069479361.json",
  "app_url": "https://3.basecamp.com/195539477/buckets/2085958499/messages/1069479351#__recording_1069479361",
  "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7CEkiCGdpZAY6BkVUSSIuZ2lkOi8vYmMzL1JlY29yZGluZy8xMDY5NDc5MzYxP2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg1yZWFkYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--8b7691463c92f63fe45627584ed759b44fe7bdaa.json",
  "parent": {
    "id": 1069479351,
    "title": "We won Leto!",
    "type": "Message",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958499/messages/1069479351.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958499/messages/1069479351"
  },
  "bucket": {
    "id": 2085958499,
    "name": "The Leto Laptop",
    "type": "Project"
  },
  "creator": {
    "id": 1049715915,
    "attachable_sgid": "BAh7CEkiCGdpZAY6BkVUSSIrZ2lkOi8vYmMzL1BlcnNvbi8xMDQ5NzE1OTE1P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg9hdHRhY2hhYmxlBjsAVEkiD2V4cGlyZXNfYXQGOwBUMA==--aeb392ebf54ffd820e45f27add22bae3a8c7da56",
    "name": "Annie Bryan",
    "email_address": "annie@honchodesign.com",
    "personable_type": "User",
    "title": "Central Markets Manager",
    "bio": "To open a store is easy, to keep it open is an art",
    "location": null,
    "created_at": "2022-11-22T08:23:21.911Z",
    "updated_at": "2022-11-22T08:23:21.911Z",
    "admin": false,
    "owner": false,
    "client": false,
    "employee": true,
    "time_zone": "America/Chicago",
    "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBMtkkT4=--9927c47a4cbee30a7f9aea667882496aba799149/avatar?v=1",
    "company": {
      "id": 1033447817,
      "name": "Honcho Design"
    },
    "can_manage_projects": true,
    "can_manage_people": true
  },
  "content": "<div>I just want to echo what just about everyone already said. This is a big one for us, and I can't wait to get going. I'll be spinning up the project shortly!</div>"
}
```
<!-- END GET /buckets/1/comments/2.json -->
###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/comment/2.json
```


Create a comment
----------------

* `POST /buckets/1/recordings/3/comments.json` publishes a comment in the project with ID `1` and under the recording with an ID of `3`.

**Required parameters**: `content` as the body of the message. See our [Rich text guide][rich] for what HTML tags are allowed.

Note: All people who are subscribed to the recording will be notified when the comment is posted.

This endpoint will return `201 Created` with the current JSON representation of the message if the creation was a success. See the [Get a comment](#get-a-comment) endpoint for more info on the payload. The `Location` header will contain a URL to the HTML version of the new comment.

###### Example JSON Request

``` json
{
  "content": "<div><em>Wow!</em> That is cool.</div>",
}
```

###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -H "Content-Type: application/json" \
  -d '{"content":"<div><em>Wow!</em> That is cool.</div>"}' \
  https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/recordings/3/comments.json
```


Update a comment
----------------

* `PUT /buckets/1/comments/2.json` allows changing content of the message with an ID of `2` in the project with ID `1`.

This endpoint will return `200 OK` with the current JSON representation of the message if the update was a success. See the [Get a comment](#get-a-comment) endpoint for more info on the payload. The `Location` header will contain a URL to the HTML version of the updated comment.

###### Example JSON Request

``` json
{
  "content": "<div><em>No way!</em> That isn't cool at all.</div>"
}
```

###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -H "Content-Type: application/json" \
  -d '{"content":"<div><em>No way!</em> That isn't cool at all.</div>"}' -X PUT \
  https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/messages/2.json
```


[recordings]: https://github.com/basecamp/bc3-api/blob/master/sections/recordings.md#recordings
[messages]:   https://github.com/basecamp/bc3-api/blob/master/sections/messages.md#messages
[todolists]:  https://github.com/basecamp/bc3-api/blob/master/sections/todolists.md#todolists
[todos]:      https://github.com/basecamp/bc3-api/blob/master/sections/todos.md#todos
[trash]:      https://github.com/basecamp/bc3-api/blob/master/sections/recordings.md#trash-a-recording
[pagination]: https://github.com/basecamp/bc3-api/blob/master/README.md#pagination
[rich]:       https://github.com/basecamp/bc3-api/blob/master/README.md#rich-text-content
