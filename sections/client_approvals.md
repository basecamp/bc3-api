Client approvals
================

Endpoints:

- [Get client approvals](#get-client-approvals)
- [Get a client approval](#get-a-client-approval)

Get client approvals
--------------------

* `GET /buckets/1/client/approvals.json` will return a [paginated list][pagination] of client approvals in the project with an ID of `1`.

###### Example JSON Response
<!-- START GET /buckets/1/client/approvals.json -->
```json
[
  {
    "id": 9007199254741743,
    "status": "active",
    "created_at": "2016-07-18T23:48:09.095Z",
    "updated_at": "2016-07-19T21:29:21.806Z",
    "title": "Business card",
    "type": "Client::Approval",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958499/client/approvals/9007199254741743.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958499/client/approvals/9007199254741743",
    "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7CEkiCGdpZAY6BkVUSSIuZ2lkOi8vYmMzL1JlY29yZGluZy8xMDY0MDkxMzU3P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg1yZWFkYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--dfea6d8a16e2f71836f2ce25ebf8c283a823c062.json",
    "parent": {
      "id": 9007199254741653,
      "title": "The Clientside",
      "type": "Client::Board",
      "url": "https://3.basecampapi.com/195539477/buckets/2085958499/client/board.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958499/client/board"
    },
    "bucket": {
      "id": 2085958499,
      "name": "The Leto Locator",
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
      "created_at": "2016-07-19T21:27:44.718Z",
      "updated_at": "2016-07-19T21:27:44.718Z",
      "admin": false,
      "owner": false,
      "time_zone": "America/Chicago",
      "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBEgqCjw=--8266bb0507508f3d46050d57b65924d5e2a005f3/avatar-64-x4",
      "company": {
        "id": 1033447817,
        "name": "Honcho Design"
      }
    },
    "content": "<div>OK, here's another one! We've got this business card worked up, just need your yes or no to proceed. Thanks!<br><br></div>\n<bc-attachment sgid=\"BAh7CEkiCGdpZAY6BkVUSSIvZ2lkOi8vYmMzL0F0dGFjaG1lbnQvMTAxOTczMDU0MT9leHBpcmVzX2luBjsAVEkiDHB1cnBvc2UGOwBUSSIPYXR0YWNoYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--010588da163ae8b6777939a970136f79d55b48b8\" content-type=\"image/jpeg\" url=\"https://3.basecamp.com/195539477/blobs/65eb219272af7a61ba216a85ef1f7032cf7a25e1/previews/full/images-images-bcard-2.jpg\" href=\"https://3.basecamp.com/195539477/blobs/65eb219272af7a61ba216a85ef1f7032cf7a25e1/download/images-images-bcard-2.jpg\" filename=\"images-images-bcard-2.jpg\" filesize=\"170483\" width=\"1824\" height=\"992\" previewable=\"true\"><figure>\n    <img srcset=\"https://3.basecampapi.com/195539477/blobs/65eb219272af7a61ba216a85ef1f7032cf7a25e1/previews/full/images-images-bcard-2.jpg?dppx=1 1x, https://3.basecampapi.com/195539477/blobs/65eb219272af7a61ba216a85ef1f7032cf7a25e1/previews/full/images-images-bcard-2.jpg?dppx=2 2x, https://3.basecampapi.com/195539477/blobs/65eb219272af7a61ba216a85ef1f7032cf7a25e1/previews/full/images-images-bcard-2.jpg?dppx=3 3x, https://3.basecampapi.com/195539477/blobs/65eb219272af7a61ba216a85ef1f7032cf7a25e1/previews/full/images-images-bcard-2.jpg?dppx=4 4x\" src=\"https://3.basecampapi.com/195539477/blobs/65eb219272af7a61ba216a85ef1f7032cf7a25e1/previews/full/images-images-bcard-2.jpg\" alt=\"Images images bcard 2\">\n  <figcaption>\n      images-images-bcard-2.jpg\n  </figcaption>\n</figure></bc-attachment>",
    "subject": "Business card",
    "due_on": null,
    "replies_count": 0,
    "replies_url": "https://3.basecampapi.com/195539477/buckets/2085958499/client/recordings/9007199254741743/replies.json",
    "approval_status": "pending",
    "approver": {
      "id": 1007299171,
      "attachable_sgid": "BAh7CEkiCGdpZAY6BkVUSSIrZ2lkOi8vYmMzL1BlcnNvbi8xMDA3Mjk5MTcxP2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg9hdHRhY2hhYmxlBjsAVEkiD2V4cGlyZXNfYXQGOwBUMA==--8c49bb120fce95a63ac0edd7a1d63f1e46b03c68",
      "name": "Miranda Grant",
      "email_address": "miranda@letobrand.com",
      "personable_type": "Client",
      "title": "Dynamic Markets Analyst",
      "bio": null,
      "created_at": "2016-09-09T22:58:30.413Z",
      "updated_at": "2016-09-09T22:58:30.413Z",
      "admin": false,
      "owner": false,
      "time_zone": "Etc/UTC",
      "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBGMqCjw=--cdbd6d1f0b3acc23c9728cf4ffd5dfe9d2333e02/avatar-64-x4",
      "company": {
        "id": 1033447818,
        "name": "Leto Brand"
      }
    }
  }
]
```
<!-- END GET /buckets/1/client/approvals.json -->
###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/client/approvals.json
```

Get a client approval
---------------------

* `GET /buckets/1/client/approvals/2.json` will return the client approval with an ID of `2` in the project with an ID of `1`.

###### Example JSON Response
<!-- START GET /buckets/1/client/approvals/2.json -->
```json
{
  "id": 9007199254741740,
  "status": "active",
  "created_at": "2016-07-16T00:14:09.095Z",
  "updated_at": "2016-07-19T21:29:21.552Z",
  "title": "New logo for the website",
  "type": "Client::Approval",
  "url": "https://3.basecampapi.com/195539477/buckets/2085958499/client/approvals/9007199254741740.json",
  "app_url": "https://3.basecamp.com/195539477/buckets/2085958499/client/approvals/9007199254741740",
  "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7CEkiCGdpZAY6BkVUSSIuZ2lkOi8vYmMzL1JlY29yZGluZy8xMDY0MDkxMzU0P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg1yZWFkYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--e94c9ee7c60206112b37949d7d10dd7764e6d4ea.json",
  "parent": {
    "id": 9007199254741653,
    "title": "The Clientside",
    "type": "Client::Board",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958499/client/board.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958499/client/board"
  },
  "bucket": {
    "id": 2085958499,
    "name": "The Leto Locator",
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
    "created_at": "2016-07-19T21:27:44.718Z",
    "updated_at": "2016-07-19T21:27:44.718Z",
    "admin": false,
    "owner": false,
    "time_zone": "America/Chicago",
    "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBEgqCjw=--8266bb0507508f3d46050d57b65924d5e2a005f3/avatar-64-x4",
    "company": {
      "id": 1033447817,
      "name": "Honcho Design"
    }
  },
  "content": "<div>Hey! We've wrapped up work on the new logo for the website and wanted to get your final sign off. What do you think? Let us know when you get a chance!<br><br></div>\n<bc-attachment sgid=\"BAh7CEkiCGdpZAY6BkVUSSIvZ2lkOi8vYmMzL0F0dGFjaG1lbnQvMTAxOTczMDU0MD9leHBpcmVzX2luBjsAVEkiDHB1cnBvc2UGOwBUSSIPYXR0YWNoYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--fe2c0fa6ae2625f0bf4268dab8e3152aa67dbbc6\" content-type=\"image/jpeg\" url=\"https://3.basecamp.com/195539477/blobs/33eba5838c3bd11a303c6c46a2c4d9260f82369e/previews/full/images-coudal-logo.jpg\" href=\"https://3.basecamp.com/195539477/blobs/33eba5838c3bd11a303c6c46a2c4d9260f82369e/download/images-coudal-logo.jpg\" filename=\"images-coudal-logo.jpg\" filesize=\"16536\" width=\"400\" height=\"400\" previewable=\"true\"><figure>\n    <img srcset=\"https://3.basecampapi.com/195539477/blobs/33eba5838c3bd11a303c6c46a2c4d9260f82369e/previews/full/images-coudal-logo.jpg?dppx=1 1x, https://3.basecampapi.com/195539477/blobs/33eba5838c3bd11a303c6c46a2c4d9260f82369e/previews/full/images-coudal-logo.jpg?dppx=2 2x, https://3.basecampapi.com/195539477/blobs/33eba5838c3bd11a303c6c46a2c4d9260f82369e/previews/full/images-coudal-logo.jpg?dppx=3 3x, https://3.basecampapi.com/195539477/blobs/33eba5838c3bd11a303c6c46a2c4d9260f82369e/previews/full/images-coudal-logo.jpg?dppx=4 4x\" src=\"https://3.basecampapi.com/195539477/blobs/33eba5838c3bd11a303c6c46a2c4d9260f82369e/previews/full/images-coudal-logo.jpg\" alt=\"Images coudal logo\">\n  <figcaption>\n      images-coudal-logo.jpg\n  </figcaption>\n</figure></bc-attachment>",
  "subject": "New logo for the website",
  "due_on": null,
  "replies_count": 0,
  "replies_url": "https://3.basecampapi.com/195539477/buckets/2085958499/client/recordings/9007199254741740/replies.json",
  "approval_status": "approved",
  "approver": {
    "id": 1007299170,
    "attachable_sgid": "BAh7CEkiCGdpZAY6BkVUSSIrZ2lkOi8vYmMzL1BlcnNvbi8xMDA3Mjk5MTcwP2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg9hdHRhY2hhYmxlBjsAVEkiD2V4cGlyZXNfYXQGOwBUMA==--c2668ff0d13534b0b05c2059e4307c7b2b8506de",
    "name": "Stephen Early",
    "email_address": "stephen@letobrand.com",
    "personable_type": "Client",
    "title": "National Directives Director",
    "bio": null,
    "created_at": "2016-09-09T22:58:30.384Z",
    "updated_at": "2016-09-09T22:58:30.384Z",
    "admin": false,
    "owner": false,
    "time_zone": "Etc/UTC",
    "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBGIqCjw=--30a34b0522d7ba3484b8c4dcd65d9087a1baef0e/avatar-64-x4",
    "company": {
      "id": 1033447818,
      "name": "Leto Brand"
    }
  },
  "responses": [
    {
      "id": 9007199254741742,
      "status": "active",
      "created_at": "2016-07-16T02:53:09.095Z",
      "updated_at": "2016-07-16T02:53:09.095Z",
      "title": "Answer Re: New logo for the website",
      "type": "Client::Approval::Response",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958499/client/approvals/9007199254741740#__recording_9007199254741742",
      "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7CEkiCGdpZAY6BkVUSSIuZ2lkOi8vYmMzL1JlY29yZGluZy8xMDY0MDkxMzU2P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg1yZWFkYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--91beafecc445ff005bafcfe69dc95462bb5f95eb.json",
      "parent": {
        "id": 9007199254741740,
        "title": "New logo for the website",
        "type": "Client::Approval",
        "url": "https://3.basecampapi.com/195539477/buckets/2085958499/client/approvals/9007199254741740.json",
        "app_url": "https://3.basecamp.com/195539477/buckets/2085958499/client/approvals/9007199254741740"
      },
      "bucket": {
        "id": 2085958499,
        "name": "The Leto Locator",
        "type": "Project"
      },
      "creator": {
        "id": 1007299172,
        "attachable_sgid": "BAh7CEkiCGdpZAY6BkVUSSIrZ2lkOi8vYmMzL1BlcnNvbi8xMDA3Mjk5MTcyP2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg9hdHRhY2hhYmxlBjsAVEkiD2V4cGlyZXNfYXQGOwBUMA==--6432a2b40209df697aeb57743d283cd642358120",
        "name": "Beth Allen",
        "email_address": "beth@letobrand.com",
        "personable_type": "Client",
        "title": "Product Tactics Architect",
        "bio": null,
        "created_at": "2016-09-09T22:58:30.427Z",
        "updated_at": "2016-09-09T22:58:30.427Z",
        "admin": false,
        "owner": false,
        "time_zone": "Etc/UTC",
        "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBGQqCjw=--0c364fe4f53105736bd410e8dad77e85c60e5465/avatar-64-x4",
        "company": {
          "id": 1033447818,
          "name": "Leto Brand"
        }
      },
      "content": "<div>Looks great! Thanks for all your hard work on this.</div>",
      "approved": true
    }
  ]
}
```
<!-- END GET /buckets/1/client/approvals/2.json -->
###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/client/approvals/2.json
```

[pagination]: https://github.com/basecamp/bc3-api/blob/master/README.md#pagination
