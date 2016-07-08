Messages
========

Endpoints:

- [Get messages](#get-messages)
- [Get a message](#get-a-message)
- [Create a message](#create-a-message)
- [Update a message](#update-a-message)
- [Trash a message][1]

Get messages
------------

* `GET /buckets/1/message_boards/3/messages.json` will return a [paginated list][2] of active messages in the Basecamp with an ID of `1` and the message board with ID of `3`.

To get the message board ID for a Basecamp, see the [Get message board][3] endpoint.

###### Example JSON Response
<!-- START GET /buckets/1/message_boards/3/messages.json -->
```json
[
  {
    "id": 9007199254741622,
    "status": "active",
    "created_at": "2016-07-08T18:26:11.487Z",
    "updated_at": "2016-07-08T16:49:43.893Z",
    "type": "Message",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958498/messages/9007199254741622.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958498/messages/9007199254741622",
    "comments_count": 1,
    "comments_url": "https://3.basecampapi.com/195539477/buckets/2085958498/recordings/9007199254741622/comments.json",
    "parent": {
      "id": 9007199254741434,
      "title": "Message Board",
      "type": "Message::Board",
      "url": "https://3.basecampapi.com/195539477/buckets/2085958498/message_boards/9007199254741434.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958498/message_boards/9007199254741434"
    },
    "bucket": {
      "id": 2085958498,
      "name": "The Leto Laptop",
      "type": "Project"
    },
    "creator": {
      "id": 1007299230,
      "name": "Matt Donahue",
      "email_address": "matt@honchodesign.com",
      "personable_type": "User",
      "title": "Global Data Strategist",
      "created_at": "2016-07-08T16:48:05.858Z",
      "updated_at": "2016-07-08T16:48:05.858Z",
      "admin": false,
      "owner": false,
      "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBJ4qCjw=--ff431338b1dfb8e245e454cc0ddaf0507bd859f7/avatar-64-x4"
    },
    "content_html": "Hey all, here are some high res shots of the laptop hardware that we can use. These are not public yet, so be careful with how you share them. We don't want any leaks at all with these images.<div data-trix-attachment='{\"sgid\":\"BAh7CEkiCGdpZAY6BkVUSSIvZ2lkOi8vYmMzL0F0dGFjaG1lbnQvMTAxOTczMDYzOD9leHBpcmVzX2luBjsAVEkiDHB1cnBvc2UGOwBUSSIPYXR0YWNoYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--e1d254352da6988e3f93ab67fd41d35e380a2dbe\",\"contentType\":\"image/jpeg\",\"previewable\":true,\"filename\":\"images-laptop_1.jpg\",\"filesize\":18241,\"url\":\"https://3.basecamp.com/195539477/blobs/3780e7fca2065165113ad1b3d6ec84d27246855e/previews/full/images-laptop_1.jpg\"}' data-trix-attributes=\"{}\"></div><div data-trix-attachment='{\"sgid\":\"BAh7CEkiCGdpZAY6BkVUSSIvZ2lkOi8vYmMzL0F0dGFjaG1lbnQvMTAxOTczMDYzOT9leHBpcmVzX2luBjsAVEkiDHB1cnBvc2UGOwBUSSIPYXR0YWNoYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--920a1ffa11bd68fc7bae02e9b1299e9c0f431f61\",\"contentType\":\"image/jpeg\",\"previewable\":true,\"filename\":\"images-laptop_2.jpg\",\"filesize\":30312,\"url\":\"https://3.basecamp.com/195539477/blobs/405d7c6a3ae9c95f68036644170eeb069c4a08d6/previews/full/images-laptop_2.jpg\"}' data-trix-attributes=\"{}\"></div><div data-trix-attachment='{\"sgid\":\"BAh7CEkiCGdpZAY6BkVUSSIvZ2lkOi8vYmMzL0F0dGFjaG1lbnQvMTAxOTczMDY0MD9leHBpcmVzX2luBjsAVEkiDHB1cnBvc2UGOwBUSSIPYXR0YWNoYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--5bdd138c939efeb664310823a9ecb6a10b37b169\",\"contentType\":\"image/jpeg\",\"previewable\":true,\"filename\":\"images-laptop_3.jpg\",\"filesize\":13852,\"url\":\"https://3.basecamp.com/195539477/blobs/d58bd99c9073905103b08cfbab82012066d02712/previews/full/images-laptop_3.jpg\"}' data-trix-attributes=\"{}\"></div><div data-trix-attachment='{\"sgid\":\"BAh7CEkiCGdpZAY6BkVUSSIvZ2lkOi8vYmMzL0F0dGFjaG1lbnQvMTAxOTczMDY0MT9leHBpcmVzX2luBjsAVEkiDHB1cnBvc2UGOwBUSSIPYXR0YWNoYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--9453d6ca2ca1a9a1292efc39bf7eab0c5324b0ed\",\"contentType\":\"image/jpeg\",\"previewable\":true,\"filename\":\"images-laptop_4.jpg\",\"filesize\":48488,\"url\":\"https://3.basecamp.com/195539477/blobs/c7fe0a6b9898ad2875191ec167b94d242c182820/previews/full/images-laptop_4.jpg\"}' data-trix-attributes=\"{}\"></div><div data-trix-attachment='{\"sgid\":\"BAh7CEkiCGdpZAY6BkVUSSIvZ2lkOi8vYmMzL0F0dGFjaG1lbnQvMTAxOTczMDY0Mj9leHBpcmVzX2luBjsAVEkiDHB1cnBvc2UGOwBUSSIPYXR0YWNoYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--029dece186956f67bb0b71831dae24e3e240f660\",\"contentType\":\"image/jpeg\",\"previewable\":true,\"filename\":\"images-laptop_5.jpg\",\"filesize\":140435,\"url\":\"https://3.basecamp.com/195539477/blobs/d28e52067f0aa316a6636519b5b13b5af807f106/previews/full/images-laptop_5.jpg\"}' data-trix-attributes=\"{}\"></div><div data-trix-attachment='{\"sgid\":\"BAh7CEkiCGdpZAY6BkVUSSIvZ2lkOi8vYmMzL0F0dGFjaG1lbnQvMTAxOTczMDY0Mz9leHBpcmVzX2luBjsAVEkiDHB1cnBvc2UGOwBUSSIPYXR0YWNoYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--7b4951c95dcab3802217664bec15a3578d7aaf6f\",\"contentType\":\"image/jpeg\",\"previewable\":true,\"filename\":\"images-laptop_6.jpg\",\"filesize\":25658,\"url\":\"https://3.basecamp.com/195539477/blobs/774547a276a27b18a73abec9b2afa68c411304fa/previews/full/images-laptop_6.jpg\"}' data-trix-attributes=\"{}\"></div><div data-trix-attachment='{\"sgid\":\"BAh7CEkiCGdpZAY6BkVUSSIvZ2lkOi8vYmMzL0F0dGFjaG1lbnQvMTAxOTczMDY0ND9leHBpcmVzX2luBjsAVEkiDHB1cnBvc2UGOwBUSSIPYXR0YWNoYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--708b86b461d818a592020bb7daba654b4b052199\",\"contentType\":\"image/jpeg\",\"previewable\":true,\"filename\":\"images-laptop_7.jpg\",\"filesize\":318977,\"url\":\"https://3.basecamp.com/195539477/blobs/5b365c54b249a70e458f95531eda8571059ba5e0/previews/full/images-laptop_7.jpg\"}' data-trix-attributes=\"{}\"></div><div data-trix-attachment='{\"sgid\":\"BAh7CEkiCGdpZAY6BkVUSSIvZ2lkOi8vYmMzL0F0dGFjaG1lbnQvMTAxOTczMDY0NT9leHBpcmVzX2luBjsAVEkiDHB1cnBvc2UGOwBUSSIPYXR0YWNoYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--6e4c71da03c44133ea3f00d053cf17fed5f0099b\",\"contentType\":\"image/jpeg\",\"previewable\":true,\"filename\":\"images-laptop_8.jpg\",\"filesize\":51341,\"url\":\"https://3.basecamp.com/195539477/blobs/13a033e4cefaba7d5298efeceae0150a19428a3b/previews/full/images-laptop_8.jpg\"}' data-trix-attributes=\"{}\"></div><div data-trix-attachment='{\"sgid\":\"BAh7CEkiCGdpZAY6BkVUSSIvZ2lkOi8vYmMzL0F0dGFjaG1lbnQvMTAxOTczMDY0Nj9leHBpcmVzX2luBjsAVEkiDHB1cnBvc2UGOwBUSSIPYXR0YWNoYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--2f575303b8eebe4b004d951c17a0d82111c8a438\",\"contentType\":\"image/jpeg\",\"previewable\":true,\"filename\":\"images-laptop_9.jpg\",\"filesize\":369239,\"url\":\"https://3.basecamp.com/195539477/blobs/e5d0b856a66c09ae6c12da6a478da70844330194/previews/full/images-laptop_9.jpg\"}' data-trix-attributes=\"{}\"></div><div data-trix-attachment='{\"sgid\":\"BAh7CEkiCGdpZAY6BkVUSSIvZ2lkOi8vYmMzL0F0dGFjaG1lbnQvMTAxOTczMDY0Nz9leHBpcmVzX2luBjsAVEkiDHB1cnBvc2UGOwBUSSIPYXR0YWNoYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--310e8cd4f210f2a81e1f1c44c37af697868a74a4\",\"contentType\":\"image/jpeg\",\"previewable\":true,\"filename\":\"images-laptop_10.jpg\",\"filesize\":25429,\"url\":\"https://3.basecamp.com/195539477/blobs/17389ad92ee40045375fd92c6d4c866c4b371a85/previews/full/images-laptop_10.jpg\"}' data-trix-attributes=\"{}\"></div><div data-trix-attachment='{\"sgid\":\"BAh7CEkiCGdpZAY6BkVUSSIvZ2lkOi8vYmMzL0F0dGFjaG1lbnQvMTAxOTczMDY0OD9leHBpcmVzX2luBjsAVEkiDHB1cnBvc2UGOwBUSSIPYXR0YWNoYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--d510fe39f9e5f9bf4f50591249e4f6550270640b\",\"contentType\":\"image/jpeg\",\"previewable\":true,\"filename\":\"images-laptop_11.jpg\",\"filesize\":20839,\"url\":\"https://3.basecamp.com/195539477/blobs/8d71d655439ce48c83a009b53a77424a7e77c49b/previews/full/images-laptop_11.jpg\"}' data-trix-attributes=\"{}\"></div><div data-trix-attachment='{\"sgid\":\"BAh7CEkiCGdpZAY6BkVUSSIvZ2lkOi8vYmMzL0F0dGFjaG1lbnQvMTAxOTczMDY0OT9leHBpcmVzX2luBjsAVEkiDHB1cnBvc2UGOwBUSSIPYXR0YWNoYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--1a60d6d2345b328752c1656f4aa79e478e1ccd58\",\"contentType\":\"image/jpeg\",\"previewable\":true,\"filename\":\"images-laptop_12.jpg\",\"filesize\":137872,\"url\":\"https://3.basecamp.com/195539477/blobs/e838e138fffa8bb4f0668006874846170f178a6f/previews/full/images-laptop_12.jpg\"}' data-trix-attributes=\"{}\"></div><div data-trix-attachment='{\"sgid\":\"BAh7CEkiCGdpZAY6BkVUSSIvZ2lkOi8vYmMzL0F0dGFjaG1lbnQvMTAxOTczMDY1MD9leHBpcmVzX2luBjsAVEkiDHB1cnBvc2UGOwBUSSIPYXR0YWNoYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--0244ce80196375935623751921dcc8b58d5bf3a3\",\"contentType\":\"image/jpeg\",\"previewable\":true,\"filename\":\"images-laptop_13.jpg\",\"filesize\":62024,\"url\":\"https://3.basecamp.com/195539477/blobs/60df4b0591ac41f52cb12a5c78d7124bd0fc2a30/previews/full/images-laptop_13.jpg\"}' data-trix-attributes=\"{}\"></div><div data-trix-attachment='{\"sgid\":\"BAh7CEkiCGdpZAY6BkVUSSIvZ2lkOi8vYmMzL0F0dGFjaG1lbnQvMTAxOTczMDY1MT9leHBpcmVzX2luBjsAVEkiDHB1cnBvc2UGOwBUSSIPYXR0YWNoYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--94e7383ecdef3e0ad5ae92e340784717e750c1de\",\"contentType\":\"image/jpeg\",\"previewable\":true,\"filename\":\"images-laptop_14.jpg\",\"filesize\":81082,\"url\":\"https://3.basecamp.com/195539477/blobs/a9afbb12573a45d4b1f4ad5dd66d76ad51f30543/previews/full/images-laptop_14.jpg\"}' data-trix-attributes=\"{}\"></div>",
    "content_text": "Hey all, here are some high res shots of the laptop hardware that we can use. These are not public yet, so be careful with how you share them. We don't want any leaks at all with these images.",
    "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7CEkiCGdpZAY6BkVUSSI0Z2lkOi8vYmMzL1JlY29yZGluZy85MDA3MTk5MjU0NzQxNjIyP2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg1yZWFkYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--422f61efafb9879901eef751ef7ef4822741fea9.json",
    "subscription_url": "https://3.basecampapi.com/195539477/buckets/2085958498/recordings/9007199254741622/subscription.json",
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

* `GET /buckets/1/messages/2.json` will return the message with an ID of `2` in the Basecamp with an ID of `1`.

###### Example JSON Response
<!-- START GET /buckets/1/messages/2.json -->
```json
{
  "id": 9007199254741443,
  "status": "active",
  "created_at": "2016-06-14T19:40:11.487Z",
  "updated_at": "2016-07-08T16:49:14.872Z",
  "type": "Message",
  "url": "https://3.basecampapi.com/195539477/buckets/2085958498/messages/9007199254741443.json",
  "app_url": "https://3.basecamp.com/195539477/buckets/2085958498/messages/9007199254741443",
  "comments_count": 10,
  "comments_url": "https://3.basecampapi.com/195539477/buckets/2085958498/recordings/9007199254741443/comments.json",
  "parent": {
    "id": 9007199254741434,
    "title": "Message Board",
    "type": "Message::Board",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958498/message_boards/9007199254741434.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958498/message_boards/9007199254741434"
  },
  "bucket": {
    "id": 2085958498,
    "name": "The Leto Laptop",
    "type": "Project"
  },
  "creator": {
    "id": 1007299208,
    "name": "Victor Cooper",
    "email_address": "victor@honchodesign.com",
    "personable_type": "User",
    "title": null,
    "created_at": "2016-07-08T16:48:02.496Z",
    "updated_at": "2016-07-08T16:48:02.592Z",
    "admin": true,
    "owner": true,
    "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBIgqCjw=--719e3f2aa4406cf5806c2c1522259710deb788e4/avatar-64-x4",
    "company": {
      "id": 1033447822,
      "name": "Honcho Design"
    }
  },
  "content_html": "Hey guys,\n\n  We won the Leto account! This is huge for us, it really marks a turning point for the company.\n\n  As you know we've been pursuing bigger clients in the consumer space, but we've done so carefully. We've never been about getting the biggest clients - those are easy to get. We've been trying to get the best clients for us - ones that will challenge us, grow us, make us better, and ultimately giving us a platform to show how awesome you guys all are. And now we have that!\n\n  A big congrats to everyone who worked so hard to make this happen, and now the fun really begins. Most of the pitch team will stay on as leading members of the first project, the Leto Microsite.\n\n  Again, great job everyone, and let's go kick some more butt!\n\n  -Victor",
  "content_text": "Hey guys,\n\nWe won the Leto account! This is huge for us, it really marks a turning point for the company.\n\nAs you know we've been pursuing bigger clients in the consumer space, but we've done so carefully. We've never been about getting the biggest clients - those are easy to get. We've been trying to get the best clients for us - ones that will challenge us, grow us, make us better, and ultimately giving us a platform to show how awesome you guys all are. And now we have that!\n\nA big congrats to everyone who worked so hard to make this happen, and now the fun really begins. Most of the pitch team will stay on as leading members of the first project, the Leto Microsite.\n\nAgain, great job everyone, and let's go kick some more butt!\n\n-Victor",
  "bookmark_url": "https://3.basecamp.com/195539477/my/bookmarks/BAh7CEkiCGdpZAY6BkVUSSI0Z2lkOi8vYmMzL1JlY29yZGluZy85MDA3MTk5MjU0NzQxNDQzP2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg1yZWFkYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--0cea494978131a59de5436e67e7f01b6db1fb8f0",
  "subscription_url": "https://3.basecamp.com/195539477/buckets/2085958498/recordings/9007199254741443/subscription",
  "subject": "We won Leto!"
}
```
<!-- END GET /buckets/1/messages/2.json -->
Nesting under the message board resource is not necessary for this endpoint.

###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/messages/2.json
```


Create a message
----------------

* `POST /buckets/1/message_boards/3/messages.json` publishes a message in the Basecamp with ID `1` and under the message board with an ID of `3`.

**Required parameters**: `subject` as the title of the message, and `status`, set to `active` to publish immediately.

_Optional parameters_: `content_html` as the body of the message. See our [Rich content][4] guide for what HTML tags are allowed.

Note: All people on a Basecamp are notified of the new message when it's posted. Changing who is subscribed is coming soon!

This endpoint will return `201 Created` with the current JSON representation of the message if the creation was a success. See the [Get a message](#get-a-message) endpoint for more info on the payload.

###### Example JSON Request

``` json
{
  "subject": "Kickoff",
  "content_html": "<div><strong>Welcome to Basecamp, everyone.</strong></div>",
  "status": "active"
}
```

###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -H "Content-Type: application/json" \
  -d '{"subject":"Kickoff","content_html":"<div><strong>Welcome to Basecamp, everyone.</strong></div>","status":"active"}' \
  https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/message_boards/3/messages.json
```


Update a message
----------------

* `PUT /buckets/1/messages/2.json` allows changing the subject and content of the message with an ID of `2` in the Basecamp with ID `1`.

This endpoint will return `200 OK` with the current JSON representation of the message if the update was a success. See the [Get a message](#get-a-message) endpoint for more info on the payload.

###### Example JSON Request

``` json
{
  "subject": "Spin-down",
  "content_html": "<div><strong>Oops, we lost that client.</strong></div>"
}
```

###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -H "Content-Type: application/json" \
  -d '{"subject":"Spin-down","content_html":"<div><strong>Oops, we lost that client.</strong></div>"}' -X PUT \
  https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/messages/2.json
```


[1]: https://github.com/basecamp/bc3-api/blob/master/sections/recordings.md#trash-a-recording
[2]: https://github.com/basecamp/bc3-api/blob/master/README.md#pagination
[3]: https://github.com/basecamp/bc3-api/blob/master/sections/message_boards.md#message-boards
[4]: https://github.com/basecamp/bc3-api/blob/master/README.md#rich-content
