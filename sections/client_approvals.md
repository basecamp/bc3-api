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
    "created_at": "2016-07-07T04:07:32.028Z",
    "updated_at": "2016-07-08T02:17:44.251Z",
    "type": "Client::Approval",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958499/client/approvals/9007199254741743.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958499/client/approvals/9007199254741743",
    "bucket": {
      "id": 2085958499,
      "type": "Project"
    },
    "parent": {
      "id": 9007199254741653,
      "type": "Client::Board",
      "url": "https://3.basecampapi.com/195539477/buckets/2085958499/client/board.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958499/client/board"
    },
    "creator": {
      "id": 1007299144,
      "name": "Annie Bryan",
      "email_address": "annie@honchodesign.com",
      "personable_type": "User",
      "title": "Central Markets Manager",
      "created_at": "2016-07-08T02:16:07.615Z",
      "updated_at": "2016-07-08T02:16:07.615Z",
      "admin": false,
      "owner": false,
      "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBEgqCjw=--8266bb0507508f3d46050d57b65924d5e2a005f3/avatar-64-x4",
      "company": {
        "id": 1033447817,
        "name": "Honcho Design"
      }
    },
    "content_html": "OK, here's another one! We've got this business card worked up, just need your yes or no to proceed. Thanks!<br><br><div data-trix-attachment='{\"sgid\":\"BAh7CEkiCGdpZAY6BkVUSSIvZ2lkOi8vYmMzL0F0dGFjaG1lbnQvMTAxOTczMDU0MT9leHBpcmVzX2luBjsAVEkiDHB1cnBvc2UGOwBUSSIPYXR0YWNoYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--010588da163ae8b6777939a970136f79d55b48b8\",\"contentType\":\"image/jpeg\",\"previewable\":true,\"filename\":\"images-images-bcard-2.jpg\",\"filesize\":170483,\"url\":\"https://3.basecamp.com/195539477/blobs/a3ccf5fb54a8261e9b98d795f10b8561fe4f0cfe/previews/full/images-images-bcard-2.jpg\"}' data-trix-attributes=\"{}\"></div>",
    "content_text": "OK, here's another one! We've got this business card worked up, just need your yes or no to proceed. Thanks!",
    "subject": "Business card",
    "due_on": null,
    "replies_count": 0,
    "replies_url": "https://3.basecampapi.com/195539477/buckets/2085958499/client/recordings/9007199254741743/replies.json",
    "approval_status": "pending",
    "approver": {
      "id": 1007299171,
      "name": "Miranda Grant",
      "email_address": "miranda@letobrand.com",
      "personable_type": "Client",
      "title": "Dynamic Markets Analyst",
      "created_at": "2016-07-08T02:16:11.469Z",
      "updated_at": "2016-07-08T02:16:11.469Z",
      "admin": false,
      "owner": false,
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

* `GET /buckets/1/client/approvals/2.json` will return the client approval with an ID of `2` in the Basecamp with an ID of `1`.

###### Example JSON Response
<!-- START GET /buckets/1/client/approvals/2.json -->
```json
{
  "id": 9007199254741740,
  "status": "active",
  "created_at": "2016-07-04T05:03:32.028Z",
  "updated_at": "2016-07-08T02:17:44.023Z",
  "type": "Client::Approval",
  "url": "https://3.basecampapi.com/195539477/buckets/2085958499/client/approvals/9007199254741740.json",
  "app_url": "https://3.basecamp.com/195539477/buckets/2085958499/client/approvals/9007199254741740",
  "bucket": {
    "id": 2085958499,
    "type": "Project"
  },
  "parent": {
    "id": 9007199254741653,
    "type": "Client::Board",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958499/client/board.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958499/client/board"
  },
  "creator": {
    "id": 1007299144,
    "name": "Annie Bryan",
    "email_address": "annie@honchodesign.com",
    "personable_type": "User",
    "title": "Central Markets Manager",
    "created_at": "2016-07-08T02:16:07.615Z",
    "updated_at": "2016-07-08T02:16:07.615Z",
    "admin": false,
    "owner": false,
    "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBEgqCjw=--8266bb0507508f3d46050d57b65924d5e2a005f3/avatar-64-x4",
    "company": {
      "id": 1033447817,
      "name": "Honcho Design"
    }
  },
  "content_html": "Hey! We've wrapped up work on the new logo for the website and wanted to get your final sign off. What do you think? Let us know when you get a chance!<br><br><div data-trix-attachment='{\"sgid\":\"BAh7CEkiCGdpZAY6BkVUSSIvZ2lkOi8vYmMzL0F0dGFjaG1lbnQvMTAxOTczMDU0MD9leHBpcmVzX2luBjsAVEkiDHB1cnBvc2UGOwBUSSIPYXR0YWNoYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--fe2c0fa6ae2625f0bf4268dab8e3152aa67dbbc6\",\"contentType\":\"image/jpeg\",\"previewable\":true,\"filename\":\"images-coudal-logo.jpg\",\"filesize\":16536,\"url\":\"https://3.basecamp.com/195539477/blobs/f316fd5d8110ebab2de56f315914908c378908c2/previews/full/images-coudal-logo.jpg\"}' data-trix-attributes=\"{}\"></div>",
  "content_text": "Hey! We've wrapped up work on the new logo for the website and wanted to get your final sign off. What do you think? Let us know when you get a chance!",
  "subject": "New logo for the website",
  "due_on": null,
  "replies_count": 0,
  "replies_url": "https://3.basecampapi.com/195539477/buckets/2085958499/client/recordings/9007199254741740/replies.json",
  "approval_status": "approved",
  "approver": {
    "id": 1007299170,
    "name": "Stephen Early",
    "email_address": "stephen@letobrand.com",
    "personable_type": "Client",
    "title": "National Directives Director",
    "created_at": "2016-07-08T02:16:11.461Z",
    "updated_at": "2016-07-08T02:16:11.461Z",
    "admin": false,
    "owner": false,
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
      "created_at": "2016-07-04T07:22:32.028Z",
      "updated_at": "2016-07-04T07:22:32.028Z",
      "type": "Client::Approval::Response",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958499/client/approvals/9007199254741740#__recording_9007199254741742",
      "bucket": {
        "id": 2085958499,
        "type": "Project"
      },
      "parent": {
        "id": 9007199254741740,
        "type": "Client::Approval",
        "url": "https://3.basecampapi.com/195539477/buckets/2085958499/client/approvals/9007199254741740.json",
        "app_url": "https://3.basecamp.com/195539477/buckets/2085958499/client/approvals/9007199254741740"
      },
      "creator": {
        "id": 1007299172,
        "name": "Beth Allen",
        "email_address": "beth@letobrand.com",
        "personable_type": "Client",
        "title": "Product Tactics Architect",
        "created_at": "2016-07-08T02:16:11.477Z",
        "updated_at": "2016-07-08T02:16:11.477Z",
        "admin": false,
        "owner": false,
        "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBGQqCjw=--0c364fe4f53105736bd410e8dad77e85c60e5465/avatar-64-x4",
        "company": {
          "id": 1033447818,
          "name": "Leto Brand"
        }
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
