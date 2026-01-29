Questions
=========

Endpoints:

- [Get questions](#get-questions)
- [Get a question](#get-a-question)
- [Create a question](#create-a-question)
- [Update a question](#update-a-question)
- [Pause a question](#pause-a-question)
- [Resume a question](#resume-a-question)
- [Update notification settings](#update-notification-settings)
- [Trash a question][trash]

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


Create a question
-----------------

* `POST /buckets/1/questionnaires/2/questions.json` creates a question in the project with ID `1` and under the questionnaire with ID `2`.

**Required parameters**:
* `question[title]` - the question to ask.
* `question[schedule]` - a hash containing the schedule configuration:
  * `frequency` - one of `every_day`, `every_week`, `every_other_week`, `every_month`, or `on_certain_days`.
  * `time_of_day` - the time to ask, e.g. `"9:00am"`.
  * `days` - an array of day numbers (0=Sunday through 6=Saturday), e.g. `["1","2","3","4","5"]` for weekdays.

This endpoint will return `201 Created` with the current JSON representation of the question if the creation was a success. See the [Get a question](#get-a-question) endpoint for more info on the payload.

###### Example JSON Request

``` json
{
  "question": {
    "title": "What did you work on today?",
    "schedule": {
      "frequency": "every_day",
      "time_of_day": "5:00pm",
      "days": ["1", "2", "3", "4", "5"]
    }
  }
}
```

###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -H "Content-Type: application/json" \
  -d '{"question":{"title":"What did you work on today?","schedule":{"frequency":"every_day","time_of_day":"5:00pm","days":["1","2","3","4","5"]}}}' \
  https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/questionnaires/2/questions.json
```


Update a question
-----------------

* `PUT /buckets/1/questions/2.json` allows changing the question with an ID of `2` in the project with ID `1`.

This endpoint will return `200 OK` with the current JSON representation of the question if the update was a success. See the [Get a question](#get-a-question) endpoint for more info on the payload.

###### Example JSON Request

``` json
{
  "question": {
    "title": "What are you working on this week?",
    "schedule": {
      "frequency": "every_week",
      "time_of_day": "9:00am",
      "days": ["1"]
    }
  }
}
```

###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -H "Content-Type: application/json" \
  -d '{"question":{"title":"What are you working on this week?","schedule":{"frequency":"every_week","time_of_day":"9:00am","days":["1"]}}}' -X PUT \
  https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/questions/2.json
```


Pause a question
----------------

* `POST /buckets/1/questions/2/pause.json` pauses the question with an ID of `2` in the project with ID `1`.

Returns `200 OK` with `{"paused": true}`.

###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -X POST \
  https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/questions/2/pause.json
```


Resume a question
-----------------

* `DELETE /buckets/1/questions/2/pause.json` resumes the question with an ID of `2` in the project with ID `1`.

Returns `200 OK` with `{"paused": false}`.

###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -X DELETE \
  https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/questions/2/pause.json
```


Update notification settings
----------------------------

* `PUT /buckets/1/questions/2/notification_settings.json` toggles notification settings for the question with an ID of `2` in the project with ID `1`.

_Optional parameters_:

* `responding` - boolean, whether the authenticated user is responding to this question.
* `subscribed` - boolean, whether the authenticated user is subscribed to notifications for this question.

Returns `200 OK` with `{"responding": true/false, "subscribed": true/false}`.

###### Example JSON Request

``` json
{
  "responding": true,
  "subscribed": false
}
```

###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -H "Content-Type: application/json" \
  -d '{"responding":true,"subscribed":false}' -X PUT \
  https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/questions/2/notification_settings.json
```


[pagination]: https://github.com/basecamp/bc3-api/blob/master/README.md#pagination
[trash]: https://github.com/basecamp/bc3-api/blob/master/sections/recordings.md#trash-a-recording
