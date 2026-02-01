Reports
=======

Endpoints:

- [Get to-do assignments](#get-to-do-assignments)
- [Get to-do assignments for a person](#get-to-do-assignments-for-a-person)
- [Get overdue to-dos](#get-overdue-to-dos)
- [Get upcoming schedule](#get-upcoming-schedule)

Get to-do assignments
---------------------

* `GET /reports/todos/assigned.json` will return a list of all people who can have to-dos assigned to them.

This endpoint is useful for building a list of people to then retrieve their individual to-do assignments.

###### Example JSON Response
<!-- START GET /reports/todos/assigned.json -->
```json
[
  {
    "id": 1049715915,
    "attachable_sgid": "BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiK2dpZDovL2JjMy9QZXJzb24vMTA0OTcxNTkxNT9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg9hdHRhY2hhYmxlBjsAVA==--56bb1f99675fd8fe08f93a706a5d2ddaa8412625",
    "name": "Amy Rivera",
    "email_address": "amy@honchodesign.com",
    "personable_type": "User",
    "title": "Central Web Coordinator",
    "bio": "I never said most of the things I said",
    "location": null,
    "created_at": "2026-01-31T08:29:32.987Z",
    "updated_at": "2026-01-31T08:29:32.987Z",
    "admin": false,
    "owner": false,
    "client": false,
    "employee": false,
    "time_zone": "America/Chicago",
    "avatar_url": "https://3.basecampapi.com/195539477/people/BAhpBMtkkT4=--9927c47a4cbee30a7f9aea667882496aba799149/avatar?v=1",
    "can_ping": true,
    "can_manage_projects": true,
    "can_manage_people": true,
    "can_access_timesheet": true,
    "can_access_hill_charts": true
  }
]
```
<!-- END GET /reports/todos/assigned.json -->
###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/reports/todos/assigned.json
```

Get to-do assignments for a person
----------------------------------

* `GET /reports/todos/assigned/1.json` will return a list of all active, pending to-dos assigned to the person with an ID of `1`.

_Optional query parameters_:

* `group_by` - when set to `bucket`, will group to-dos by project. When set to `date`, will group by due date. Default: `bucket`.

###### Example JSON Response
<!-- START GET /reports/todos/assigned/1.json -->
```json
{
  "person": {
    "id": 1049715915,
    "attachable_sgid": "BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiK2dpZDovL2JjMy9QZXJzb24vMTA0OTcxNTkxNT9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg9hdHRhY2hhYmxlBjsAVA==--56bb1f99675fd8fe08f93a706a5d2ddaa8412625",
    "name": "Amy Rivera",
    "email_address": "amy@honchodesign.com",
    "personable_type": "User",
    "title": "Central Web Coordinator",
    "bio": "I never said most of the things I said",
    "location": null,
    "created_at": "2026-01-31T08:29:32.987Z",
    "updated_at": "2026-01-31T08:29:32.987Z",
    "admin": false,
    "owner": false,
    "client": false,
    "employee": false,
    "time_zone": "America/Chicago",
    "avatar_url": "https://3.basecampapi.com/195539477/people/BAhpBMtkkT4=--9927c47a4cbee30a7f9aea667882496aba799149/avatar?v=1",
    "can_ping": true,
    "can_manage_projects": true,
    "can_manage_people": true,
    "can_access_timesheet": true,
    "can_access_hill_charts": true
  },
  "grouped_by": "bucket",
  "todos": [
    {
      "id": 1069479164,
      "status": "active",
      "visible_to_clients": false,
      "created_at": "2026-01-02T02:59:00.000Z",
      "updated_at": "2026-01-02T02:59:00.000Z",
      "title": "Amy vs. Sharon",
      "inherits_status": true,
      "type": "Todo",
      "url": "https://3.basecampapi.com/195539477/buckets/2085958502/todos/1069479164.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958502/todos/1069479164",
      "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiLmdpZDovL2JjMy9SZWNvcmRpbmcvMTA2OTQ3OTE2ND9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg1yZWFkYWJsZQY7AFQ=--8af0e81cbcfd171784f476df4fcd8a0defb0d525.json",
      "subscription_url": "https://3.basecampapi.com/195539477/buckets/2085958502/recordings/1069479164/subscription.json",
      "comments_count": 0,
      "comments_url": "https://3.basecampapi.com/195539477/buckets/2085958502/recordings/1069479164/comments.json",
      "position": 2,
      "parent": {
        "id": 1069479162,
        "title": "Group D",
        "type": "Todolist",
        "url": "https://3.basecampapi.com/195539477/buckets/2085958502/todolists/1069479162.json",
        "app_url": "https://3.basecamp.com/195539477/buckets/2085958502/todolists/1069479162"
      },
      "bucket": {
        "id": 2085958502,
        "name": "Honcho Design Newsroom",
        "type": "Project"
      },
      "creator": {
        "id": 1049715918,
        "attachable_sgid": "BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiK2dpZDovL2JjMy9QZXJzb24vMTA0OTcxNTkxOD9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg9hdHRhY2hhYmxlBjsAVA==--d6212bd7e60bf63ea61797589b2638cbbf2d4ed7",
        "name": "Brian Jenks",
        "email_address": "brian@honchodesign.com",
        "personable_type": "User",
        "title": "International Branding Liason",
        "bio": null,
        "location": null,
        "created_at": "2026-01-31T08:29:34.525Z",
        "updated_at": "2026-01-31T08:29:34.525Z",
        "admin": false,
        "owner": false,
        "client": false,
        "employee": false,
        "time_zone": "America/Chicago",
        "avatar_url": "https://3.basecampapi.com/195539477/people/BAhpBM5kkT4=--50075f17f313c1198fb6f27e5d466327804dfd22/avatar?v=1",
        "can_ping": true,
        "can_manage_projects": true,
        "can_manage_people": true,
        "can_access_timesheet": true,
        "can_access_hill_charts": true
      },
      "description": "",
      "completed": false,
      "content": "Amy vs. Sharon",
      "starts_on": null,
      "due_on": null,
      "assignees": [
        {
          "id": 1049715915,
          "attachable_sgid": "BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiK2dpZDovL2JjMy9QZXJzb24vMTA0OTcxNTkxNT9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg9hdHRhY2hhYmxlBjsAVA==--56bb1f99675fd8fe08f93a706a5d2ddaa8412625",
          "name": "Amy Rivera",
          "email_address": "amy@honchodesign.com",
          "personable_type": "User",
          "title": "Central Web Coordinator",
          "bio": "I never said most of the things I said",
          "location": null,
          "created_at": "2026-01-31T08:29:32.987Z",
          "updated_at": "2026-01-31T08:29:32.987Z",
          "admin": false,
          "owner": false,
          "client": false,
          "employee": false,
          "time_zone": "America/Chicago",
          "avatar_url": "https://3.basecampapi.com/195539477/people/BAhpBMtkkT4=--9927c47a4cbee30a7f9aea667882496aba799149/avatar?v=1",
          "can_ping": true,
          "can_manage_projects": true,
          "can_manage_people": true,
          "can_access_timesheet": true,
          "can_access_hill_charts": true
        }
      ],
      "completion_subscribers": [],
      "completion_url": "https://3.basecampapi.com/195539477/buckets/2085958502/todos/1069479164/completion.json"
    }
  ]
}
```
<!-- END GET /reports/todos/assigned/1.json -->
###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/reports/todos/assigned/1.json
```

Get overdue to-dos
------------------

* `GET /reports/todos/overdue.json` will return all overdue to-dos across all projects, grouped by how late they are.

The response includes four groups:
* `under_a_week_late` - to-dos due within the last 7 days
* `over_a_week_late` - to-dos due between 7 and 30 days ago
* `over_a_month_late` - to-dos due between 30 and 90 days ago
* `over_three_months_late` - to-dos due more than 90 days ago

###### Example JSON Response
<!-- START GET /reports/todos/overdue.json -->
```json
{
  "under_a_week_late": [],
  "over_a_week_late": [],
  "over_a_month_late": [],
  "over_three_months_late": []
}
```
<!-- END GET /reports/todos/overdue.json -->
###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/reports/todos/overdue.json
```

Get upcoming schedule
---------------------

* `GET /reports/schedules/upcoming.json` will return schedule entries and assignable items within a specified date window.

**Required query parameters**:

* `window_starts_on` - the start date of the window (ISO 8601, `YYYY-MM-DD`)
* `window_ends_on` - the end date of the window (ISO 8601, `YYYY-MM-DD`)

The response includes:
* `schedule_entries` - one-time schedule entries within the window
* `recurring_schedule_entry_occurrences` - occurrences of recurring schedule entries within the window
* `assignables` - to-dos, cards, and steps with due dates within the window

###### Example JSON Response
<!-- START GET /reports/schedules/upcoming.json -->
```json
{
  "schedule_entries": [
    {
      "id": 1069479912,
      "status": "active",
      "visible_to_clients": false,
      "url": "https://3.basecampapi.com/195539477/buckets/2085958504/schedule_entries/1069479912.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958504/schedule_entries/1069479912",
      "type": "ScheduleEntry",
      "summary": "Team Meeting",
      "all_day": false,
      "recurring": false,
      "starts_at": "2026-02-01T10:36:20.949Z",
      "ends_at": "2026-02-01T14:36:20.950Z",
      "creator": {
        "id": 1049715913,
        "name": "Victor Cooper",
        "avatar_url": "https://3.basecampapi.com/195539477/people/BAhpBMlkkT4=--5fe7b70fbee7a7f0e2e1e19df7579e5d880c753d/avatar?v=1"
      },
      "participants": [
        {
          "id": 1049715944,
          "name": "Steve Marsh",
          "avatar_url": "https://3.basecampapi.com/195539477/people/BAhpBOhkkT4=--b169e35b345bcc26eca6964b7ef7de2c16b6f238/avatar?v=1"
        }
      ],
      "bucket": {
        "id": 2085958504,
        "name": "The Leto Laptop"
      },
      "comments_count": 0
    }
  ],
  "recurring_schedule_entry_occurrences": [],
  "assignables": [
    {
      "id": 1069479603,
      "status": "active",
      "visible_to_clients": false,
      "url": "https://3.basecampapi.com/195539477/buckets/2085958504/card_tables/steps/1069479603.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958504/card_tables/cards/1069479602#__recording_1069479603",
      "starts_on": null,
      "due_on": "2026-02-04",
      "type": "step",
      "content": "Find inspiration",
      "assignees": [
        {
          "id": 1049715931,
          "name": "Tashia Hughes",
          "avatar_url": "https://3.basecampapi.com/195539477/people/BAhpBNtkkT4=--b72a5df90f237e00570273b726a82176287186e4/avatar?v=1"
        }
      ],
      "bucket": {
        "id": 2085958504,
        "name": "The Leto Laptop"
      },
      "parent": {
        "id": 1069479602,
        "title": "New and fancy UI"
      },
      "completion_url": "/195539477/buckets/2085958504/card_tables/steps/1069479603/completions.json",
      "completed": false,
      "repeating": false,
      "comments_count": 0
    }
  ]
}
```
<!-- END GET /reports/schedules/upcoming.json -->
###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" "https://3.basecampapi.com/$ACCOUNT_ID/reports/schedules/upcoming.json?window_starts_on=2025-10-10&window_ends_on=2025-10-17"
```

[pagination]: https://github.com/basecamp/bc3-api/blob/master/README.md#pagination
[people]: https://github.com/basecamp/bc3-api/blob/master/sections/people.md#people
[projects]: https://github.com/basecamp/bc3-api/blob/master/sections/projects.md#projects
