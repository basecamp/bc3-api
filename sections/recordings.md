Recordings
==========

Most of the data structures in the Basecamp 3 API are represented as "Recordings", with generic actions available to be performed.

Endpoints:

- [Get recordings](#get-recordings)
- [Trash a recording](#trash-a-recording)

Get recordings
--------------

* `GET /projects/recordings.json?type=$TYPE` will return a [paginated list][1] of records for the given `type` of recording.

**Required parameters**: `type`, which must be `Comment`, `Document`, `Message`, `Question::Answer`, `Schedule::Entry`, `Todo`, `Todolist`, or `Upload`.

_Optional parameters_:

* `bucket` - Single or comma separated list of [Basecamp][2] IDs. Default: All active Basecamps visible to the current user.
* `status` - Options: `active`, `archived`, or `trashed`. Default: `active`
* `sort` - Options: `created_at` or `updated_at`. Default: `created_at`.
* `direction` - Options: `desc` or `asc`. Default: `desc`.

Examples: `/projects/recordings.json?type=Todo`, `/projects/recordings.json?type=Message&bucket=1`, `/projects/recordings.json?type=Document&bucket=1,2&sort=updated_at&direction=asc`


Trash a recording
-----------------

* `PUT /buckets/1/recordings/2/status/trashed.json` will mark the recording with an ID of `2`in the Basecamp with ID `1` as trashed.

No parameters required. Returns `204 No Content` if successful.

###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -H "Content-Type: application/json" -X PUT \
  https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/recordings/2/status/trashed.json
```

[1]: https://github.com/basecamp/bc3-api/blob/master/README.md#pagination
[2]: https://github.com/basecamp/bc3-api/blob/master/sections/basecamps.md#basecamps
