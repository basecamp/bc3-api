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
    "id": 1069479847,
    "status": "active",
    "visible_to_clients": false,
    "created_at": "2022-11-22T08:25:04.190Z",
    "updated_at": "2022-11-22T08:25:04.316Z",
    "title": "Team Meeting",
    "inherits_status": true,
    "type": "Schedule::Entry",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958499/schedule_entries/1069479847.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958499/schedule_entries/1069479847",
    "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7CEkiCGdpZAY6BkVUSSIuZ2lkOi8vYmMzL1JlY29yZGluZy8xMDY5NDc5ODQ3P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg1yZWFkYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--1c0cc0c23c279ac645718b2ea9912d5513075d97.json",
    "subscription_url": "https://3.basecampapi.com/195539477/buckets/2085958499/recordings/1069479847/subscription.json",
    "comments_count": 0,
    "comments_url": "https://3.basecampapi.com/195539477/buckets/2085958499/recordings/1069479847/comments.json",
    "parent": {
      "id": 1069479342,
      "title": "Schedule",
      "type": "Schedule",
      "url": "https://3.basecampapi.com/195539477/buckets/2085958499/schedules/1069479342.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958499/schedules/1069479342"
    },
    "bucket": {
      "id": 2085958499,
      "name": "The Leto Laptop",
      "type": "Project"
    },
    "creator": {
      "id": 1049715914,
      "attachable_sgid": "BAh7CEkiCGdpZAY6BkVUSSIrZ2lkOi8vYmMzL1BlcnNvbi8xMDQ5NzE1OTE0P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg9hdHRhY2hhYmxlBjsAVEkiD2V4cGlyZXNfYXQGOwBUMA==--ff006accb6e013cca785190fa38f42c091d24f1e",
      "name": "Victor Cooper",
      "email_address": "victor@honchodesign.com",
      "personable_type": "User",
      "title": "Chief Strategist",
      "bio": "Don’t let your dreams be dreams",
      "location": "Chicago, IL",
      "created_at": "2022-11-22T08:23:21.732Z",
      "updated_at": "2022-11-22T08:23:21.904Z",
      "admin": true,
      "owner": true,
      "client": false,
      "employee": true,
      "time_zone": "America/Chicago",
      "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBMpkkT4=--5520caeec1845b5090bbfc993ffe8eca8d138e14/avatar?v=1",
      "company": {
        "id": 1033447817,
        "name": "Honcho Design"
      },
      "can_manage_projects": true,
      "can_manage_people": true
    },
    "description": "<div>Time to synergize!</div>",
    "summary": "Team Meeting",
    "all_day": false,
    "starts_at": "2022-11-23T10:25:04.177Z",
    "ends_at": "2022-11-23T14:25:04.177Z",
    "participants": [
      {
        "id": 1049715921,
        "attachable_sgid": "BAh7CEkiCGdpZAY6BkVUSSIrZ2lkOi8vYmMzL1BlcnNvbi8xMDQ5NzE1OTIxP2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg9hdHRhY2hhYmxlBjsAVEkiD2V4cGlyZXNfYXQGOwBUMA==--61b488a9fa97d2e628aee86cf51a4ba0171888c2",
        "name": "Steve Marsh",
        "email_address": "steve@honchodesign.com",
        "personable_type": "User",
        "title": "Legacy Directives Strategist",
        "bio": "You can do it!",
        "location": null,
        "created_at": "2022-11-22T08:23:21.991Z",
        "updated_at": "2022-11-22T08:23:21.991Z",
        "admin": false,
        "owner": false,
        "client": false,
        "employee": true,
        "time_zone": "Etc/UTC",
        "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBNFkkT4=--c57bba9b44447be39d4a79a5e7f2a592cae9e82c/avatar?v=1",
        "company": {
          "id": 1033447817,
          "name": "Honcho Design"
        },
        "can_manage_projects": true,
        "can_manage_people": true
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
  "id": 1069479847,
  "status": "active",
  "visible_to_clients": false,
  "created_at": "2022-11-22T08:25:04.190Z",
  "updated_at": "2022-11-22T08:25:04.316Z",
  "title": "Team Meeting",
  "inherits_status": true,
  "type": "Schedule::Entry",
  "url": "https://3.basecampapi.com/195539477/buckets/2085958499/schedule_entries/1069479847.json",
  "app_url": "https://3.basecamp.com/195539477/buckets/2085958499/schedule_entries/1069479847",
  "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7CEkiCGdpZAY6BkVUSSIuZ2lkOi8vYmMzL1JlY29yZGluZy8xMDY5NDc5ODQ3P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg1yZWFkYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--1c0cc0c23c279ac645718b2ea9912d5513075d97.json",
  "subscription_url": "https://3.basecampapi.com/195539477/buckets/2085958499/recordings/1069479847/subscription.json",
  "comments_count": 0,
  "comments_url": "https://3.basecampapi.com/195539477/buckets/2085958499/recordings/1069479847/comments.json",
  "parent": {
    "id": 1069479342,
    "title": "Schedule",
    "type": "Schedule",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958499/schedules/1069479342.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958499/schedules/1069479342"
  },
  "bucket": {
    "id": 2085958499,
    "name": "The Leto Laptop",
    "type": "Project"
  },
  "creator": {
    "id": 1049715914,
    "attachable_sgid": "BAh7CEkiCGdpZAY6BkVUSSIrZ2lkOi8vYmMzL1BlcnNvbi8xMDQ5NzE1OTE0P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg9hdHRhY2hhYmxlBjsAVEkiD2V4cGlyZXNfYXQGOwBUMA==--ff006accb6e013cca785190fa38f42c091d24f1e",
    "name": "Victor Cooper",
    "email_address": "victor@honchodesign.com",
    "personable_type": "User",
    "title": "Chief Strategist",
    "bio": "Don’t let your dreams be dreams",
    "location": "Chicago, IL",
    "created_at": "2022-11-22T08:23:21.732Z",
    "updated_at": "2022-11-22T08:23:21.904Z",
    "admin": true,
    "owner": true,
    "client": false,
    "employee": true,
    "time_zone": "America/Chicago",
    "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBMpkkT4=--5520caeec1845b5090bbfc993ffe8eca8d138e14/avatar?v=1",
    "company": {
      "id": 1033447817,
      "name": "Honcho Design"
    },
    "can_manage_projects": true,
    "can_manage_people": true
  },
  "description": "<div>Time to synergize!</div>",
  "summary": "Team Meeting",
  "all_day": false,
  "starts_at": "2022-11-23T10:25:04.177Z",
  "ends_at": "2022-11-23T14:25:04.177Z",
  "participants": [
    {
      "id": 1049715921,
      "attachable_sgid": "BAh7CEkiCGdpZAY6BkVUSSIrZ2lkOi8vYmMzL1BlcnNvbi8xMDQ5NzE1OTIxP2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg9hdHRhY2hhYmxlBjsAVEkiD2V4cGlyZXNfYXQGOwBUMA==--61b488a9fa97d2e628aee86cf51a4ba0171888c2",
      "name": "Steve Marsh",
      "email_address": "steve@honchodesign.com",
      "personable_type": "User",
      "title": "Legacy Directives Strategist",
      "bio": "You can do it!",
      "location": null,
      "created_at": "2022-11-22T08:23:21.991Z",
      "updated_at": "2022-11-22T08:23:21.991Z",
      "admin": false,
      "owner": false,
      "client": false,
      "employee": true,
      "time_zone": "Etc/UTC",
      "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBNFkkT4=--c57bba9b44447be39d4a79a5e7f2a592cae9e82c/avatar?v=1",
      "company": {
        "id": 1033447817,
        "name": "Honcho Design"
      },
      "can_manage_projects": true,
      "can_manage_people": true
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
