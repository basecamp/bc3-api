Messages
========

Endpoints:

- [Get messages](#get-messages)
- [Get a message](#get-a-message)
- [Create a message](#create-a-message)
- [Update a message](#update-a-message)
- [Pin a message](#pin-a-message)
- [Trash a message][1]

Get messages
------------

* `GET /buckets/1/message_boards/3/messages.json` will return a [paginated list][2] of active messages in the project with an ID of `1` and the message board with ID of `3`.

To get the message board ID for a project, see the [Get message board][3] endpoint.

###### Example JSON Response
<!-- START GET /buckets/1/message_boards/3/messages.json -->
```json
[
  {
    "id": 1069479530,
    "status": "active",
    "visible_to_clients": false,
    "created_at": "2022-11-22T10:46:58.169Z",
    "updated_at": "2022-11-22T08:25:22.515Z",
    "title": "Laptop high res glamour shots",
    "inherits_status": true,
    "type": "Message",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958499/messages/1069479530.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958499/messages/1069479530",
    "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7CEkiCGdpZAY6BkVUSSIuZ2lkOi8vYmMzL1JlY29yZGluZy8xMDY5NDc5NTMwP2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg1yZWFkYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--cd21e5988947fa915c1175835cd76ae503ca02f5.json",
    "subscription_url": "https://3.basecampapi.com/195539477/buckets/2085958499/recordings/1069479530/subscription.json",
    "comments_count": 1,
    "comments_url": "https://3.basecampapi.com/195539477/buckets/2085958499/recordings/1069479530/comments.json",
    "parent": {
      "id": 1069479338,
      "title": "Message Board",
      "type": "Message::Board",
      "url": "https://3.basecampapi.com/195539477/buckets/2085958499/message_boards/1069479338.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958499/message_boards/1069479338"
    },
    "bucket": {
      "id": 2085958499,
      "name": "The Leto Laptop",
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
    "content": "<div>Hey all, here are some high res shots of the laptop hardware that we can use. These are not public yet, so be careful with how you share them. We don't want any leaks at all with these images.</div>\n<bc-attachment sgid=\"BAh7CEkiCGdpZAY6BkVUSSIvZ2lkOi8vYmMzL0F0dGFjaG1lbnQvMTA0NjYyODQ3Nz9leHBpcmVzX2luBjsAVEkiDHB1cnBvc2UGOwBUSSIPYXR0YWNoYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--84b918badb15ad28a6f897cea3b3d406c6223017\" content-type=\"image/jpeg\" href=\"http://storage.3.basecamp.test/195539477/blobs/5713ef53a57c9b7d79083f56afb1be6ca5a1ba53/download/images-laptop_1.jpg\" filename=\"images-laptop_1.jpg\" filesize=\"72\"><figure>\n  <figcaption>\n    images-laptop_1.jpg\n  </figcaption>\n</figure></bc-attachment>\n<bc-attachment sgid=\"BAh7CEkiCGdpZAY6BkVUSSIvZ2lkOi8vYmMzL0F0dGFjaG1lbnQvMTA0NjYyODQ3OD9leHBpcmVzX2luBjsAVEkiDHB1cnBvc2UGOwBUSSIPYXR0YWNoYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--cb367ba6eb962461eff0f1615d53815ea9cd8a1e\" content-type=\"image/jpeg\" href=\"http://storage.3.basecamp.test/195539477/blobs/586505231fbae3bc04ae92da03093d1112b8f620/download/images-laptop_2.jpg\" filename=\"images-laptop_2.jpg\" filesize=\"72\"><figure>\n  <figcaption>\n    images-laptop_2.jpg\n  </figcaption>\n</figure></bc-attachment>\n<bc-attachment sgid=\"BAh7CEkiCGdpZAY6BkVUSSIvZ2lkOi8vYmMzL0F0dGFjaG1lbnQvMTA0NjYyODQ3OT9leHBpcmVzX2luBjsAVEkiDHB1cnBvc2UGOwBUSSIPYXR0YWNoYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--b496342f9ab81cfe64920d43856b8aa6cb647d0d\" content-type=\"image/jpeg\" href=\"http://storage.3.basecamp.test/195539477/blobs/b6f88c8e96f1a086008cf3ac9e1e4a703b6000ab/download/images-laptop_3.jpg\" filename=\"images-laptop_3.jpg\" filesize=\"72\"><figure>\n  <figcaption>\n    images-laptop_3.jpg\n  </figcaption>\n</figure></bc-attachment>\n<bc-attachment sgid=\"BAh7CEkiCGdpZAY6BkVUSSIvZ2lkOi8vYmMzL0F0dGFjaG1lbnQvMTA0NjYyODQ4MD9leHBpcmVzX2luBjsAVEkiDHB1cnBvc2UGOwBUSSIPYXR0YWNoYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--63e7e319c92bea31fb62eb53fbe30ed980651895\" content-type=\"image/jpeg\" href=\"http://storage.3.basecamp.test/195539477/blobs/523146fe3521c5faaba604700b5b6d5d88fc7310/download/images-laptop_4.jpg\" filename=\"images-laptop_4.jpg\" filesize=\"72\"><figure>\n  <figcaption>\n    images-laptop_4.jpg\n  </figcaption>\n</figure></bc-attachment>\n<bc-attachment sgid=\"BAh7CEkiCGdpZAY6BkVUSSIvZ2lkOi8vYmMzL0F0dGFjaG1lbnQvMTA0NjYyODQ4MT9leHBpcmVzX2luBjsAVEkiDHB1cnBvc2UGOwBUSSIPYXR0YWNoYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--4bdabf5b4567e4aa7e87f93cd5fe0d88a4a0d7ef\" content-type=\"image/jpeg\" href=\"http://storage.3.basecamp.test/195539477/blobs/ead3dae0ffd7eb1e2259202f171a66e7e25e2407/download/images-laptop_5.jpg\" filename=\"images-laptop_5.jpg\" filesize=\"72\"><figure>\n  <figcaption>\n    images-laptop_5.jpg\n  </figcaption>\n</figure></bc-attachment>\n<bc-attachment sgid=\"BAh7CEkiCGdpZAY6BkVUSSIvZ2lkOi8vYmMzL0F0dGFjaG1lbnQvMTA0NjYyODQ4Mj9leHBpcmVzX2luBjsAVEkiDHB1cnBvc2UGOwBUSSIPYXR0YWNoYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--e67c73a59c0838e9076e28c64712f8d02c0fdcd9\" content-type=\"image/jpeg\" href=\"http://storage.3.basecamp.test/195539477/blobs/ee2c53dbe6756bda7453f312ed90b52074cba10d/download/images-laptop_6.jpg\" filename=\"images-laptop_6.jpg\" filesize=\"72\"><figure>\n  <figcaption>\n    images-laptop_6.jpg\n  </figcaption>\n</figure></bc-attachment>\n<bc-attachment sgid=\"BAh7CEkiCGdpZAY6BkVUSSIvZ2lkOi8vYmMzL0F0dGFjaG1lbnQvMTA0NjYyODQ4Mz9leHBpcmVzX2luBjsAVEkiDHB1cnBvc2UGOwBUSSIPYXR0YWNoYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--f71ced2e45d873c8a57c436e7839d4bffa5e2d95\" content-type=\"image/jpeg\" href=\"http://storage.3.basecamp.test/195539477/blobs/ffdce7d75b84e35a592c2b2d57b1564d155b1c4c/download/images-laptop_7.jpg\" filename=\"images-laptop_7.jpg\" filesize=\"72\"><figure>\n  <figcaption>\n    images-laptop_7.jpg\n  </figcaption>\n</figure></bc-attachment>\n<bc-attachment sgid=\"BAh7CEkiCGdpZAY6BkVUSSIvZ2lkOi8vYmMzL0F0dGFjaG1lbnQvMTA0NjYyODQ4ND9leHBpcmVzX2luBjsAVEkiDHB1cnBvc2UGOwBUSSIPYXR0YWNoYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--4b07b015e135c6e114f8fdf5ff4549ca398ed0a1\" content-type=\"image/jpeg\" href=\"http://storage.3.basecamp.test/195539477/blobs/3c9c4a56599411e2a2c5c612b67aa8734f52fd88/download/images-laptop_8.jpg\" filename=\"images-laptop_8.jpg\" filesize=\"72\"><figure>\n  <figcaption>\n    images-laptop_8.jpg\n  </figcaption>\n</figure></bc-attachment>\n<bc-attachment sgid=\"BAh7CEkiCGdpZAY6BkVUSSIvZ2lkOi8vYmMzL0F0dGFjaG1lbnQvMTA0NjYyODQ4NT9leHBpcmVzX2luBjsAVEkiDHB1cnBvc2UGOwBUSSIPYXR0YWNoYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--de238ce05aad8d1058c8e54080fc407fd1754bc4\" content-type=\"image/jpeg\" href=\"http://storage.3.basecamp.test/195539477/blobs/d8592cb4f60cc9b7c4b9fe9d54165121d5fbe1df/download/images-laptop_9.jpg\" filename=\"images-laptop_9.jpg\" filesize=\"72\"><figure>\n  <figcaption>\n    images-laptop_9.jpg\n  </figcaption>\n</figure></bc-attachment>\n<bc-attachment sgid=\"BAh7CEkiCGdpZAY6BkVUSSIvZ2lkOi8vYmMzL0F0dGFjaG1lbnQvMTA0NjYyODQ4Nj9leHBpcmVzX2luBjsAVEkiDHB1cnBvc2UGOwBUSSIPYXR0YWNoYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--cd3f5a3e3d25e5337125e201d2a9f92d86e1736d\" content-type=\"image/jpeg\" href=\"http://storage.3.basecamp.test/195539477/blobs/4786954c9702fca935d5d7d17423967ac21ffd10/download/images-laptop_10.jpg\" filename=\"images-laptop_10.jpg\" filesize=\"73\"><figure>\n  <figcaption>\n    images-laptop_10.jpg\n  </figcaption>\n</figure></bc-attachment>\n<bc-attachment sgid=\"BAh7CEkiCGdpZAY6BkVUSSIvZ2lkOi8vYmMzL0F0dGFjaG1lbnQvMTA0NjYyODQ4Nz9leHBpcmVzX2luBjsAVEkiDHB1cnBvc2UGOwBUSSIPYXR0YWNoYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--024575e58ef67e0fa65457ddbeeeef61645e32b3\" content-type=\"image/jpeg\" href=\"http://storage.3.basecamp.test/195539477/blobs/618f2f0dcd2ec95ce9ccc18842ed2456857f4018/download/images-laptop_11.jpg\" filename=\"images-laptop_11.jpg\" filesize=\"73\"><figure>\n  <figcaption>\n    images-laptop_11.jpg\n  </figcaption>\n</figure></bc-attachment>\n<bc-attachment sgid=\"BAh7CEkiCGdpZAY6BkVUSSIvZ2lkOi8vYmMzL0F0dGFjaG1lbnQvMTA0NjYyODQ4OD9leHBpcmVzX2luBjsAVEkiDHB1cnBvc2UGOwBUSSIPYXR0YWNoYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--1b3cf015ab98ca5e9a023ec50ea94591bdd15f91\" content-type=\"image/jpeg\" href=\"http://storage.3.basecamp.test/195539477/blobs/970db0b81e795f25d30963c3577d18db44943429/download/images-laptop_12.jpg\" filename=\"images-laptop_12.jpg\" filesize=\"73\"><figure>\n  <figcaption>\n    images-laptop_12.jpg\n  </figcaption>\n</figure></bc-attachment>\n<bc-attachment sgid=\"BAh7CEkiCGdpZAY6BkVUSSIvZ2lkOi8vYmMzL0F0dGFjaG1lbnQvMTA0NjYyODQ4OT9leHBpcmVzX2luBjsAVEkiDHB1cnBvc2UGOwBUSSIPYXR0YWNoYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--77389cdc814085380ea647a7a37c439960ce4e92\" content-type=\"image/jpeg\" href=\"http://storage.3.basecamp.test/195539477/blobs/8459c044e4504fe4a3396028e481ac63ec81f999/download/images-laptop_13.jpg\" filename=\"images-laptop_13.jpg\" filesize=\"73\"><figure>\n  <figcaption>\n    images-laptop_13.jpg\n  </figcaption>\n</figure></bc-attachment>\n<bc-attachment sgid=\"BAh7CEkiCGdpZAY6BkVUSSIvZ2lkOi8vYmMzL0F0dGFjaG1lbnQvMTA0NjYyODQ5MD9leHBpcmVzX2luBjsAVEkiDHB1cnBvc2UGOwBUSSIPYXR0YWNoYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--ca6d202373731fb4704964724761f0d0c16285a2\" content-type=\"image/jpeg\" href=\"http://storage.3.basecamp.test/195539477/blobs/94ff9e0ccb2447155905e13d6899753e815641a6/download/images-laptop_14.jpg\" filename=\"images-laptop_14.jpg\" filesize=\"73\"><figure>\n  <figcaption>\n    images-laptop_14.jpg\n  </figcaption>\n</figure></bc-attachment>",
    "subject": "Laptop high res glamour shots"
  }
]
```
<!-- END GET /buckets/1/message_boards/3/messages.json -->
###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/message_boards/3/messages.json
```


Get a message
-------------

* `GET /buckets/1/messages/2.json` will return the message with an ID of `2` in the project with an ID of `1`.

###### Example JSON Response
<!-- START GET /buckets/1/messages/2.json -->
```json
{
  "id": 1069479351,
  "status": "active",
  "visible_to_clients": false,
  "created_at": "2022-10-29T10:17:58.169Z",
  "updated_at": "2022-11-22T17:53:36.289Z",
  "title": "We won Leto!",
  "inherits_status": true,
  "type": "Message",
  "url": "https://3.basecampapi.com/195539477/buckets/2085958499/messages/1069479351.json",
  "app_url": "https://3.basecamp.com/195539477/buckets/2085958499/messages/1069479351",
  "bookmark_url": "https://3.basecamp.com/195539477/my/bookmarks/BAh7CEkiCGdpZAY6BkVUSSIuZ2lkOi8vYmMzL1JlY29yZGluZy8xMDY5NDc5MzUxP2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg1yZWFkYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--8d413a5e5694e558bd418b7a0ced751d7c9cf921",
  "subscription_url": "https://3.basecamp.com/195539477/buckets/2085958499/recordings/1069479351/subscription",
  "comments_count": 10,
  "comments_url": "https://3.basecampapi.com/195539477/buckets/2085958499/recordings/1069479351/comments.json",
  "parent": {
    "id": 1069479338,
    "title": "Message Board",
    "type": "Message::Board",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958499/message_boards/1069479338.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958499/message_boards/1069479338"
  },
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
  "content": "<div>Hey guys,\n\n  We won the Leto account! This is huge for us, it really marks a turning point for the company.\n\n  As you know we've been pursuing bigger clients in the consumer space, but we've done so carefully. We've never been about getting the biggest clients - those are easy to get. We've been trying to get the best clients for us - ones that will challenge us, grow us, make us better, and ultimately giving us a platform to show how awesome you guys all are. And now we have that!\n\n  A big congrats to everyone who worked so hard to make this happen, and now the fun really begins. Most of the pitch team will stay on as leading members of the first project, the Leto Microsite.\n\n  Again, great job everyone, and let's go kick some more butt!\n\n  -Victor</div>",
  "subject": "We won Leto!"
}
```
<!-- END GET /buckets/1/messages/2.json -->

###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/messages/2.json
```


Create a message
----------------

* `POST /buckets/1/message_boards/3/messages.json` publishes a message in the project with ID `1` and under the message board with an ID of `3`.

**Required parameters**: `subject` as the title of the message, and `status`, set to `active` to publish immediately.

_Optional parameters_: 

* `content` as the body of the message. See our [Rich text guide][4] for what HTML tags are allowed.
* `category_id` to set a type for the message. To get a list of all the message types for a project, see the [Get message types][5] endpoint. 
* `subscriptions` an array of people IDs to be notified of the new message when it's posted and subscribed to it. If not present, all people on the project will be notified and subscribed.
* `visible_to_clients` boolean setting the visiblility of the created message. Default `false`

This endpoint will return `201 Created` with the current JSON representation of the message if the creation was a success. See the [Get a message](#get-a-message) endpoint for more info on the payload.

###### Example JSON Request

``` json
{
  "subject": "Kickoff",
  "content": "<div><strong>Welcome to Basecamp, everyone.</strong></div>",
  "status": "active"
}
```

###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -H "Content-Type: application/json" \
  -d '{"subject":"Kickoff","content":"<div><strong>Welcome to Basecamp, everyone.</strong></div>","status":"active"}' \
  https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/message_boards/3/messages.json
```


Update a message
----------------

* `PUT /buckets/1/messages/2.json` allows changing the `subject`, `content` and `category_id` of the message with an ID of `2` in the project with ID `1`.

This endpoint will return `200 OK` with the current JSON representation of the message if the update was a success. See the [Get a message](#get-a-message) endpoint for more info on the payload.

###### Example JSON Request

``` json
{
  "subject": "Spin-down",
  "content": "<div><strong>Oops, we lost that client.</strong></div>"
}
```

###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -H "Content-Type: application/json" \
  -d '{"subject":"Spin-down","content":"<div><strong>Oops, we lost that client.</strong></div>"}' -X PUT \
  https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/messages/2.json
```

Pin a message
----------------

* `POST /buckets/1/recordings/2/pin.json` pins the message with ID `2` in the project with id `1`.
* `DELETE /buckets/1/recordings/2/pin.json` unpins the message with ID `2` in the project with id `1`.

This endpoint will return `204 No content` if the operation was a success.

###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -H "Content-Type: application/json" \
  -X POST \
  https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/recordings/2/pin.json
```
``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -H "Content-Type: application/json" \
  -X DELETE \
  https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/recordings/2/pin.json
```

[1]: https://github.com/basecamp/bc3-api/blob/master/sections/recordings.md#trash-a-recording
[2]: https://github.com/basecamp/bc3-api/blob/master/README.md#pagination
[3]: https://github.com/basecamp/bc3-api/blob/master/sections/message_boards.md#message-boards
[4]: https://github.com/basecamp/bc3-api/blob/master/sections/rich_text.md
[5]: https://github.com/basecamp/bc3-api/blob/master/sections/message_types.md#get-message-types
