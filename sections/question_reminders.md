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
[]
```
<!-- END GET /my/question_reminders.json -->

###### Copy as cURL

```shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/my/question_reminders.json
```


[pagination]: https://github.com/basecamp/bc3-api/blob/master/README.md#pagination
