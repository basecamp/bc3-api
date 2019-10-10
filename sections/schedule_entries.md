Schedule entries
================

Endpoints:

- [Get schedule entries](#get-schedule-entries)
- [Get a schedule entry](#get-a-schedule-entry)
- [Create a schedule entry](#create-a-schedule-entry)
- [Update a schedule entry](#update-a-schedule-entry)
- [Trash a schedule entry][trash]

Get schedule entries
--------------------

* `GET /buckets/1/schedules/3/entries.json` will return a [paginated list][pagination] of active schedule entries in the project with an ID of `1` and the schedule with ID of `3`.

To get the schedule ID for a project, see the [Get schedule][schedule] endpoint.

_Optional query parameters_:

* `status` - when set to `archived` or `trashed`, will return archived or trashed schedule entries that are in this schedule.

###### Example JSON Response
<!-- START GET /buckets/1/schedules/3/entries.json -->
```json
[
  {
    "id": 9007199254741759,
    "status": "active",
    "created_at": "2016-07-19T21:33:36.406Z",
    "updated_at": "2016-07-19T21:33:39.692Z",
    "title": "Team Meeting",
    "inherits_status": true,
    "type": "Schedule::Entry",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958498/schedule_entries/9007199254741759.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958498/schedule_entries/9007199254741759",
    "comments_count": 0,
    "comments_url": "https://3.basecampapi.com/195539477/buckets/2085958498/recordings/9007199254741759/comments.json",
    "parent": {
      "id": 9007199254741436,
      "title": "Schedule",
      "type": "Schedule",
      "url": "https://3.basecampapi.com/195539477/buckets/2085958498/schedules/9007199254741436.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958498/schedules/9007199254741436"
    },
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
    "description": "<div>Time to synergize!</div>",
    "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7CEkiCGdpZAY6BkVUSSI0Z2lkOi8vYmMzL1JlY29yZGluZy85MDA3MTk5MjU0NzQxNzU5P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg1yZWFkYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--150340d7bf9e45970422758888bbf0176a1fdd2c.json",
    "subscription_url": "https://3.basecampapi.com/195539477/buckets/2085958498/recordings/9007199254741759/subscription.json",
    "summary": "Team Meeting",
    "all_day": false,
    "starts_at": "2016-07-20T23:33:36.369Z",
    "ends_at": "2016-07-21T03:33:36.369Z",
    "participants": [
      {
        "id": 1007299150,
        "attachable_sgid": "BAh7CEkiCGdpZAY6BkVUSSIrZ2lkOi8vYmMzL1BlcnNvbi8xMDA3Mjk5MTUwP2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg9hdHRhY2hhYmxlBjsAVEkiD2V4cGlyZXNfYXQGOwBUMA==--9856de8e8169dda9e2c441b7184985194b2d2296",
        "name": "Steve Marsh",
        "email_address": "steve@honchodesign.com",
        "personable_type": "User",
        "title": "Legacy Directives Strategist",
        "bio": "You can do it!",
        "created_at": "2016-09-09T22:58:28.369Z",
        "updated_at": "2016-09-09T22:58:28.369Z",
        "admin": false,
        "owner": false,
        "time_zone": "America/Chicago",
        "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBE4qCjw=--b544b6a710bd76020abc076fc041895954025116/avatar-64-x4",
        "company": {
          "id": 1033447817,
          "name": "Honcho Design"
        }
      }
    ]
  }
]
```
<!-- END GET /buckets/1/schedules/3/entries.json -->
###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/schedules/3/entries.json
```


Get a schedule entry
--------------------

* `GET /buckets/1/schedule_entries/2.json` will return the schedule entry with an ID of `2` in the project with an ID of `1`.

**Note:** this endpoint redirects to the first individual occurrence of the entry, for **recurring schedule entries**. It's also possible to access a recurring schedule entry via any of the individual occurrences: `GET /buckets/1/schedule_entries/2/occurrences/20190218.json` will return the occurrence for a recurring schedule entry with an ID of `2`, happening on `2019-02-18`, in the project with an ID of `1`. It'll return 404 for invalid occurrences.

###### Example JSON Response
<!-- START GET /buckets/1/schedule_entries/2.json -->
```json
{
  "id": 9007199254741759,
  "status": "active",
  "created_at": "2016-07-19T21:33:36.406Z",
  "updated_at": "2016-07-19T21:33:39.692Z",
  "inherits_status": true,
  "type": "Schedule::Entry",
  "url": "https://3.basecampapi.com/195539477/buckets/2085958498/schedule_entries/9007199254741759.json",
  "app_url": "https://3.basecamp.com/195539477/buckets/2085958498/schedule_entries/9007199254741759",
  "comments_count": 0,
  "comments_url": "https://3.basecampapi.com/195539477/buckets/2085958498/recordings/9007199254741759/comments.json",
  "parent": {
    "id": 9007199254741436,
    "title": "Schedule",
    "type": "Schedule",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958498/schedules/9007199254741436.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958498/schedules/9007199254741436"
  },
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
  "description": "<div>Time to synergize!</div>",
  "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7CEkiCGdpZAY6BkVUSSI0Z2lkOi8vYmMzL1JlY29yZGluZy85MDA3MTk5MjU0NzQxNzU5P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg1yZWFkYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--150340d7bf9e45970422758888bbf0176a1fdd2c.json",
  "subscription_url": "https://3.basecampapi.com/195539477/buckets/2085958498/recordings/9007199254741759/subscription.json",
  "summary": "Team Meeting",
  "all_day": false,
  "starts_at": "2016-07-20T23:33:36.369Z",
  "ends_at": "2016-07-21T03:33:36.369Z",
  "participants": [
    {
      "id": 1007299150,
      "attachable_sgid": "BAh7CEkiCGdpZAY6BkVUSSIrZ2lkOi8vYmMzL1BlcnNvbi8xMDA3Mjk5MTUwP2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg9hdHRhY2hhYmxlBjsAVEkiD2V4cGlyZXNfYXQGOwBUMA==--9856de8e8169dda9e2c441b7184985194b2d2296",
      "name": "Steve Marsh",
      "email_address": "steve@honchodesign.com",
      "personable_type": "User",
      "title": "Legacy Directives Strategist",
      "bio": "You can do it!",
      "created_at": "2016-09-09T22:58:28.369Z",
      "updated_at": "2016-09-09T22:58:28.369Z",
      "admin": false,
      "owner": false,
      "time_zone": "America/Chicago",
      "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBE4qCjw=--b544b6a710bd76020abc076fc041895954025116/avatar-64-x4",
      "company": {
        "id": 1033447817,
        "name": "Honcho Design"
      }
    }
  ]
}
```
<!-- END GET /buckets/1/schedule_entries/2.json -->

Recurring schedule entries will include an additional `recurrence_schedule` attribute. For example:

```json
"recurrence_schedule": {
    "frequency": "every_month",
    "days": [
        1
    ],
    "hour": 10,
    "minute": 30,
    "week_instance": 3,
    "start_date": "2019-02-18",
    "end_date": "2019-10-25"
}
```

###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/schedule_entries/2.json
```


Create a schedule entry
-----------------------

* `POST /buckets/1/schedules/3/entries.json` creates a schedule entry in the project with ID `1` and under the schedule with an ID of `3`.

**Required parameters**:

* `summary` - what this schedule entry is about
* `starts_at` - date-time (ISO 8601) for when this schedule entry begins
* `ends_at` - date-time (ISO 8601) for when this schedule entry ends

_Optional parameters_:

* `description` - containing more information about the schedule entry. See our [Rich text guide][rich] for what HTML tags allowed.
* `participant_ids` - an array of people IDs that will participate in this entry. Please see the [Get people][people] endpoints to retrieve them.
* `all_day` - when set to `true`, the schedule entry will not have a specific start or end time, and instead will be held for the entire day or days denoted in `starts_at` and `ends_at`
* `notify` - when set to `true`, will notify the participants about the entry

This endpoint will return `201 Created` with the current JSON representation of the schedule entry if the creation was a success. See the [Get a schedule entry](#get-a-schedule-entry) endpoint for more info on the payload.

###### Example JSON Request

``` json
{
  "summary": "Important Meeting",
  "starts_at": "2015-06-04T00:00:00Z",
  "ends_at": "2015-06-04T02:00:00Z"
}
```

###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -H "Content-Type: application/json" \
  -d '{"summary":"Important Meeting","starts_at":"2015-06-04T00:00:00Z","ends_at":"2015-06-04T00:00:00Z"}' \
  https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/schedules/3/entries.json
```


Update a schedule entry
-----------------------

* `PUT /buckets/1/schedule_entries/2.json` allows changing of the schedule entry with an ID of `2` in the project with ID `1`.

Clients may change any of the required or optional parameters as listed in the [Create a schedule entry](#create-a-schedule-entry) endpoint.

This endpoint will return `200 OK` with the current JSON representation of the schedule entry if the update was a success. See the [Get a schedule entry](#get-a-schedule-entry) endpoint for more info on the payload.

###### Example JSON Request

``` json
{
  "summary": "All Day Meeting",
  "starts_at": "2015-06-04",
  "ends_at": "2015-06-04",
  "all_day": true
}
```

###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -H "Content-Type: application/json" \
  -d '{"summary":"All Day Meeting","starts_at":"2015-06-04","ends_at":"2015-06-04","all_day":true}' -X PUT \
  https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/schedule_entries/2.json
```


[trash]: https://github.com/basecamp/bc3-api/blob/master/sections/recordings.md#trash-a-recording
[pagination]: https://github.com/basecamp/bc3-api/blob/master/README.md#pagination
[schedule]: https://github.com/basecamp/bc3-api/blob/master/sections/schedules.md#get-schedule
[rich]: https://github.com/basecamp/bc3-api/blob/master/sections/rich_text.md
[people]: https://github.com/basecamp/bc3-api/blob/master/sections/people.md#people
