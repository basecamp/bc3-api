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
    "id": 1069479654,
    "status": "active",
    "visible_to_clients": false,
    "created_at": "2022-11-21T12:13:14.049Z",
    "updated_at": "2022-11-22T08:24:21.287Z",
    "title": "Business card",
    "inherits_status": true,
    "type": "Client::Approval",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958500/client/approvals/1069479654.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958500/client/approvals/1069479654",
    "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7CEkiCGdpZAY6BkVUSSIuZ2lkOi8vYmMzL1JlY29yZGluZy8xMDY5NDc5NjU0P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg1yZWFkYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--9cfe8a2356c54d6c68971d684758701488bccd00.json",
    "subscription_url": "https://3.basecampapi.com/195539477/buckets/2085958500/recordings/1069479654/subscription.json",
    "parent": {
      "id": 1069479564,
      "title": "The Clientside",
      "type": "Client::Board",
      "url": "https://3.basecampapi.com/195539477/buckets/2085958500/client/board.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958500/client/board.1069479564"
    },
    "bucket": {
      "id": 2085958500,
      "name": "The Leto Locator",
      "type": "Project"
    },
    "creator": {
      "id": 1049715915,
      "attachable_sgid": "BAh7CEkiCGdpZAY6BkVUSSIrZ2lkOi8vYmMzL1BlcnNvbi8xMDQ5NzE1OTE1P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg9hdHRhY2hhYmxlBjsAVEkiD2V4cGlyZXNfYXQGOwBUMA==--aeb392ebf54ffd820e45f27add22bae3a8c7da56",
      "name": "Annie Bryan",
      "email_address": "annie@honchodesign.com",
      "personable_type": "User",
      "title": "Central Markets Manager",
      "bio": "To open a store is easy, to keep it open is an art",
      "location": null,
      "created_at": "2022-11-22T08:23:21.911Z",
      "updated_at": "2022-11-22T08:23:21.911Z",
      "admin": false,
      "owner": false,
      "client": false,
      "employee": true,
      "time_zone": "America/Chicago",
      "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBMtkkT4=--9927c47a4cbee30a7f9aea667882496aba799149/avatar?v=1",
      "company": {
        "id": 1033447817,
        "name": "Honcho Design"
      },
      "can_manage_projects": true,
      "can_manage_people": true
    },
    "content": "<div>OK, here's another one! We've got this business card worked up, just need your yes or no to proceed. Thanks!<br><br></div>\n<bc-attachment sgid=\"BAh7CEkiCGdpZAY6BkVUSSIvZ2lkOi8vYmMzL0F0dGFjaG1lbnQvMTA0NjYyODUwOD9leHBpcmVzX2luBjsAVEkiDHB1cnBvc2UGOwBUSSIPYXR0YWNoYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--9e4ae61292d6ab96839a87e62fd01332d450b305\" content-type=\"image/jpeg\" href=\"http://storage.3.basecamp.test/195539477/blobs/120963eadc5d765e5d2ce99aef5654dbee59b6a6/download/images-images-bcard-2.jpg\" filename=\"images-images-bcard-2.jpg\" filesize=\"78\"><figure>\n  <figcaption>\n    images-images-bcard-2.jpg\n  </figcaption>\n</figure></bc-attachment>",
    "subject": "Business card",
    "due_on": null,
    "replies_count": 0,
    "replies_url": "https://3.basecampapi.com/195539477/buckets/2085958500/client/recordings/1069479654/replies.json",
    "approval_status": "pending",
    "approver": {
      "id": 1049715942,
      "attachable_sgid": "BAh7CEkiCGdpZAY6BkVUSSIrZ2lkOi8vYmMzL1BlcnNvbi8xMDQ5NzE1OTQyP2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg9hdHRhY2hhYmxlBjsAVEkiD2V4cGlyZXNfYXQGOwBUMA==--fa05bcc15bdd53f8a944ba3f2386b0ec8aedfc73",
      "name": "Miranda Grant",
      "email_address": "miranda@letobrand.com",
      "personable_type": "Client",
      "title": "Dynamic Markets Analyst",
      "bio": null,
      "location": null,
      "created_at": "2022-11-22T08:23:22.343Z",
      "updated_at": "2022-11-22T08:23:22.343Z",
      "admin": false,
      "owner": false,
      "client": false,
      "employee": false,
      "time_zone": "Etc/UTC",
      "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBOZkkT4=--b8553b154990a1112ab6275b749296c4a3b56334/avatar?v=1",
      "company": {
        "id": 1033447818,
        "name": "Leto Brand"
      },
      "can_manage_projects": false,
      "can_manage_people": false
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
  "id": 1069479651,
  "status": "active",
  "visible_to_clients": false,
  "created_at": "2022-11-18T09:54:14.049Z",
  "updated_at": "2022-11-22T08:24:21.164Z",
  "title": "New logo for the website",
  "inherits_status": true,
  "type": "Client::Approval",
  "url": "https://3.basecampapi.com/195539477/buckets/2085958500/client/approvals/1069479651.json",
  "app_url": "https://3.basecamp.com/195539477/buckets/2085958500/client/approvals/1069479651",
  "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7CEkiCGdpZAY6BkVUSSIuZ2lkOi8vYmMzL1JlY29yZGluZy8xMDY5NDc5NjUxP2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg1yZWFkYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--e141c7eaa049920cdc4bb43d509f3c99ae537f68.json",
  "subscription_url": "https://3.basecampapi.com/195539477/buckets/2085958500/recordings/1069479651/subscription.json",
  "parent": {
    "id": 1069479564,
    "title": "The Clientside",
    "type": "Client::Board",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958500/client/board.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958500/client/board.1069479564"
  },
  "bucket": {
    "id": 2085958500,
    "name": "The Leto Locator",
    "type": "Project"
  },
  "creator": {
    "id": 1049715915,
    "attachable_sgid": "BAh7CEkiCGdpZAY6BkVUSSIrZ2lkOi8vYmMzL1BlcnNvbi8xMDQ5NzE1OTE1P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg9hdHRhY2hhYmxlBjsAVEkiD2V4cGlyZXNfYXQGOwBUMA==--aeb392ebf54ffd820e45f27add22bae3a8c7da56",
    "name": "Annie Bryan",
    "email_address": "annie@honchodesign.com",
    "personable_type": "User",
    "title": "Central Markets Manager",
    "bio": "To open a store is easy, to keep it open is an art",
    "location": null,
    "created_at": "2022-11-22T08:23:21.911Z",
    "updated_at": "2022-11-22T08:23:21.911Z",
    "admin": false,
    "owner": false,
    "client": false,
    "employee": true,
    "time_zone": "America/Chicago",
    "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBMtkkT4=--9927c47a4cbee30a7f9aea667882496aba799149/avatar?v=1",
    "company": {
      "id": 1033447817,
      "name": "Honcho Design"
    },
    "can_manage_projects": true,
    "can_manage_people": true
  },
  "content": "<div>Hey! We've wrapped up work on the new logo for the website and wanted to get your final sign off. What do you think? Let us know when you get a chance!<br><br></div>\n<bc-attachment sgid=\"BAh7CEkiCGdpZAY6BkVUSSIvZ2lkOi8vYmMzL0F0dGFjaG1lbnQvMTA0NjYyODUwNz9leHBpcmVzX2luBjsAVEkiDHB1cnBvc2UGOwBUSSIPYXR0YWNoYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--36cd4d0b64342a5c6f62d85c73755c5c80bc7263\" content-type=\"image/jpeg\" href=\"http://storage.3.basecamp.test/195539477/blobs/ceeb417cb53c029ec6c4d7894516848cf048ee2a/download/images-coudal-logo.jpg\" filename=\"images-coudal-logo.jpg\" filesize=\"75\"><figure>\n  <figcaption>\n    images-coudal-logo.jpg\n  </figcaption>\n</figure></bc-attachment>",
  "subject": "New logo for the website",
  "due_on": null,
  "replies_count": 0,
  "replies_url": "https://3.basecampapi.com/195539477/buckets/2085958500/client/recordings/1069479651/replies.json",
  "approval_status": "approved",
  "approver": {
    "id": 1049715941,
    "attachable_sgid": "BAh7CEkiCGdpZAY6BkVUSSIrZ2lkOi8vYmMzL1BlcnNvbi8xMDQ5NzE1OTQxP2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg9hdHRhY2hhYmxlBjsAVEkiD2V4cGlyZXNfYXQGOwBUMA==--10099ab54fac5884db30b9bd897ea030023d4d0a",
    "name": "Stephen Early",
    "email_address": "stephen@letobrand.com",
    "personable_type": "Client",
    "title": "National Directives Director",
    "bio": null,
    "location": null,
    "created_at": "2022-11-22T08:23:22.341Z",
    "updated_at": "2022-11-22T08:23:22.341Z",
    "admin": false,
    "owner": false,
    "client": false,
    "employee": false,
    "time_zone": "Etc/UTC",
    "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBOVkkT4=--33e3fc268c87411378691c71b6f13658e0b40967/avatar?v=1",
    "company": {
      "id": 1033447818,
      "name": "Leto Brand"
    },
    "can_manage_projects": false,
    "can_manage_people": false
  },
  "responses": [
    {
      "id": 1069479653,
      "status": "active",
      "visible_to_clients": false,
      "created_at": "2022-11-18T10:47:14.049Z",
      "updated_at": "2022-11-18T10:47:14.049Z",
      "title": "Answer Re: New logo for the website",
      "inherits_status": true,
      "type": "Client::Approval::Response",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958500/client/approvals/1069479651#__recording_1069479653",
      "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7CEkiCGdpZAY6BkVUSSIuZ2lkOi8vYmMzL1JlY29yZGluZy8xMDY5NDc5NjUzP2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg1yZWFkYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--df835cb45337b87233145ffb48304200c319c153.json",
      "parent": {
        "id": 1069479651,
        "title": "New logo for the website",
        "type": "Client::Approval",
        "url": "https://3.basecampapi.com/195539477/buckets/2085958500/client/approvals/1069479651.json",
        "app_url": "https://3.basecamp.com/195539477/buckets/2085958500/client/approvals/1069479651"
      },
      "bucket": {
        "id": 2085958500,
        "name": "The Leto Locator",
        "type": "Project"
      },
      "creator": {
        "id": 1049715943,
        "attachable_sgid": "BAh7CEkiCGdpZAY6BkVUSSIrZ2lkOi8vYmMzL1BlcnNvbi8xMDQ5NzE1OTQzP2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg9hdHRhY2hhYmxlBjsAVEkiD2V4cGlyZXNfYXQGOwBUMA==--aa4fa01aface7171cf769ff933e6defc921f6169",
        "name": "Beth Allen",
        "email_address": "beth@letobrand.com",
        "personable_type": "Client",
        "title": "Product Tactics Architect",
        "bio": null,
        "location": null,
        "created_at": "2022-11-22T08:23:22.345Z",
        "updated_at": "2022-11-22T08:23:22.345Z",
        "admin": false,
        "owner": false,
        "client": false,
        "employee": false,
        "time_zone": "Etc/UTC",
        "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBOdkkT4=--1d2b80e583133f93afe008f88166b674fc0287a4/avatar?v=1",
        "company": {
          "id": 1033447818,
          "name": "Leto Brand"
        },
        "can_manage_projects": false,
        "can_manage_people": false
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
