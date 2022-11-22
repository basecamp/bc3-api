Questions
=========

Endpoints:

- [Get questions](#get-questions)
- [Get a question](#get-a-question)

Get questions
-------------

* `GET /buckets/1/questionnaires/2/questions.json` will return a [paginated list][pagination] of questions in the project with an ID of `1` and the questionnaire with ID of `2`.

###### Example JSON Response
<!-- START GET /buckets/1/questionnaires/2/questions.json -->
```json
[
  {
    "id": 1069479362,
    "status": "active",
    "visible_to_clients": false,
    "created_at": "2022-10-29T10:56:58.169Z",
    "updated_at": "2022-11-22T08:25:12.645Z",
    "title": "What did you work on today?",
    "inherits_status": true,
    "type": "Question",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958499/questions/1069479362.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958499/questions/1069479362",
    "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7CEkiCGdpZAY6BkVUSSIuZ2lkOi8vYmMzL1JlY29yZGluZy8xMDY5NDc5MzYyP2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg1yZWFkYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--98a22f48366f2b97eda3cc5996bcbd018f2118e3.json",
    "subscription_url": "https://3.basecampapi.com/195539477/buckets/2085958499/recordings/1069479362/subscription.json",
    "parent": {
      "id": 1069479343,
      "title": "Automatic Check-ins",
      "type": "Questionnaire",
      "url": "https://3.basecampapi.com/195539477/buckets/2085958499/questionnaires/1069479343.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958499/questionnaires/1069479343"
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
      "bio": "Don’t let your dreams be dreams",
      "location": "Chicago, IL",
      "created_at": "2022-11-22T08:23:21.732Z",
      "updated_at": "2022-11-22T08:23:21.904Z",
      "admin": true,
      "owner": true,
      "client": false,
      "employee": true,
      "time_zone": "America/Chicago",
      "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBMpkkT4=--5520caeec1845b5090bbfc993ffe8eca8d138e14/avatar?v=1",
      "company": {
        "id": 1033447817,
        "name": "Honcho Design"
      },
      "can_manage_projects": true,
      "can_manage_people": true
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
      "hour": 17,
      "minute": 0,
      "week_instance": null,
      "week_interval": null,
      "month_interval": null,
      "start_date": "2022-11-22",
      "end_date": null
    },
    "answers_count": 32,
    "answers_url": "https://3.basecampapi.com/195539477/buckets/2085958499/questions/1069479362/answers.json"
  }
]
```
<!-- END GET /buckets/1/questionnaires/2/questions.json -->
###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/questionnaires/2/questions.json
```

Get a question
--------------

* `GET /buckets/1/questions/2.json` will return the question with an ID of `2` in the project with an ID of `1`.

###### Example JSON Response
<!-- START GET /buckets/1/questions/2.json -->
```json
{
  "id": 1069479362,
  "status": "active",
  "visible_to_clients": false,
  "created_at": "2022-10-29T10:56:58.169Z",
  "updated_at": "2022-11-22T08:25:12.645Z",
  "title": "What did you work on today?",
  "inherits_status": true,
  "type": "Question",
  "url": "https://3.basecampapi.com/195539477/buckets/2085958499/questions/1069479362.json",
  "app_url": "https://3.basecamp.com/195539477/buckets/2085958499/questions/1069479362",
  "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7CEkiCGdpZAY6BkVUSSIuZ2lkOi8vYmMzL1JlY29yZGluZy8xMDY5NDc5MzYyP2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg1yZWFkYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--98a22f48366f2b97eda3cc5996bcbd018f2118e3.json",
  "subscription_url": "https://3.basecampapi.com/195539477/buckets/2085958499/recordings/1069479362/subscription.json",
  "parent": {
    "id": 1069479343,
    "title": "Automatic Check-ins",
    "type": "Questionnaire",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958499/questionnaires/1069479343.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958499/questionnaires/1069479343"
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
    "bio": "Don’t let your dreams be dreams",
    "location": "Chicago, IL",
    "created_at": "2022-11-22T08:23:21.732Z",
    "updated_at": "2022-11-22T08:23:21.904Z",
    "admin": true,
    "owner": true,
    "client": false,
    "employee": true,
    "time_zone": "America/Chicago",
    "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBMpkkT4=--5520caeec1845b5090bbfc993ffe8eca8d138e14/avatar?v=1",
    "company": {
      "id": 1033447817,
      "name": "Honcho Design"
    },
    "can_manage_projects": true,
    "can_manage_people": true
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
    "hour": 17,
    "minute": 0,
    "week_instance": null,
    "week_interval": null,
    "month_interval": null,
    "start_date": "2022-11-22",
    "end_date": null
  },
  "answers_count": 32,
  "answers_url": "https://3.basecampapi.com/195539477/buckets/2085958499/questions/1069479362/answers.json"
}
```
<!-- END GET /buckets/1/questions/2.json -->
###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/questions/2.json
```

[pagination]: https://github.com/basecamp/bc3-api/blob/master/README.md#pagination
