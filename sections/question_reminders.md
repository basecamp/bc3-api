Question reminders
==================

Endpoints:

- [Get question reminders](#get-question-reminders)

Get question reminders
----------------------

* `GET /my/question_reminders.json` will return a [paginated list][pagination] of pending check-in reminders for the authenticated user.

Each reminder includes the question it belongs to, along with the question's project (bucket).

###### Example JSON Response
<!-- START GET /my/question_reminders.json -->
```json
[
  {
    "reminder_id": 1004522375,
    "remind_at": "2026-02-02T15:00:00.000Z",
    "group_on": "2026-02-02",
    "question": {
      "id": 1069479417,
      "status": "active",
      "visible_to_clients": false,
      "created_at": "2025-12-19T02:37:00.000Z",
      "updated_at": "2026-01-31T08:32:59.995Z",
      "title": "What did you work on today?",
      "inherits_status": true,
      "type": "Question",
      "url": "https://3.basecampapi.com/195539477/buckets/2085958504/questions/1069479417.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958504/questions/1069479417",
      "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiLmdpZDovL2JjMy9SZWNvcmRpbmcvMTA2OTQ3OTQxNz9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg1yZWFkYWJsZQY7AFQ=--17f918a3dc2d23e366010e5ff9f46d2d5208c9bf.json",
      "subscription_url": "https://3.basecampapi.com/195539477/buckets/2085958504/recordings/1069479417/subscription.json",
      "parent": {
        "id": 1069479397,
        "title": "Automatic Check-ins",
        "type": "Questionnaire",
        "url": "https://3.basecampapi.com/195539477/buckets/2085958504/questionnaires/1069479397.json",
        "app_url": "https://3.basecamp.com/195539477/buckets/2085958504/questionnaires/1069479397"
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
      "paused": false,
      "schedule": {
        "frequency": "every_day",
        "days": [
          1,
          2,
          3,
          4,
          5
        ],
        "hour": 9,
        "minute": 0,
        "week_instance": 1,
        "week_interval": null,
        "month_interval": null,
        "start_date": "2026-01-31",
        "duration": null,
        "end_date": null
      },
      "answers_count": 32,
      "answers_url": "https://3.basecampapi.com/195539477/buckets/2085958504/questions/1069479417/answers.json"
    }
  }
]
```
<!-- END GET /my/question_reminders.json -->

###### Copy as cURL

```shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/my/question_reminders.json
```


[pagination]: https://github.com/basecamp/bc3-api/blob/master/README.md#pagination
