Client approvals
================

Endpoints:

- [Get client approvals](#get-client-approvals)
- [Get a client approval](#get-a-client-approval)

Get client approvals
--------------------

* `GET /buckets/1/client/approvals.json` will return a [paginated list][pagination] of client approvals in the Basecamp with an ID of `1`.

###### Example JSON Response
<!-- START GET /buckets/1/client/approvals.json -->
```json
[
  {
    "id": 9007199254741743,
    "status": "active",
    "created_at": "2016-07-07T17:45:44.210Z",
    "updated_at": "2016-07-08T16:49:59.554Z",
    "type": "Client::Approval",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958499/client/approvals/9007199254741743.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958499/client/approvals/9007199254741743",
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
      "name": "Annie Bryan",
      "email_address": "annie@honchodesign.com",
      "personable_type": "User",
      "title": "Central Markets Manager",
      "created_at": "2016-07-13T14:03:35.872Z",
      "updated_at": "2016-07-13T14:03:35.872Z",
      "admin": false,
      "owner": false,
      "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBEgqCjw=--8266bb0507508f3d46050d57b65924d5e2a005f3/avatar-64-x4",
      "company": {
        "id": 1033447817,
        "name": "Honcho Design"
      }
    },
    "content": "OK, here's another one! We've got this business card worked up, just need your yes or no to proceed. Thanks!<br><br>\n<bc-attachment sgid=\"BAh7CEkiCGdpZAY6BkVUSSIvZ2lkOi8vYmMzL0F0dGFjaG1lbnQvMTAxOTczMDU0MT9leHBpcmVzX2luBjsAVEkiDHB1cnBvc2UGOwBUSSIPYXR0YWNoYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--010588da163ae8b6777939a970136f79d55b48b8\" content-type=\"image/jpeg\" url=\"https://3.basecamp.com/195539477/blobs/0632f71e5413a0ef1c19ec783895a15e6c9b4501/previews/full/images-images-bcard-2.jpg\" href=\"https://3.basecamp.com/195539477/blobs/0632f71e5413a0ef1c19ec783895a15e6c9b4501/download/images-images-bcard-2.jpg\" filename=\"images-images-bcard-2.jpg\" filesize=\"170483\" width=\"1824\" height=\"992\" previewable=\"true\"><figure>\n    <img srcset=\"https://3.basecampapi.com/195539477/blobs/0632f71e5413a0ef1c19ec783895a15e6c9b4501/previews/full/images-images-bcard-2.jpg?dppx=1 1x, https://3.basecampapi.com/195539477/blobs/0632f71e5413a0ef1c19ec783895a15e6c9b4501/previews/full/images-images-bcard-2.jpg?dppx=2 2x, https://3.basecampapi.com/195539477/blobs/0632f71e5413a0ef1c19ec783895a15e6c9b4501/previews/full/images-images-bcard-2.jpg?dppx=3 3x, https://3.basecampapi.com/195539477/blobs/0632f71e5413a0ef1c19ec783895a15e6c9b4501/previews/full/images-images-bcard-2.jpg?dppx=4 4x\" src=\"https://3.basecampapi.com/195539477/blobs/0632f71e5413a0ef1c19ec783895a15e6c9b4501/previews/full/images-images-bcard-2.jpg\" alt=\"Images images bcard 2\">\n  <figcaption>\n      images-images-bcard-2.jpg\n  </figcaption>\n</figure></bc-attachment>",
    "subject": "Business card",
    "due_on": null,
    "replies_count": 0,
    "replies_url": "https://3.basecampapi.com/195539477/buckets/2085958499/client/recordings/9007199254741743/replies.json",
    "approval_status": "pending"
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

* `GET /buckets/1/client/approvals/2.json` will return the client approval with an ID of `2` in the Basecamp with an ID of `1`.

###### Example JSON Response
<!-- START GET /buckets/1/client/approvals/2.json -->
```json
{
  "id": 9007199254741740,
  "status": "active",
  "created_at": "2016-07-04T17:52:44.210Z",
  "updated_at": "2016-07-08T16:49:59.220Z",
  "type": "Client::Approval",
  "url": "https://3.basecampapi.com/195539477/buckets/2085958499/client/approvals/9007199254741740.json",
  "app_url": "https://3.basecamp.com/195539477/buckets/2085958499/client/approvals/9007199254741740",
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
    "name": "Annie Bryan",
    "email_address": "annie@honchodesign.com",
    "personable_type": "User",
    "title": "Central Markets Manager",
    "created_at": "2016-07-13T14:03:35.872Z",
    "updated_at": "2016-07-13T14:03:35.872Z",
    "admin": false,
    "owner": false,
    "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBEgqCjw=--8266bb0507508f3d46050d57b65924d5e2a005f3/avatar-64-x4",
    "company": {
      "id": 1033447817,
      "name": "Honcho Design"
    }
  },
  "content": "Hey! We've wrapped up work on the new logo for the website and wanted to get your final sign off. What do you think? Let us know when you get a chance!<br><br>\n<bc-attachment sgid=\"BAh7CEkiCGdpZAY6BkVUSSIvZ2lkOi8vYmMzL0F0dGFjaG1lbnQvMTAxOTczMDU0MD9leHBpcmVzX2luBjsAVEkiDHB1cnBvc2UGOwBUSSIPYXR0YWNoYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--fe2c0fa6ae2625f0bf4268dab8e3152aa67dbbc6\" content-type=\"image/jpeg\" url=\"https://3.basecamp.com/195539477/blobs/c221496c89cae594bda8cb212bd54111a77cb942/previews/full/images-coudal-logo.jpg\" href=\"https://3.basecamp.com/195539477/blobs/c221496c89cae594bda8cb212bd54111a77cb942/download/images-coudal-logo.jpg\" filename=\"images-coudal-logo.jpg\" filesize=\"16536\" width=\"400\" height=\"400\" previewable=\"true\"><figure>\n    <img srcset=\"https://3.basecampapi.com/195539477/blobs/c221496c89cae594bda8cb212bd54111a77cb942/previews/full/images-coudal-logo.jpg?dppx=1 1x, https://3.basecampapi.com/195539477/blobs/c221496c89cae594bda8cb212bd54111a77cb942/previews/full/images-coudal-logo.jpg?dppx=2 2x, https://3.basecampapi.com/195539477/blobs/c221496c89cae594bda8cb212bd54111a77cb942/previews/full/images-coudal-logo.jpg?dppx=3 3x, https://3.basecampapi.com/195539477/blobs/c221496c89cae594bda8cb212bd54111a77cb942/previews/full/images-coudal-logo.jpg?dppx=4 4x\" src=\"https://3.basecampapi.com/195539477/blobs/c221496c89cae594bda8cb212bd54111a77cb942/previews/full/images-coudal-logo.jpg\" alt=\"Images coudal logo\">\n  <figcaption>\n      images-coudal-logo.jpg\n  </figcaption>\n</figure></bc-attachment>",
  "subject": "New logo for the website",
  "due_on": null,
  "replies_count": 0,
  "replies_url": "https://3.basecampapi.com/195539477/buckets/2085958499/client/recordings/9007199254741740/replies.json",
  "approval_status": "approved",
  "responses": [
    {
      "id": 9007199254741742,
      "status": "active",
      "created_at": "2016-07-09T18:51:30.037Z",
      "updated_at": "2016-07-09T18:51:30.037Z",
      "type": "Client::Approval::Response",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958499/client/approvals/9007199254741740#__recording_9007199254741742",
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
      "content": "Looks great! Thanks for all your hard work on this.",
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
