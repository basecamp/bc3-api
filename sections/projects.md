Projects
=========

Endpoints:

- [Get all projects](#get-projects)
- [Get a project](#get-a-project)
- [Create a project](#create-a-project)
- [Update a project](#update-a-project)
- [Trash a project](#trash-a-project)

Get all projects
----------------

* `GET /projects.json` will return a [paginated list][pagination] of active projects visible to the current user sorted by most recently created project first.

_Optional parameters_:

* `status` - when set to `archived` or `trashed`, will return archived or trashed projects visible to the current user.

###### Example JSON Response
<!-- START GET /projects.json -->
```json
[
  {
    "id": 2085958499,
    "status": "active",
    "created_at": "2022-10-28T08:23:58.169Z",
    "updated_at": "2022-11-22T17:56:27.363Z",
    "name": "The Leto Laptop",
    "description": "Laptop product launch.",
    "purpose": "topic",
    "clients_enabled": false,
    "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7CEkiCGdpZAY6BkVUSSIrZ2lkOi8vYmMzL0J1Y2tldC8yMDg1OTU4NDk5P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg1yZWFkYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--691d627098347705738640552798539681dcd3b6.json",
    "url": "https://3.basecampapi.com/195539477/projects/2085958499.json",
    "app_url": "https://3.basecamp.com/195539477/projects/2085958499",
    "dock": [
      {
        "id": 1069479338,
        "title": "Message Board",
        "name": "message_board",
        "enabled": true,
        "position": 1,
        "url": "https://3.basecampapi.com/195539477/buckets/2085958499/message_boards/1069479338.json",
        "app_url": "https://3.basecamp.com/195539477/buckets/2085958499/message_boards/1069479338"
      },
      {
        "id": 1069479339,
        "title": "To-dos",
        "name": "todoset",
        "enabled": true,
        "position": 2,
        "url": "https://3.basecampapi.com/195539477/buckets/2085958499/todosets/1069479339.json",
        "app_url": "https://3.basecamp.com/195539477/buckets/2085958499/todosets/1069479339"
      },
      {
        "id": 1069479340,
        "title": "Docs & Files",
        "name": "vault",
        "enabled": true,
        "position": 3,
        "url": "https://3.basecampapi.com/195539477/buckets/2085958499/vaults/1069479340.json",
        "app_url": "https://3.basecamp.com/195539477/buckets/2085958499/vaults/1069479340"
      },
      {
        "id": 1069479341,
        "title": "Campfire",
        "name": "chat",
        "enabled": true,
        "position": 4,
        "url": "https://3.basecampapi.com/195539477/buckets/2085958499/chats/1069479341.json",
        "app_url": "https://3.basecamp.com/195539477/buckets/2085958499/chats/1069479341"
      },
      {
        "id": 1069479342,
        "title": "Schedule",
        "name": "schedule",
        "enabled": true,
        "position": 5,
        "url": "https://3.basecampapi.com/195539477/buckets/2085958499/schedules/1069479342.json",
        "app_url": "https://3.basecamp.com/195539477/buckets/2085958499/schedules/1069479342"
      },
      {
        "id": 1069479343,
        "title": "Automatic Check-ins",
        "name": "questionnaire",
        "enabled": false,
        "position": null,
        "url": "https://3.basecampapi.com/195539477/buckets/2085958499/questionnaires/1069479343.json",
        "app_url": "https://3.basecamp.com/195539477/buckets/2085958499/questionnaires/1069479343"
      },
      {
        "id": 1069479344,
        "title": "Email Forwards",
        "name": "inbox",
        "enabled": false,
        "position": null,
        "url": "https://3.basecampapi.com/195539477/buckets/2085958499/inboxes/1069479344.json",
        "app_url": "https://3.basecamp.com/195539477/buckets/2085958499/inboxes/1069479344"
      },
      {
        "id": 1069479345,
        "title": "Card Table",
        "name": "kanban_board",
        "enabled": false,
        "position": null,
        "url": "https://3.basecampapi.com/195539477/buckets/2085958499/card_tables/1069479345.json",
        "app_url": "https://3.basecamp.com/195539477/buckets/2085958499/card_tables/1069479345"
      }
    ],
    "bookmarked": true
  },
  {
    "id": 2085958500,
    "status": "active",
    "created_at": "2022-10-08T08:24:14.049Z",
    "updated_at": "2022-11-22T08:25:24.633Z",
    "name": "The Leto Locator",
    "description": "New software and hardware built for locating and securing Leto products.",
    "purpose": "topic",
    "clients_enabled": false,
    "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7CEkiCGdpZAY6BkVUSSIrZ2lkOi8vYmMzL0J1Y2tldC8yMDg1OTU4NTAwP2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg1yZWFkYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--3792afdce2e0fb99a38a2fcecf198313a428c478.json",
    "url": "https://3.basecampapi.com/195539477/projects/2085958500.json",
    "app_url": "https://3.basecamp.com/195539477/projects/2085958500",
    "client_company": {
      "id": 1033447818,
      "name": "Leto Brand"
    },
    "clientside": {
      "url": "https://3.basecampapi.com/195539477/buckets/2085958500/client/board.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958500/client/board"
    },
    "dock": [
      {
        "id": 1069479551,
        "title": "Message Board",
        "name": "message_board",
        "enabled": true,
        "position": 1,
        "url": "https://3.basecampapi.com/195539477/buckets/2085958500/message_boards/1069479551.json",
        "app_url": "https://3.basecamp.com/195539477/buckets/2085958500/message_boards/1069479551"
      },
      {
        "id": 1069479552,
        "title": "To-dos",
        "name": "todoset",
        "enabled": true,
        "position": 2,
        "url": "https://3.basecampapi.com/195539477/buckets/2085958500/todosets/1069479552.json",
        "app_url": "https://3.basecamp.com/195539477/buckets/2085958500/todosets/1069479552"
      },
      {
        "id": 1069479553,
        "title": "Docs & Files",
        "name": "vault",
        "enabled": true,
        "position": 3,
        "url": "https://3.basecampapi.com/195539477/buckets/2085958500/vaults/1069479553.json",
        "app_url": "https://3.basecamp.com/195539477/buckets/2085958500/vaults/1069479553"
      },
      {
        "id": 1069479554,
        "title": "Campfire",
        "name": "chat",
        "enabled": true,
        "position": 4,
        "url": "https://3.basecampapi.com/195539477/buckets/2085958500/chats/1069479554.json",
        "app_url": "https://3.basecamp.com/195539477/buckets/2085958500/chats/1069479554"
      },
      {
        "id": 1069479555,
        "title": "Schedule",
        "name": "schedule",
        "enabled": true,
        "position": 5,
        "url": "https://3.basecampapi.com/195539477/buckets/2085958500/schedules/1069479555.json",
        "app_url": "https://3.basecamp.com/195539477/buckets/2085958500/schedules/1069479555"
      },
      {
        "id": 1069479556,
        "title": "Automatic Check-ins",
        "name": "questionnaire",
        "enabled": false,
        "position": null,
        "url": "https://3.basecampapi.com/195539477/buckets/2085958500/questionnaires/1069479556.json",
        "app_url": "https://3.basecamp.com/195539477/buckets/2085958500/questionnaires/1069479556"
      },
      {
        "id": 1069479557,
        "title": "Email Forwards",
        "name": "inbox",
        "enabled": false,
        "position": null,
        "url": "https://3.basecampapi.com/195539477/buckets/2085958500/inboxes/1069479557.json",
        "app_url": "https://3.basecamp.com/195539477/buckets/2085958500/inboxes/1069479557"
      },
      {
        "id": 1069479558,
        "title": "Card Table",
        "name": "kanban_board",
        "enabled": false,
        "position": null,
        "url": "https://3.basecampapi.com/195539477/buckets/2085958500/card_tables/1069479558.json",
        "app_url": "https://3.basecamp.com/195539477/buckets/2085958500/card_tables/1069479558"
      }
    ],
    "bookmarked": true
  }
]
```
<!-- END GET /projects.json -->
###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/projects.json
```


Get a project
--------------

* `GET /projects/1.json` will return the project with the given ID, granted they have access to it.

The `dock` key contains an array of the current tools for this project. The `enabled` flag will be `true` if the tool is turned on for use. You can use the `url` parameter from each tool to jump to the resources available inside of this project.

###### Example JSON Response
<!-- START GET /projects/1.json -->
```json
{
  "id": 2085958499,
  "status": "active",
  "created_at": "2022-10-28T08:23:58.169Z",
  "updated_at": "2022-11-22T17:56:27.363Z",
  "name": "The Leto Laptop",
  "description": "Laptop product launch.",
  "purpose": "topic",
  "clients_enabled": false,
  "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7CEkiCGdpZAY6BkVUSSIrZ2lkOi8vYmMzL0J1Y2tldC8yMDg1OTU4NDk5P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg1yZWFkYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--691d627098347705738640552798539681dcd3b6.json",
  "url": "https://3.basecampapi.com/195539477/projects/2085958499.json",
  "app_url": "https://3.basecamp.com/195539477/projects/2085958499",
  "dock": [
    {
      "id": 1069479338,
      "title": "Message Board",
      "name": "message_board",
      "enabled": true,
      "position": 1,
      "url": "https://3.basecampapi.com/195539477/buckets/2085958499/message_boards/1069479338.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958499/message_boards/1069479338"
    },
    {
      "id": 1069479339,
      "title": "To-dos",
      "name": "todoset",
      "enabled": true,
      "position": 2,
      "url": "https://3.basecampapi.com/195539477/buckets/2085958499/todosets/1069479339.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958499/todosets/1069479339"
    },
    {
      "id": 1069479340,
      "title": "Docs & Files",
      "name": "vault",
      "enabled": true,
      "position": 3,
      "url": "https://3.basecampapi.com/195539477/buckets/2085958499/vaults/1069479340.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958499/vaults/1069479340"
    },
    {
      "id": 1069479341,
      "title": "Campfire",
      "name": "chat",
      "enabled": true,
      "position": 4,
      "url": "https://3.basecampapi.com/195539477/buckets/2085958499/chats/1069479341.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958499/chats/1069479341"
    },
    {
      "id": 1069479342,
      "title": "Schedule",
      "name": "schedule",
      "enabled": true,
      "position": 5,
      "url": "https://3.basecampapi.com/195539477/buckets/2085958499/schedules/1069479342.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958499/schedules/1069479342"
    },
    {
      "id": 1069479343,
      "title": "Automatic Check-ins",
      "name": "questionnaire",
      "enabled": false,
      "position": null,
      "url": "https://3.basecampapi.com/195539477/buckets/2085958499/questionnaires/1069479343.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958499/questionnaires/1069479343"
    },
    {
      "id": 1069479344,
      "title": "Email Forwards",
      "name": "inbox",
      "enabled": false,
      "position": null,
      "url": "https://3.basecampapi.com/195539477/buckets/2085958499/inboxes/1069479344.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958499/inboxes/1069479344"
    },
    {
      "id": 1069479345,
      "title": "Card Table",
      "name": "kanban_board",
      "enabled": false,
      "position": null,
      "url": "https://3.basecampapi.com/195539477/buckets/2085958499/card_tables/1069479345.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958499/card_tables/1069479345"
    }
  ]
}
```
<!-- END GET /projects/1.json -->
###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/projects/1.json
```


Create a project
-----------------

* `POST /projects.json` with at least a `name`, and optionally a `description`, to create a new project.

###### Example JSON Request

``` json
{
  "name": "Marketing Campaign",
  "description": "For Client: Xyz Corp Conference"
}
```

This will return `201 Created` with the current JSON representation of the project if the creation was a success. See the [Get a project](#get-a-project) endpoint for more info. If the account is on a free subscription and you're trying to create a new project you'll see a `507 Insufficient Storage` and a response of:

``` json
{
  "error": "The project limit for this account has been reached."
}
```

If you hit that error, the user will need to upgrade their subscription to any plan, which all have unlimited projects.

###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -H "Content-Type: application/json" \
  -d '{"name":"Marketing Campaign","description":"For Client: Xyz Corp Conference"}' \
  https://3.basecampapi.com/$ACCOUNT_ID/projects.json
```


Update a project
-----------------

* `PUT /projects/1.json` will allow updating of a project's name and description.

**Required parameters**: `name` of the project.

_Optional parameters_:

* `description` - containing more information about the project.
* `schedule_attributes[start_date]` - project start date (ISO 8601). If provided also the end_date is
    required.
* `schedule_attributes[end_date]` - project end date (ISO 8601). If provided also the start_date is
    required.
* `admissions` - specifies access policy for a project within the same account. Available options
    are:
    * `invite` - only invited users can see the project.
    * `employee` - anyone from the account can see the project.
    * `team` - anyone from the account (except clients) can see the project.

###### Example JSON Request

``` json
{
  "name": "Marketing Campaign",
  "description": "For Client: Xyz Corp Conference",
  "admissions": "team",
  "schedule_attributes": {
    "start_date": "2022-01-01",
    "end_date": "2022-04-01"
  }
}
```

This will return `200 OK` with the current JSON representation of the project if the update was a success. See the [Get a project](#get-a-project) endpoint for more info.

###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -H "Content-Type: application/json" \
  -d '{"name":"Marketing Campaign for Xyz Corp","description":"2016-2017 Strategy"}' -X PUT \
  https://3.basecampapi.com/$ACCOUNT_ID/projects/2085958506.json
```


Trash a project
----------------

* `DELETE /projects/1.json` will mark the project with the given ID as trashed.

Trashed projects will be deleted from Basecamp 4 after 30 days. No parameters required. Returns `204 No Content` if successful.

###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -H "Content-Type: application/json" -X DELETE \
  https://3.basecampapi.com/$ACCOUNT_ID/projects/2085958507.json
```

[pagination]: https://github.com/basecamp/bc3-api/blob/master/README.md#pagination
