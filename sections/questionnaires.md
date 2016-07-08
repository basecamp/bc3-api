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
  "created_at": "2016-07-08T16:49:11.634Z",
  "updated_at": "2016-07-08T16:50:36.572Z",
  "type": "Questionnaire",
  "url": "https://3.basecampapi.com/195539477/buckets/2085958498/questionnaires/9007199254741437.json",
  "app_url": "https://3.basecamp.com/195539477/buckets/2085958498/questionnaires/9007199254741437",
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
