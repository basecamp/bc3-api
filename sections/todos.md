To-dos
======

Endpoints:

- [Get to-dos](#get-to-dos)
- [Get a to-do](#get-a-to-do)
- [Create a to-do](#create-a-to-do)
- [Update a to-do](#update-a-to-do)
- [Complete a to-do](#complete-a-to-do)
- [Uncomplete a to-do](#uncomplete-a-to-do)
- [Reposition a to-do](#reposition-a-to-do)
- [Trash a to-do][1]

Get to-dos
----------

* `GET /buckets/1/todolists/3/todos.json` will return a [paginated list][2] of active to-dos in the project with an ID of `1` and the to-do list with ID of `3`.

_Optional query parameters_:

This endpoint without any parameters returns only active, pending (i.e. not completed) to-dos. 

* `status` - when set to `archived` or `trashed`, will return archived or trashed to-dos that are in this list, including both pending and completed.
* `completed` - when set to `true`, will only return to-dos that are completed. Can be combined with the `status` parameter.

###### Example JSON Response
<!-- START GET /buckets/1/todolists/3/todos.json -->
```json
[
  {
    "id": 1069479574,
    "status": "active",
    "visible_to_clients": false,
    "created_at": "2026-01-15T06:18:00.000Z",
    "updated_at": "2026-01-15T06:18:00.000Z",
    "title": "Go cutting edge: iOS8 and Android 4.5 only",
    "inherits_status": true,
    "type": "Todo",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958504/todos/1069479574.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958504/todos/1069479574",
    "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiLmdpZDovL2JjMy9SZWNvcmRpbmcvMTA2OTQ3OTU3ND9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg1yZWFkYWJsZQY7AFQ=--902c7ca4798684fca5b9fe7621a760f4a0d432cd.json",
    "subscription_url": "https://3.basecampapi.com/195539477/buckets/2085958504/recordings/1069479574/subscription.json",
    "comments_count": 0,
    "comments_url": "https://3.basecampapi.com/195539477/buckets/2085958504/recordings/1069479574/comments.json",
    "position": 1,
    "parent": {
      "id": 1069479573,
      "title": "Strategy ideas",
      "type": "Todolist",
      "url": "https://3.basecampapi.com/195539477/buckets/2085958504/todolists/1069479573.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958504/todolists/1069479573"
    },
    "bucket": {
      "id": 2085958504,
      "name": "The Leto Laptop",
      "type": "Project"
    },
    "creator": {
      "id": 1049715938,
      "attachable_sgid": "BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiK2dpZDovL2JjMy9QZXJzb24vMTA0OTcxNTkzOD9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg9hdHRhY2hhYmxlBjsAVA==--4ccc567a0a3b10e354bca909b704637b601f0b16",
      "name": "Annie Bryan",
      "email_address": "annie@honchodesign.com",
      "personable_type": "User",
      "title": "Central Markets Manager",
      "bio": "To open a store is easy, to keep it open is an art",
      "location": null,
      "created_at": "2026-01-31T08:29:42.795Z",
      "updated_at": "2026-01-31T08:29:42.795Z",
      "admin": false,
      "owner": false,
      "client": false,
      "employee": true,
      "time_zone": "America/Chicago",
      "avatar_url": "https://3.basecampapi.com/195539477/people/BAhpBOJkkT4=--732a71fbd28ec10d9bf4466abd3588a8bea40bdb/avatar?v=1",
      "company": {
        "id": 1033447817,
        "name": "Honcho Design"
      },
      "can_ping": true,
      "can_manage_projects": true,
      "can_manage_people": true,
      "can_access_timesheet": true,
      "can_access_hill_charts": true
    },
    "description": "",
    "completed": false,
    "content": "Go cutting edge: iOS8 and Android 4.5 only",
    "starts_on": null,
    "due_on": null,
    "assignees": [],
    "completion_subscribers": [],
    "completion_url": "https://3.basecampapi.com/195539477/buckets/2085958504/todos/1069479574/completion.json"
  }
]
```
<!-- END GET /buckets/1/todolists/3/todos.json -->
###### Copy as cURL

```shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/todolists/3/todos.json
```


Get a to-do
-----------

* `GET /buckets/1/todos/2.json` will return the to-do with an ID of `2` in the project with an ID of `1`.

###### Example JSON Response
<!-- START GET /buckets/1/todos/2.json -->
```json
{
  "id": 1069479576,
  "status": "active",
  "visible_to_clients": false,
  "created_at": "2026-01-15T07:20:00.000Z",
  "updated_at": "2026-02-01T02:53:46.582Z",
  "title": "Clear and simple UI",
  "inherits_status": true,
  "type": "Todo",
  "url": "https://3.basecampapi.com/195539477/buckets/2085958504/todos/1069479576.json",
  "app_url": "https://3.basecamp.com/195539477/buckets/2085958504/todos/1069479576",
  "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiLmdpZDovL2JjMy9SZWNvcmRpbmcvMTA2OTQ3OTU3Nj9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg1yZWFkYWJsZQY7AFQ=--11a40c121978ed499b97e8c9ed0d3bfc8632df41.json",
  "subscription_url": "https://3.basecampapi.com/195539477/buckets/2085958504/recordings/1069479576/subscription.json",
  "comments_count": 0,
  "comments_url": "https://3.basecampapi.com/195539477/buckets/2085958504/recordings/1069479576/comments.json",
  "parent": {
    "id": 1069479573,
    "title": "Strategy ideas",
    "type": "Todolist",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958504/todolists/1069479573.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958504/todolists/1069479573"
  },
  "bucket": {
    "id": 2085958504,
    "name": "The Leto Laptop",
    "type": "Project"
  },
  "creator": {
    "id": 1049715938,
    "attachable_sgid": "BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiK2dpZDovL2JjMy9QZXJzb24vMTA0OTcxNTkzOD9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg9hdHRhY2hhYmxlBjsAVA==--4ccc567a0a3b10e354bca909b704637b601f0b16",
    "name": "Annie Bryan",
    "email_address": "annie@honchodesign.com",
    "personable_type": "User",
    "title": "Central Markets Manager",
    "bio": "To open a store is easy, to keep it open is an art",
    "location": null,
    "created_at": "2026-01-31T08:29:42.795Z",
    "updated_at": "2026-01-31T08:29:42.795Z",
    "admin": false,
    "owner": false,
    "client": false,
    "employee": true,
    "time_zone": "America/Chicago",
    "avatar_url": "https://3.basecampapi.com/195539477/people/BAhpBOJkkT4=--732a71fbd28ec10d9bf4466abd3588a8bea40bdb/avatar?v=1",
    "company": {
      "id": 1033447817,
      "name": "Honcho Design"
    },
    "can_ping": true,
    "can_manage_projects": true,
    "can_manage_people": true,
    "can_access_timesheet": true,
    "can_access_hill_charts": true
  },
  "description": "",
  "completed": true,
  "completion": {
    "created_at": "2026-02-01T02:53:46.523Z",
    "creator": {
      "id": 1049715930,
      "attachable_sgid": "BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiK2dpZDovL2JjMy9QZXJzb24vMTA0OTcxNTkzMD9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg9hdHRhY2hhYmxlBjsAVA==--322099b137f9e0b6bc944b5b9fe7a2692da94814",
      "name": "Sharon Bradford",
      "email_address": "sharon@honchodesign.com",
      "personable_type": "User",
      "title": "Principal Branding Administrator",
      "bio": null,
      "location": null,
      "created_at": "2026-01-31T08:29:40.859Z",
      "updated_at": "2026-01-31T08:29:40.859Z",
      "admin": false,
      "owner": false,
      "client": false,
      "employee": false,
      "time_zone": "America/Chicago",
      "avatar_url": "https://3.basecampapi.com/195539477/people/BAhpBNpkkT4=--789594e5e542ab99e467a51c9dec0a9035abc0e0/avatar?v=1",
      "can_ping": true,
      "can_manage_projects": true,
      "can_manage_people": true,
      "can_access_timesheet": true,
      "can_access_hill_charts": true
    }
  },
  "content": "Clear and simple UI",
  "starts_on": null,
  "due_on": null,
  "assignees": [
    {
      "id": 1049715930,
      "attachable_sgid": "BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiK2dpZDovL2JjMy9QZXJzb24vMTA0OTcxNTkzMD9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg9hdHRhY2hhYmxlBjsAVA==--322099b137f9e0b6bc944b5b9fe7a2692da94814",
      "name": "Sharon Bradford",
      "email_address": "sharon@honchodesign.com",
      "personable_type": "User",
      "title": "Principal Branding Administrator",
      "bio": null,
      "location": null,
      "created_at": "2026-01-31T08:29:40.859Z",
      "updated_at": "2026-01-31T08:29:40.859Z",
      "admin": false,
      "owner": false,
      "client": false,
      "employee": false,
      "time_zone": "America/Chicago",
      "avatar_url": "https://3.basecampapi.com/195539477/people/BAhpBNpkkT4=--789594e5e542ab99e467a51c9dec0a9035abc0e0/avatar?v=1",
      "can_ping": true,
      "can_manage_projects": true,
      "can_manage_people": true,
      "can_access_timesheet": true,
      "can_access_hill_charts": true
    }
  ],
  "completion_subscribers": [
    {
      "id": 1049715930,
      "attachable_sgid": "BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiK2dpZDovL2JjMy9QZXJzb24vMTA0OTcxNTkzMD9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg9hdHRhY2hhYmxlBjsAVA==--322099b137f9e0b6bc944b5b9fe7a2692da94814",
      "name": "Sharon Bradford",
      "email_address": "sharon@honchodesign.com",
      "personable_type": "User",
      "title": "Principal Branding Administrator",
      "bio": null,
      "location": null,
      "created_at": "2026-01-31T08:29:40.859Z",
      "updated_at": "2026-01-31T08:29:40.859Z",
      "admin": false,
      "owner": false,
      "client": false,
      "employee": false,
      "time_zone": "America/Chicago",
      "avatar_url": "https://3.basecampapi.com/195539477/people/BAhpBNpkkT4=--789594e5e542ab99e467a51c9dec0a9035abc0e0/avatar?v=1",
      "can_ping": true,
      "can_manage_projects": true,
      "can_manage_people": true,
      "can_access_timesheet": true,
      "can_access_hill_charts": true
    }
  ],
  "completion_url": "https://3.basecampapi.com/195539477/buckets/2085958504/todos/1069479576/completion.json"
}
```
<!-- END GET /buckets/1/todos/2.json -->
###### Copy as cURL

```shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/todos/2.json
```


Create a to-do
--------------

* `POST /buckets/1/todolists/3/todos.json` creates a to-do in the project with ID `1` and under the to-do list with an ID of `3`.

**Required parameters**: `content` for what the to-do is for.

_Optional parameters_:

* `description` - containing information about the to-do. See our [Rich text guide][3] for what HTML tags allowed.
* `assignee_ids` - an array of people that will be assigned to this to-do. Please see the [Get people][4] endpoints to retrieve them.
* `completion_subscriber_ids` - an array of people that will be notified on to-do completion. Please see the [Get people][4] endpoints to retrieve them.
* `notify` - when set to `true`, will notify the assignees about being assigned.
* `due_on` - a date when the to-do should be completed.
* `starts_on` - allows the to-do to run from this date to the `due_on` date.

This endpoint will return `201 Created` with the current JSON representation of the to-do if the creation was a success. See the [Get a to-do](#get-a-to-do) endpoint for more info on the payload.

###### Example JSON Request

```json
{
  "content": "Program it",
  "description": "<div><em>Try that new language!</em></div>",
  "due_on": "2016-05-01"
}
```

###### Copy as cURL

```shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -H "Content-Type: application/json" \
  -d '{"content":"Program it","description":"<div><em>Try that new language!</em></div>","due_on":"2016-05-01"}' \
  https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/todolists/3/todos.json
```


Update a to-do
--------------

* `PUT /buckets/1/todos/2.json` allows changing the to-do with an ID of `2` in the project with ID `1`.

This endpoint will return `200 OK` with the current JSON representation of the to-do if the update was a success. See the [Get a to-do](#get-a-to-do) endpoint for more info on the payload.

**Required parameters**: Pass _all existing parameters_ in addition to those being updated. Omitting a parameter will clear its value, for example, empty/missing `assignee_ids` clears existing assignees.
* `content` for what the to-do is for. This one is always required, it can't be omitted as it can't be blank.
* `description` - containing information about the to-do. See our [Rich text guide][3] for what HTML tags allowed.
* `assignee_ids` - an array of people that will be assigned to this to-do. Please see the [Get people][4] endpoints to retrieve them.
* `completion_subscriber_ids` - an array of people that will be notified on to-do completion. Please see the [Get people][4] endpoints to retrieve them. 
* `notify` - when set to `true`, will notify the assignees about being assigned.
* `due_on` - a date when the to-do should be completed.
* `starts_on` - allows the to-do to run from this date to the `due_on` date.

For example, to update the to-do's `content` from [Create a to-do](#create-a-todo):

###### Example JSON Request

```json
{
  "content": "Only changing content! Passing the rest to preserve them.",
  "description": "<div><em>Try that new language!</em></div>",
  "due_on": "2016-05-01"
}
```

###### Copy as cURL

```shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -H "Content-Type: application/json" \
  -d '{"content":"Only changing content! Passing the rest to preserve them.","description":"<div><em>Try that new language!</em></div>","due_on":"2016-05-01"}' -X PUT \
  https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/todos/2.json
```


Complete a to-do
----------------

* `POST /buckets/1/todos/2/completion.json` will mark the to-do with an ID of `2` in the project with ID `1` as completed.

This endpoint will return `204 No Content` if successful. No parameters are required.

###### Copy as cURL

```shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -H "Content-Type: application/json" -X POST \
  https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/todos/2/completion.json
```


Uncomplete a to-do
------------------

* `DELETE /buckets/1/todos/2/completion.json` will mark the to-do with an ID of `2` in the project with ID `1` as uncompleted.

This endpoint will return `204 No Content` if successful. No parameters are required.

###### Copy as cURL

```shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -H "Content-Type: application/json" -X DELETE \
  https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/todos/2/completion.json
```


Reposition a to-do
------------------

* `PUT /buckets/1/todos/2/position.json` allows changing the position of the to-do with an ID of `2` in the project with ID `1`.

**Required parameters**: `position` greater than or equal to one.

_Optional parameters_:

* `parent_id` - the ID of a to-do list to move this to-do into. When provided, the to-do will be repositioned within the specified to-do list instead of its current parent.

This endpoint will return `204 No Content` if the update was a success.

###### Example JSON Request

```json
{
  "position": 3
}
```

To move a to-do to a different to-do list and set its position:

```json
{
  "position": 1,
  "parent_id": 5
}
```

###### Copy as cURL

```shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -H "Content-Type: application/json" \
  -d '{"position":3}' -X PUT \
  https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/todos/2/position.json
```


[1]: https://github.com/basecamp/bc3-api/blob/master/sections/recordings.md#trash-a-recording
[2]: https://github.com/basecamp/bc3-api/blob/master/README.md#pagination
[3]: https://github.com/basecamp/bc3-api/blob/master/sections/rich_text.md
[4]: https://github.com/basecamp/bc3-api/blob/master/sections/people.md#get-all-people
