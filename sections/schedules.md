Schedules
=========

All schedule entries under a Basecamp are children of a schedule resource.

Endpoints:

- [Get schedule](#get-schedule)


Get schedule
------------

* `GET /buckets/1/schedules/2.json` will return the schedule for the Basecamp with an ID of `1`.

To get the schedule ID for a Basecamp, see the [Get a Basecamp][1] endpoint's `dock` payload. To retrieve its schedule entries lists, see the [Get schedule entries][2] endpoint.

###### Example JSON Response
<!-- START GET /buckets/1/schedules/2.json -->
```json
{
  "id": 9007199254741436,
  "status": "active",
  "created_at": "2016-07-19T16:47:30.623Z",
  "updated_at": "2016-07-19T16:49:32.877Z",
  "type": "Schedule",
  "url": "https://3.basecampapi.com/195539477/buckets/2085958498/schedules/9007199254741436.json",
  "app_url": "https://3.basecamp.com/195539477/buckets/2085958498/schedules/9007199254741436",
  "bucket": {
    "id": 2085958498,
    "name": "The Leto Laptop",
    "type": "Project"
  },
  "creator": {
    "id": 1007299143,
    "attachable_sgid": "BAh7CEkiCGdpZAY6BkVUSSIrZ2lkOi8vYmMzL1BlcnNvbi8xMDA3Mjk5MTQzP2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg9hdHRhY2hhYmxlBjsAVEkiD2V4cGlyZXNfYXQGOwBUMA==--919d2c8b11ff403eefcab9db42dd26846d0c3102",
    "name": "Victor Cooper",
    "email_address": "victor@honchodesign.com",
    "personable_type": "User",
    "title": "Chief Strategist",
    "bio": "Don't let your dreams be dreams",
    "created_at": "2016-09-09T22:58:27.559Z",
    "updated_at": "2016-09-09T22:58:31.296Z",
    "admin": true,
    "owner": true,
    "time_zone": "America/Chicago",
    "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBEcqCjw=--c632b967cec296b87363a697a67a87f9cc1e5b45/avatar-64-x4",
    "company": {
      "id": 1033447817,
      "name": "Honcho Design"
    }
  },
  "title": "Schedule",
  "entries_count": 1,
  "entries_url": "https://3.basecampapi.com/195539477/buckets/2085958498/schedules/9007199254741436/entries.json"
}
```
<!-- END GET /buckets/1/schedules/2.json -->
###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/schedules/2.json
```


[1]: https://github.com/basecamp/bc3-api/blob/master/sections/basecamps.md#get-a-basecamp
[2]: https://github.com/basecamp/bc3-api/blob/master/sections/schedule_entries.md#get-schedule-entries
[3]: https://github.com/basecamp/bc3-api/blob/master/sections/recordings.md#trash-a-recording
