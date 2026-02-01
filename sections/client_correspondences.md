Client correspondences
======================

Endpoints:

- [Get client correspondences](#get-client-correspondences)
- [Get a client correspondence](#get-a-client-correspondence)

Get client correspondences
--------------------------

* `GET /buckets/1/client/correspondences.json` will return a [paginated list][pagination] of client correspondences in the project with an ID of `1`.

###### Example JSON Response
<!-- START GET /buckets/1/client/correspondences.json -->
```json
[
  {
    "id": 1069479702,
    "status": "active",
    "visible_to_clients": false,
    "created_at": "2026-01-26T18:32:00.000Z",
    "updated_at": "2026-01-31T08:33:24.732Z",
    "title": "Final deliverables and launch are right around the corner",
    "inherits_status": true,
    "type": "Client::Correspondence",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958505/client/correspondences/1069479702.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958505/client/correspondences/1069479702",
    "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiLmdpZDovL2JjMy9SZWNvcmRpbmcvMTA2OTQ3OTcwMj9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg1yZWFkYWJsZQY7AFQ=--549ac000e6e0eac9d8df54b89a1c0a473ab78e57.json",
    "subscription_url": "https://3.basecampapi.com/195539477/buckets/2085958505/recordings/1069479702/subscription.json",
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
    "subject": "Final deliverables and launch are right around the corner",
    "replies_count": 5,
    "replies_url": "https://3.basecampapi.com/195539477/buckets/2085958505/client/recordings/1069479702/replies.json"
  }
]
```
<!-- END GET /buckets/1/client/correspondences.json -->
###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/client/correspondences.json
```

Get a client correspondence
---------------------------

* `GET /buckets/1/client/correspondences/2.json` will return the client correspondence with an ID of `2` in the project with an ID of `1`.

###### Example JSON Response
<!-- START GET /buckets/1/client/correspondences/2.json -->
```json
{
  "id": 1069479622,
  "status": "active",
  "visible_to_clients": false,
  "created_at": "2025-12-18T23:05:00.000Z",
  "updated_at": "2026-01-31T08:33:03.644Z",
  "title": "Project kickoff!",
  "inherits_status": true,
  "type": "Client::Correspondence",
  "url": "https://3.basecampapi.com/195539477/buckets/2085958505/client/correspondences/1069479622.json",
  "app_url": "https://3.basecamp.com/195539477/buckets/2085958505/client/correspondences/1069479622",
  "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiLmdpZDovL2JjMy9SZWNvcmRpbmcvMTA2OTQ3OTYyMj9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg1yZWFkYWJsZQY7AFQ=--05a942db8b0024e8a6f293a19b83d795cf079601.json",
  "subscription_url": "https://3.basecampapi.com/195539477/buckets/2085958505/recordings/1069479622/subscription.json",
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
    "id": 1049715922,
    "attachable_sgid": "BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiK2dpZDovL2JjMy9QZXJzb24vMTA0OTcxNTkyMj9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg9hdHRhY2hhYmxlBjsAVA==--ed42dd1af36c4756554ffb2a20de4e019f0c28d3",
    "name": "Jay Edmonds",
    "email_address": "jay@honchodesign.com",
    "personable_type": "User",
    "title": "Internal Marketing Assistant",
    "bio": null,
    "location": null,
    "created_at": "2026-01-31T08:29:36.692Z",
    "updated_at": "2026-01-31T08:29:36.692Z",
    "admin": false,
    "owner": false,
    "client": false,
    "employee": false,
    "time_zone": "America/Chicago",
    "avatar_url": "https://3.basecampapi.com/195539477/people/BAhpBNJkkT4=--6ef93d58440c2ed1fec4457e3eb5f09572e866a4/avatar?v=1",
    "can_ping": true,
    "can_manage_projects": true,
    "can_manage_people": true,
    "can_access_timesheet": true,
    "can_access_hill_charts": true
  },
  "content": "",
  "subject": "Project kickoff!",
  "replies_count": 6,
  "replies_url": "https://3.basecampapi.com/195539477/buckets/2085958505/client/recordings/1069479622/replies.json"
}
```
<!-- END GET /buckets/1/client/correspondences/2.json -->
###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/client/correspondences/2.json
```

[pagination]: https://github.com/basecamp/bc3-api/blob/master/README.md#pagination
