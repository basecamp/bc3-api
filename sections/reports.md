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
    "id": 1049715914,
    "attachable_sgid": "BAh7CEkiCGdpZAY6BkVUSSIrZ2lkOi8vYmMzL1BlcnNvbi8xMDQ5NzE1OTE0P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg9hdHRhY2hhYmxlBjsAVEkiD2V4cGlyZXNfYXQGOwBUMA==--ff006accb6e013cca785190fa38f42c091d24f1e",
    "name": "Victor Cooper",
    "email_address": "victor@honchodesign.com",
    "personable_type": "User",
    "title": "Chief Strategist",
    "bio": "Don't let your dreams be dreams",
    "location": "Chicago, IL",
    "created_at": "2025-10-10T11:41:42.284Z",
    "updated_at": "2025-10-10T11:41:43.054Z",
    "admin": true,
    "owner": true,
    "client": false,
    "employee": true,
    "time_zone": "America/Chicago",
    "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBPNkkT4=--5049939da9ea89df60ade5a1c42d324c1651c66c/avatar?v=1",
    "company": {
      "id": 1033447819,
      "name": "Honcho Design"
    },
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
    "id": 1049715914,
    "attachable_sgid": "BAh7CEkiCGdpZAY6BkVUSSIrZ2lkOi8vYmMzL1BlcnNvbi8xMDQ5NzE1OTE0P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg9hdHRhY2hhYmxlBjsAVEkiD2V4cGlyZXNfYXQGOwBUMA==--ff006accb6e013cca785190fa38f42c091d24f1e",
    "name": "Victor Cooper",
    "email_address": "victor@honchodesign.com",
    "personable_type": "User",
    "title": "Chief Strategist",
    "bio": "Don't let your dreams be dreams",
    "location": "Chicago, IL",
    "created_at": "2025-10-10T11:41:42.284Z",
    "updated_at": "2025-10-10T11:41:43.054Z",
    "admin": true,
    "owner": true,
    "client": false,
    "employee": true,
    "time_zone": "America/Chicago",
    "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBPNkkT4=--5049939da9ea89df60ade5a1c42d324c1651c66c/avatar?v=1",
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
  "grouped_by": "bucket",
  "todos": [
    {
      "id": 1069479521,
      "status": "active",
      "visible_to_clients": false,
      "created_at": "2025-10-10T12:43:58.169Z",
      "updated_at": "2025-10-10T12:43:58.169Z",
      "title": "Go cutting edge: iOS8 and Android 4.5 only",
      "inherits_status": true,
      "type": "Todo",
      "url": "https://3.basecampapi.com/195539477/buckets/2085958499/todos/1069479521.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958499/todos/1069479521",
      "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7CEkiCGdpZAY6BkVUSSIuZ2lkOi8vYmMzL1JlY29yZGluZy8xMDY5NDc5NTIxP2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg1yZWFkYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--ca42d4aed48383928eedbeb305bbc7667ce0418e.json",
      "subscription_url": "https://3.basecampapi.com/195539477/buckets/2085958499/recordings/1069479521/subscription.json",
      "comments_count": 0,
      "comments_url": "https://3.basecampapi.com/195539477/buckets/2085958499/recordings/1069479521/comments.json",
      "position": 1,
      "parent": {
        "id": 1069479520,
        "title": "Strategy ideas",
        "type": "Todolist",
        "url": "https://3.basecampapi.com/195539477/buckets/2085958499/todolists/1069479520.json",
        "app_url": "https://3.basecamp.com/195539477/buckets/2085958499/todolists/1069479520"
      },
      "bucket": {
        "id": 2085958499,
        "name": "The Leto Laptop",
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
        "created_at": "2025-10-10T11:41:42.284Z",
        "updated_at": "2025-10-10T11:41:42.284Z",
        "admin": false,
        "owner": false,
        "client": false,
        "employee": true,
        "time_zone": "America/Chicago",
        "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBMtkkT4=--9927c47a4cbee30a7f9aea667882496aba799149/avatar?v=1",
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
      "description": "",
      "completed": false,
      "content": "Go cutting edge: iOS8 and Android 4.5 only",
      "starts_on": null,
      "due_on": "2025-10-15",
      "assignees": [
        {
          "id": 1049715914,
          "attachable_sgid": "BAh7CEkiCGdpZAY6BkVUSSIrZ2lkOi8vYmMzL1BlcnNvbi8xMDQ5NzE1OTE0P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg9hdHRhY2hhYmxlBjsAVEkiD2V4cGlyZXNfYXQGOwBUMA==--ff006accb6e013cca785190fa38f42c091d24f1e",
          "name": "Victor Cooper",
          "email_address": "victor@honchodesign.com",
          "personable_type": "User",
          "title": "Chief Strategist",
          "bio": "Don't let your dreams be dreams",
          "location": "Chicago, IL",
          "created_at": "2025-10-10T11:41:42.284Z",
          "updated_at": "2025-10-10T11:41:43.054Z",
          "admin": true,
          "owner": true,
          "client": false,
          "employee": true,
          "time_zone": "America/Chicago",
          "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBPNkkT4=--5049939da9ea89df60ade5a1c42d324c1651c66c/avatar?v=1",
          "company": {
            "id": 1033447819,
            "name": "Honcho Design"
          },
          "can_ping": true,
          "can_manage_projects": true,
          "can_manage_people": true,
          "can_access_timesheet": true,
          "can_access_hill_charts": true
        }
      ],
      "completion_subscribers": [],
      "completion_url": "https://3.basecampapi.com/195539477/buckets/2085958499/todos/1069479521/completion.json"
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
  "under_a_week_late": [
    {
      "id": 1069479521,
      "status": "active",
      "visible_to_clients": false,
      "created_at": "2025-10-10T12:43:58.169Z",
      "updated_at": "2025-10-10T12:43:58.169Z",
      "title": "Review budget proposal",
      "inherits_status": true,
      "type": "Todo",
      "url": "https://3.basecampapi.com/195539477/buckets/2085958499/todos/1069479521.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958499/todos/1069479521",
      "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7CEkiCGdpZAY6BkVUSSIuZ2lkOi8vYmMzL1JlY29yZGluZy8xMDY5NDc5NTIxP2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg1yZWFkYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--ca42d4aed48383928eedbeb305bbc7667ce0418e.json",
      "subscription_url": "https://3.basecampapi.com/195539477/buckets/2085958499/recordings/1069479521/subscription.json",
      "comments_count": 0,
      "comments_url": "https://3.basecampapi.com/195539477/buckets/2085958499/recordings/1069479521/comments.json",
      "position": 1,
      "parent": {
        "id": 1069479520,
        "title": "Finance tasks",
        "type": "Todolist",
        "url": "https://3.basecampapi.com/195539477/buckets/2085958499/todolists/1069479520.json",
        "app_url": "https://3.basecamp.com/195539477/buckets/2085958499/todolists/1069479520"
      },
      "bucket": {
        "id": 2085958499,
        "name": "The Leto Laptop",
        "type": "Project"
      },
      "creator": {
        "id": 1049715914,
        "attachable_sgid": "BAh7CEkiCGdpZAY6BkVUSSIrZ2lkOi8vYmMzL1BlcnNvbi8xMDQ5NzE1OTE0P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg9hdHRhY2hhYmxlBjsAVEkiD2V4cGlyZXNfYXQGOwBUMA==--ff006accb6e013cca785190fa38f42c091d24f1e",
        "name": "Victor Cooper",
        "email_address": "victor@honchodesign.com",
        "personable_type": "User",
        "title": "Chief Strategist",
        "bio": "Don't let your dreams be dreams",
        "location": "Chicago, IL",
        "created_at": "2025-10-10T11:41:42.284Z",
        "updated_at": "2025-10-10T11:41:43.054Z",
        "admin": true,
        "owner": true,
        "client": false,
        "employee": true,
        "time_zone": "America/Chicago",
        "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBPNkkT4=--5049939da9ea89df60ade5a1c42d324c1651c66c/avatar?v=1",
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
      "description": "",
      "completed": false,
      "content": "Review budget proposal",
      "starts_on": null,
      "due_on": "2025-10-08",
      "assignees": [],
      "completion_subscribers": [],
      "completion_url": "https://3.basecampapi.com/195539477/buckets/2085958499/todos/1069479521/completion.json"
    }
  ],
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
      "id": 1069479847,
      "status": "active",
      "visible_to_clients": false,
      "url": "https://3.basecampapi.com/195539477/buckets/2085958499/schedule_entries/1069479847.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958499/schedule_entries/1069479847",
      "type": "ScheduleEntry",
      "summary": "Team Meeting",
      "all_day": false,
      "recurring": false,
      "starts_at": "2025-10-11T10:00:00.000Z",
      "ends_at": "2025-10-11T11:00:00.000Z",
      "creator": {
        "id": 1049715914,
        "name": "Victor Cooper",
        "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBPNkkT4=--5049939da9ea89df60ade5a1c42d324c1651c66c/avatar?v=1"
      },
      "participants": [
        {
          "id": 1049715921,
          "name": "Steve Marsh",
          "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBNFkkT4=--c57bba9b44447be39d4a79a5e7f2a592cae9e82c/avatar?v=1"
        }
      ],
      "bucket": {
        "id": 2085958499,
        "name": "The Leto Laptop"
      },
      "comments_count": 0
    }
  ],
  "recurring_schedule_entry_occurrences": [
    {
      "id": 1069479850,
      "status": "active",
      "visible_to_clients": false,
      "url": "https://3.basecampapi.com/195539477/buckets/2085958499/schedule_entries/1069479850.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958499/schedule_entries/1069479850/occurrences/20251014",
      "type": "ScheduleEntry",
      "summary": "Weekly Standup",
      "all_day": false,
      "recurring": true,
      "starts_at": "2025-10-14T09:00:00.000Z",
      "ends_at": "2025-10-14T09:30:00.000Z",
      "creator": {
        "id": 1049715914,
        "name": "Victor Cooper",
        "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBPNkkT4=--5049939da9ea89df60ade5a1c42d324c1651c66c/avatar?v=1"
      },
      "participants": [],
      "bucket": {
        "id": 2085958499,
        "name": "The Leto Laptop"
      },
      "comments_count": 0
    }
  ],
  "assignables": [
    {
      "id": 1069479521,
      "status": "active",
      "visible_to_clients": false,
      "url": "https://3.basecampapi.com/195539477/buckets/2085958499/todos/1069479521.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958499/todos/1069479521",
      "starts_on": null,
      "due_on": "2025-10-15",
      "type": "Todo",
      "content": "Go cutting edge: iOS8 and Android 4.5 only",
      "assignees": [
        {
          "id": 1049715914,
          "name": "Victor Cooper",
          "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBPNkkT4=--5049939da9ea89df60ade5a1c42d324c1651c66c/avatar?v=1"
        }
      ],
      "bucket": {
        "id": 2085958499,
        "name": "The Leto Laptop"
      },
      "parent": {
        "id": 1069479520,
        "title": "Strategy ideas"
      },
      "completion_url": "https://3.basecampapi.com/195539477/buckets/2085958499/todos/1069479521/completion.json",
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
