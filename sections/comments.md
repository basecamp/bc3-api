Comments
========

To determine if a resource can be commented on, check for the presences of `comment_count` and `comments_url` attributes in its JSON response.

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
    "id": 9007199254741444,
    "status": "active",
    "created_at": "2016-07-19T21:32:42.627Z",
    "updated_at": "2016-07-19T21:32:42.627Z",
    "title": "Re: We won Leto!",
    "type": "Comment",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958498/comments/9007199254741444.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958498/messages/9007199254741443#__recording_9007199254741444",
    "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7CEkiCGdpZAY6BkVUSSIuZ2lkOi8vYmMzL1JlY29yZGluZy8xMDY0MDkxMDY4P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg1yZWFkYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--8c119c5f0532a854e2d2d84ea0ffeb5462277bda.json",
    "parent": {
      "id": 9007199254741443,
      "title": "We won Leto!",
      "type": "Message",
      "url": "https://3.basecampapi.com/195539477/buckets/2085958498/messages/9007199254741443.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958498/messages/9007199254741443"
    },
    "bucket": {
      "id": 2085958498,
      "name": "The Leto Laptop",
      "type": "Project"
    },
    "creator": {
      "id": 1007299152,
      "attachable_sgid": "BAh7CEkiCGdpZAY6BkVUSSIrZ2lkOi8vYmMzL1BlcnNvbi8xMDA3Mjk5MTUyP2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg9hdHRhY2hhYmxlBjsAVEkiD2V4cGlyZXNfYXQGOwBUMA==--c70d0dcbf061acc7ca36da4b88819f15af03df52",
      "name": "Andrew Wong",
      "email_address": "andrew@honchodesign.com",
      "personable_type": "User",
      "title": "Senior Branding Strategist",
      "bio": null,
      "created_at": "2016-09-09T22:58:28.576Z",
      "updated_at": "2016-09-09T22:58:28.576Z",
      "admin": false,
      "owner": false,
      "time_zone": "America/Chicago",
      "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBFAqCjw=--0413da7be3ef98ba6e3274f859fb29fc38698edf/avatar-64-x4"
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
  "id": 9007199254741453,
  "status": "active",
  "created_at": "2016-07-19T22:54:43.939Z",
  "updated_at": "2016-07-19T22:54:43.939Z",
  "title": "Re: We won Leto!",
  "type": "Comment",
  "url": "https://3.basecampapi.com/195539477/buckets/2085958498/comments/9007199254741453.json",
  "app_url": "https://3.basecamp.com/195539477/buckets/2085958498/messages/9007199254741443#__recording_9007199254741453",
  "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7CEkiCGdpZAY6BkVUSSIuZ2lkOi8vYmMzL1JlY29yZGluZy8xMDY0MDkxMDY4P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg1yZWFkYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--8c119c5f0532a854e2d2d84ea0ffeb5462277bda.json",
  "parent": {
    "id": 9007199254741443,
    "title": "We won Leto!",
    "type": "Message",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958498/messages/9007199254741443.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958498/messages/9007199254741443"
  },
  "bucket": {
    "id": 2085958498,
    "name": "The Leto Laptop",
    "type": "Project"
  },
  "creator": {
    "id": 1007299144,
    "attachable_sgid": "BAh7CEkiCGdpZAY6BkVUSSIrZ2lkOi8vYmMzL1BlcnNvbi8xMDA3Mjk5MTQ0P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg9hdHRhY2hhYmxlBjsAVEkiD2V4cGlyZXNfYXQGOwBUMA==--2e34d7611a9fcaeb82342d015a671cf5e998c036",
    "name": "Annie Bryan",
    "email_address": "annie@honchodesign.com",
    "personable_type": "User",
    "title": "Central Markets Manager",
    "bio": "To open a store is easy, to keep it open is an art",
    "created_at": "2016-09-09T22:58:27.734Z",
    "updated_at": "2016-09-09T22:58:27.734Z",
    "admin": false,
    "owner": false,
    "time_zone": "America/Chicago",
    "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBEgqCjw=--8266bb0507508f3d46050d57b65924d5e2a005f3/avatar-64-x4",
    "company": {
      "id": 1033447817,
      "name": "Honcho Design"
    }
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
