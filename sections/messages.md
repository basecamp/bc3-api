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
    "created_at": "2016-06-27T18:02:10.480Z",
    "updated_at": "2016-06-27T17:30:37.518Z",
    "bucket_path": "/195539477/buckets/2085958498",
    "type": "Message",
    "comments_count": 1,
    "url": "https://3.basecampapi.com/195539477/buckets/2085958498/messages/9007199254741622.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958498/messages/9007199254741622",
    "creator": {
      "id": 1007299165,
      "name": "Matt Donahue",
      "email_address": "matt@honchodesign.com",
      "personable_type": "User",
      "title": "Global Data Strategist",
      "created_at": "2016-06-27T17:29:15.846Z",
      "updated_at": "2016-06-27T17:29:15.846Z",
      "admin": false,
      "owner": false,
      "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBF0qCjw=--21513efb0cf6f64f7a0720b2c56ac6145ae6680c/avatar-64-x4"
    },
    "bucket": {
      "id": 1042979252,
      "account_id": 1009501286,
      "name": "The Leto Laptop",
      "description": "Laptop product launch.",
      "created_at": "2016-06-02T17:30:10.480Z",
      "updated_at": "2016-06-02T17:30:10.480Z",
      "creator_id": 1007299143,
      "client_company_id": null
    },
    "parent": {
      "id": 9007199254741434,
      "title": "Message Board",
      "url": "https://3.basecampapi.com/195539477/buckets/2085958498/message_boards/9007199254741434.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958498/message_boards/9007199254741434"
    },
    "content_html": "Hey all, here are some high res shots of the laptop hardware that we can use. These are not public yet, so be careful with how you share them. We don't want any leaks at all with these images.<div data-trix-attachment='{\"sgid\":\"BAh7CEkiCGdpZAY6BkVUSSIvZ2lkOi8vYmMzL0F0dGFjaG1lbnQvMTAxOTczMDUxMD9leHBpcmVzX2luBjsAVEkiDHB1cnBvc2UGOwBUSSIPYXR0YWNoYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--592aadadb870f5984557f268717d9084d44ac29f\",\"contentType\":\"image/jpeg\",\"previewable\":true,\"filename\":\"images-laptop_1.jpg\",\"filesize\":18241,\"url\":\"https://3.basecamp.com/195539477/blobs/2f7d995342877227f8c406b0114881d95d3ef787/previews/full/images-laptop_1.jpg\"}' data-trix-attributes=\"{}\"></div><div data-trix-attachment='{\"sgid\":\"BAh7CEkiCGdpZAY6BkVUSSIvZ2lkOi8vYmMzL0F0dGFjaG1lbnQvMTAxOTczMDUxMT9leHBpcmVzX2luBjsAVEkiDHB1cnBvc2UGOwBUSSIPYXR0YWNoYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--62a3d1cb555cd4e0e75c07d91fdbce65148e36b4\",\"contentType\":\"image/jpeg\",\"previewable\":true,\"filename\":\"images-laptop_2.jpg\",\"filesize\":30312,\"url\":\"https://3.basecamp.com/195539477/blobs/ef316ed0ef5645867147f069c7f381d633e6134a/previews/full/images-laptop_2.jpg\"}' data-trix-attributes=\"{}\"></div><div data-trix-attachment='{\"sgid\":\"BAh7CEkiCGdpZAY6BkVUSSIvZ2lkOi8vYmMzL0F0dGFjaG1lbnQvMTAxOTczMDUxMj9leHBpcmVzX2luBjsAVEkiDHB1cnBvc2UGOwBUSSIPYXR0YWNoYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--03e3397841118f2c697a7b34295803244128fd9b\",\"contentType\":\"image/jpeg\",\"previewable\":true,\"filename\":\"images-laptop_3.jpg\",\"filesize\":13852,\"url\":\"https://3.basecamp.com/195539477/blobs/ace935ed0c34459d94d0824d5e4970dc8e488e60/previews/full/images-laptop_3.jpg\"}' data-trix-attributes=\"{}\"></div><div data-trix-attachment='{\"sgid\":\"BAh7CEkiCGdpZAY6BkVUSSIvZ2lkOi8vYmMzL0F0dGFjaG1lbnQvMTAxOTczMDUxMz9leHBpcmVzX2luBjsAVEkiDHB1cnBvc2UGOwBUSSIPYXR0YWNoYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--a848f869f12b3512835f6c33dac32f07b29f3733\",\"contentType\":\"image/jpeg\",\"previewable\":true,\"filename\":\"images-laptop_4.jpg\",\"filesize\":48488,\"url\":\"https://3.basecamp.com/195539477/blobs/33779cf6aeb049206efbfd8f7f76fbcbc832b8b9/previews/full/images-laptop_4.jpg\"}' data-trix-attributes=\"{}\"></div><div data-trix-attachment='{\"sgid\":\"BAh7CEkiCGdpZAY6BkVUSSIvZ2lkOi8vYmMzL0F0dGFjaG1lbnQvMTAxOTczMDUxND9leHBpcmVzX2luBjsAVEkiDHB1cnBvc2UGOwBUSSIPYXR0YWNoYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--759722abf530cb66824f6ba18e0ff45d7238bc94\",\"contentType\":\"image/jpeg\",\"previewable\":true,\"filename\":\"images-laptop_5.jpg\",\"filesize\":140435,\"url\":\"https://3.basecamp.com/195539477/blobs/42a0d0d5ca36c66b67fc48fb46c2b180f9d90aa8/previews/full/images-laptop_5.jpg\"}' data-trix-attributes=\"{}\"></div><div data-trix-attachment='{\"sgid\":\"BAh7CEkiCGdpZAY6BkVUSSIvZ2lkOi8vYmMzL0F0dGFjaG1lbnQvMTAxOTczMDUxNT9leHBpcmVzX2luBjsAVEkiDHB1cnBvc2UGOwBUSSIPYXR0YWNoYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--a28c26f0b5a9d3374f145c0324aa7fc824a42147\",\"contentType\":\"image/jpeg\",\"previewable\":true,\"filename\":\"images-laptop_6.jpg\",\"filesize\":25658,\"url\":\"https://3.basecamp.com/195539477/blobs/0b1dbd1f2578a068989576d6d857ab7740305c2d/previews/full/images-laptop_6.jpg\"}' data-trix-attributes=\"{}\"></div><div data-trix-attachment='{\"sgid\":\"BAh7CEkiCGdpZAY6BkVUSSIvZ2lkOi8vYmMzL0F0dGFjaG1lbnQvMTAxOTczMDUxNj9leHBpcmVzX2luBjsAVEkiDHB1cnBvc2UGOwBUSSIPYXR0YWNoYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--62eca09ca83b3d553b8effd013bcaad37b206b85\",\"contentType\":\"image/jpeg\",\"previewable\":true,\"filename\":\"images-laptop_7.jpg\",\"filesize\":318977,\"url\":\"https://3.basecamp.com/195539477/blobs/d3f54a8bff5f3579d4d7f2f9636543b2a968c1f3/previews/full/images-laptop_7.jpg\"}' data-trix-attributes=\"{}\"></div><div data-trix-attachment='{\"sgid\":\"BAh7CEkiCGdpZAY6BkVUSSIvZ2lkOi8vYmMzL0F0dGFjaG1lbnQvMTAxOTczMDUxNz9leHBpcmVzX2luBjsAVEkiDHB1cnBvc2UGOwBUSSIPYXR0YWNoYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--4bbf6e7e4cee46a47d1b6c043bfa6c0a007db36b\",\"contentType\":\"image/jpeg\",\"previewable\":true,\"filename\":\"images-laptop_8.jpg\",\"filesize\":51341,\"url\":\"https://3.basecamp.com/195539477/blobs/b96662fa279c67b85e20d218479625f6a6b388b5/previews/full/images-laptop_8.jpg\"}' data-trix-attributes=\"{}\"></div><div data-trix-attachment='{\"sgid\":\"BAh7CEkiCGdpZAY6BkVUSSIvZ2lkOi8vYmMzL0F0dGFjaG1lbnQvMTAxOTczMDUxOD9leHBpcmVzX2luBjsAVEkiDHB1cnBvc2UGOwBUSSIPYXR0YWNoYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--b51983a66d102e7e3ca9d7f8e053916a421cf912\",\"contentType\":\"image/jpeg\",\"previewable\":true,\"filename\":\"images-laptop_9.jpg\",\"filesize\":369239,\"url\":\"https://3.basecamp.com/195539477/blobs/d10d68ec9d67c640aa72e1def79588ad51cc89bb/previews/full/images-laptop_9.jpg\"}' data-trix-attributes=\"{}\"></div><div data-trix-attachment='{\"sgid\":\"BAh7CEkiCGdpZAY6BkVUSSIvZ2lkOi8vYmMzL0F0dGFjaG1lbnQvMTAxOTczMDUxOT9leHBpcmVzX2luBjsAVEkiDHB1cnBvc2UGOwBUSSIPYXR0YWNoYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--43df281070f1a48f082e68ce18f03612c1cf3281\",\"contentType\":\"image/jpeg\",\"previewable\":true,\"filename\":\"images-laptop_10.jpg\",\"filesize\":25429,\"url\":\"https://3.basecamp.com/195539477/blobs/0cda1fb208601ab41dc4c0c62f98028132766f91/previews/full/images-laptop_10.jpg\"}' data-trix-attributes=\"{}\"></div><div data-trix-attachment='{\"sgid\":\"BAh7CEkiCGdpZAY6BkVUSSIvZ2lkOi8vYmMzL0F0dGFjaG1lbnQvMTAxOTczMDUyMD9leHBpcmVzX2luBjsAVEkiDHB1cnBvc2UGOwBUSSIPYXR0YWNoYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--021113670f9861e151e4bac1b23efa43687f54b2\",\"contentType\":\"image/jpeg\",\"previewable\":true,\"filename\":\"images-laptop_11.jpg\",\"filesize\":20839,\"url\":\"https://3.basecamp.com/195539477/blobs/b9d96206c03e6c9657d66a056786c2c338301566/previews/full/images-laptop_11.jpg\"}' data-trix-attributes=\"{}\"></div><div data-trix-attachment='{\"sgid\":\"BAh7CEkiCGdpZAY6BkVUSSIvZ2lkOi8vYmMzL0F0dGFjaG1lbnQvMTAxOTczMDUyMT9leHBpcmVzX2luBjsAVEkiDHB1cnBvc2UGOwBUSSIPYXR0YWNoYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--1ef625e29704c65ad2989f77e313593422b3fdee\",\"contentType\":\"image/jpeg\",\"previewable\":true,\"filename\":\"images-laptop_12.jpg\",\"filesize\":137872,\"url\":\"https://3.basecamp.com/195539477/blobs/0316daf55ff38546bb653b5d057a2f55c84486e7/previews/full/images-laptop_12.jpg\"}' data-trix-attributes=\"{}\"></div><div data-trix-attachment='{\"sgid\":\"BAh7CEkiCGdpZAY6BkVUSSIvZ2lkOi8vYmMzL0F0dGFjaG1lbnQvMTAxOTczMDUyMj9leHBpcmVzX2luBjsAVEkiDHB1cnBvc2UGOwBUSSIPYXR0YWNoYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--3f4dee05282595cde069001a4e4ca57593fabe77\",\"contentType\":\"image/jpeg\",\"previewable\":true,\"filename\":\"images-laptop_13.jpg\",\"filesize\":62024,\"url\":\"https://3.basecamp.com/195539477/blobs/83598669028886545504ec3033ed3ad651a54010/previews/full/images-laptop_13.jpg\"}' data-trix-attributes=\"{}\"></div><div data-trix-attachment='{\"sgid\":\"BAh7CEkiCGdpZAY6BkVUSSIvZ2lkOi8vYmMzL0F0dGFjaG1lbnQvMTAxOTczMDUyMz9leHBpcmVzX2luBjsAVEkiDHB1cnBvc2UGOwBUSSIPYXR0YWNoYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--7f1bfb82b57ece55d108c2762f1c34b35474e418\",\"contentType\":\"image/jpeg\",\"previewable\":true,\"filename\":\"images-laptop_14.jpg\",\"filesize\":81082,\"url\":\"https://3.basecamp.com/195539477/blobs/38d57365325ece98386469b20523c41bd8e60b7d/previews/full/images-laptop_14.jpg\"}' data-trix-attributes=\"{}\"></div>",
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
  "created_at": "2016-06-03T19:15:10.480Z",
  "updated_at": "2016-06-27T17:30:12.881Z",
  "bucket_path": "/195539477/buckets/2085958498",
  "type": "Message",
  "comments_count": 10,
  "url": "https://3.basecampapi.com/195539477/buckets/2085958498/messages/9007199254741443.json",
  "app_url": "https://3.basecamp.com/195539477/buckets/2085958498/messages/9007199254741443",
  "creator": {
    "id": 1007299143,
    "name": "Victor Cooper",
    "email_address": "victor@honchodesign.com",
    "personable_type": "User",
    "title": null,
    "created_at": "2016-06-27T17:29:12.654Z",
    "updated_at": "2016-06-27T17:29:12.752Z",
    "admin": true,
    "owner": true,
    "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBEcqCjw=--c632b967cec296b87363a697a67a87f9cc1e5b45/avatar-64-x4",
    "company": {
      "id": 1033447817,
      "name": "Honcho Design"
    }
  },
  "bucket": {
    "id": 1042979252,
    "account_id": 1009501286,
    "name": "The Leto Laptop",
    "description": "Laptop product launch.",
    "created_at": "2016-06-02T17:30:10.480Z",
    "updated_at": "2016-06-02T17:30:10.480Z",
    "creator_id": 1007299143,
    "client_company_id": null
  },
  "parent": {
    "id": 9007199254741434,
    "title": "Message Board",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958498/message_boards/9007199254741434.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958498/message_boards/9007199254741434"
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

Nesting under the message board resource is not necessary for this endpoint. Clients may deliver `subject` or `content_html` parameters, or both if necessary.

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
