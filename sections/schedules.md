Schedules
=========

All schedule entries under a Basecamp are children of a schedule resource.

Endpoints:

- [Get schedule](#get-schedule)
- [Hide schedule tool](#hide-schedule-tool)


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
  "created_at": "2016-07-08T02:17:06.354Z",
  "updated_at": "2016-07-08T02:18:18.394Z",
  "type": "Schedule",
  "url": "https://3.basecampapi.com/195539477/buckets/2085958498/schedules/9007199254741436.json",
  "app_url": "https://3.basecamp.com/195539477/buckets/2085958498/schedules/9007199254741436",
  "bucket": {
    "id": 2085958498,
    "type": "Project"
  },
  "creator": {
    "id": 1007299143,
    "name": "Victor Cooper",
    "email_address": "victor@honchodesign.com",
    "personable_type": "User",
    "title": null,
    "created_at": "2016-07-08T02:16:07.483Z",
    "updated_at": "2016-07-08T02:16:11.821Z",
    "admin": true,
    "owner": true,
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


Hide schedule tool
------------------

If you'd like to remove schedules and schedule events from the list of active tools for a Basecamp, use the [Trash a recording][2] endpoint with the ID of the schedule as the recording ID.


[1]: https://github.com/basecamp/bc3-api/blob/master/sections/basecamps.md#get-a-basecamp
[2]: https://github.com/basecamp/bc3-api/blob/master/sections/schedule_entries.md#get-schedule-entries
[3]: https://github.com/basecamp/bc3-api/blob/master/sections/recordings.md#trash-a-recording
