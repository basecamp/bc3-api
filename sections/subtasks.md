Subtasks
========

To determine if a resource accepts subtasks, check for the presence of `subtasks_count` and `subtasks_url` attributes in its JSON response — today that means [to-dos][todos] and [cards][card].

For historical reasons the wire type says `Kanban::Step` rather than `Subtask`; they are the same thing.

Endpoints:

- [Get a recording's subtasks](#get-a-recordings-subtasks)
- [Get a subtask](#get-a-subtask)
- [Create a subtask](#create-a-subtask)
- [Update a subtask](#update-a-subtask)
- [Complete a subtask](#complete-a-subtask)
- [Uncomplete a subtask](#uncomplete-a-subtask)
- [Reposition a subtask](#reposition-a-subtask)
- [Delete a subtask](#delete-a-subtask)

Get a recording's subtasks
--------------------------

* `GET /recordings/3/subtasks.json` will return a [paginated list][pagination] of the subtasks of the recording with an ID of `3`, in position order.

###### Example JSON Response
<!-- START GET /recordings/3/subtasks.json -->
```json
[
  {
    "id": 1069479877,
    "status": "active",
    "visible_to_clients": false,
    "created_at": "2026-07-02T00:23:00.000Z",
    "updated_at": "2026-07-02T00:23:00.000Z",
    "title": "Hero shot on the desk",
    "inherits_status": true,
    "type": "Kanban::Step",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958504/subtasks/1069479877.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958504/todos/1069479876#__recording_1069479877",
    "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiLmdpZDovL2JjMy9SZWNvcmRpbmcvMTA2OTQ3OTg3Nz9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg1yZWFkYWJsZQY7AFQ=--266e5283e4c42aa18671e82d04300ff0bb59db40.json",
    "position": 1,
    "parent": {
      "id": 1069479876,
      "title": "Shot list - indoor and outdoor",
      "type": "Todo",
      "url": "https://3.basecampapi.com/195539477/buckets/2085958504/todos/1069479876.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958504/todos/1069479876"
    },
    "bucket": {
      "id": 2085958504,
      "name": "The Leto Laptop",
      "type": "Project"
    },
    "creator": {
      "id": 1049715929,
      "attachable_sgid": "BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiK2dpZDovL2JjMy9QZXJzb24vMTA0OTcxNTkyOT9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg9hdHRhY2hhYmxlBjsAVA==--d79103e78a10cd9f8ecda7470ea315674ac8a79a",
      "name": "Matt Donahue",
      "personable_type": "User",
      "title": "Global Data Strategist",
      "tagline": null,
      "location": null,
      "created_at": "2026-08-12T12:01:07.949Z",
      "updated_at": "2026-08-12T12:01:07.949Z",
      "email_address": "matt@honchodesign.com",
      "bio": null,
      "admin": false,
      "owner": false,
      "client": false,
      "employee": false,
      "time_zone": "America/Chicago",
      "avatar_url": "https://3.basecampapi.com/195539477/people/BAhpBNlkkT4=--0f3c77d8c13069d514fd3f0ad694a67e426bad0f/avatar",
      "can_ping": true,
      "can_manage_projects": true,
      "can_manage_people": true,
      "can_access_timesheet": true,
      "can_access_hill_charts": true
    },
    "completed": false,
    "due_on": null,
    "assignees": [],
    "completion_url": "https://3.basecampapi.com/195539477/subtasks/1069479877/completion.json"
  }
]
```
<!-- END GET /recordings/3/subtasks.json -->
###### Copy as cURL

```shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/recordings/3/subtasks.json
```


Get a subtask
-------------

* `GET /subtasks/2.json` will return the subtask with an ID of `2`.

###### Example JSON Response
<!-- START GET /subtasks/2.json -->
```json
{
  "id": 1069479879,
  "status": "active",
  "visible_to_clients": false,
  "created_at": "2026-07-02T02:18:00.000Z",
  "updated_at": "2026-07-02T02:18:00.000Z",
  "title": "Outdoors, natural light",
  "inherits_status": true,
  "type": "Kanban::Step",
  "url": "https://3.basecampapi.com/195539477/buckets/2085958504/subtasks/1069479879.json",
  "app_url": "https://3.basecamp.com/195539477/buckets/2085958504/todos/1069479876#__recording_1069479879",
  "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiLmdpZDovL2JjMy9SZWNvcmRpbmcvMTA2OTQ3OTg3OT9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg1yZWFkYWJsZQY7AFQ=--5b8a6fa77957d7d7efbdfb7e0e301a6ca5b61787.json",
  "position": 3,
  "parent": {
    "id": 1069479876,
    "title": "Shot list - indoor and outdoor",
    "type": "Todo",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958504/todos/1069479876.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958504/todos/1069479876"
  },
  "bucket": {
    "id": 2085958504,
    "name": "The Leto Laptop",
    "type": "Project"
  },
  "creator": {
    "id": 1049715929,
    "attachable_sgid": "BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiK2dpZDovL2JjMy9QZXJzb24vMTA0OTcxNTkyOT9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg9hdHRhY2hhYmxlBjsAVA==--d79103e78a10cd9f8ecda7470ea315674ac8a79a",
    "name": "Matt Donahue",
    "personable_type": "User",
    "title": "Global Data Strategist",
    "tagline": null,
    "location": null,
    "created_at": "2026-08-12T12:01:07.949Z",
    "updated_at": "2026-08-12T12:01:07.949Z",
    "email_address": "matt@honchodesign.com",
    "bio": null,
    "admin": false,
    "owner": false,
    "client": false,
    "employee": false,
    "time_zone": "America/Chicago",
    "avatar_url": "https://3.basecampapi.com/195539477/people/BAhpBNlkkT4=--0f3c77d8c13069d514fd3f0ad694a67e426bad0f/avatar",
    "can_ping": true,
    "can_manage_projects": true,
    "can_manage_people": true,
    "can_access_timesheet": true,
    "can_access_hill_charts": true
  },
  "completed": false,
  "due_on": null,
  "assignees": [
    {
      "id": 1049715938,
      "attachable_sgid": "BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiK2dpZDovL2JjMy9QZXJzb24vMTA0OTcxNTkzOD9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg9hdHRhY2hhYmxlBjsAVA==--4ccc567a0a3b10e354bca909b704637b601f0b16",
      "name": "Annie Bryan",
      "personable_type": "User",
      "title": "Central Markets Manager",
      "tagline": "To open a store is easy, to keep it open is an art",
      "location": null,
      "created_at": "2026-08-12T12:01:09.160Z",
      "updated_at": "2026-08-12T12:01:09.160Z",
      "email_address": "annie@honchodesign.com",
      "bio": "To open a store is easy, to keep it open is an art",
      "admin": false,
      "owner": false,
      "client": false,
      "employee": true,
      "time_zone": "America/Chicago",
      "avatar_url": "https://3.basecampapi.com/195539477/people/BAhpBOJkkT4=--732a71fbd28ec10d9bf4466abd3588a8bea40bdb/avatar",
      "company": {
        "id": 1033447817,
        "name": "Honcho Design"
      },
      "can_ping": true,
      "can_manage_projects": true,
      "can_manage_people": true,
      "can_access_timesheet": true,
      "can_access_hill_charts": true
    }
  ],
  "completion_url": "https://3.basecampapi.com/195539477/subtasks/1069479879/completion.json"
}
```
<!-- END GET /subtasks/2.json -->
###### Copy as cURL

```shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/subtasks/2.json
```


Create a subtask
----------------

* `POST /recordings/3/subtasks.json` creates a subtask under the recording with an ID of `3`. Only [to-dos][todos] and [cards][card] accept subtasks; other recordings will return `403 Forbidden`.

**Required parameters**: `title` of the subtask.

_Optional parameters_:

* `due_on` - due date (ISO 8601) of the subtask.
* `assignee_ids` - an array of people ids that will be assigned to this subtask. Please see the [Get people][people] endpoints to retrieve them.

This endpoint will return `201 Created` with the current JSON representation of the subtask if the creation was a success. See [Get a subtask](#get-a-subtask) for more info on the payload.

###### Example JSON Request

```json
{
  "title": "Book the room",
  "due_on": "2021-01-01",
  "assignee_ids": [30068628, 270913789]
}
```

###### Copy as cURL

```shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -H "Content-Type: application/json" \
  -d '{"title": "Book the room", "due_on": "2021-01-01", "assignee_ids": [30068628, 270913789]}' \
  https://3.basecampapi.com/$ACCOUNT_ID/recordings/3/subtasks.json
```


Update a subtask
----------------

* `PUT /subtasks/2.json` allows changing of the subtask with an ID of `2`.

_Optional parameters_:

* `title` - of the subtask.
* `due_on` - due date (ISO 8601) of the subtask.
* `assignee_ids` - an array of people ids that will be assigned to this subtask. Please see the [Get people][people] endpoints to retrieve them.

**Note:** this is a partial update — any parameter you omit is left unchanged. To clear a value, send it explicitly:

| To…                     | Send                 |
| ----------------------- | -------------------- |
| leave a value unchanged | omit the parameter   |
| clear the due date      | `"due_on": null`     |
| remove all assignees    | `"assignee_ids": []` |

This endpoint will return `200 OK` with the current JSON representation of the subtask if the update was a success. See [Get a subtask](#get-a-subtask) for more info on the payload.

###### Example JSON Request

```json
{
  "title": "Book the big room",
  "due_on": "2021-01-01",
  "assignee_ids": [30068628, 270913789]
}
```

###### Copy as cURL

```shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -H "Content-Type: application/json" \
  -d '{"title": "Book the big room", "due_on": "2021-01-01", "assignee_ids": [30068628, 270913789]}' -X PUT \
  https://3.basecampapi.com/$ACCOUNT_ID/subtasks/2.json
```


Complete a subtask
------------------

* `POST /subtasks/2/completion.json` will mark the subtask with an ID of `2` as completed.

This endpoint will return `204 No Content` if successful. No parameters are required.

###### Copy as cURL

```shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -H "Content-Type: application/json" -X POST \
  https://3.basecampapi.com/$ACCOUNT_ID/subtasks/2/completion.json
```


Uncomplete a subtask
--------------------

* `DELETE /subtasks/2/completion.json` will mark the subtask with an ID of `2` as uncompleted.

This endpoint will return `204 No Content` if successful. No parameters are required.

###### Copy as cURL

```shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -H "Content-Type: application/json" -X DELETE \
  https://3.basecampapi.com/$ACCOUNT_ID/subtasks/2/completion.json
```


Reposition a subtask
--------------------

* `PUT /subtasks/2/position.json` moves the subtask with an ID of `2` to a new position among its siblings.

**Required parameters**:

* `position` – the 1-based position to move it to.

This endpoint will return `204 No Content` if successful.

###### Example JSON Request

```json
{
  "position": 4
}
```

###### Copy as cURL

```shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -H "Content-Type: application/json" \
  -d '{"position": 4}' -X PUT \
  https://3.basecampapi.com/$ACCOUNT_ID/subtasks/2/position.json
```


Delete a subtask
----------------

* `DELETE /subtasks/2.json` will delete the subtask with an ID of `2`.

No parameters required. Returns `204 No Content` if successful. On accounts where deleting is limited to admins and the subtask's creator, everyone else gets a `403 Forbidden`.

###### Copy as cURL

```shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -X DELETE \
  https://3.basecampapi.com/$ACCOUNT_ID/subtasks/2.json
```


[card]:   card_table_cards.md#get-a-card
[pagination]: ../README.md#pagination
[people]: people.md#get-all-people
[todos]:  todos.md#get-a-to-do
