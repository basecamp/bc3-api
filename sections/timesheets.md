Timesheets
==========

Endpoints:

- [Get timesheet report](#get-timesheet-report)
- [Get timesheet for a project](#get-timesheet-for-a-project)
- [Get timesheet for a recording](#get-timesheet-for-a-recording)

Get timesheet report
--------------------

* `GET /reports/timesheet.json` will return a list of all timesheet entries across the account, within a given timeframe.

**Note:** This endpoint is currently not paginated.

_Optional query parameters_:

This endpoint without any parameters returns only timesheet entries for the last month. 

* `start_date` - report start date (ISO 8601). If provided also the end_date is
    required.
* `end_date` - report end date (ISO 8601). If provided also the start_date is
    required.
* `person_id` - single [person][1] ID. Default: Everyone.
* `bucket_id` - single [project][2] ID. Default: All projects.

###### Example JSON Response
<!-- START GET /reports/timesheet.json -->
```json
[
  {
    "id": 1069480964,
    "status": "active",
    "visible_to_clients": false,
    "created_at": "2025-10-10T11:47:23.018Z",
    "updated_at": "2025-10-10T11:47:23.018Z",
    "title": "Timesheet entry",
    "inherits_status": true,
    "type": "Timesheet::Entry",
    "url": "https://3.basecampapi.com/195539477/projects/2085958503/timesheet/entries/1069480964.json",
    "app_url": "https://3.basecamp.com/195539477/projects/2085958503/timesheet/entries/1069480964",
    "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiLmdpZDovL2JjMy9SZWNvcmRpbmcvMTA2OTQ4MDk2ND9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg1yZWFkYWJsZQY7AFQ=--09a2201048c3c68eba357073056b1c3676de382b.json",
    "parent": {
      "id": 1069480455,
      "title": "We won Leto!",
      "type": "Message",
      "url": "https://3.basecampapi.com/195539477/buckets/2085958503/messages/1069480455.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958503/messages/1069480455"
    },
    "bucket": {
      "id": 2085958503,
      "name": "The Leto Laptop",
      "type": "Project"
    },
    "creator": {
      "id": 1049715955,
      "attachable_sgid": "BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiK2dpZDovL2JjMy9QZXJzb24vMTA0OTcxNTk1NT9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg9hdHRhY2hhYmxlBjsAVA==--6a8affd82c540e7c1f7e846b2b02fedb01bcd3f0",
      "name": "Victor Cooper",
      "email_address": "victor@honchodesign.com",
      "personable_type": "User",
      "title": "Chief Strategist",
      "bio": "Don’t let your dreams be dreams",
      "location": "Chicago, IL",
      "created_at": "2025-10-10T11:41:42.284Z",
      "updated_at": "2025-10-10T11:41:43.054Z",
      "admin": true,
      "owner": true,
      "client": false,
      "employee": true,
      "time_zone": "America/Chicago",
      "avatar_url": "http://bc3-cdn.localhost:3001/195539477/people/BAhpBPNkkT4=--5049939da9ea89df60ade5a1c42d324c1651c66c/avatar?v=1",
      "company": {
        "id": 1033447819,
        "name": "Honcho Design"
      },
      "can_ping": true,
      "can_manage_projects": true,
      "can_manage_people": true,
      "can_access_timesheet": true,
      "can_access_hill_charts": true
    },
    "date": "2025-10-09",
    "description": "Team Meeting Prep",
    "hours": "2.0"
  }
]
```
<!-- END GET /reports/timesheet.json -->
###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/reports/timesheet.json
```

Get timesheet for a project
---------------------------

* `GET /projects/1/timesheet.json` will return a [paginated list][pagination] of timesheet entries in the project with an ID of `1`.

###### Example JSON Response
<!-- START GET /projects/1/timesheet.json -->
```json
[
  {
    "id": 1069480964,
    "status": "active",
    "visible_to_clients": false,
    "created_at": "2025-10-10T11:47:23.018Z",
    "updated_at": "2025-10-10T11:47:23.018Z",
    "title": "Timesheet entry",
    "inherits_status": true,
    "type": "Timesheet::Entry",
    "url": "https://3.basecampapi.com/195539477/projects/2085958503/timesheet/entries/1069480964.json",
    "app_url": "https://3.basecamp.com/195539477/projects/2085958503/timesheet/entries/1069480964",
    "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiLmdpZDovL2JjMy9SZWNvcmRpbmcvMTA2OTQ4MDk2ND9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg1yZWFkYWJsZQY7AFQ=--09a2201048c3c68eba357073056b1c3676de382b.json",
    "parent": {
      "id": 1069480455,
      "title": "We won Leto!",
      "type": "Message",
      "url": "https://3.basecampapi.com/195539477/buckets/2085958503/messages/1069480455.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958503/messages/1069480455"
    },
    "bucket": {
      "id": 2085958503,
      "name": "The Leto Laptop",
      "type": "Project"
    },
    "creator": {
      "id": 1049715955,
      "attachable_sgid": "BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiK2dpZDovL2JjMy9QZXJzb24vMTA0OTcxNTk1NT9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg9hdHRhY2hhYmxlBjsAVA==--6a8affd82c540e7c1f7e846b2b02fedb01bcd3f0",
      "name": "Victor Cooper",
      "email_address": "victor@honchodesign.com",
      "personable_type": "User",
      "title": "Chief Strategist",
      "bio": "Don’t let your dreams be dreams",
      "location": "Chicago, IL",
      "created_at": "2025-10-10T11:41:42.284Z",
      "updated_at": "2025-10-10T11:41:43.054Z",
      "admin": true,
      "owner": true,
      "client": false,
      "employee": true,
      "time_zone": "America/Chicago",
      "avatar_url": "http://bc3-cdn.localhost:3001/195539477/people/BAhpBPNkkT4=--5049939da9ea89df60ade5a1c42d324c1651c66c/avatar?v=1",
      "company": {
        "id": 1033447819,
        "name": "Honcho Design"
      },
      "can_ping": true,
      "can_manage_projects": true,
      "can_manage_people": true,
      "can_access_timesheet": true,
      "can_access_hill_charts": true
    },
    "date": "2025-10-09",
    "description": "Team Meeting Prep",
    "hours": "2.0"
  }
]
```
<!-- END GET /projects/1/timesheet.json -->
###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/projects/1/timesheet.json
```

Get timesheet for a recording
-----------------------------

* `GET /projects/1/recordings/2/timesheet.json` will return a [paginated list][pagination] of timesheet entries in the project with an ID of `1` and the recording with ID of `2`.

###### Example JSON Response
<!-- START GET /projects/1/recordings/2/timesheet.json -->
```json
[
  {
    "id": 1069480964,
    "status": "active",
    "visible_to_clients": false,
    "created_at": "2025-10-10T11:47:23.018Z",
    "updated_at": "2025-10-10T11:47:23.018Z",
    "title": "Timesheet entry",
    "inherits_status": true,
    "type": "Timesheet::Entry",
    "url": "https://3.basecampapi.com/195539477/projects/2085958503/timesheet/entries/1069480964.json",
    "app_url": "https://3.basecamp.com/195539477/projects/2085958503/timesheet/entries/1069480964",
    "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiLmdpZDovL2JjMy9SZWNvcmRpbmcvMTA2OTQ4MDk2ND9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg1yZWFkYWJsZQY7AFQ=--09a2201048c3c68eba357073056b1c3676de382b.json",
    "parent": {
      "id": 1069480455,
      "title": "We won Leto!",
      "type": "Message",
      "url": "https://3.basecampapi.com/195539477/buckets/2085958503/messages/1069480455.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958503/messages/1069480455"
    },
    "bucket": {
      "id": 2085958503,
      "name": "The Leto Laptop",
      "type": "Project"
    },
    "creator": {
      "id": 1049715955,
      "attachable_sgid": "BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiK2dpZDovL2JjMy9QZXJzb24vMTA0OTcxNTk1NT9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg9hdHRhY2hhYmxlBjsAVA==--6a8affd82c540e7c1f7e846b2b02fedb01bcd3f0",
      "name": "Victor Cooper",
      "email_address": "victor@honchodesign.com",
      "personable_type": "User",
      "title": "Chief Strategist",
      "bio": "Don’t let your dreams be dreams",
      "location": "Chicago, IL",
      "created_at": "2025-10-10T11:41:42.284Z",
      "updated_at": "2025-10-10T11:41:43.054Z",
      "admin": true,
      "owner": true,
      "client": false,
      "employee": true,
      "time_zone": "America/Chicago",
      "avatar_url": "http://bc3-cdn.localhost:3001/195539477/people/BAhpBPNkkT4=--5049939da9ea89df60ade5a1c42d324c1651c66c/avatar?v=1",
      "company": {
        "id": 1033447819,
        "name": "Honcho Design"
      },
      "can_ping": true,
      "can_manage_projects": true,
      "can_manage_people": true,
      "can_access_timesheet": true,
      "can_access_hill_charts": true
    },
    "date": "2025-10-09",
    "description": "Team Meeting Prep",
    "hours": "2.0"
  }
]
```
<!-- END GET /projects/1/recordings/2/timesheet.json -->
###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/projects/1/recordings/2/timesheet.json
```

[1]: https://github.com/basecamp/bc3-api/blob/master/sections/people.md#people
[2]: https://github.com/basecamp/bc3-api/blob/master/sections/projects.md#projects
