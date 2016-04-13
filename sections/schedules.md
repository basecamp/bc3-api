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

``` json
{
  "id": 9007199254741016,
  "created_at": "2016-04-05T06:16:29.846-05:00",
  "updated_at": "2016-04-13T05:30:21.843-05:00",
  "title": "Schedule",
  "entries_count": 3,
  "entries_url": "https://3.basecampapi.com/195539477/buckets/2085958495/schedules/9007199254741015/entries.json",
  "status": "active",
  "url": "https://3.basecampapi.com/195539477/buckets/2085958495/schedules/9007199254741015",
  "type": "Schedule",
  "creator": {
    "id": 1007299143,
    "name": "Victor Cooper",
    "email_address": "victor@honchodesign.com",
    "personable_type": "User",
    "title": null,
    "created_at": "2016-04-05T06:16:24.895-05:00",
    "updated_at": "2016-04-13T04:34:12.591-05:00",
    "admin": true,
    "owner": true,
    "avatar_url": "https://3.basecamp-assets.com/195539477/people/BAhpBEcqCjw=--c632b967cec296b87363a697a67a87f9cc1e5b45/avatar-64-x4",
    "company": {
      "id": 1033447817,
      "name": "Honcho Design"
    }
  },
  "bucket": {
    "id": 1042979249,
    "account_id": 1009501286,
    "name": "Annie's Corner",
    "description": "Annie's Stuff. Keep Out. 😁",
    "created_at": "2016-03-05T05:16:29.737-06:00",
    "updated_at": "2016-03-05T05:16:29.737-06:00",
    "creator_id": 1007299143,
    "client_company_id": null
  },
  "bucket_path": "/195539477/buckets/2085958495"
}
```

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
