Questionnaires
==============

All automatic check-ins questions under a Basecamp are children of a questionnaire resource.

Endpoints:

- [Get questionnaire](#get-questionnaire)

Get questionnaire
-----------------

* `GET /buckets/1/questionnaires/2.json` will return the questionnaire for the Basecamp with an ID of `1`.

To get the questionnaire ID for a Basecamp, see the [Get a Basecamp][basecamp] endpoint's `dock` payload. To retrieve its questions, see the [Get questions][questions] endpoint.

###### Example JSON Response
<!-- START GET /buckets/1/questionnaires/2.json -->
```json
{
  "id": 9007199254741437,
  "status": "active",
  "created_at": "2016-07-07T22:11:09.633Z",
  "updated_at": "2016-07-07T22:11:44.733Z",
  "bucket_path": "/195539477/buckets/2085958498",
  "type": "Questionnaire",
  "comments_count": 0,
  "url": "https://3.basecampapi.com/195539477/buckets/2085958498/questionnaires/9007199254741437.json",
  "app_url": "https://3.basecamp.com/195539477/buckets/2085958498/questionnaires/9007199254741437",
  "creator": {
    "id": 1007299143,
    "name": "Victor Cooper",
    "email_address": "victor@honchodesign.com",
    "personable_type": "User",
    "title": null,
    "created_at": "2016-07-07T22:09:54.930Z",
    "updated_at": "2016-07-07T22:09:59.586Z",
    "admin": true,
    "owner": true,
    "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBEcqCjw=--c632b967cec296b87363a697a67a87f9cc1e5b45/avatar-64-x4",
    "company": {
      "id": 1033447817,
      "name": "Honcho Design"
    }
  },
  "bucket": {
    "id": 1042979252,
    "account_id": 1009501286,
    "name": "The Leto Laptop",
    "description": "Laptop product launch.",
    "created_at": "2016-06-12T22:11:09.454Z",
    "updated_at": "2016-06-12T22:11:09.454Z",
    "creator_id": 1007299143,
    "client_company_id": null
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

[basecamp]: https://github.com/basecamp/bc3-api/blob/master/sections/basecamps.md#get-a-basecamp
[questions]: https://github.com/basecamp/bc3-api/blob/master/sections/questions.md#get-questions
