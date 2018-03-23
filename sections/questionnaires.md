Questionnaires
==============

All automatic check-ins questions under a project are children of a questionnaire resource.

Endpoints:

- [Get questionnaire](#get-questionnaire)

Get questionnaire
-----------------

* `GET /buckets/1/questionnaires/2.json` will return the questionnaire for the project with an ID of `1`.

To get the questionnaire ID for a project, see the [Get a Project][project] endpoint's `dock` payload. To retrieve its questions, see the [Get questions][questions] endpoint.

###### Example JSON Response
<!-- START GET /buckets/1/questionnaires/2.json -->
```json
{
  "id": 9007199254741437,
  "status": "active",
  "created_at": "2016-07-19T16:47:30.653Z",
  "updated_at": "2016-07-19T18:24:05.737Z",
  "title": "Automatic Check-ins",
  "type": "Questionnaire",
  "url": "https://3.basecampapi.com/195539477/buckets/2085958498/questionnaires/9007199254741437.json",
  "app_url": "https://3.basecamp.com/195539477/buckets/2085958498/questionnaires/9007199254741437",
  "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7CEkiCGdpZAY6BkVUSSIuZ2lkOi8vYmMzL1JlY29yZGluZy8xMDY0MDkxMDUzP2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg1yZWFkYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--e028731626fb4f0e4665ba42e349ce5c72031b31.json",
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
  "name": "Automatic Check-ins",
  "questions_count": 5,
  "questions_url": "https://3.basecampapi.com/195539477/buckets/2085958498/questionnaires/9007199254741437/questions.json"
}
```
<!-- END GET /buckets/1/questionnaires/2.json -->

###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/questionnaires/2.json
```

[project]: https://github.com/basecamp/bc3-api/blob/master/sections/projects.md#get-a-project
[questions]: https://github.com/basecamp/bc3-api/blob/master/sections/questions.md#get-questions
