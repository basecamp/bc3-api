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
    "id": 1069479710,
    "status": "active",
    "visible_to_clients": false,
    "created_at": "2026-01-30T19:58:00.000Z",
    "updated_at": "2026-01-30T19:58:00.000Z",
    "title": "Business card",
    "inherits_status": true,
    "type": "Client::Approval",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958505/client/approvals/1069479710.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958505/client/approvals/1069479710",
    "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiLmdpZDovL2JjMy9SZWNvcmRpbmcvMTA2OTQ3OTcxMD9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg1yZWFkYWJsZQY7AFQ=--c829d12a1ba1abe280f06a0f79bcbc38c7c189cb.json",
    "subscription_url": "https://3.basecampapi.com/195539477/buckets/2085958505/recordings/1069479710/subscription.json",
    "parent": {
      "id": 1069479620,
      "title": "The Clientside",
      "type": "Client::Board",
      "url": "https://3.basecampapi.com/195539477/buckets/2085958505/client/board.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958505/client/board.1069479620"
    },
    "bucket": {
      "id": 2085958505,
      "name": "The Leto Locator",
      "type": "Project"
    },
    "creator": {
      "id": 1049715938,
      "attachable_sgid": "BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiK2dpZDovL2JjMy9QZXJzb24vMTA0OTcxNTkzOD9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg9hdHRhY2hhYmxlBjsAVA==--4ccc567a0a3b10e354bca909b704637b601f0b16",
      "name": "Annie Bryan",
      "email_address": "annie@honchodesign.com",
      "personable_type": "User",
      "title": "Central Markets Manager",
      "bio": "To open a store is easy, to keep it open is an art",
      "location": null,
      "created_at": "2026-01-31T08:29:42.795Z",
      "updated_at": "2026-01-31T08:29:42.795Z",
      "admin": false,
      "owner": false,
      "client": false,
      "employee": true,
      "time_zone": "America/Chicago",
      "avatar_url": "https://3.basecampapi.com/195539477/people/BAhpBOJkkT4=--732a71fbd28ec10d9bf4466abd3588a8bea40bdb/avatar?v=1",
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
    "content": "",
    "subject": "Business card",
    "due_on": null,
    "replies_count": 0,
    "replies_url": "https://3.basecampapi.com/195539477/buckets/2085958505/client/recordings/1069479710/replies.json",
    "approval_status": "pending",
    "approver": {
      "id": 1049715936,
      "attachable_sgid": "BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiK2dpZDovL2JjMy9QZXJzb24vMTA0OTcxNTkzNj9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg9hdHRhY2hhYmxlBjsAVA==--55b2520c141258726568f476e5bbceb75c25e774",
      "name": "Miranda Grant",
      "email_address": "miranda@letobrand.com",
      "personable_type": "Client",
      "title": "Dynamic Markets Analyst",
      "bio": null,
      "location": null,
      "created_at": "2026-01-31T08:29:42.724Z",
      "updated_at": "2026-01-31T08:29:42.724Z",
      "admin": false,
      "owner": false,
      "client": false,
      "employee": false,
      "time_zone": "Etc/UTC",
      "avatar_url": "https://3.basecampapi.com/195539477/people/BAhpBOBkkT4=--78fb2ba7c3091268f41638ef90dee7dd32f395d6/avatar?v=1",
      "company": {
        "id": 1033447818,
        "name": "Leto Brand"
      },
      "can_ping": true,
      "can_manage_projects": false,
      "can_manage_people": false,
      "can_access_timesheet": false,
      "can_access_hill_charts": false
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
  "id": 1069479708,
  "status": "active",
  "visible_to_clients": false,
  "created_at": "2026-01-27T18:09:00.000Z",
  "updated_at": "2026-01-31T08:33:25.094Z",
  "title": "New logo for the website",
  "inherits_status": true,
  "type": "Client::Approval",
  "url": "https://3.basecampapi.com/195539477/buckets/2085958505/client/approvals/1069479708.json",
  "app_url": "https://3.basecamp.com/195539477/buckets/2085958505/client/approvals/1069479708",
  "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiLmdpZDovL2JjMy9SZWNvcmRpbmcvMTA2OTQ3OTcwOD9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg1yZWFkYWJsZQY7AFQ=--04b696f4ae155bb3e5af2626c7e368f092038285.json",
  "subscription_url": "https://3.basecampapi.com/195539477/buckets/2085958505/recordings/1069479708/subscription.json",
  "parent": {
    "id": 1069479620,
    "title": "The Clientside",
    "type": "Client::Board",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958505/client/board.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958505/client/board.1069479620"
  },
  "bucket": {
    "id": 2085958505,
    "name": "The Leto Locator",
    "type": "Project"
  },
  "creator": {
    "id": 1049715938,
    "attachable_sgid": "BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiK2dpZDovL2JjMy9QZXJzb24vMTA0OTcxNTkzOD9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg9hdHRhY2hhYmxlBjsAVA==--4ccc567a0a3b10e354bca909b704637b601f0b16",
    "name": "Annie Bryan",
    "email_address": "annie@honchodesign.com",
    "personable_type": "User",
    "title": "Central Markets Manager",
    "bio": "To open a store is easy, to keep it open is an art",
    "location": null,
    "created_at": "2026-01-31T08:29:42.795Z",
    "updated_at": "2026-01-31T08:29:42.795Z",
    "admin": false,
    "owner": false,
    "client": false,
    "employee": true,
    "time_zone": "America/Chicago",
    "avatar_url": "https://3.basecampapi.com/195539477/people/BAhpBOJkkT4=--732a71fbd28ec10d9bf4466abd3588a8bea40bdb/avatar?v=1",
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
  "content": "",
  "subject": "New logo for the website",
  "due_on": null,
  "replies_count": 0,
  "replies_url": "https://3.basecampapi.com/195539477/buckets/2085958505/client/recordings/1069479708/replies.json",
  "approval_status": "approved",
  "approver": {
    "id": 1049715935,
    "attachable_sgid": "BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiK2dpZDovL2JjMy9QZXJzb24vMTA0OTcxNTkzNT9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg9hdHRhY2hhYmxlBjsAVA==--d8bb591232517f997e82d5a8f68e4c9c9033e60f",
    "name": "Stephen Early",
    "email_address": "stephen@letobrand.com",
    "personable_type": "Client",
    "title": "National Directives Director",
    "bio": null,
    "location": null,
    "created_at": "2026-01-31T08:29:42.692Z",
    "updated_at": "2026-01-31T08:29:42.692Z",
    "admin": false,
    "owner": false,
    "client": false,
    "employee": false,
    "time_zone": "Etc/UTC",
    "avatar_url": "https://3.basecampapi.com/195539477/people/BAhpBN9kkT4=--7df21243a6650f691505323b707250c92aeb468d/avatar?v=1",
    "company": {
      "id": 1033447818,
      "name": "Leto Brand"
    },
    "can_ping": true,
    "can_manage_projects": false,
    "can_manage_people": false,
    "can_access_timesheet": false,
    "can_access_hill_charts": false
  },
  "responses": [
    {
      "id": 1069479709,
      "status": "active",
      "visible_to_clients": false,
      "created_at": "2026-01-27T18:49:00.000Z",
      "updated_at": "2026-01-27T18:49:00.000Z",
      "title": "Answer Re: New logo for the website",
      "inherits_status": true,
      "type": "Client::Approval::Response",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958505/client/approvals/1069479708#__recording_1069479709",
      "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiLmdpZDovL2JjMy9SZWNvcmRpbmcvMTA2OTQ3OTcwOT9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg1yZWFkYWJsZQY7AFQ=--6a06b056fc64cff7b08bc5c62335871b3b85f859.json",
      "parent": {
        "id": 1069479708,
        "title": "New logo for the website",
        "type": "Client::Approval",
        "url": "https://3.basecampapi.com/195539477/buckets/2085958505/client/approvals/1069479708.json",
        "app_url": "https://3.basecamp.com/195539477/buckets/2085958505/client/approvals/1069479708"
      },
      "bucket": {
        "id": 2085958505,
        "name": "The Leto Locator",
        "type": "Project"
      },
      "creator": {
        "id": 1049715937,
        "attachable_sgid": "BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiK2dpZDovL2JjMy9QZXJzb24vMTA0OTcxNTkzNz9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg9hdHRhY2hhYmxlBjsAVA==--86a39f74ccfe7d8d0a393a80b92182b9a85819d0",
        "name": "Beth Allen",
        "email_address": "beth@letobrand.com",
        "personable_type": "Client",
        "title": "Product Tactics Architect",
        "bio": null,
        "location": null,
        "created_at": "2026-01-31T08:29:42.744Z",
        "updated_at": "2026-01-31T08:29:42.744Z",
        "admin": false,
        "owner": false,
        "client": false,
        "employee": false,
        "time_zone": "Etc/UTC",
        "avatar_url": "https://3.basecampapi.com/195539477/people/BAhpBOFkkT4=--560f7fa1330d4341e3c089226bcb7fefb82dbfd1/avatar?v=1",
        "company": {
          "id": 1033447818,
          "name": "Leto Brand"
        },
        "can_ping": true,
        "can_manage_projects": false,
        "can_manage_people": false,
        "can_access_timesheet": false,
        "can_access_hill_charts": false
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
