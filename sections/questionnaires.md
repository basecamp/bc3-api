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
  "id": 1069479397,
  "status": "active",
  "visible_to_clients": false,
  "created_at": "2026-01-31T08:32:04.661Z",
  "updated_at": "2026-01-31T08:33:00.032Z",
  "title": "Automatic Check-ins",
  "inherits_status": true,
  "type": "Questionnaire",
  "url": "https://3.basecampapi.com/195539477/buckets/2085958504/questionnaires/1069479397.json",
  "app_url": "https://3.basecamp.com/195539477/buckets/2085958504/questionnaires/1069479397",
  "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiLmdpZDovL2JjMy9SZWNvcmRpbmcvMTA2OTQ3OTM5Nz9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg1yZWFkYWJsZQY7AFQ=--8a08bad52e951496c325b880e726a250e5ae9240.json",
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
  "name": "Automatic Check-ins",
  "questions_count": 1,
  "questions_url": "https://3.basecampapi.com/195539477/buckets/2085958504/questionnaires/1069479397/questions.json"
}
```
<!-- END GET /buckets/1/questionnaires/2.json -->

###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/questionnaires/2.json
```

[project]: https://github.com/basecamp/bc3-api/blob/master/sections/projects.md#get-a-project
[questions]: https://github.com/basecamp/bc3-api/blob/master/sections/questions.md#get-questions
