Question answers
================

Endpoints:

- [Get question answers](#get-question-answers)
- [Get a question answer](#get-a-question-answer)

Get question answers
--------------------

* `GET /buckets/1/questions/2/answers.json` will return a [paginated list][pagination] of answers in the project with an ID of `1` and the question with ID of `2`.

###### Example JSON Response
<!-- START GET /buckets/1/questions/2/answers.json -->
```json
[
  {
    "id": 9007199254741640,
    "status": "active",
    "created_at": "2016-07-19T22:53:41.446Z",
    "updated_at": "2016-07-19T22:53:41.446Z",
    "title": "Answer to “What did you work on today?”",
    "type": "Question::Answer",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958498/question_answers/9007199254741640.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958498/questions/9007199254741454/answers/2016-07-19#__recording_9007199254741640",
    "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7CEkiCGdpZAY6BkVUSSIuZ2lkOi8vYmMzL1JlY29yZGluZy8xMDY0MDkxMjU0P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg1yZWFkYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--06444efacad452ffc5fdd0fd0d27912f5697f29d.json",
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
      "attachable_sgid": "BAh7CEkiCGdpZAY6BkVUSSIrZ2lkOi8vYmMzL1BlcnNvbi8xMDA3Mjk5MTY1P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg9hdHRhY2hhYmxlBjsAVEkiD2V4cGlyZXNfYXQGOwBUMA==--c28a27d0c490353fc1a5c2a50ce8eda0fae07370",
      "name": "Matt Donahue",
      "email_address": "matt@honchodesign.com",
      "personable_type": "User",
      "title": "Global Data Strategist",
      "bio": null,
      "created_at": "2016-07-19T21:27:47.654Z",
      "updated_at": "2016-07-19T21:27:47.654Z",
      "admin": false,
      "owner": false,
      "time_zone": "America/Chicago",
      "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBF0qCjw=--21513efb0cf6f64f7a0720b2c56ac6145ae6680c/avatar-64-x4"
    },
    "content": "<div>Preparing for the next presentation. Feeling good!</div>",
    "group_on": "2016-07-19"
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

* `GET /buckets/1/question_answers/2.json` will return the answer with an ID of `2` in the project with an ID of `1`.

###### Example JSON Response
<!-- START GET /buckets/1/question_answers/2.json -->
```json
{
  "id": 9007199254741640,
  "status": "active",
  "created_at": "2016-07-19T22:53:41.446Z",
  "updated_at": "2016-07-19T22:53:41.446Z",
  "title": "Answer to “What did you work on today?”",
  "type": "Question::Answer",
  "url": "https://3.basecampapi.com/195539477/buckets/2085958498/question_answers/9007199254741640.json",
  "app_url": "https://3.basecamp.com/195539477/buckets/2085958498/questions/9007199254741454/answers/2016-07-19#__recording_9007199254741640",
  "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7CEkiCGdpZAY6BkVUSSIuZ2lkOi8vYmMzL1JlY29yZGluZy8xMDY0MDkxMjU0P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg1yZWFkYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--06444efacad452ffc5fdd0fd0d27912f5697f29d.json",
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
    "attachable_sgid": "BAh7CEkiCGdpZAY6BkVUSSIrZ2lkOi8vYmMzL1BlcnNvbi8xMDA3Mjk5MTY1P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg9hdHRhY2hhYmxlBjsAVEkiD2V4cGlyZXNfYXQGOwBUMA==--c28a27d0c490353fc1a5c2a50ce8eda0fae07370",
    "name": "Matt Donahue",
    "email_address": "matt@honchodesign.com",
    "personable_type": "User",
    "title": "Global Data Strategist",
    "bio": null,
    "created_at": "2016-07-19T21:27:47.654Z",
    "updated_at": "2016-07-19T21:27:47.654Z",
    "admin": false,
    "owner": false,
    "time_zone": "America/Chicago",
    "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBF0qCjw=--21513efb0cf6f64f7a0720b2c56ac6145ae6680c/avatar-64-x4"
  },
  "content": "<div>Preparing for the next presentation. Feeling good!</div>",
  "group_on": "2016-07-19"
}
```
<!-- END GET /buckets/1/question_answers/2.json -->
###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/question_answers/2.json
```

[pagination]: https://github.com/basecamp/bc3-api/blob/master/README.md#pagination
