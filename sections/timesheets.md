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
    "id": 1069479915,
    "status": "active",
    "visible_to_clients": false,
    "created_at": "2026-01-31T08:37:37.811Z",
    "updated_at": "2026-01-31T08:37:37.811Z",
    "title": "Timesheet entry",
    "inherits_status": true,
    "type": "Timesheet::Entry",
    "url": "https://3.basecampapi.com/195539477/projects/2085958504/timesheet/entries/1069479915.json",
    "app_url": "https://3.basecamp.com/195539477/projects/2085958504/timesheet/entries/1069479915",
    "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiLmdpZDovL2JjMy9SZWNvcmRpbmcvMTA2OTQ3OTkxNT9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg1yZWFkYWJsZQY7AFQ=--eedd8d56e2e90002cdb2a96028846f61e1ae34f9.json",
    "parent": {
      "id": 1069479406,
      "title": "We won Leto!",
      "type": "Message",
      "url": "https://3.basecampapi.com/195539477/buckets/2085958504/messages/1069479406.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958504/messages/1069479406"
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
    "date": "2026-01-30",
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
    "id": 1069479915,
    "status": "active",
    "visible_to_clients": false,
    "created_at": "2026-01-31T08:37:37.811Z",
    "updated_at": "2026-01-31T08:37:37.811Z",
    "title": "Timesheet entry",
    "inherits_status": true,
    "type": "Timesheet::Entry",
    "url": "https://3.basecampapi.com/195539477/projects/2085958504/timesheet/entries/1069479915.json",
    "app_url": "https://3.basecamp.com/195539477/projects/2085958504/timesheet/entries/1069479915",
    "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiLmdpZDovL2JjMy9SZWNvcmRpbmcvMTA2OTQ3OTkxNT9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg1yZWFkYWJsZQY7AFQ=--eedd8d56e2e90002cdb2a96028846f61e1ae34f9.json",
    "parent": {
      "id": 1069479406,
      "title": "We won Leto!",
      "type": "Message",
      "url": "https://3.basecampapi.com/195539477/buckets/2085958504/messages/1069479406.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958504/messages/1069479406"
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
    "date": "2026-01-30",
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
    "id": 1069479915,
    "status": "active",
    "visible_to_clients": false,
    "created_at": "2026-01-31T08:37:37.811Z",
    "updated_at": "2026-01-31T08:37:37.811Z",
    "title": "Timesheet entry",
    "inherits_status": true,
    "type": "Timesheet::Entry",
    "url": "https://3.basecampapi.com/195539477/projects/2085958504/timesheet/entries/1069479915.json",
    "app_url": "https://3.basecamp.com/195539477/projects/2085958504/timesheet/entries/1069479915",
    "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiLmdpZDovL2JjMy9SZWNvcmRpbmcvMTA2OTQ3OTkxNT9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg1yZWFkYWJsZQY7AFQ=--eedd8d56e2e90002cdb2a96028846f61e1ae34f9.json",
    "parent": {
      "id": 1069479406,
      "title": "We won Leto!",
      "type": "Message",
      "url": "https://3.basecampapi.com/195539477/buckets/2085958504/messages/1069479406.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958504/messages/1069479406"
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
    "date": "2026-01-30",
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
