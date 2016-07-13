Question answers
================

Endpoints:

- [Get question answers](#get-question-answers)
- [Get a question answer](#get-a-question-answer)

Get question answers
--------------------

* `GET /buckets/1/questions/2/answers.json` will return a [paginated list][pagination] of answers in the Basecamp with an ID of `1` and the question with ID of `2`.

###### Example JSON Response
<!-- START GET /buckets/1/questions/2/answers.json -->
```json
[
  {
    "id": 9007199254741640,
    "status": "active",
    "created_at": "2016-07-13T16:40:20.237Z",
    "updated_at": "2016-07-13T16:40:20.237Z",
    "type": "Question::Answer",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958498/question_answers/9007199254741640.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958498/questions/9007199254741454/answers/2016-07-13#__recording_9007199254741640",
    "comments_count": 0,
    "comments_url": "https://3.basecampapi.com/195539477/buckets/2085958498/recordings/9007199254741640/comments.json",
    "parent": {
      "id": 9007199254741454,
      "title": "What did you work on today?",
      "type": "Question",
      "url": "https://3.basecampapi.com/195539477/buckets/2085958498/questions/9007199254741454.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958498/questions/9007199254741454"
    },
    "bucket": {
      "id": 2085958498,
      "name": "The Leto Laptop",
      "type": "Project"
    },
    "creator": {
      "id": 1007299165,
      "name": "Matt Donahue",
      "email_address": "matt@honchodesign.com",
      "personable_type": "User",
      "title": "Global Data Strategist",
      "created_at": "2016-07-13T14:03:40.217Z",
      "updated_at": "2016-07-13T14:03:40.217Z",
      "admin": false,
      "owner": false,
      "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBF0qCjw=--21513efb0cf6f64f7a0720b2c56ac6145ae6680c/avatar-64-x4"
    },
    "content": "Preparing for the next presentation. Feeling good!",
    "group_on": "2016-07-13"
  }
]
```
<!-- END GET /buckets/1/questions/2/answers.json -->
###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/questions/2/answers.json
```

Get a question answer
---------------------

* `GET /buckets/1/question_answers/2.json` will return the answer with an ID of `2` in the Basecamp with an ID of `1`.

###### Example JSON Response
<!-- START GET /buckets/1/question_answers/2.json -->
```json
{
  "id": 9007199254741640,
  "status": "active",
  "created_at": "2016-07-13T16:40:20.237Z",
  "updated_at": "2016-07-13T16:40:20.237Z",
  "type": "Question::Answer",
  "url": "https://3.basecampapi.com/195539477/buckets/2085958498/question_answers/9007199254741640.json",
  "app_url": "https://3.basecamp.com/195539477/buckets/2085958498/questions/9007199254741454/answers/2016-07-13#__recording_9007199254741640",
  "comments_count": 0,
  "comments_url": "https://3.basecampapi.com/195539477/buckets/2085958498/recordings/9007199254741640/comments.json",
  "parent": {
    "id": 9007199254741454,
    "title": "What did you work on today?",
    "type": "Question",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958498/questions/9007199254741454.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958498/questions/9007199254741454"
  },
  "bucket": {
    "id": 2085958498,
    "name": "The Leto Laptop",
    "type": "Project"
  },
  "creator": {
    "id": 1007299165,
    "name": "Matt Donahue",
    "email_address": "matt@honchodesign.com",
    "personable_type": "User",
    "title": "Global Data Strategist",
    "created_at": "2016-07-13T14:03:40.217Z",
    "updated_at": "2016-07-13T14:03:40.217Z",
    "admin": false,
    "owner": false,
    "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBF0qCjw=--21513efb0cf6f64f7a0720b2c56ac6145ae6680c/avatar-64-x4"
  },
  "content": "Preparing for the next presentation. Feeling good!",
  "group_on": "2016-07-13"
}
```
<!-- END GET /buckets/1/question_answers/2.json -->
###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/question_answers/2.json
```

[pagination]: https://github.com/basecamp/bc3-api/blob/master/README.md#pagination
