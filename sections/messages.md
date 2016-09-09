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
    "created_at": "2016-07-20T00:21:41.446Z",
    "updated_at": "2016-07-19T21:29:08.739Z",
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
      "id": 1007299165,
      "attachable_sgid": "BAh7CEkiCGdpZAY6BkVUSSIrZ2lkOi8vYmMzL1BlcnNvbi8xMDA3Mjk5MTY1P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg9hdHRhY2hhYmxlBjsAVEkiD2V4cGlyZXNfYXQGOwBUMA==--c28a27d0c490353fc1a5c2a50ce8eda0fae07370",
      "name": "Matt Donahue",
      "email_address": "matt@honchodesign.com",
      "personable_type": "User",
      "title": "Global Data Strategist",
      "created_at": "2016-07-19T21:27:47.654Z",
      "updated_at": "2016-07-19T21:27:47.654Z",
      "admin": false,
      "owner": false,
      "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBF0qCjw=--21513efb0cf6f64f7a0720b2c56ac6145ae6680c/avatar-64-x4"
    },
    "content": "<div>Hey all, here are some high res shots of the laptop hardware that we can use. These are not public yet, so be careful with how you share them. We don't want any leaks at all with these images.</div>\n<bc-attachment sgid=\"BAh7CEkiCGdpZAY6BkVUSSIvZ2lkOi8vYmMzL0F0dGFjaG1lbnQvMTAxOTczMDUxMD9leHBpcmVzX2luBjsAVEkiDHB1cnBvc2UGOwBUSSIPYXR0YWNoYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--592aadadb870f5984557f268717d9084d44ac29f\" content-type=\"image/jpeg\" url=\"https://3.basecamp.com/195539477/blobs/2b75b4a7daabf45fa287f069a320af349334abaa/previews/full/images-laptop_1.jpg\" href=\"https://3.basecamp.com/195539477/blobs/2b75b4a7daabf45fa287f069a320af349334abaa/download/images-laptop_1.jpg\" filename=\"images-laptop_1.jpg\" filesize=\"18241\" width=\"630\" height=\"420\" previewable=\"true\"><figure>\n    <img srcset=\"https://3.basecampapi.com/195539477/blobs/2b75b4a7daabf45fa287f069a320af349334abaa/previews/full/images-laptop_1.jpg?dppx=1 1x, https://3.basecampapi.com/195539477/blobs/2b75b4a7daabf45fa287f069a320af349334abaa/previews/full/images-laptop_1.jpg?dppx=2 2x, https://3.basecampapi.com/195539477/blobs/2b75b4a7daabf45fa287f069a320af349334abaa/previews/full/images-laptop_1.jpg?dppx=3 3x, https://3.basecampapi.com/195539477/blobs/2b75b4a7daabf45fa287f069a320af349334abaa/previews/full/images-laptop_1.jpg?dppx=4 4x\" src=\"https://3.basecampapi.com/195539477/blobs/2b75b4a7daabf45fa287f069a320af349334abaa/previews/full/images-laptop_1.jpg\" alt=\"Images laptop 1\">\n  <figcaption>\n      images-laptop_1.jpg\n  </figcaption>\n</figure></bc-attachment>\n<bc-attachment sgid=\"BAh7CEkiCGdpZAY6BkVUSSIvZ2lkOi8vYmMzL0F0dGFjaG1lbnQvMTAxOTczMDUxMT9leHBpcmVzX2luBjsAVEkiDHB1cnBvc2UGOwBUSSIPYXR0YWNoYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--62a3d1cb555cd4e0e75c07d91fdbce65148e36b4\" content-type=\"image/jpeg\" url=\"https://3.basecamp.com/195539477/blobs/02f029f64e7f87f18e1d1378f927323b5696921c/previews/full/images-laptop_2.jpg\" href=\"https://3.basecamp.com/195539477/blobs/02f029f64e7f87f18e1d1378f927323b5696921c/download/images-laptop_2.jpg\" filename=\"images-laptop_2.jpg\" filesize=\"30312\" width=\"600\" height=\"337\" previewable=\"true\"><figure>\n    <img srcset=\"https://3.basecampapi.com/195539477/blobs/02f029f64e7f87f18e1d1378f927323b5696921c/previews/full/images-laptop_2.jpg?dppx=1 1x, https://3.basecampapi.com/195539477/blobs/02f029f64e7f87f18e1d1378f927323b5696921c/previews/full/images-laptop_2.jpg?dppx=2 2x, https://3.basecampapi.com/195539477/blobs/02f029f64e7f87f18e1d1378f927323b5696921c/previews/full/images-laptop_2.jpg?dppx=3 3x, https://3.basecampapi.com/195539477/blobs/02f029f64e7f87f18e1d1378f927323b5696921c/previews/full/images-laptop_2.jpg?dppx=4 4x\" src=\"https://3.basecampapi.com/195539477/blobs/02f029f64e7f87f18e1d1378f927323b5696921c/previews/full/images-laptop_2.jpg\" alt=\"Images laptop 2\">\n  <figcaption>\n      images-laptop_2.jpg\n  </figcaption>\n</figure></bc-attachment>\n<bc-attachment sgid=\"BAh7CEkiCGdpZAY6BkVUSSIvZ2lkOi8vYmMzL0F0dGFjaG1lbnQvMTAxOTczMDUxMj9leHBpcmVzX2luBjsAVEkiDHB1cnBvc2UGOwBUSSIPYXR0YWNoYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--03e3397841118f2c697a7b34295803244128fd9b\" content-type=\"image/jpeg\" url=\"https://3.basecamp.com/195539477/blobs/0edbd2b0c64ecfc70830112c706889018ef02235/previews/full/images-laptop_3.jpg\" href=\"https://3.basecamp.com/195539477/blobs/0edbd2b0c64ecfc70830112c706889018ef02235/download/images-laptop_3.jpg\" filename=\"images-laptop_3.jpg\" filesize=\"13852\" width=\"610\" height=\"435\" previewable=\"true\"><figure>\n    <img srcset=\"https://3.basecampapi.com/195539477/blobs/0edbd2b0c64ecfc70830112c706889018ef02235/previews/full/images-laptop_3.jpg?dppx=1 1x, https://3.basecampapi.com/195539477/blobs/0edbd2b0c64ecfc70830112c706889018ef02235/previews/full/images-laptop_3.jpg?dppx=2 2x, https://3.basecampapi.com/195539477/blobs/0edbd2b0c64ecfc70830112c706889018ef02235/previews/full/images-laptop_3.jpg?dppx=3 3x, https://3.basecampapi.com/195539477/blobs/0edbd2b0c64ecfc70830112c706889018ef02235/previews/full/images-laptop_3.jpg?dppx=4 4x\" src=\"https://3.basecampapi.com/195539477/blobs/0edbd2b0c64ecfc70830112c706889018ef02235/previews/full/images-laptop_3.jpg\" alt=\"Images laptop 3\">\n  <figcaption>\n      images-laptop_3.jpg\n  </figcaption>\n</figure></bc-attachment>\n<bc-attachment sgid=\"BAh7CEkiCGdpZAY6BkVUSSIvZ2lkOi8vYmMzL0F0dGFjaG1lbnQvMTAxOTczMDUxMz9leHBpcmVzX2luBjsAVEkiDHB1cnBvc2UGOwBUSSIPYXR0YWNoYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--a848f869f12b3512835f6c33dac32f07b29f3733\" content-type=\"image/jpeg\" url=\"https://3.basecamp.com/195539477/blobs/cdbc672004177582b560423499645bc2b4de2ec3/previews/full/images-laptop_4.jpg\" href=\"https://3.basecamp.com/195539477/blobs/cdbc672004177582b560423499645bc2b4de2ec3/download/images-laptop_4.jpg\" filename=\"images-laptop_4.jpg\" filesize=\"48488\" width=\"1856\" height=\"940\" previewable=\"true\"><figure>\n    <img srcset=\"https://3.basecampapi.com/195539477/blobs/cdbc672004177582b560423499645bc2b4de2ec3/previews/full/images-laptop_4.jpg?dppx=1 1x, https://3.basecampapi.com/195539477/blobs/cdbc672004177582b560423499645bc2b4de2ec3/previews/full/images-laptop_4.jpg?dppx=2 2x, https://3.basecampapi.com/195539477/blobs/cdbc672004177582b560423499645bc2b4de2ec3/previews/full/images-laptop_4.jpg?dppx=3 3x, https://3.basecampapi.com/195539477/blobs/cdbc672004177582b560423499645bc2b4de2ec3/previews/full/images-laptop_4.jpg?dppx=4 4x\" src=\"https://3.basecampapi.com/195539477/blobs/cdbc672004177582b560423499645bc2b4de2ec3/previews/full/images-laptop_4.jpg\" alt=\"Images laptop 4\">\n  <figcaption>\n      images-laptop_4.jpg\n  </figcaption>\n</figure></bc-attachment>\n<bc-attachment sgid=\"BAh7CEkiCGdpZAY6BkVUSSIvZ2lkOi8vYmMzL0F0dGFjaG1lbnQvMTAxOTczMDUxND9leHBpcmVzX2luBjsAVEkiDHB1cnBvc2UGOwBUSSIPYXR0YWNoYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--759722abf530cb66824f6ba18e0ff45d7238bc94\" content-type=\"image/jpeg\" url=\"https://3.basecamp.com/195539477/blobs/2d3178d17e0109df4ab3d8e3a23b48b52cae8a2f/previews/full/images-laptop_5.jpg\" href=\"https://3.basecamp.com/195539477/blobs/2d3178d17e0109df4ab3d8e3a23b48b52cae8a2f/download/images-laptop_5.jpg\" filename=\"images-laptop_5.jpg\" filesize=\"140435\" width=\"640\" height=\"427\" previewable=\"true\"><figure>\n    <img srcset=\"https://3.basecampapi.com/195539477/blobs/2d3178d17e0109df4ab3d8e3a23b48b52cae8a2f/previews/full/images-laptop_5.jpg?dppx=1 1x, https://3.basecampapi.com/195539477/blobs/2d3178d17e0109df4ab3d8e3a23b48b52cae8a2f/previews/full/images-laptop_5.jpg?dppx=2 2x, https://3.basecampapi.com/195539477/blobs/2d3178d17e0109df4ab3d8e3a23b48b52cae8a2f/previews/full/images-laptop_5.jpg?dppx=3 3x, https://3.basecampapi.com/195539477/blobs/2d3178d17e0109df4ab3d8e3a23b48b52cae8a2f/previews/full/images-laptop_5.jpg?dppx=4 4x\" src=\"https://3.basecampapi.com/195539477/blobs/2d3178d17e0109df4ab3d8e3a23b48b52cae8a2f/previews/full/images-laptop_5.jpg\" alt=\"Images laptop 5\">\n  <figcaption>\n      images-laptop_5.jpg\n  </figcaption>\n</figure></bc-attachment>\n<bc-attachment sgid=\"BAh7CEkiCGdpZAY6BkVUSSIvZ2lkOi8vYmMzL0F0dGFjaG1lbnQvMTAxOTczMDUxNT9leHBpcmVzX2luBjsAVEkiDHB1cnBvc2UGOwBUSSIPYXR0YWNoYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--a28c26f0b5a9d3374f145c0324aa7fc824a42147\" content-type=\"image/jpeg\" url=\"https://3.basecamp.com/195539477/blobs/2b907197edae60b27ac0f58d6b043ccfce995cf0/previews/full/images-laptop_6.jpg\" href=\"https://3.basecamp.com/195539477/blobs/2b907197edae60b27ac0f58d6b043ccfce995cf0/download/images-laptop_6.jpg\" filename=\"images-laptop_6.jpg\" filesize=\"25658\" width=\"520\" height=\"365\" previewable=\"true\"><figure>\n    <img srcset=\"https://3.basecampapi.com/195539477/blobs/2b907197edae60b27ac0f58d6b043ccfce995cf0/previews/full/images-laptop_6.jpg?dppx=1 1x, https://3.basecampapi.com/195539477/blobs/2b907197edae60b27ac0f58d6b043ccfce995cf0/previews/full/images-laptop_6.jpg?dppx=2 2x, https://3.basecampapi.com/195539477/blobs/2b907197edae60b27ac0f58d6b043ccfce995cf0/previews/full/images-laptop_6.jpg?dppx=3 3x, https://3.basecampapi.com/195539477/blobs/2b907197edae60b27ac0f58d6b043ccfce995cf0/previews/full/images-laptop_6.jpg?dppx=4 4x\" src=\"https://3.basecampapi.com/195539477/blobs/2b907197edae60b27ac0f58d6b043ccfce995cf0/previews/full/images-laptop_6.jpg\" alt=\"Images laptop 6\">\n  <figcaption>\n      images-laptop_6.jpg\n  </figcaption>\n</figure></bc-attachment>\n<bc-attachment sgid=\"BAh7CEkiCGdpZAY6BkVUSSIvZ2lkOi8vYmMzL0F0dGFjaG1lbnQvMTAxOTczMDUxNj9leHBpcmVzX2luBjsAVEkiDHB1cnBvc2UGOwBUSSIPYXR0YWNoYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--62eca09ca83b3d553b8effd013bcaad37b206b85\" content-type=\"image/jpeg\" url=\"https://3.basecamp.com/195539477/blobs/8dd4fe5b5c90114cae1071746472bc41e76339f3/previews/full/images-laptop_7.jpg\" href=\"https://3.basecamp.com/195539477/blobs/8dd4fe5b5c90114cae1071746472bc41e76339f3/download/images-laptop_7.jpg\" filename=\"images-laptop_7.jpg\" filesize=\"318977\" width=\"1500\" height=\"991\" previewable=\"true\"><figure>\n    <img srcset=\"https://3.basecampapi.com/195539477/blobs/8dd4fe5b5c90114cae1071746472bc41e76339f3/previews/full/images-laptop_7.jpg?dppx=1 1x, https://3.basecampapi.com/195539477/blobs/8dd4fe5b5c90114cae1071746472bc41e76339f3/previews/full/images-laptop_7.jpg?dppx=2 2x, https://3.basecampapi.com/195539477/blobs/8dd4fe5b5c90114cae1071746472bc41e76339f3/previews/full/images-laptop_7.jpg?dppx=3 3x, https://3.basecampapi.com/195539477/blobs/8dd4fe5b5c90114cae1071746472bc41e76339f3/previews/full/images-laptop_7.jpg?dppx=4 4x\" src=\"https://3.basecampapi.com/195539477/blobs/8dd4fe5b5c90114cae1071746472bc41e76339f3/previews/full/images-laptop_7.jpg\" alt=\"Images laptop 7\">\n  <figcaption>\n      images-laptop_7.jpg\n  </figcaption>\n</figure></bc-attachment>\n<bc-attachment sgid=\"BAh7CEkiCGdpZAY6BkVUSSIvZ2lkOi8vYmMzL0F0dGFjaG1lbnQvMTAxOTczMDUxNz9leHBpcmVzX2luBjsAVEkiDHB1cnBvc2UGOwBUSSIPYXR0YWNoYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--4bbf6e7e4cee46a47d1b6c043bfa6c0a007db36b\" content-type=\"image/jpeg\" url=\"https://3.basecamp.com/195539477/blobs/ee41e9e6d721eadb8e10adf1faad4795a2a32b60/previews/full/images-laptop_8.jpg\" href=\"https://3.basecamp.com/195539477/blobs/ee41e9e6d721eadb8e10adf1faad4795a2a32b60/download/images-laptop_8.jpg\" filename=\"images-laptop_8.jpg\" filesize=\"51341\" width=\"540\" height=\"334\" previewable=\"true\"><figure>\n    <img srcset=\"https://3.basecampapi.com/195539477/blobs/ee41e9e6d721eadb8e10adf1faad4795a2a32b60/previews/full/images-laptop_8.jpg?dppx=1 1x, https://3.basecampapi.com/195539477/blobs/ee41e9e6d721eadb8e10adf1faad4795a2a32b60/previews/full/images-laptop_8.jpg?dppx=2 2x, https://3.basecampapi.com/195539477/blobs/ee41e9e6d721eadb8e10adf1faad4795a2a32b60/previews/full/images-laptop_8.jpg?dppx=3 3x, https://3.basecampapi.com/195539477/blobs/ee41e9e6d721eadb8e10adf1faad4795a2a32b60/previews/full/images-laptop_8.jpg?dppx=4 4x\" src=\"https://3.basecampapi.com/195539477/blobs/ee41e9e6d721eadb8e10adf1faad4795a2a32b60/previews/full/images-laptop_8.jpg\" alt=\"Images laptop 8\">\n  <figcaption>\n      images-laptop_8.jpg\n  </figcaption>\n</figure></bc-attachment>\n<bc-attachment sgid=\"BAh7CEkiCGdpZAY6BkVUSSIvZ2lkOi8vYmMzL0F0dGFjaG1lbnQvMTAxOTczMDUxOD9leHBpcmVzX2luBjsAVEkiDHB1cnBvc2UGOwBUSSIPYXR0YWNoYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--b51983a66d102e7e3ca9d7f8e053916a421cf912\" content-type=\"image/jpeg\" url=\"https://3.basecamp.com/195539477/blobs/4d8d60c3e7a1d868080139fcc754f795a5efe897/previews/full/images-laptop_9.jpg\" href=\"https://3.basecamp.com/195539477/blobs/4d8d60c3e7a1d868080139fcc754f795a5efe897/download/images-laptop_9.jpg\" filename=\"images-laptop_9.jpg\" filesize=\"369239\" width=\"1844\" height=\"1037\" previewable=\"true\"><figure>\n    <img srcset=\"https://3.basecampapi.com/195539477/blobs/4d8d60c3e7a1d868080139fcc754f795a5efe897/previews/full/images-laptop_9.jpg?dppx=1 1x, https://3.basecampapi.com/195539477/blobs/4d8d60c3e7a1d868080139fcc754f795a5efe897/previews/full/images-laptop_9.jpg?dppx=2 2x, https://3.basecampapi.com/195539477/blobs/4d8d60c3e7a1d868080139fcc754f795a5efe897/previews/full/images-laptop_9.jpg?dppx=3 3x, https://3.basecampapi.com/195539477/blobs/4d8d60c3e7a1d868080139fcc754f795a5efe897/previews/full/images-laptop_9.jpg?dppx=4 4x\" src=\"https://3.basecampapi.com/195539477/blobs/4d8d60c3e7a1d868080139fcc754f795a5efe897/previews/full/images-laptop_9.jpg\" alt=\"Images laptop 9\">\n  <figcaption>\n      images-laptop_9.jpg\n  </figcaption>\n</figure></bc-attachment>\n<bc-attachment sgid=\"BAh7CEkiCGdpZAY6BkVUSSIvZ2lkOi8vYmMzL0F0dGFjaG1lbnQvMTAxOTczMDUxOT9leHBpcmVzX2luBjsAVEkiDHB1cnBvc2UGOwBUSSIPYXR0YWNoYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--43df281070f1a48f082e68ce18f03612c1cf3281\" content-type=\"image/jpeg\" url=\"https://3.basecamp.com/195539477/blobs/2ffe919518fa9350f4f7f47edc4ab959399a04e5/previews/full/images-laptop_10.jpg\" href=\"https://3.basecamp.com/195539477/blobs/2ffe919518fa9350f4f7f47edc4ab959399a04e5/download/images-laptop_10.jpg\" filename=\"images-laptop_10.jpg\" filesize=\"25429\" width=\"620\" height=\"413\" previewable=\"true\"><figure>\n    <img srcset=\"https://3.basecampapi.com/195539477/blobs/2ffe919518fa9350f4f7f47edc4ab959399a04e5/previews/full/images-laptop_10.jpg?dppx=1 1x, https://3.basecampapi.com/195539477/blobs/2ffe919518fa9350f4f7f47edc4ab959399a04e5/previews/full/images-laptop_10.jpg?dppx=2 2x, https://3.basecampapi.com/195539477/blobs/2ffe919518fa9350f4f7f47edc4ab959399a04e5/previews/full/images-laptop_10.jpg?dppx=3 3x, https://3.basecampapi.com/195539477/blobs/2ffe919518fa9350f4f7f47edc4ab959399a04e5/previews/full/images-laptop_10.jpg?dppx=4 4x\" src=\"https://3.basecampapi.com/195539477/blobs/2ffe919518fa9350f4f7f47edc4ab959399a04e5/previews/full/images-laptop_10.jpg\" alt=\"Images laptop 10\">\n  <figcaption>\n      images-laptop_10.jpg\n  </figcaption>\n</figure></bc-attachment>\n<bc-attachment sgid=\"BAh7CEkiCGdpZAY6BkVUSSIvZ2lkOi8vYmMzL0F0dGFjaG1lbnQvMTAxOTczMDUyMD9leHBpcmVzX2luBjsAVEkiDHB1cnBvc2UGOwBUSSIPYXR0YWNoYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--021113670f9861e151e4bac1b23efa43687f54b2\" content-type=\"image/jpeg\" url=\"https://3.basecamp.com/195539477/blobs/d87211a3f76a8370a69973ba577f34236d239853/previews/full/images-laptop_11.jpg\" href=\"https://3.basecamp.com/195539477/blobs/d87211a3f76a8370a69973ba577f34236d239853/download/images-laptop_11.jpg\" filename=\"images-laptop_11.jpg\" filesize=\"20839\" width=\"620\" height=\"413\" previewable=\"true\"><figure>\n    <img srcset=\"https://3.basecampapi.com/195539477/blobs/d87211a3f76a8370a69973ba577f34236d239853/previews/full/images-laptop_11.jpg?dppx=1 1x, https://3.basecampapi.com/195539477/blobs/d87211a3f76a8370a69973ba577f34236d239853/previews/full/images-laptop_11.jpg?dppx=2 2x, https://3.basecampapi.com/195539477/blobs/d87211a3f76a8370a69973ba577f34236d239853/previews/full/images-laptop_11.jpg?dppx=3 3x, https://3.basecampapi.com/195539477/blobs/d87211a3f76a8370a69973ba577f34236d239853/previews/full/images-laptop_11.jpg?dppx=4 4x\" src=\"https://3.basecampapi.com/195539477/blobs/d87211a3f76a8370a69973ba577f34236d239853/previews/full/images-laptop_11.jpg\" alt=\"Images laptop 11\">\n  <figcaption>\n      images-laptop_11.jpg\n  </figcaption>\n</figure></bc-attachment>\n<bc-attachment sgid=\"BAh7CEkiCGdpZAY6BkVUSSIvZ2lkOi8vYmMzL0F0dGFjaG1lbnQvMTAxOTczMDUyMT9leHBpcmVzX2luBjsAVEkiDHB1cnBvc2UGOwBUSSIPYXR0YWNoYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--1ef625e29704c65ad2989f77e313593422b3fdee\" content-type=\"image/jpeg\" url=\"https://3.basecamp.com/195539477/blobs/f4dcd0c0c8a56c5e60e96dd1630ef03b890fee9f/previews/full/images-laptop_12.jpg\" href=\"https://3.basecamp.com/195539477/blobs/f4dcd0c0c8a56c5e60e96dd1630ef03b890fee9f/download/images-laptop_12.jpg\" filename=\"images-laptop_12.jpg\" filesize=\"137872\" width=\"1280\" height=\"708\" previewable=\"true\"><figure>\n    <img srcset=\"https://3.basecampapi.com/195539477/blobs/f4dcd0c0c8a56c5e60e96dd1630ef03b890fee9f/previews/full/images-laptop_12.jpg?dppx=1 1x, https://3.basecampapi.com/195539477/blobs/f4dcd0c0c8a56c5e60e96dd1630ef03b890fee9f/previews/full/images-laptop_12.jpg?dppx=2 2x, https://3.basecampapi.com/195539477/blobs/f4dcd0c0c8a56c5e60e96dd1630ef03b890fee9f/previews/full/images-laptop_12.jpg?dppx=3 3x, https://3.basecampapi.com/195539477/blobs/f4dcd0c0c8a56c5e60e96dd1630ef03b890fee9f/previews/full/images-laptop_12.jpg?dppx=4 4x\" src=\"https://3.basecampapi.com/195539477/blobs/f4dcd0c0c8a56c5e60e96dd1630ef03b890fee9f/previews/full/images-laptop_12.jpg\" alt=\"Images laptop 12\">\n  <figcaption>\n      images-laptop_12.jpg\n  </figcaption>\n</figure></bc-attachment>\n<bc-attachment sgid=\"BAh7CEkiCGdpZAY6BkVUSSIvZ2lkOi8vYmMzL0F0dGFjaG1lbnQvMTAxOTczMDUyMj9leHBpcmVzX2luBjsAVEkiDHB1cnBvc2UGOwBUSSIPYXR0YWNoYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--3f4dee05282595cde069001a4e4ca57593fabe77\" content-type=\"image/jpeg\" url=\"https://3.basecamp.com/195539477/blobs/0ca4f33e10be1222ae354f98a59b220ff613ba4e/previews/full/images-laptop_13.jpg\" href=\"https://3.basecamp.com/195539477/blobs/0ca4f33e10be1222ae354f98a59b220ff613ba4e/download/images-laptop_13.jpg\" filename=\"images-laptop_13.jpg\" filesize=\"62024\" width=\"928\" height=\"618\" previewable=\"true\"><figure>\n    <img srcset=\"https://3.basecampapi.com/195539477/blobs/0ca4f33e10be1222ae354f98a59b220ff613ba4e/previews/full/images-laptop_13.jpg?dppx=1 1x, https://3.basecampapi.com/195539477/blobs/0ca4f33e10be1222ae354f98a59b220ff613ba4e/previews/full/images-laptop_13.jpg?dppx=2 2x, https://3.basecampapi.com/195539477/blobs/0ca4f33e10be1222ae354f98a59b220ff613ba4e/previews/full/images-laptop_13.jpg?dppx=3 3x, https://3.basecampapi.com/195539477/blobs/0ca4f33e10be1222ae354f98a59b220ff613ba4e/previews/full/images-laptop_13.jpg?dppx=4 4x\" src=\"https://3.basecampapi.com/195539477/blobs/0ca4f33e10be1222ae354f98a59b220ff613ba4e/previews/full/images-laptop_13.jpg\" alt=\"Images laptop 13\">\n  <figcaption>\n      images-laptop_13.jpg\n  </figcaption>\n</figure></bc-attachment>\n<bc-attachment sgid=\"BAh7CEkiCGdpZAY6BkVUSSIvZ2lkOi8vYmMzL0F0dGFjaG1lbnQvMTAxOTczMDUyMz9leHBpcmVzX2luBjsAVEkiDHB1cnBvc2UGOwBUSSIPYXR0YWNoYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--7f1bfb82b57ece55d108c2762f1c34b35474e418\" content-type=\"image/jpeg\" url=\"https://3.basecamp.com/195539477/blobs/0678d3c2d77dc87a5085bd8ae430129b2ddd7165/previews/full/images-laptop_14.jpg\" href=\"https://3.basecamp.com/195539477/blobs/0678d3c2d77dc87a5085bd8ae430129b2ddd7165/download/images-laptop_14.jpg\" filename=\"images-laptop_14.jpg\" filesize=\"81082\" width=\"1600\" height=\"1066\" previewable=\"true\"><figure>\n    <img srcset=\"https://3.basecampapi.com/195539477/blobs/0678d3c2d77dc87a5085bd8ae430129b2ddd7165/previews/full/images-laptop_14.jpg?dppx=1 1x, https://3.basecampapi.com/195539477/blobs/0678d3c2d77dc87a5085bd8ae430129b2ddd7165/previews/full/images-laptop_14.jpg?dppx=2 2x, https://3.basecampapi.com/195539477/blobs/0678d3c2d77dc87a5085bd8ae430129b2ddd7165/previews/full/images-laptop_14.jpg?dppx=3 3x, https://3.basecampapi.com/195539477/blobs/0678d3c2d77dc87a5085bd8ae430129b2ddd7165/previews/full/images-laptop_14.jpg?dppx=4 4x\" src=\"https://3.basecampapi.com/195539477/blobs/0678d3c2d77dc87a5085bd8ae430129b2ddd7165/previews/full/images-laptop_14.jpg\" alt=\"Images laptop 14\">\n  <figcaption>\n      images-laptop_14.jpg\n  </figcaption>\n</figure></bc-attachment>",
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
  "created_at": "2016-06-25T22:33:41.446Z",
  "updated_at": "2016-07-19T21:28:44.028Z",
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
    "id": 1007299143,
    "attachable_sgid": "BAh7CEkiCGdpZAY6BkVUSSIrZ2lkOi8vYmMzL1BlcnNvbi8xMDA3Mjk5MTQzP2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg9hdHRhY2hhYmxlBjsAVEkiD2V4cGlyZXNfYXQGOwBUMA==--919d2c8b11ff403eefcab9db42dd26846d0c3102",
    "name": "Victor Cooper",
    "email_address": "victor@honchodesign.com",
    "personable_type": "User",
    "title": "Chief Strategist",
    "bio": "Don't let your dreams be dreams",
    "created_at": "2016-09-09T22:58:27.559Z",
    "updated_at": "2016-09-09T22:58:31.296Z",
    "admin": true,
    "owner": true,
    "time_zone": "America/Chicago",
    "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBEcqCjw=--c632b967cec296b87363a697a67a87f9cc1e5b45/avatar-64-x4",
    "company": {
      "id": 1033447817,
      "name": "Honcho Design"
    }
  },
  "content": "<div>Hey guys,\n\n  We won the Leto account! This is huge for us, it really marks a turning point for the company.\n\n  As you know we've been pursuing bigger clients in the consumer space, but we've done so carefully. We've never been about getting the biggest clients - those are easy to get. We've been trying to get the best clients for us - ones that will challenge us, grow us, make us better, and ultimately giving us a platform to show how awesome you guys all are. And now we have that!\n\n  A big congrats to everyone who worked so hard to make this happen, and now the fun really begins. Most of the pitch team will stay on as leading members of the first project, the Leto Microsite.\n\n  Again, great job everyone, and let's go kick some more butt!\n\n  -Victor</div>",
  "bookmark_url": "https://3.basecamp.com/195539477/my/bookmarks/BAh7CEkiCGdpZAY6BkVUSSI0Z2lkOi8vYmMzL1JlY29yZGluZy85MDA3MTk5MjU0NzQxNDQzP2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg1yZWFkYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--0cea494978131a59de5436e67e7f01b6db1fb8f0",
  "subscription_url": "https://3.basecamp.com/195539477/buckets/2085958498/recordings/9007199254741443/subscription",
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

* `POST /buckets/1/message_boards/3/messages.json` publishes a message in the Basecamp with ID `1` and under the message board with an ID of `3`.

**Required parameters**: `subject` as the title of the message, and `status`, set to `active` to publish immediately.

_Optional parameters_: `content` as the body of the message. See our [Rich text guide][4] for what HTML tags are allowed.

Note: All people on a Basecamp are notified of the new message when it's posted.

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

* `PUT /buckets/1/messages/2.json` allows changing the `subject` and `content` of the message with an ID of `2` in the Basecamp with ID `1`.

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


[1]: https://github.com/basecamp/bc3-api/blob/master/sections/recordings.md#trash-a-recording
[2]: https://github.com/basecamp/bc3-api/blob/master/README.md#pagination
[3]: https://github.com/basecamp/bc3-api/blob/master/sections/message_boards.md#message-boards
[4]: https://github.com/basecamp/bc3-api/blob/master/sections/rich_text.md
