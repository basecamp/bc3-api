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
      "id": 1007299209,
      "name": "Annie Bryan",
      "email_address": "annie@honchodesign.com",
      "personable_type": "User",
      "title": "Central Markets Manager",
      "created_at": "2016-07-08T16:48:02.619Z",
      "updated_at": "2016-07-08T16:48:02.619Z",
      "admin": false,
      "owner": false,
      "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBIkqCjw=--003094c5a28c4331af92401ec3675148e81d7bc1/avatar-64-x4",
      "company": {
        "id": 1033447822,
        "name": "Honcho Design"
      }
    },
    "content_html": "OK, here's another one! We've got this business card worked up, just need your yes or no to proceed. Thanks!<br><br><div data-trix-attachment='{\"sgid\":\"BAh7CEkiCGdpZAY6BkVUSSIvZ2lkOi8vYmMzL0F0dGFjaG1lbnQvMTAxOTczMDY2OT9leHBpcmVzX2luBjsAVEkiDHB1cnBvc2UGOwBUSSIPYXR0YWNoYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--2d82d37e1b7f2fcb02cf8496f28248be744f23a4\",\"contentType\":\"image/jpeg\",\"previewable\":true,\"filename\":\"images-images-bcard-2.jpg\",\"filesize\":170483,\"url\":\"https://3.basecamp.com/195539477/blobs/67e03adc47a6339f7e22c76c2de266089c416b36/previews/full/images-images-bcard-2.jpg\"}' data-trix-attributes=\"{}\"></div>",
    "content_text": "OK, here's another one! We've got this business card worked up, just need your yes or no to proceed. Thanks!",
    "subject": "Business card",
    "due_on": null,
    "replies_count": 0,
    "replies_url": "https://3.basecampapi.com/195539477/buckets/2085958499/client/recordings/9007199254741743/replies.json",
    "approval_status": "pending",
    "approver": {
      "id": 1007299236,
      "name": "Miranda Grant",
      "email_address": "miranda@letobrand.com",
      "personable_type": "Client",
      "title": "Dynamic Markets Analyst",
      "created_at": "2016-07-08T16:48:06.631Z",
      "updated_at": "2016-07-08T16:48:06.631Z",
      "admin": false,
      "owner": false,
      "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBKQqCjw=--584072d3a05649645bbb413e74b1e0306ab0b12a/avatar-64-x4",
      "company": {
        "id": 1033447823,
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
    "id": 1007299209,
    "name": "Annie Bryan",
    "email_address": "annie@honchodesign.com",
    "personable_type": "User",
    "title": "Central Markets Manager",
    "created_at": "2016-07-08T16:48:02.619Z",
    "updated_at": "2016-07-08T16:48:02.619Z",
    "admin": false,
    "owner": false,
    "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBIkqCjw=--003094c5a28c4331af92401ec3675148e81d7bc1/avatar-64-x4",
    "company": {
      "id": 1033447822,
      "name": "Honcho Design"
    }
  },
  "content_html": "Hey! We've wrapped up work on the new logo for the website and wanted to get your final sign off. What do you think? Let us know when you get a chance!<br><br><div data-trix-attachment='{\"sgid\":\"BAh7CEkiCGdpZAY6BkVUSSIvZ2lkOi8vYmMzL0F0dGFjaG1lbnQvMTAxOTczMDY2OD9leHBpcmVzX2luBjsAVEkiDHB1cnBvc2UGOwBUSSIPYXR0YWNoYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--0bfcb4dabacf0e5f70f4ddd01655015a769fbd82\",\"contentType\":\"image/jpeg\",\"previewable\":true,\"filename\":\"images-coudal-logo.jpg\",\"filesize\":16536,\"url\":\"https://3.basecamp.com/195539477/blobs/5ac1085ad0117370c25f0221fe7683d4a0b06e9c/previews/full/images-coudal-logo.jpg\"}' data-trix-attributes=\"{}\"></div>",
  "content_text": "Hey! We've wrapped up work on the new logo for the website and wanted to get your final sign off. What do you think? Let us know when you get a chance!",
  "subject": "New logo for the website",
  "due_on": null,
  "replies_count": 0,
  "replies_url": "https://3.basecampapi.com/195539477/buckets/2085958499/client/recordings/9007199254741740/replies.json",
  "approval_status": "approved",
  "approver": {
    "id": 1007299235,
    "name": "Stephen Early",
    "email_address": "stephen@letobrand.com",
    "personable_type": "Client",
    "title": "National Directives Director",
    "created_at": "2016-07-08T16:48:06.620Z",
    "updated_at": "2016-07-08T16:48:06.620Z",
    "admin": false,
    "owner": false,
    "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBKMqCjw=--605a670338311d36b6cb93f8fc1e94a466a047b4/avatar-64-x4",
    "company": {
      "id": 1033447823,
      "name": "Leto Brand"
    }
  },
  "responses": [
    {
      "id": 9007199254741742,
      "status": "active",
      "created_at": "2016-07-04T20:34:44.210Z",
      "updated_at": "2016-07-04T20:34:44.210Z",
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
      "creator": {
        "id": 1007299237,
        "name": "Beth Allen",
        "email_address": "beth@letobrand.com",
        "personable_type": "Client",
        "title": "Product Tactics Architect",
        "created_at": "2016-07-08T16:48:06.642Z",
        "updated_at": "2016-07-08T16:48:06.642Z",
        "admin": false,
        "owner": false,
        "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBKUqCjw=--f7a188667d86c05c148bb4f52caac7ab6d25d7f2/avatar-64-x4",
        "company": {
          "id": 1033447823,
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
