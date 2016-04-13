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

* `GET /buckets/1/schedules/3/entries.json` will return a [paginated list][pagination] of active schedule entries in the Basecamp with an ID of `1` and the schedule with ID of `3`.

To get the schedule ID for a Basecamp, see the [Get schedule][schedule] endpoint.

_Optional query parameters_:

* `status` - when set to `archived` or `trashed`, will return archived or trashed schedule entries that are in this schedule.

###### Example JSON Response

``` json
[
  {
    "id": 9007199254741764,
    "created_at": "2016-04-13T04:36:14.917-05:00",
    "updated_at": "2016-04-13T04:36:17.610-05:00",
    "summary": "Meeting",
    "description_html": "<div>Let's talk about stuff!</div>",
    "description_text": "Let's talk about stuff!",
    "starts_at": "2016-04-13T09:30:00.000Z",
    "ends_at": "2016-04-13T10:00:00.000Z",
    "all_day": false,
    "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7CEkiCGdpZAY6BkVUSSI0Z2lkOi8vYmMzL1JlY29yZGluZy85MDA3MTk5MjU0NzQxNzY0P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg1yZWFkYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--ee6896a897ae0079b5949557ef4dd6315600af32",
    "subscription_url": "https://3.basecampapi.com/195539477/buckets/2085958495/recordings/9007199254741764/subscription",
    "participants": [
      {
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
      }
    ],
    "status": "active",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958495/schedule_entries/9007199254741764",
    "type": "Schedule::Entry",
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
    "bucket_path": "/195539477/buckets/2085958495",
    "parent": {
      "id": 9007199254741016,
      "title": "Schedule",
      "url": "https://3.basecampapi.com/195539477/buckets/2085958495/schedules/9007199254741015"
    }
  },
  ...
]
```

###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/schedules/3/entries.json
```


Get a schedule entry
--------------------

* `GET /buckets/1/schedule_entries/2.json` will return the schedule entry with an ID of `2` in the Basecamp with an ID of `1`.

Note: Nesting under the schedule resource is not necessary for this endpoint.

###### Example JSON Response

``` json
{
  "id": 9007199254741764,
  "created_at": "2016-04-13T04:36:14.917-05:00",
  "updated_at": "2016-04-13T04:36:17.610-05:00",
  "summary": "Meeting",
  "description_html": "<div>Let's talk about stuff!</div>",
  "description_text": "Let's talk about stuff!",
  "starts_at": "2016-04-13T09:30:00.000Z",
  "ends_at": "2016-04-13T10:00:00.000Z",
  "all_day": false,
  "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7CEkiCGdpZAY6BkVUSSI0Z2lkOi8vYmMzL1JlY29yZGluZy85MDA3MTk5MjU0NzQxNzY0P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg1yZWFkYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--ee6896a897ae0079b5949557ef4dd6315600af32",
  "subscription_url": "https://3.basecampapi.com/195539477/buckets/2085958495/recordings/9007199254741764/subscription",
  "participants": [
    {
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
    }
  ],
  "status": "active",
  "url": "https://3.basecampapi.com/195539477/buckets/2085958495/schedule_entries/9007199254741764",
  "type": "Schedule::Entry",
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
  "bucket_path": "/195539477/buckets/2085958495",
  "parent": {
    "id": 9007199254741016,
    "title": "Schedule",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958495/schedules/9007199254741015"
  }
}
```

###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/schedule_entries/2.json
```


Create a schedule entry
-----------------------

* `POST /buckets/1/schedules/3/entries.json` creates a schedule entry in the Basecamp with ID `1` and under the schedule with an ID of `3`.

**Required parameters**:

* `summary` - what this schedule entry is about
* `starts_at` - timestamp for when this schedule entry begins
* `ends_at` - timestamp for when this schedule entry ends

_Optional parameters_:

* `description_html` - containing more information about the schedule entry. See our [Rich content][rich] guide for what HTML tags allowed.
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

* `PUT /buckets/1/schedule_entries/2.json` allows changing of the schedule entry with an ID of `2` in the Basecamp with ID `1`.

Nesting under the schedule resource is not necessary for this endpoint. Clients may change any of the required or optional parameters as listed in the [Create a schedule entry](#create-a-schedule-entry) endpoint.

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
[rich]: https://github.com/basecamp/bc3-api/blob/master/README.md#rich-content
[people]: https://github.com/basecamp/bc3-api/blob/master/sections/people.md#people
