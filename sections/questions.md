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
    "created_at": "2016-07-08T16:49:11.640Z",
    "updated_at": "2016-07-08T16:50:34.223Z",
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
      "id": 1007299208,
      "name": "Victor Cooper",
      "email_address": "victor@honchodesign.com",
      "personable_type": "User",
      "title": null,
      "created_at": "2016-07-08T16:48:02.496Z",
      "updated_at": "2016-07-08T16:48:02.592Z",
      "admin": true,
      "owner": true,
      "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBIgqCjw=--719e3f2aa4406cf5806c2c1522259710deb788e4/avatar-64-x4",
      "company": {
        "id": 1033447822,
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
  "created_at": "2016-06-14T19:25:11.487Z",
  "updated_at": "2016-07-08T16:50:36.555Z",
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
    "id": 1007299209,
    "name": "Annie Bryan",
    "email_address": "annie@honchodesign.com",
    "personable_type": "User",
    "title": "Central Markets Manager",
    "created_at": "2016-07-08T16:48:02.619Z",
    "updated_at": "2016-07-08T16:48:02.619Z",
    "admin": false,
    "owner": false,
    "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBIkqCjw=--003094c5a28c4331af92401ec3675148e81d7bc1/avatar-64-x4",
    "company": {
      "id": 1033447822,
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
