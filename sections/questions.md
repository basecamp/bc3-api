Questions
=========

Endpoints:

- [Get questions](#get-questions)
- [Get a question](#get-a-question)

Get questions
-------------

* `GET /buckets/1/questionnaires/2/questions.json` will return a [paginated list][pagination] of questions in the Basecamp with an ID of `1` and the questionnaire with ID of `2`.

###### Example JSON Response
<!-- START GET /buckets/1/questionnaires/2/questions.json -->
```json
[
  {
    "id": 9007199254741438,
    "status": "active",
    "created_at": "2016-07-19T16:47:30.665Z",
    "updated_at": "2016-07-19T18:24:05.529Z",
    "type": "Question",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958498/questions/9007199254741438.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958498/questions/9007199254741438",
    "parent": {
      "id": 9007199254741437,
      "title": "Automatic Check-ins",
      "type": "Questionnaire",
      "url": "https://3.basecampapi.com/195539477/buckets/2085958498/questionnaires/9007199254741437.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958498/questionnaires/9007199254741437"
    },
    "bucket": {
      "id": 2085958498,
      "name": "The Leto Laptop",
      "type": "Project"
    },
    "creator": {
      "id": 1007299143,
      "attachable_sgid": "BAh7CEkiCGdpZAY6BkVUSSIrZ2lkOi8vYmMzL1BlcnNvbi8xMDA3Mjk5MTQzP2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg9hdHRhY2hhYmxlBjsAVEkiD2V4cGlyZXNfYXQGOwBUMA==--919d2c8b11ff403eefcab9db42dd26846d0c3102",
      "name": "Victor Cooper",
      "email_address": "victor@honchodesign.com",
      "personable_type": "User",
      "title": "Chief Strategist",
      "bio": "Don't let your dreams be dreams",
      "created_at": "2016-09-09T22:58:27.559Z",
      "updated_at": "2016-09-09T22:58:31.296Z",
      "admin": true,
      "owner": true,
      "time_zone": "America/Chicago",
      "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBEcqCjw=--c632b967cec296b87363a697a67a87f9cc1e5b45/avatar-64-x4",
      "company": {
        "id": 1033447817,
        "name": "Honcho Design"
      }
    },
    "paused": true,
    "title": "See anything great lately that inspired you?",
    "schedule_code": "every_friday",
    "schedule_time_of_day": "evening",
    "answers_count": 0,
    "answers_url": "https://3.basecampapi.com/195539477/buckets/2085958498/questions/9007199254741438/answers.json"
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

* `GET /buckets/1/questions/2.json` will return the question with an ID of `2` in the Basecamp with an ID of `1`.

###### Example JSON Response
<!-- START GET /buckets/1/questions/2.json -->
```json
{
  "id": 9007199254741454,
  "status": "active",
  "created_at": "2016-06-25T16:54:30.492Z",
  "updated_at": "2016-07-19T18:24:05.559Z",
  "type": "Question",
  "url": "https://3.basecampapi.com/195539477/buckets/2085958498/questions/9007199254741454.json",
  "app_url": "https://3.basecamp.com/195539477/buckets/2085958498/questions/9007199254741454",
  "parent": {
    "id": 9007199254741437,
    "title": "Automatic Check-ins",
    "type": "Questionnaire",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958498/questionnaires/9007199254741437.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958498/questionnaires/9007199254741437"
  },
  "bucket": {
    "id": 2085958498,
    "name": "The Leto Laptop",
    "type": "Project"
  },
  "creator": {
    "id": 1007299144,
    "attachable_sgid": "BAh7CEkiCGdpZAY6BkVUSSIrZ2lkOi8vYmMzL1BlcnNvbi8xMDA3Mjk5MTQ0P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg9hdHRhY2hhYmxlBjsAVEkiD2V4cGlyZXNfYXQGOwBUMA==--2e34d7611a9fcaeb82342d015a671cf5e998c036",
    "name": "Annie Bryan",
    "email_address": "annie@honchodesign.com",
    "personable_type": "User",
    "title": "Central Markets Manager",
    "bio": "To open a store is easy, to keep it open is an art",
    "created_at": "2016-09-09T22:58:27.734Z",
    "updated_at": "2016-09-09T22:58:27.734Z",
    "admin": false,
    "owner": false,
    "time_zone": "America/Chicago",
    "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBEgqCjw=--8266bb0507508f3d46050d57b65924d5e2a005f3/avatar-64-x4",
    "company": {
      "id": 1033447817,
      "name": "Honcho Design"
    }
  },
  "paused": false,
  "title": "What did you work on today?",
  "schedule_code": "every_weekday",
  "schedule_time_of_day": "evening",
  "answers_count": 32,
  "answers_url": "https://3.basecampapi.com/195539477/buckets/2085958498/questions/9007199254741454/answers.json"
}
```
<!-- END GET /buckets/1/questions/2.json -->
###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/questions/2.json
```

[pagination]: https://github.com/basecamp/bc3-api/blob/master/README.md#pagination
