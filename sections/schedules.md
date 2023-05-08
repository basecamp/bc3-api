Schedules
=========

All schedule entries under a project are children of a schedule resource.

Endpoints:

- [Get schedule](#get-schedule)
- [Update a schedule](#update-a-schedule)


Get schedule
------------

* `GET /buckets/1/schedules/2.json` will return the schedule for the project with an ID of `1`.

To get the schedule ID for a project, see the [Get a project][1] endpoint's `dock` payload. To retrieve its schedule entries lists, see the [Get schedule entries][2] endpoint.

###### Example JSON Response
<!-- START GET /buckets/1/schedules/2.json -->
```json
{
  "id": 1069479342,
  "status": "active",
  "visible_to_clients": false,
  "created_at": "2022-11-22T08:23:58.237Z",
  "updated_at": "2022-11-22T08:25:04.318Z",
  "title": "Schedule",
  "inherits_status": true,
  "type": "Schedule",
  "url": "https://3.basecampapi.com/195539477/buckets/2085958499/schedules/1069479342.json",
  "app_url": "https://3.basecamp.com/195539477/buckets/2085958499/schedules/1069479342",
  "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7CEkiCGdpZAY6BkVUSSIuZ2lkOi8vYmMzL1JlY29yZGluZy8xMDY5NDc5MzQyP2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg1yZWFkYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--c25a35abffcd11650599ed79c2b7aa7b62c72a60.json",
  "position": 5,
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
  "includes_due_dates": true,
  "entries_count": 1,
  "entries_url": "https://3.basecampapi.com/195539477/buckets/2085958499/schedules/1069479342/entries.json"
}
```
<!-- END GET /buckets/1/schedules/2.json -->
###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/schedules/2.json
```

Update a schedule
-----------------------

* `PUT /buckets/1/schedules/2.json` allows changing of the schedule with an ID of `2` in the project with ID `1`.

**Required parameters**:

* `includes_due_dates` - whether the schedule should include due dates from to-dos, cards and steps.

This endpoint will return `200 OK` with the current JSON representation of the schedule if the update was a success.

###### Example JSON Request

``` json
{
  "includes_due_dates": "false"
}
```

###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -H "Content-Type: application/json" \
  -d '{"schedule": {"includes_due_dates": "false"}}' -X PUT \
  https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/schedules/2.json
```


[1]: https://github.com/basecamp/bc3-api/blob/master/sections/projects.md#get-a-project
[2]: https://github.com/basecamp/bc3-api/blob/master/sections/schedule_entries.md#get-schedule-entries
[3]: https://github.com/basecamp/bc3-api/blob/master/sections/recordings.md#trash-a-recording
