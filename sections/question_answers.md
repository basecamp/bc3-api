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
    "id": 1069479547,
    "status": "active",
    "visible_to_clients": false,
    "created_at": "2022-11-22T12:05:58.169Z",
    "updated_at": "2022-11-22T12:05:58.169Z",
    "title": "Answer to “What did you work on today?”",
    "inherits_status": true,
    "type": "Question::Answer",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958499/question_answers/1069479547.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958499/question_answers/1069479547",
    "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7CEkiCGdpZAY6BkVUSSIuZ2lkOi8vYmMzL1JlY29yZGluZy8xMDY5NDc5NTQ3P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg1yZWFkYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--d845e9d18c423a5f3d1d84039d37c670ba8b0066.json",
    "subscription_url": "https://3.basecampapi.com/195539477/buckets/2085958499/recordings/1069479547/subscription.json",
    "comments_count": 0,
    "comments_url": "https://3.basecampapi.com/195539477/buckets/2085958499/recordings/1069479547/comments.json",
    "parent": {
      "id": 1069479362,
      "title": "What did you work on today?",
      "type": "Question",
      "url": "https://3.basecampapi.com/195539477/buckets/2085958499/questions/1069479362.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958499/questions/1069479362"
    },
    "bucket": {
      "id": 2085958499,
      "name": "The Leto Laptop",
      "type": "Project"
    },
    "creator": {
      "id": 1049715915,
      "attachable_sgid": "BAh7CEkiCGdpZAY6BkVUSSIrZ2lkOi8vYmMzL1BlcnNvbi8xMDQ5NzE1OTE1P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg9hdHRhY2hhYmxlBjsAVEkiD2V4cGlyZXNfYXQGOwBUMA==--aeb392ebf54ffd820e45f27add22bae3a8c7da56",
      "name": "Annie Bryan",
      "email_address": "annie@honchodesign.com",
      "personable_type": "User",
      "title": "Central Markets Manager",
      "bio": "To open a store is easy, to keep it open is an art",
      "location": null,
      "created_at": "2022-11-22T08:23:21.911Z",
      "updated_at": "2022-11-22T08:23:21.911Z",
      "admin": false,
      "owner": false,
      "client": false,
      "employee": true,
      "time_zone": "America/Chicago",
      "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBMtkkT4=--9927c47a4cbee30a7f9aea667882496aba799149/avatar?v=1",
      "company": {
        "id": 1033447817,
        "name": "Honcho Design"
      },
      "can_manage_projects": true,
      "can_manage_people": true
    },
    "content": "<div>Last week or so was tough, but I think we're back on track. The next design presentation is coming up and we're in good shape.</div>",
    "group_on": "2022-11-22"
  }
]
```
<!-- END GET /buckets/1/questions/2/answers.json -->
###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/questions/2/answers.json
```

List answerers
--------------

* `GET /buckets/1/questions/2/answers/by.json` will return a [paginated list][pagination] of people who have answered the question with ID `2` in the project with an ID of `1`.

By default, long-deceased people are filtered out. Pass `?deceased=true` to include them.

Each entry is a person object.

###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/questions/2/answers/by.json
```

Get answers by person
---------------------

* `GET /buckets/1/questions/2/answers/by/3.json` will return a [paginated list][pagination] of answers to the question with ID `2` in the project with an ID of `1`, filtered to only answers by the person with ID `3`.

###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/questions/2/answers/by/3.json
```

Get a question answer
---------------------

* `GET /buckets/1/question_answers/2.json` will return the answer with an ID of `2` in the project with an ID of `1`.

###### Example JSON Response
<!-- START GET /buckets/1/question_answers/2.json -->
```json
{
  "id": 1069479547,
  "status": "active",
  "visible_to_clients": false,
  "created_at": "2022-11-22T12:05:58.169Z",
  "updated_at": "2022-11-22T12:05:58.169Z",
  "title": "Answer to “What did you work on today?”",
  "inherits_status": true,
  "type": "Question::Answer",
  "url": "https://3.basecampapi.com/195539477/buckets/2085958499/question_answers/1069479547.json",
  "app_url": "https://3.basecamp.com/195539477/buckets/2085958499/question_answers/1069479547",
  "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7CEkiCGdpZAY6BkVUSSIuZ2lkOi8vYmMzL1JlY29yZGluZy8xMDY5NDc5NTQ3P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg1yZWFkYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--d845e9d18c423a5f3d1d84039d37c670ba8b0066.json",
  "subscription_url": "https://3.basecampapi.com/195539477/buckets/2085958499/recordings/1069479547/subscription.json",
  "comments_count": 0,
  "comments_url": "https://3.basecampapi.com/195539477/buckets/2085958499/recordings/1069479547/comments.json",
  "parent": {
    "id": 1069479362,
    "title": "What did you work on today?",
    "type": "Question",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958499/questions/1069479362.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958499/questions/1069479362"
  },
  "bucket": {
    "id": 2085958499,
    "name": "The Leto Laptop",
    "type": "Project"
  },
  "creator": {
    "id": 1049715915,
    "attachable_sgid": "BAh7CEkiCGdpZAY6BkVUSSIrZ2lkOi8vYmMzL1BlcnNvbi8xMDQ5NzE1OTE1P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg9hdHRhY2hhYmxlBjsAVEkiD2V4cGlyZXNfYXQGOwBUMA==--aeb392ebf54ffd820e45f27add22bae3a8c7da56",
    "name": "Annie Bryan",
    "email_address": "annie@honchodesign.com",
    "personable_type": "User",
    "title": "Central Markets Manager",
    "bio": "To open a store is easy, to keep it open is an art",
    "location": null,
    "created_at": "2022-11-22T08:23:21.911Z",
    "updated_at": "2022-11-22T08:23:21.911Z",
    "admin": false,
    "owner": false,
    "client": false,
    "employee": true,
    "time_zone": "America/Chicago",
    "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBMtkkT4=--9927c47a4cbee30a7f9aea667882496aba799149/avatar?v=1",
    "company": {
      "id": 1033447817,
      "name": "Honcho Design"
    },
    "can_manage_projects": true,
    "can_manage_people": true
  },
  "content": "<div>Last week or so was tough, but I think we're back on track. The next design presentation is coming up and we're in good shape.</div>",
  "group_on": "2022-11-22"
}
```
<!-- END GET /buckets/1/question_answers/2.json -->
###### Copy as cURL

``` shell
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

``` json
{
  "question_answer": {
    "content": "<div>Today I worked on the API documentation.</div>",
    "group_on": "2024-01-22"
  }
}
```

###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -H "Content-Type: application/json" \
  -d '{"question_answer":{"content":"<div>Today I worked on the API documentation.</div>","group_on":"2024-01-22"}}' \
  https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/questions/2/answers.json
```


Update a question answer
------------------------

* `PUT /buckets/1/question_answers/2.json` allows changing the answer with an ID of `2` in the project with ID `1`.

This endpoint will return `204 No Content` if the update was a success.

###### Example JSON Request

``` json
{
  "question_answer": {
    "content": "<div>Updated: Today I finished the API documentation.</div>"
  }
}
```

###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -H "Content-Type: application/json" \
  -d '{"question_answer":{"content":"<div>Updated: Today I finished the API documentation.</div>"}}' -X PUT \
  https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/question_answers/2.json
```


[pagination]: https://github.com/basecamp/bc3-api/blob/master/README.md#pagination
[rich_text]: https://github.com/basecamp/bc3-api/blob/master/sections/rich_text.md
[trash]: https://github.com/basecamp/bc3-api/blob/master/sections/recordings.md#trash-a-recording
