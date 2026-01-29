Question reminders
==================

Endpoints:

- [Get question reminders](#get-question-reminders)

Get question reminders
----------------------

* `GET /my/question_reminders.json` will return a [paginated list][pagination] of pending check-in reminders for the authenticated user.

Each reminder includes the question it belongs to, along with the question's project (bucket).

###### Example JSON Response
<!-- START GET /my/question_reminders.json -->
```json
[
  {
    "reminder_id": 12345,
    "remind_at": "2024-01-22T17:00:00.000Z",
    "group_on": "2024-01-22",
    "question": {
      "id": 1069479362,
      "title": "What did you work on today?",
      "type": "Question",
      "url": "https://3.basecampapi.com/195539477/buckets/2085958499/questions/1069479362.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958499/questions/1069479362",
      "bucket": {
        "id": 2085958499,
        "name": "The Leto Laptop",
        "type": "Project"
      }
    }
  }
]
```
<!-- END GET /my/question_reminders.json -->

###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/my/question_reminders.json
```


[pagination]: https://github.com/basecamp/bc3-api/blob/master/README.md#pagination
