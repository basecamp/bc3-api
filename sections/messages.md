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
    "created_at": "2016-07-08T02:52:06.221Z",
    "updated_at": "2016-07-08T02:17:31.713Z",
    "type": "Message",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958498/messages/9007199254741622.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958498/messages/9007199254741622",
    "comments_count": 1,
    "comments_url": "https://3.basecampapi.com/195539477/buckets/2085958498/recordings/9007199254741622/comments.json",
    "bucket": {
      "id": 2085958498,
      "type": "Project"
    },
    "parent": {
      "id": 9007199254741434,
      "type": "Message::Board",
      "url": "https://3.basecampapi.com/195539477/buckets/2085958498/message_boards/9007199254741434.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958498/message_boards/9007199254741434"
    },
    "creator": {
      "id": 1007299165,
      "name": "Matt Donahue",
      "email_address": "matt@honchodesign.com",
      "personable_type": "User",
      "title": "Global Data Strategist",
      "created_at": "2016-07-08T02:16:10.850Z",
      "updated_at": "2016-07-08T02:16:10.850Z",
      "admin": false,
      "owner": false,
      "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBF0qCjw=--21513efb0cf6f64f7a0720b2c56ac6145ae6680c/avatar-64-x4"
    },
    "content_html": "Hey all, here are some high res shots of the laptop hardware that we can use. These are not public yet, so be careful with how you share them. We don't want any leaks at all with these images.<div data-trix-attachment='{\"sgid\":\"BAh7CEkiCGdpZAY6BkVUSSIvZ2lkOi8vYmMzL0F0dGFjaG1lbnQvMTAxOTczMDUxMD9leHBpcmVzX2luBjsAVEkiDHB1cnBvc2UGOwBUSSIPYXR0YWNoYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--592aadadb870f5984557f268717d9084d44ac29f\",\"contentType\":\"image/jpeg\",\"previewable\":true,\"filename\":\"images-laptop_1.jpg\",\"filesize\":18241,\"url\":\"https://3.basecamp.com/195539477/blobs/37e609eac3b489322cb4781d5859d865aaee5cb7/previews/full/images-laptop_1.jpg\"}' data-trix-attributes=\"{}\"></div><div data-trix-attachment='{\"sgid\":\"BAh7CEkiCGdpZAY6BkVUSSIvZ2lkOi8vYmMzL0F0dGFjaG1lbnQvMTAxOTczMDUxMT9leHBpcmVzX2luBjsAVEkiDHB1cnBvc2UGOwBUSSIPYXR0YWNoYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--62a3d1cb555cd4e0e75c07d91fdbce65148e36b4\",\"contentType\":\"image/jpeg\",\"previewable\":true,\"filename\":\"images-laptop_2.jpg\",\"filesize\":30312,\"url\":\"https://3.basecamp.com/195539477/blobs/e3cb619f5ed8aea8a8a0372f06c0f98ca681cfe8/previews/full/images-laptop_2.jpg\"}' data-trix-attributes=\"{}\"></div><div data-trix-attachment='{\"sgid\":\"BAh7CEkiCGdpZAY6BkVUSSIvZ2lkOi8vYmMzL0F0dGFjaG1lbnQvMTAxOTczMDUxMj9leHBpcmVzX2luBjsAVEkiDHB1cnBvc2UGOwBUSSIPYXR0YWNoYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--03e3397841118f2c697a7b34295803244128fd9b\",\"contentType\":\"image/jpeg\",\"previewable\":true,\"filename\":\"images-laptop_3.jpg\",\"filesize\":13852,\"url\":\"https://3.basecamp.com/195539477/blobs/13f9e94f8c251cf33904d952b5f7632e87667d3b/previews/full/images-laptop_3.jpg\"}' data-trix-attributes=\"{}\"></div><div data-trix-attachment='{\"sgid\":\"BAh7CEkiCGdpZAY6BkVUSSIvZ2lkOi8vYmMzL0F0dGFjaG1lbnQvMTAxOTczMDUxMz9leHBpcmVzX2luBjsAVEkiDHB1cnBvc2UGOwBUSSIPYXR0YWNoYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--a848f869f12b3512835f6c33dac32f07b29f3733\",\"contentType\":\"image/jpeg\",\"previewable\":true,\"filename\":\"images-laptop_4.jpg\",\"filesize\":48488,\"url\":\"https://3.basecamp.com/195539477/blobs/9f66fe022052212f757495b88cb52a626db084c1/previews/full/images-laptop_4.jpg\"}' data-trix-attributes=\"{}\"></div><div data-trix-attachment='{\"sgid\":\"BAh7CEkiCGdpZAY6BkVUSSIvZ2lkOi8vYmMzL0F0dGFjaG1lbnQvMTAxOTczMDUxND9leHBpcmVzX2luBjsAVEkiDHB1cnBvc2UGOwBUSSIPYXR0YWNoYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--759722abf530cb66824f6ba18e0ff45d7238bc94\",\"contentType\":\"image/jpeg\",\"previewable\":true,\"filename\":\"images-laptop_5.jpg\",\"filesize\":140435,\"url\":\"https://3.basecamp.com/195539477/blobs/7e8573c4f6aa93645285bda900449c05afae4bc5/previews/full/images-laptop_5.jpg\"}' data-trix-attributes=\"{}\"></div><div data-trix-attachment='{\"sgid\":\"BAh7CEkiCGdpZAY6BkVUSSIvZ2lkOi8vYmMzL0F0dGFjaG1lbnQvMTAxOTczMDUxNT9leHBpcmVzX2luBjsAVEkiDHB1cnBvc2UGOwBUSSIPYXR0YWNoYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--a28c26f0b5a9d3374f145c0324aa7fc824a42147\",\"contentType\":\"image/jpeg\",\"previewable\":true,\"filename\":\"images-laptop_6.jpg\",\"filesize\":25658,\"url\":\"https://3.basecamp.com/195539477/blobs/cfdd471d367c9844868f613b7baa970a2c931778/previews/full/images-laptop_6.jpg\"}' data-trix-attributes=\"{}\"></div><div data-trix-attachment='{\"sgid\":\"BAh7CEkiCGdpZAY6BkVUSSIvZ2lkOi8vYmMzL0F0dGFjaG1lbnQvMTAxOTczMDUxNj9leHBpcmVzX2luBjsAVEkiDHB1cnBvc2UGOwBUSSIPYXR0YWNoYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--62eca09ca83b3d553b8effd013bcaad37b206b85\",\"contentType\":\"image/jpeg\",\"previewable\":true,\"filename\":\"images-laptop_7.jpg\",\"filesize\":318977,\"url\":\"https://3.basecamp.com/195539477/blobs/5f1545b452c258c0c5f3a927847e12dea65108c4/previews/full/images-laptop_7.jpg\"}' data-trix-attributes=\"{}\"></div><div data-trix-attachment='{\"sgid\":\"BAh7CEkiCGdpZAY6BkVUSSIvZ2lkOi8vYmMzL0F0dGFjaG1lbnQvMTAxOTczMDUxNz9leHBpcmVzX2luBjsAVEkiDHB1cnBvc2UGOwBUSSIPYXR0YWNoYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--4bbf6e7e4cee46a47d1b6c043bfa6c0a007db36b\",\"contentType\":\"image/jpeg\",\"previewable\":true,\"filename\":\"images-laptop_8.jpg\",\"filesize\":51341,\"url\":\"https://3.basecamp.com/195539477/blobs/a7b59e3fa46cc02620dd943e8b4306c54eb46642/previews/full/images-laptop_8.jpg\"}' data-trix-attributes=\"{}\"></div><div data-trix-attachment='{\"sgid\":\"BAh7CEkiCGdpZAY6BkVUSSIvZ2lkOi8vYmMzL0F0dGFjaG1lbnQvMTAxOTczMDUxOD9leHBpcmVzX2luBjsAVEkiDHB1cnBvc2UGOwBUSSIPYXR0YWNoYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--b51983a66d102e7e3ca9d7f8e053916a421cf912\",\"contentType\":\"image/jpeg\",\"previewable\":true,\"filename\":\"images-laptop_9.jpg\",\"filesize\":369239,\"url\":\"https://3.basecamp.com/195539477/blobs/8d25ff67e0cd6806e04eb3bb28cd0513e9dcbd9d/previews/full/images-laptop_9.jpg\"}' data-trix-attributes=\"{}\"></div><div data-trix-attachment='{\"sgid\":\"BAh7CEkiCGdpZAY6BkVUSSIvZ2lkOi8vYmMzL0F0dGFjaG1lbnQvMTAxOTczMDUxOT9leHBpcmVzX2luBjsAVEkiDHB1cnBvc2UGOwBUSSIPYXR0YWNoYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--43df281070f1a48f082e68ce18f03612c1cf3281\",\"contentType\":\"image/jpeg\",\"previewable\":true,\"filename\":\"images-laptop_10.jpg\",\"filesize\":25429,\"url\":\"https://3.basecamp.com/195539477/blobs/0a9063cc7e702663b0299002060239c70a9ea798/previews/full/images-laptop_10.jpg\"}' data-trix-attributes=\"{}\"></div><div data-trix-attachment='{\"sgid\":\"BAh7CEkiCGdpZAY6BkVUSSIvZ2lkOi8vYmMzL0F0dGFjaG1lbnQvMTAxOTczMDUyMD9leHBpcmVzX2luBjsAVEkiDHB1cnBvc2UGOwBUSSIPYXR0YWNoYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--021113670f9861e151e4bac1b23efa43687f54b2\",\"contentType\":\"image/jpeg\",\"previewable\":true,\"filename\":\"images-laptop_11.jpg\",\"filesize\":20839,\"url\":\"https://3.basecamp.com/195539477/blobs/ab96b02d9032e38e124c1e6f24224ca6dc3d70ef/previews/full/images-laptop_11.jpg\"}' data-trix-attributes=\"{}\"></div><div data-trix-attachment='{\"sgid\":\"BAh7CEkiCGdpZAY6BkVUSSIvZ2lkOi8vYmMzL0F0dGFjaG1lbnQvMTAxOTczMDUyMT9leHBpcmVzX2luBjsAVEkiDHB1cnBvc2UGOwBUSSIPYXR0YWNoYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--1ef625e29704c65ad2989f77e313593422b3fdee\",\"contentType\":\"image/jpeg\",\"previewable\":true,\"filename\":\"images-laptop_12.jpg\",\"filesize\":137872,\"url\":\"https://3.basecamp.com/195539477/blobs/1aa7771d49cabd3ede954e114aa98117a36b12a8/previews/full/images-laptop_12.jpg\"}' data-trix-attributes=\"{}\"></div><div data-trix-attachment='{\"sgid\":\"BAh7CEkiCGdpZAY6BkVUSSIvZ2lkOi8vYmMzL0F0dGFjaG1lbnQvMTAxOTczMDUyMj9leHBpcmVzX2luBjsAVEkiDHB1cnBvc2UGOwBUSSIPYXR0YWNoYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--3f4dee05282595cde069001a4e4ca57593fabe77\",\"contentType\":\"image/jpeg\",\"previewable\":true,\"filename\":\"images-laptop_13.jpg\",\"filesize\":62024,\"url\":\"https://3.basecamp.com/195539477/blobs/7048f1769b27f59faf44ffc671fc57467d4af5be/previews/full/images-laptop_13.jpg\"}' data-trix-attributes=\"{}\"></div><div data-trix-attachment='{\"sgid\":\"BAh7CEkiCGdpZAY6BkVUSSIvZ2lkOi8vYmMzL0F0dGFjaG1lbnQvMTAxOTczMDUyMz9leHBpcmVzX2luBjsAVEkiDHB1cnBvc2UGOwBUSSIPYXR0YWNoYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--7f1bfb82b57ece55d108c2762f1c34b35474e418\",\"contentType\":\"image/jpeg\",\"previewable\":true,\"filename\":\"images-laptop_14.jpg\",\"filesize\":81082,\"url\":\"https://3.basecamp.com/195539477/blobs/330a5adcb4d3bb136a8747f0fc02864bdf4d466e/previews/full/images-laptop_14.jpg\"}' data-trix-attributes=\"{}\"></div>",
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
  "created_at": "2016-06-14T03:55:06.221Z",
  "updated_at": "2016-07-08T02:17:08.675Z",
  "type": "Message",
  "url": "https://3.basecampapi.com/195539477/buckets/2085958498/messages/9007199254741443.json",
  "app_url": "https://3.basecamp.com/195539477/buckets/2085958498/messages/9007199254741443",
  "comments_count": 10,
  "comments_url": "https://3.basecampapi.com/195539477/buckets/2085958498/recordings/9007199254741443/comments.json",
  "bucket": {
    "id": 2085958498,
    "type": "Project"
  },
  "parent": {
    "id": 9007199254741434,
    "type": "Message::Board",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958498/message_boards/9007199254741434.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958498/message_boards/9007199254741434"
  },
  "creator": {
    "id": 1007299143,
    "name": "Victor Cooper",
    "email_address": "victor@honchodesign.com",
    "personable_type": "User",
    "title": null,
    "created_at": "2016-07-08T02:16:07.483Z",
    "updated_at": "2016-07-08T02:16:11.821Z",
    "admin": true,
    "owner": true,
    "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBEcqCjw=--c632b967cec296b87363a697a67a87f9cc1e5b45/avatar-64-x4",
    "company": {
      "id": 1033447817,
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
