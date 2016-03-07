Recordings
==========

Most of the data structures in the Basecamp 3 API are represented as "Recordings", with generic actions available to be performed. The following resources have generic actions enabled:

- [Messages][1]
- [Comments][2]

Endpoints:

- [Trash a recording](#trash-a-recording)

(More actions will be exposed in the API soon!)


Trash a recording
-----------------

* `PUT /buckets/1/recordings/2/status/trashed.json` will mark the recording with an ID of `2`in the Basecamp with ID `1` as trashed.

No parameters required. Returns `204 No Content` if successful.

###### Copy as cURL:

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -H "Content-Type: application/json" -X PUT \
  http://bc3.dev/$ACCOUNT_ID/buckets/2085958506/recordings/9007199254743021/status/trashed.json
```


[1]: https://github.com/basecamp/bc3-api/blob/master/sections/messages.md#messages
[2]: https://github.com/basecamp/bc3-api/blob/master/sections/comments.md#comments
