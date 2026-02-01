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
    "id": 1069479583,
    "status": "active",
    "visible_to_clients": false,
    "created_at": "2026-01-17T15:33:00.000Z",
    "updated_at": "2026-01-31T08:35:10.718Z",
    "title": "Laptop high res glamour shots",
    "inherits_status": true,
    "type": "Message",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958504/messages/1069479583.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958504/messages/1069479583",
    "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiLmdpZDovL2JjMy9SZWNvcmRpbmcvMTA2OTQ3OTU4Mz9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg1yZWFkYWJsZQY7AFQ=--ac8884ce8febf69d7dedba2bdbd479cec94880e7.json",
    "subscription_url": "https://3.basecampapi.com/195539477/buckets/2085958504/recordings/1069479583/subscription.json",
    "comments_count": 1,
    "comments_url": "https://3.basecampapi.com/195539477/buckets/2085958504/recordings/1069479583/comments.json",
    "parent": {
      "id": 1069479392,
      "title": "Message Board",
      "type": "Message::Board",
      "url": "https://3.basecampapi.com/195539477/buckets/2085958504/message_boards/1069479392.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958504/message_boards/1069479392"
    },
    "bucket": {
      "id": 2085958504,
      "name": "The Leto Laptop",
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
    "content": "Hey all, here are some high res shots of the laptop hardware that we can use. These are not public yet, so be careful with how you share them. We don't want any leaks at all with these images.<br><br><bc-attachment sgid=\"BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiL2dpZDovL2JjMy9BdHRhY2htZW50LzEwNDY2Mjg0NzU_ZXhwaXJlc19pbgY7AFRJIghwdXIGOwBUSSIPYXR0YWNoYWJsZQY7AFQ=--60072a7f701afce5c5415c2f5b648edcde05e9f1\" content-type=\"image/avif\" url=\"https://3.basecampapi.com/195539477/blobs/8bf6758364a57a038cfd54bb3127b063642ea6a7/previews/full\" href=\"https://3.basecamp-static.com/195539477/blobs/8bf6758364a57a038cfd54bb3127b063642ea6a7/download/laptop_1\" filename=\"laptop_1\" filesize=\"14531\" width=\"630\" height=\"420\" previewable=\"true\" presentation=\"\"><figure>\n    <img srcset=\"https://3.basecampapi.com/195539477/blobs/8bf6758364a57a038cfd54bb3127b063642ea6a7/previews/full?dppx=2 2x, https://3.basecampapi.com/195539477/blobs/8bf6758364a57a038cfd54bb3127b063642ea6a7/previews/full?dppx=1 1x, https://3.basecampapi.com/195539477/blobs/8bf6758364a57a038cfd54bb3127b063642ea6a7/previews/full?dppx=3 3x, https://3.basecampapi.com/195539477/blobs/8bf6758364a57a038cfd54bb3127b063642ea6a7/previews/full?dppx=4 4x\" src=\"https://3.basecampapi.com/195539477/blobs/8bf6758364a57a038cfd54bb3127b063642ea6a7/previews/full\">\n  <figcaption>\n    laptop_1\n  </figcaption>\n</figure></bc-attachment> <bc-attachment sgid=\"BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiL2dpZDovL2JjMy9BdHRhY2htZW50LzEwNDY2Mjg0NzY_ZXhwaXJlc19pbgY7AFRJIghwdXIGOwBUSSIPYXR0YWNoYWJsZQY7AFQ=--78d6aeab5f5505ed418ed5425ba9a2d6c88969dd\" content-type=\"image/avif\" url=\"https://3.basecampapi.com/195539477/blobs/f65d63f62029086f4b16c923c70d403cad3205b2/previews/full\" href=\"https://3.basecamp-static.com/195539477/blobs/f65d63f62029086f4b16c923c70d403cad3205b2/download/laptop_2\" filename=\"laptop_2\" filesize=\"18545\" width=\"600\" height=\"337\" previewable=\"true\" presentation=\"\"><figure>\n    <img srcset=\"https://3.basecampapi.com/195539477/blobs/f65d63f62029086f4b16c923c70d403cad3205b2/previews/full?dppx=2 2x, https://3.basecampapi.com/195539477/blobs/f65d63f62029086f4b16c923c70d403cad3205b2/previews/full?dppx=1 1x, https://3.basecampapi.com/195539477/blobs/f65d63f62029086f4b16c923c70d403cad3205b2/previews/full?dppx=3 3x, https://3.basecampapi.com/195539477/blobs/f65d63f62029086f4b16c923c70d403cad3205b2/previews/full?dppx=4 4x\" src=\"https://3.basecampapi.com/195539477/blobs/f65d63f62029086f4b16c923c70d403cad3205b2/previews/full\">\n  <figcaption>\n    laptop_2\n  </figcaption>\n</figure></bc-attachment> <bc-attachment sgid=\"BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiL2dpZDovL2JjMy9BdHRhY2htZW50LzEwNDY2Mjg0Nzc_ZXhwaXJlc19pbgY7AFRJIghwdXIGOwBUSSIPYXR0YWNoYWJsZQY7AFQ=--6c08dffec34a6454ab069505cbe40744b95af86c\" content-type=\"image/avif\" url=\"https://3.basecampapi.com/195539477/blobs/ef0646bde0caacfd3eba11e94272bb1311160315/previews/full\" href=\"https://3.basecamp-static.com/195539477/blobs/ef0646bde0caacfd3eba11e94272bb1311160315/download/laptop_3\" filename=\"laptop_3\" filesize=\"11942\" width=\"610\" height=\"435\" previewable=\"true\" presentation=\"\"><figure>\n    <img srcset=\"https://3.basecampapi.com/195539477/blobs/ef0646bde0caacfd3eba11e94272bb1311160315/previews/full?dppx=2 2x, https://3.basecampapi.com/195539477/blobs/ef0646bde0caacfd3eba11e94272bb1311160315/previews/full?dppx=1 1x, https://3.basecampapi.com/195539477/blobs/ef0646bde0caacfd3eba11e94272bb1311160315/previews/full?dppx=3 3x, https://3.basecampapi.com/195539477/blobs/ef0646bde0caacfd3eba11e94272bb1311160315/previews/full?dppx=4 4x\" src=\"https://3.basecampapi.com/195539477/blobs/ef0646bde0caacfd3eba11e94272bb1311160315/previews/full\">\n  <figcaption>\n    laptop_3\n  </figcaption>\n</figure></bc-attachment> <bc-attachment sgid=\"BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiL2dpZDovL2JjMy9BdHRhY2htZW50LzEwNDY2Mjg0Nzg_ZXhwaXJlc19pbgY7AFRJIghwdXIGOwBUSSIPYXR0YWNoYWJsZQY7AFQ=--5ea06fe17cff52380f599939ee90060e2c1ad274\" content-type=\"image/avif\" url=\"https://3.basecampapi.com/195539477/blobs/6d0e58e2820aab147c9fdd4ae5418b5812b263c4/previews/full\" href=\"https://3.basecamp-static.com/195539477/blobs/6d0e58e2820aab147c9fdd4ae5418b5812b263c4/download/laptop_4\" filename=\"laptop_4\" filesize=\"10894\" width=\"700\" height=\"355\" previewable=\"true\" presentation=\"\"><figure>\n    <img srcset=\"https://3.basecampapi.com/195539477/blobs/6d0e58e2820aab147c9fdd4ae5418b5812b263c4/previews/full?dppx=2 2x, https://3.basecampapi.com/195539477/blobs/6d0e58e2820aab147c9fdd4ae5418b5812b263c4/previews/full?dppx=1 1x, https://3.basecampapi.com/195539477/blobs/6d0e58e2820aab147c9fdd4ae5418b5812b263c4/previews/full?dppx=3 3x, https://3.basecampapi.com/195539477/blobs/6d0e58e2820aab147c9fdd4ae5418b5812b263c4/previews/full?dppx=4 4x\" src=\"https://3.basecampapi.com/195539477/blobs/6d0e58e2820aab147c9fdd4ae5418b5812b263c4/previews/full\">\n  <figcaption>\n    laptop_4\n  </figcaption>\n</figure></bc-attachment> <bc-attachment sgid=\"BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiL2dpZDovL2JjMy9BdHRhY2htZW50LzEwNDY2Mjg0Nzk_ZXhwaXJlc19pbgY7AFRJIghwdXIGOwBUSSIPYXR0YWNoYWJsZQY7AFQ=--38376bcaa1e52f3e344580ddaa112beba391b42a\" content-type=\"image/avif\" url=\"https://3.basecampapi.com/195539477/blobs/869749dcd5385f7d3450ab86aa6410bb259c9e23/previews/full\" href=\"https://3.basecamp-static.com/195539477/blobs/869749dcd5385f7d3450ab86aa6410bb259c9e23/download/laptop_5\" filename=\"laptop_5\" filesize=\"14497\" width=\"640\" height=\"427\" previewable=\"true\" presentation=\"\"><figure>\n    <img srcset=\"https://3.basecampapi.com/195539477/blobs/869749dcd5385f7d3450ab86aa6410bb259c9e23/previews/full?dppx=2 2x, https://3.basecampapi.com/195539477/blobs/869749dcd5385f7d3450ab86aa6410bb259c9e23/previews/full?dppx=1 1x, https://3.basecampapi.com/195539477/blobs/869749dcd5385f7d3450ab86aa6410bb259c9e23/previews/full?dppx=3 3x, https://3.basecampapi.com/195539477/blobs/869749dcd5385f7d3450ab86aa6410bb259c9e23/previews/full?dppx=4 4x\" src=\"https://3.basecampapi.com/195539477/blobs/869749dcd5385f7d3450ab86aa6410bb259c9e23/previews/full\">\n  <figcaption>\n    laptop_5\n  </figcaption>\n</figure></bc-attachment> <bc-attachment sgid=\"BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiL2dpZDovL2JjMy9BdHRhY2htZW50LzEwNDY2Mjg0ODA_ZXhwaXJlc19pbgY7AFRJIghwdXIGOwBUSSIPYXR0YWNoYWJsZQY7AFQ=--db6d30f319fedea2072df5a9e533ae9b83372504\" content-type=\"image/avif\" url=\"https://3.basecampapi.com/195539477/blobs/f5aea9fe27be0ca31f818a8d7fbb7722389187aa/previews/full\" href=\"https://3.basecamp-static.com/195539477/blobs/f5aea9fe27be0ca31f818a8d7fbb7722389187aa/download/laptop_6\" filename=\"laptop_6\" filesize=\"9370\" width=\"520\" height=\"365\" previewable=\"true\" presentation=\"\"><figure>\n    <img srcset=\"https://3.basecampapi.com/195539477/blobs/f5aea9fe27be0ca31f818a8d7fbb7722389187aa/previews/full?dppx=2 2x, https://3.basecampapi.com/195539477/blobs/f5aea9fe27be0ca31f818a8d7fbb7722389187aa/previews/full?dppx=1 1x, https://3.basecampapi.com/195539477/blobs/f5aea9fe27be0ca31f818a8d7fbb7722389187aa/previews/full?dppx=3 3x, https://3.basecampapi.com/195539477/blobs/f5aea9fe27be0ca31f818a8d7fbb7722389187aa/previews/full?dppx=4 4x\" src=\"https://3.basecampapi.com/195539477/blobs/f5aea9fe27be0ca31f818a8d7fbb7722389187aa/previews/full\">\n  <figcaption>\n    laptop_6\n  </figcaption>\n</figure></bc-attachment> <bc-attachment sgid=\"BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiL2dpZDovL2JjMy9BdHRhY2htZW50LzEwNDY2Mjg0ODE_ZXhwaXJlc19pbgY7AFRJIghwdXIGOwBUSSIPYXR0YWNoYWJsZQY7AFQ=--d2c070cd0872b6049fb79df6cd9ada7464e1757e\" content-type=\"image/avif\" url=\"https://3.basecampapi.com/195539477/blobs/fbcafaab409a811285c0cc067b9dd7d10e2511b0/previews/full\" href=\"https://3.basecamp-static.com/195539477/blobs/fbcafaab409a811285c0cc067b9dd7d10e2511b0/download/laptop_7\" filename=\"laptop_7\" filesize=\"48646\" width=\"700\" height=\"462\" previewable=\"true\" presentation=\"\"><figure>\n    <img srcset=\"https://3.basecampapi.com/195539477/blobs/fbcafaab409a811285c0cc067b9dd7d10e2511b0/previews/full?dppx=2 2x, https://3.basecampapi.com/195539477/blobs/fbcafaab409a811285c0cc067b9dd7d10e2511b0/previews/full?dppx=1 1x, https://3.basecampapi.com/195539477/blobs/fbcafaab409a811285c0cc067b9dd7d10e2511b0/previews/full?dppx=3 3x, https://3.basecampapi.com/195539477/blobs/fbcafaab409a811285c0cc067b9dd7d10e2511b0/previews/full?dppx=4 4x\" src=\"https://3.basecampapi.com/195539477/blobs/fbcafaab409a811285c0cc067b9dd7d10e2511b0/previews/full\">\n  <figcaption>\n    laptop_7\n  </figcaption>\n</figure></bc-attachment> <bc-attachment sgid=\"BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiL2dpZDovL2JjMy9BdHRhY2htZW50LzEwNDY2Mjg0ODI_ZXhwaXJlc19pbgY7AFRJIghwdXIGOwBUSSIPYXR0YWNoYWJsZQY7AFQ=--98023c4f0b4cdf0ff6ef6395ea0163aa774a3444\" content-type=\"image/avif\" url=\"https://3.basecampapi.com/195539477/blobs/5e87a6fdcc861107635d62220828423792431527/previews/full\" href=\"https://3.basecamp-static.com/195539477/blobs/5e87a6fdcc861107635d62220828423792431527/download/laptop_8\" filename=\"laptop_8\" filesize=\"12904\" width=\"540\" height=\"334\" previewable=\"true\" presentation=\"\"><figure>\n    <img srcset=\"https://3.basecampapi.com/195539477/blobs/5e87a6fdcc861107635d62220828423792431527/previews/full?dppx=2 2x, https://3.basecampapi.com/195539477/blobs/5e87a6fdcc861107635d62220828423792431527/previews/full?dppx=1 1x, https://3.basecampapi.com/195539477/blobs/5e87a6fdcc861107635d62220828423792431527/previews/full?dppx=3 3x, https://3.basecampapi.com/195539477/blobs/5e87a6fdcc861107635d62220828423792431527/previews/full?dppx=4 4x\" src=\"https://3.basecampapi.com/195539477/blobs/5e87a6fdcc861107635d62220828423792431527/previews/full\">\n  <figcaption>\n    laptop_8\n  </figcaption>\n</figure></bc-attachment> <bc-attachment sgid=\"BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiL2dpZDovL2JjMy9BdHRhY2htZW50LzEwNDY2Mjg0ODM_ZXhwaXJlc19pbgY7AFRJIghwdXIGOwBUSSIPYXR0YWNoYWJsZQY7AFQ=--fbc4cc6ef8b067a79efaaf026444744a0a4b4393\" content-type=\"image/avif\" url=\"https://3.basecampapi.com/195539477/blobs/45dded682cf4b1f290a6b31f459468fa5f70ef09/previews/full\" href=\"https://3.basecamp-static.com/195539477/blobs/45dded682cf4b1f290a6b31f459468fa5f70ef09/download/laptop_9\" filename=\"laptop_9\" filesize=\"30919\" width=\"700\" height=\"394\" previewable=\"true\" presentation=\"\"><figure>\n    <img srcset=\"https://3.basecampapi.com/195539477/blobs/45dded682cf4b1f290a6b31f459468fa5f70ef09/previews/full?dppx=2 2x, https://3.basecampapi.com/195539477/blobs/45dded682cf4b1f290a6b31f459468fa5f70ef09/previews/full?dppx=1 1x, https://3.basecampapi.com/195539477/blobs/45dded682cf4b1f290a6b31f459468fa5f70ef09/previews/full?dppx=3 3x, https://3.basecampapi.com/195539477/blobs/45dded682cf4b1f290a6b31f459468fa5f70ef09/previews/full?dppx=4 4x\" src=\"https://3.basecampapi.com/195539477/blobs/45dded682cf4b1f290a6b31f459468fa5f70ef09/previews/full\">\n  <figcaption>\n    laptop_9\n  </figcaption>\n</figure></bc-attachment> <bc-attachment sgid=\"BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiL2dpZDovL2JjMy9BdHRhY2htZW50LzEwNDY2Mjg0ODQ_ZXhwaXJlc19pbgY7AFRJIghwdXIGOwBUSSIPYXR0YWNoYWJsZQY7AFQ=--c6b88bec2c004b4dfafbdc8a30b181d31da08db6\" content-type=\"image/avif\" url=\"https://3.basecampapi.com/195539477/blobs/feea600fe205e12c4a318c0ad9d9b228ec31b01c/previews/full\" href=\"https://3.basecamp-static.com/195539477/blobs/feea600fe205e12c4a318c0ad9d9b228ec31b01c/download/laptop_10\" filename=\"laptop_10\" filesize=\"7014\" width=\"620\" height=\"413\" previewable=\"true\" presentation=\"\"><figure>\n    <img srcset=\"https://3.basecampapi.com/195539477/blobs/feea600fe205e12c4a318c0ad9d9b228ec31b01c/previews/full?dppx=2 2x, https://3.basecampapi.com/195539477/blobs/feea600fe205e12c4a318c0ad9d9b228ec31b01c/previews/full?dppx=1 1x, https://3.basecampapi.com/195539477/blobs/feea600fe205e12c4a318c0ad9d9b228ec31b01c/previews/full?dppx=3 3x, https://3.basecampapi.com/195539477/blobs/feea600fe205e12c4a318c0ad9d9b228ec31b01c/previews/full?dppx=4 4x\" src=\"https://3.basecampapi.com/195539477/blobs/feea600fe205e12c4a318c0ad9d9b228ec31b01c/previews/full\">\n  <figcaption>\n    laptop_10\n  </figcaption>\n</figure></bc-attachment> <bc-attachment sgid=\"BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiL2dpZDovL2JjMy9BdHRhY2htZW50LzEwNDY2Mjg0ODU_ZXhwaXJlc19pbgY7AFRJIghwdXIGOwBUSSIPYXR0YWNoYWJsZQY7AFQ=--419dc4a33710d0001fac8cf007bcf22bd187719b\" content-type=\"image/avif\" url=\"https://3.basecampapi.com/195539477/blobs/e0c24a8764007e77cb12403c9612913a2f10e2de/previews/full\" href=\"https://3.basecamp-static.com/195539477/blobs/e0c24a8764007e77cb12403c9612913a2f10e2de/download/laptop_11\" filename=\"laptop_11\" filesize=\"2693\" width=\"620\" height=\"413\" previewable=\"true\" presentation=\"\"><figure>\n    <img srcset=\"https://3.basecampapi.com/195539477/blobs/e0c24a8764007e77cb12403c9612913a2f10e2de/previews/full?dppx=2 2x, https://3.basecampapi.com/195539477/blobs/e0c24a8764007e77cb12403c9612913a2f10e2de/previews/full?dppx=1 1x, https://3.basecampapi.com/195539477/blobs/e0c24a8764007e77cb12403c9612913a2f10e2de/previews/full?dppx=3 3x, https://3.basecampapi.com/195539477/blobs/e0c24a8764007e77cb12403c9612913a2f10e2de/previews/full?dppx=4 4x\" src=\"https://3.basecampapi.com/195539477/blobs/e0c24a8764007e77cb12403c9612913a2f10e2de/previews/full\">\n  <figcaption>\n    laptop_11\n  </figcaption>\n</figure></bc-attachment> <bc-attachment sgid=\"BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiL2dpZDovL2JjMy9BdHRhY2htZW50LzEwNDY2Mjg0ODY_ZXhwaXJlc19pbgY7AFRJIghwdXIGOwBUSSIPYXR0YWNoYWJsZQY7AFQ=--58c62d34383210581f1fc79361a50307607df6f7\" content-type=\"image/avif\" url=\"https://3.basecampapi.com/195539477/blobs/2f0f80be0932d4cb30c036ca2a31ee74ec3f5495/previews/full\" href=\"https://3.basecamp-static.com/195539477/blobs/2f0f80be0932d4cb30c036ca2a31ee74ec3f5495/download/laptop_12\" filename=\"laptop_12\" filesize=\"23152\" width=\"700\" height=\"387\" previewable=\"true\" presentation=\"\"><figure>\n    <img srcset=\"https://3.basecampapi.com/195539477/blobs/2f0f80be0932d4cb30c036ca2a31ee74ec3f5495/previews/full?dppx=2 2x, https://3.basecampapi.com/195539477/blobs/2f0f80be0932d4cb30c036ca2a31ee74ec3f5495/previews/full?dppx=1 1x, https://3.basecampapi.com/195539477/blobs/2f0f80be0932d4cb30c036ca2a31ee74ec3f5495/previews/full?dppx=3 3x, https://3.basecampapi.com/195539477/blobs/2f0f80be0932d4cb30c036ca2a31ee74ec3f5495/previews/full?dppx=4 4x\" src=\"https://3.basecampapi.com/195539477/blobs/2f0f80be0932d4cb30c036ca2a31ee74ec3f5495/previews/full\">\n  <figcaption>\n    laptop_12\n  </figcaption>\n</figure></bc-attachment> <bc-attachment sgid=\"BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiL2dpZDovL2JjMy9BdHRhY2htZW50LzEwNDY2Mjg0ODc_ZXhwaXJlc19pbgY7AFRJIghwdXIGOwBUSSIPYXR0YWNoYWJsZQY7AFQ=--0feed7e80ebc54613d3b860ddec93492919ff470\" content-type=\"image/avif\" url=\"https://3.basecampapi.com/195539477/blobs/6f7e5981c5699e1d400c582b97d47d28d59b5828/previews/full\" href=\"https://3.basecamp-static.com/195539477/blobs/6f7e5981c5699e1d400c582b97d47d28d59b5828/download/laptop_13\" filename=\"laptop_13\" filesize=\"27751\" width=\"700\" height=\"466\" previewable=\"true\" presentation=\"\"><figure>\n    <img srcset=\"https://3.basecampapi.com/195539477/blobs/6f7e5981c5699e1d400c582b97d47d28d59b5828/previews/full?dppx=2 2x, https://3.basecampapi.com/195539477/blobs/6f7e5981c5699e1d400c582b97d47d28d59b5828/previews/full?dppx=1 1x, https://3.basecampapi.com/195539477/blobs/6f7e5981c5699e1d400c582b97d47d28d59b5828/previews/full?dppx=3 3x, https://3.basecampapi.com/195539477/blobs/6f7e5981c5699e1d400c582b97d47d28d59b5828/previews/full?dppx=4 4x\" src=\"https://3.basecampapi.com/195539477/blobs/6f7e5981c5699e1d400c582b97d47d28d59b5828/previews/full\">\n  <figcaption>\n    laptop_13\n  </figcaption>\n</figure></bc-attachment> <bc-attachment sgid=\"BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiL2dpZDovL2JjMy9BdHRhY2htZW50LzEwNDY2Mjg0ODg_ZXhwaXJlc19pbgY7AFRJIghwdXIGOwBUSSIPYXR0YWNoYWJsZQY7AFQ=--7310094b0e002f2e888252d45ca93a224af64cd1\" content-type=\"image/avif\" url=\"https://3.basecampapi.com/195539477/blobs/264c0a5bd648394b8be1a56bb364e8296acedb09/previews/full\" href=\"https://3.basecamp-static.com/195539477/blobs/264c0a5bd648394b8be1a56bb364e8296acedb09/download/laptop_14\" filename=\"laptop_14\" filesize=\"15988\" width=\"700\" height=\"466\" previewable=\"true\" presentation=\"\"><figure>\n    <img srcset=\"https://3.basecampapi.com/195539477/blobs/264c0a5bd648394b8be1a56bb364e8296acedb09/previews/full?dppx=2 2x, https://3.basecampapi.com/195539477/blobs/264c0a5bd648394b8be1a56bb364e8296acedb09/previews/full?dppx=1 1x, https://3.basecampapi.com/195539477/blobs/264c0a5bd648394b8be1a56bb364e8296acedb09/previews/full?dppx=3 3x, https://3.basecampapi.com/195539477/blobs/264c0a5bd648394b8be1a56bb364e8296acedb09/previews/full?dppx=4 4x\" src=\"https://3.basecampapi.com/195539477/blobs/264c0a5bd648394b8be1a56bb364e8296acedb09/previews/full\">\n  <figcaption>\n    laptop_14\n  </figcaption>\n</figure></bc-attachment>",
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
  "id": 1069479406,
  "status": "active",
  "visible_to_clients": false,
  "created_at": "2025-12-18T23:30:00.000Z",
  "updated_at": "2026-01-31T08:37:37.818Z",
  "title": "We won Leto!",
  "inherits_status": true,
  "type": "Message",
  "url": "https://3.basecampapi.com/195539477/buckets/2085958504/messages/1069479406.json",
  "app_url": "https://3.basecamp.com/195539477/buckets/2085958504/messages/1069479406",
  "bookmark_url": "https://3.basecamp.com/195539477/my/bookmarks/BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiLmdpZDovL2JjMy9SZWNvcmRpbmcvMTA2OTQ3OTQwNj9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg1yZWFkYWJsZQY7AFQ=--309e0fbab86893aaaf279f01f2a0795c56716aeb",
  "subscription_url": "https://3.basecamp.com/195539477/buckets/2085958504/recordings/1069479406/subscription",
  "comments_count": 10,
  "comments_url": "https://3.basecampapi.com/195539477/buckets/2085958504/recordings/1069479406/comments.json",
  "parent": {
    "id": 1069479392,
    "title": "Message Board",
    "type": "Message::Board",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958504/message_boards/1069479392.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958504/message_boards/1069479392"
  },
  "bucket": {
    "id": 2085958504,
    "name": "The Leto Laptop",
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
  "content": "Hey guys,<br><br>We won the Leto account! This is huge for us, it really marks a turning point for the company.<br><br>As you know we've been pursuing bigger clients in the consumer space, but we've done so carefully. We've never been about getting the biggest clients - those are easy to get. We've been trying to get the best clients for us - ones that will challenge us, grow us, make us better, and ultimately giving us a platform to show how awesome you guys all are. And now we have that!<br><br>A big congrats to everyone who worked so hard to make this happen, and now the fun really begins. Most of the pitch team will stay on as leading members of the first project, the Leto Microsite.<br><br>Again, great job everyone, and let's go kick some more butt!<br><br>-Victor",
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

This endpoint will return `204 No Content` if the operation was a success.

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
