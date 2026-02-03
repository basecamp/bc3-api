Question answers
================

Endpoints:

- [Get question answers](#get-question-answers)
- [List answerers](#list-answerers)
- [Get answers by person](#get-answers-by-person)
- [Get a question answer](#get-a-question-answer)
- [Create a question answer](#create-a-question-answer)
- [Update a question answer](#update-a-question-answer)
- [Trash a question answer][trash]

Get question answers
--------------------

* `GET /buckets/1/questions/2/answers.json` will return a [paginated list][pagination] of answers in the project with an ID of `1` and the question with ID of `2`.

_Optional query parameters_:

* `date` - an ISO 8601 date string to filter answers by day, e.g. `2024-01-22`.
* `creator_id` - a person ID to filter answers by author.

###### Example JSON Response
<!-- START GET /buckets/1/questions/2/answers.json -->
```json
[
  {
    "id": 1069479545,
    "status": "active",
    "visible_to_clients": false,
    "created_at": "2026-01-26T22:11:00.000Z",
    "updated_at": "2026-01-26T22:11:00.000Z",
    "title": "Answer to “What did you work on today?”",
    "inherits_status": true,
    "type": "Question::Answer",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958504/question_answers/1069479545.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958504/question_answers/1069479545",
    "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiLmdpZDovL2JjMy9SZWNvcmRpbmcvMTA2OTQ3OTU0NT9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg1yZWFkYWJsZQY7AFQ=--4ecc639365c1b1091bba2cebaad8b5d8bd1be402.json",
    "subscription_url": "https://3.basecampapi.com/195539477/buckets/2085958504/recordings/1069479545/subscription.json",
    "comments_count": 0,
    "comments_url": "https://3.basecampapi.com/195539477/buckets/2085958504/recordings/1069479545/comments.json",
    "parent": {
      "id": 1069479417,
      "title": "What did you work on today?",
      "type": "Question",
      "url": "https://3.basecampapi.com/195539477/buckets/2085958504/questions/1069479417.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958504/questions/1069479417"
    },
    "bucket": {
      "id": 2085958504,
      "name": "The Leto Laptop",
      "type": "Project"
    },
    "creator": {
      "id": 1049715940,
      "attachable_sgid": "BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiK2dpZDovL2JjMy9QZXJzb24vMTA0OTcxNTk0MD9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg9hdHRhY2hhYmxlBjsAVA==--8a036dc6e0dee6b7db74851189b981fe69f4172d",
      "name": "Jared Davis",
      "email_address": "jared@honchodesign.com",
      "personable_type": "User",
      "title": "International Tactics Facilitator",
      "bio": "Oh, so they have internet on computers now!",
      "location": null,
      "created_at": "2026-01-31T08:29:43.792Z",
      "updated_at": "2026-01-31T08:29:43.792Z",
      "admin": false,
      "owner": false,
      "client": false,
      "employee": true,
      "time_zone": "America/Chicago",
      "avatar_url": "https://3.basecampapi.com/195539477/people/BAhpBORkkT4=--2667d9ced3ec021946197cbb6c3083f0f95f3b6a/avatar?v=1",
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
    "content": "Prototype is done, components in really good shape. I think we're going to split for now and come back when design is more settled.",
    "group_on": "2026-01-26"
  }
]
```
<!-- END GET /buckets/1/questions/2/answers.json -->
###### Copy as cURL

```shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/questions/2/answers.json
```

List answerers
--------------

* `GET /buckets/1/questions/2/answers/by.json` will return a [paginated list][pagination] of people who have answered the question with ID `2` in the project with an ID of `1`.

By default, long-deceased people are filtered out. Pass `?deceased=true` to include them.

Each entry is a person object.

###### Copy as cURL

```shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/questions/2/answers/by.json
```

Get answers by person
---------------------

* `GET /buckets/1/questions/2/answers/by/3.json` will return a [paginated list][pagination] of answers to the question with ID `2` in the project with an ID of `1`, filtered to only answers by the person with ID `3`.

###### Copy as cURL

```shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/questions/2/answers/by/3.json
```

Get a question answer
---------------------

* `GET /buckets/1/question_answers/2.json` will return the answer with an ID of `2` in the project with an ID of `1`.

###### Example JSON Response
<!-- START GET /buckets/1/question_answers/2.json -->
```json
{
  "id": 1069479545,
  "status": "active",
  "visible_to_clients": false,
  "created_at": "2026-01-26T22:11:00.000Z",
  "updated_at": "2026-01-26T22:11:00.000Z",
  "title": "Answer to “What did you work on today?”",
  "inherits_status": true,
  "type": "Question::Answer",
  "url": "https://3.basecampapi.com/195539477/buckets/2085958504/question_answers/1069479545.json",
  "app_url": "https://3.basecamp.com/195539477/buckets/2085958504/question_answers/1069479545",
  "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiLmdpZDovL2JjMy9SZWNvcmRpbmcvMTA2OTQ3OTU0NT9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg1yZWFkYWJsZQY7AFQ=--4ecc639365c1b1091bba2cebaad8b5d8bd1be402.json",
  "subscription_url": "https://3.basecampapi.com/195539477/buckets/2085958504/recordings/1069479545/subscription.json",
  "comments_count": 0,
  "comments_url": "https://3.basecampapi.com/195539477/buckets/2085958504/recordings/1069479545/comments.json",
  "parent": {
    "id": 1069479417,
    "title": "What did you work on today?",
    "type": "Question",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958504/questions/1069479417.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958504/questions/1069479417"
  },
  "bucket": {
    "id": 2085958504,
    "name": "The Leto Laptop",
    "type": "Project"
  },
  "creator": {
    "id": 1049715940,
    "attachable_sgid": "BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiK2dpZDovL2JjMy9QZXJzb24vMTA0OTcxNTk0MD9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg9hdHRhY2hhYmxlBjsAVA==--8a036dc6e0dee6b7db74851189b981fe69f4172d",
    "name": "Jared Davis",
    "email_address": "jared@honchodesign.com",
    "personable_type": "User",
    "title": "International Tactics Facilitator",
    "bio": "Oh, so they have internet on computers now!",
    "location": null,
    "created_at": "2026-01-31T08:29:43.792Z",
    "updated_at": "2026-01-31T08:29:43.792Z",
    "admin": false,
    "owner": false,
    "client": false,
    "employee": true,
    "time_zone": "America/Chicago",
    "avatar_url": "https://3.basecampapi.com/195539477/people/BAhpBORkkT4=--2667d9ced3ec021946197cbb6c3083f0f95f3b6a/avatar?v=1",
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
  "content": "Prototype is done, components in really good shape. I think we're going to split for now and come back when design is more settled.",
  "group_on": "2026-01-26"
}
```
<!-- END GET /buckets/1/question_answers/2.json -->
###### Copy as cURL

```shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/question_answers/2.json
```


Create a question answer
------------------------

* `POST /buckets/1/questions/2/answers.json` creates an answer to the question with ID `2` in the project with ID `1`.

**Required parameters**: `content` containing the answer text. See our [Rich text guide][rich_text] for what HTML tags are allowed.

_Optional parameters_:
* `group_on` - a date (ISO 8601) to group this answer with others from the same day.

This endpoint will return `201 Created` with the current JSON representation of the answer if the creation was a success. See the [Get a question answer](#get-a-question-answer) endpoint for more info on the payload.

###### Example JSON Request

```json
{
  "question_answer": {
    "content": "<div>Today I worked on the API documentation.</div>",
    "group_on": "2024-01-22"
  }
}
```

###### Copy as cURL

```shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -H "Content-Type: application/json" \
  -d '{"question_answer":{"content":"<div>Today I worked on the API documentation.</div>","group_on":"2024-01-22"}}' \
  https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/questions/2/answers.json
```


Update a question answer
------------------------

* `PUT /buckets/1/question_answers/2.json` allows changing the answer with an ID of `2` in the project with ID `1`.

This endpoint will return `204 No Content` if the update was a success.

###### Example JSON Request

```json
{
  "question_answer": {
    "content": "<div>Updated: Today I finished the API documentation.</div>"
  }
}
```

###### Copy as cURL

```shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -H "Content-Type: application/json" \
  -d '{"question_answer":{"content":"<div>Updated: Today I finished the API documentation.</div>"}}' -X PUT \
  https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/question_answers/2.json
```


[pagination]: https://github.com/basecamp/bc3-api/blob/master/README.md#pagination
[rich_text]: https://github.com/basecamp/bc3-api/blob/master/sections/rich_text.md
[trash]: https://github.com/basecamp/bc3-api/blob/master/sections/recordings.md#trash-a-recording
