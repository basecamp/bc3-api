Timesheets
==========

Endpoints:

- [Get timesheet report](#get-timesheet-report)
- [Get timesheet for a project](#get-timesheet-for-a-project)
- [Get timesheet for a recording](#get-timesheet-for-a-recording)
- [Get a timesheet entry](#get-a-timesheet-entry)
- [Create a timesheet entry](#create-a-timesheet-entry)
- [Update a timesheet entry](#update-a-timesheet-entry)
- [Trash a timesheet entry][3]

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
    "hours": "2.0",
    "person": {
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
    }
  }
]
```
<!-- END GET /reports/timesheet.json -->
###### Copy as cURL

```shell
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
    "hours": "2.0",
    "person": {
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
    }
  }
]
```
<!-- END GET /projects/1/timesheet.json -->
###### Copy as cURL

```shell
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
    "hours": "2.0",
    "person": {
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
    }
  }
]
```
<!-- END GET /projects/1/recordings/2/timesheet.json -->
###### Copy as cURL

```shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/projects/1/recordings/2/timesheet.json
```

Get a timesheet entry
---------------------

* `GET /projects/1/timesheet/entries/2.json` will return the timesheet entry with an ID of `2` in the project with an ID of `1`.

###### Example JSON Response
<!-- START GET /projects/1/timesheet/entries/2.json -->
```json
{
  "id": 1069480091,
  "status": "active",
  "visible_to_clients": false,
  "created_at": "2026-02-06T22:55:54.662Z",
  "updated_at": "2026-02-06T22:55:54.662Z",
  "title": "Timesheet entry",
  "inherits_status": true,
  "type": "Timesheet::Entry",
  "url": "https://3.basecampapi.com/195539477/projects/2085958504/timesheet/entries/1069480091.json",
  "app_url": "https://3.basecamp.com/195539477/projects/2085958504/timesheet/entries/1069480091",
  "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiLmdpZDovL2JjMy9SZWNvcmRpbmcvMTA2OTQ4MDA5MT9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg1yZWFkYWJsZQY7AFQ=--0b7abbaa49e554506a83edc6934173ebe077c1f0.json",
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
  "date": "2026-02-06",
  "description": "API docs example",
  "hours": "1.5",
  "person": {
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
  }
}
```
<!-- END GET /projects/1/timesheet/entries/2.json -->
###### Copy as cURL

```shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/projects/1/timesheet/entries/2.json
```

Create a timesheet entry
------------------------

* `POST /projects/1/recordings/2/timesheet/entries.json` creates a timesheet entry in the project with ID `1` under the recording with ID `2`.

The recording can be any timesheetable type: a message, to-do, card, document, upload, schedule entry, or the project timesheet itself.

**Required parameters**:

* `date` - the date the time was spent (ISO 8601, e.g. `2024-05-16`).
* `hours` - the number of hours. Accepts decimal (`1.5`) or time format (`1:30`).

_Optional parameters_:

* `description` - a note about the work performed.
* `person_id` - the [person][1] the time is for. Defaults to the authenticated user. Must be a non-client member of the project.

This endpoint will return `201 Created` with the current JSON representation of the timesheet entry if the creation was a success. See the [Get timesheet for a project](#get-timesheet-for-a-project) endpoint for more info on the payload.

###### Example JSON Request

```json
{
  "date": "2024-05-16",
  "hours": "1:30",
  "description": "Client meeting prep"
}
```

###### Example JSON Response
<!-- START POST /projects/1/recordings/2/timesheet/entries.json -->
```json
{
  "id": 1069480091,
  "status": "active",
  "visible_to_clients": false,
  "created_at": "2026-02-06T22:55:54.662Z",
  "updated_at": "2026-02-06T22:55:54.662Z",
  "title": "Timesheet entry",
  "inherits_status": true,
  "type": "Timesheet::Entry",
  "url": "https://3.basecampapi.com/195539477/projects/2085958504/timesheet/entries/1069480091.json",
  "app_url": "https://3.basecamp.com/195539477/projects/2085958504/timesheet/entries/1069480091",
  "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiLmdpZDovL2JjMy9SZWNvcmRpbmcvMTA2OTQ4MDA5MT9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg1yZWFkYWJsZQY7AFQ=--0b7abbaa49e554506a83edc6934173ebe077c1f0.json",
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
  "date": "2026-02-06",
  "description": "API docs example",
  "hours": "1.5",
  "person": {
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
  }
}
```
<!-- END POST /projects/1/recordings/2/timesheet/entries.json -->

###### Copy as cURL

```shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -H "Content-Type: application/json" \
  -d '{"date":"2024-05-16","hours":"1:30","description":"Client meeting prep"}' \
  https://3.basecampapi.com/$ACCOUNT_ID/projects/1/recordings/2/timesheet/entries.json
```

Update a timesheet entry
------------------------

* `PUT /projects/1/timesheet/entries/2.json` allows changing the timesheet entry with an ID of `2` in the project with ID `1`.

This endpoint will return `200 OK` with the current JSON representation of the timesheet entry if the update was a success. See the [Get timesheet for a project](#get-timesheet-for-a-project) endpoint for more info on the payload.

_Optional parameters_: Only pass the parameters you want to change.

* `date` - the date the time was spent (ISO 8601).
* `hours` - the number of hours. Accepts decimal (`1.5`) or time format (`1:30`).
* `description` - a note about the work performed.
* `person_id` - the [person][1] the time is for. Must be a non-client member of the project.

###### Example JSON Request

```json
{
  "hours": "2.5",
  "description": "Updated description"
}
```

###### Example JSON Response
<!-- START PUT /projects/1/timesheet/entries/2.json -->
```json
{
  "id": 1069480091,
  "status": "active",
  "visible_to_clients": false,
  "created_at": "2026-02-06T22:55:54.662Z",
  "updated_at": "2026-02-06T22:55:55.514Z",
  "title": "Timesheet entry",
  "inherits_status": true,
  "type": "Timesheet::Entry",
  "url": "https://3.basecampapi.com/195539477/projects/2085958504/timesheet/entries/1069480091.json",
  "app_url": "https://3.basecamp.com/195539477/projects/2085958504/timesheet/entries/1069480091",
  "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiLmdpZDovL2JjMy9SZWNvcmRpbmcvMTA2OTQ4MDA5MT9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg1yZWFkYWJsZQY7AFQ=--0b7abbaa49e554506a83edc6934173ebe077c1f0.json",
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
  "date": "2026-02-06",
  "description": "Updated via API",
  "hours": "2.5",
  "person": {
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
  }
}
```
<!-- END PUT /projects/1/timesheet/entries/2.json -->

###### Copy as cURL

```shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -H "Content-Type: application/json" \
  -X PUT -d '{"hours":"2.5","description":"Updated description"}' \
  https://3.basecampapi.com/$ACCOUNT_ID/projects/1/timesheet/entries/2.json
```

[1]: https://github.com/basecamp/bc3-api/blob/master/sections/people.md#people
[2]: https://github.com/basecamp/bc3-api/blob/master/sections/projects.md#projects
[3]: https://github.com/basecamp/bc3-api/blob/master/sections/recordings.md#trash-a-recording
