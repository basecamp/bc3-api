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
    "id": 9007199254741453,
    "status": "active",
    "created_at": "2017-02-15T13:37:19.641Z",
    "updated_at": "2017-02-15T13:37:19.935Z",
    "title": "How do you think the project’s been going so far?",
    "inherits_status": true,
    "type": "Question",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958499/questions/9007199254741453.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958499/questions/9007199254741453",
    "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7CEkiCGdpZAY6BkVUSSIuZ2lkOi8vYmMzL1JlY29yZGluZy8xMDY0MDkxMDY5P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg1yZWFkYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--d8bf83b21fff569e5e491b4613646f7fa0838fc6.json",
    "parent": {
      "id": 9007199254741452,
      "title": "Automatic Check-ins",
      "type": "Questionnaire",
      "url": "https://3.basecampapi.com/195539477/buckets/2085958499/questionnaires/9007199254741452.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958499/questionnaires/9007199254741452"
    },
    "bucket": {
      "id": 2085958499,
      "name": "The Leto Laptop",
      "type": "Project"
    },
    "creator": {
      "id": 1049715914,
      "attachable_sgid": "BAh7CEkiCGdpZAY6BkVUSSIrZ2lkOi8vYmMzL1BlcnNvbi8xMDQ5NzE1OTE0P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg9hdHRhY2hhYmxlBjsAVEkiD2V4cGlyZXNfYXQGOwBUMA==--f7a107e8e50594823dc25f59b44aeefc7b1a4bc8",
      "name": "Victor Cooper",
      "email_address": "victor@honchodesign.com",
      "personable_type": "User",
      "title": "Chief Strategist",
      "bio": "Don't let your dreams be dreams",
      "created_at": "2017-02-15T13:35:18.642Z",
      "updated_at": "2017-02-15T13:37:50.616Z",
      "admin": true,
      "owner": true,
      "time_zone": "America/Chicago",
      "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBMpkkT4=--83f46d5bcb97c314029a53364e3b0444a55759b3/avatar-64-x4",
      "company": {
        "id": 1033447817,
        "name": "Honcho Design"
      }
    },
    "paused": true,
    "schedule": {
      "frequency": "every_week",
      "days": [
        5
      ],
      "hour": 16,
      "minute": 30,
      "start_date": "2017-02-15"
    },
    "answers_count": 0,
    "answers_url": "https://3.basecampapi.com/195539477/buckets/2085958499/questions/9007199254741453/answers.json"
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
  "id": 9007199254741468,
  "status": "active",
  "created_at": "2017-02-16T15:22:19.512Z",
  "updated_at": "2017-02-15T13:37:49.481Z",
  "inherits_status": true,
  "type": "Question",
  "url": "https://3.basecampapi.com/195539477/buckets/2085958499/questions/9007199254741468.json",
  "app_url": "https://3.basecamp.com/195539477/buckets/2085958499/questions/9007199254741468",
  "parent": {
    "id": 9007199254741452,
    "title": "Automatic Check-ins",
    "type": "Questionnaire",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958499/questionnaires/9007199254741452.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958499/questionnaires/9007199254741452"
  },
  "bucket": {
    "id": 2085958499,
    "name": "The Leto Laptop",
    "type": "Project"
  },
  "creator": {
    "id": 1049715915,
    "attachable_sgid": "BAh7CEkiCGdpZAY6BkVUSSIrZ2lkOi8vYmMzL1BlcnNvbi8xMDQ5NzE1OTE1P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg9hdHRhY2hhYmxlBjsAVEkiD2V4cGlyZXNfYXQGOwBUMA==--8c53de5ec1a145d6f44a5b40c1051628ea38a9e2",
    "name": "Annie Bryan",
    "email_address": "annie@honchodesign.com",
    "personable_type": "User",
    "title": "Central Markets Manager",
    "bio": "To open a store is easy, to keep it open is an art",
    "created_at": "2017-02-15T13:35:19.313Z",
    "updated_at": "2017-02-15T13:35:19.313Z",
    "admin": false,
    "owner": false,
    "time_zone": "America/Chicago",
    "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBMtkkT4=--8f9d15263df7a830cc0228be25bf1cf6ffdda3a8/avatar-64-x4",
    "company": {
      "id": 1033447817,
      "name": "Honcho Design"
    }
  },
  "paused": false,
  "title": "What did you work on today?",
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
    "start_date": "2017-02-15"
  },
  "answers_count": 32,
  "answers_url": "https://3.basecampapi.com/195539477/buckets/2085958499/questions/9007199254741468/answers.json"
}
```
<!-- END GET /buckets/1/questions/2.json -->
###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/questions/2.json
```

[pagination]: https://github.com/basecamp/bc3-api/blob/master/README.md#pagination
