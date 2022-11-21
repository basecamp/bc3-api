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
    "id": 2085958498,
    "status": "active",
    "created_at": "2016-09-20T14:34:10.467Z",
    "updated_at": "2016-09-20T14:50:48.007Z",
    "name": "The Leto Laptop",
    "description": "Laptop product launch.",
    "purpose": "topic",
    "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7CEkiCGdpZAY6BkVUSSIrZ2lkOi8vYmMzL0J1Y2tldC8yMDg1OTU4NDk4P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg1yZWFkYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--c8e1a465de900eb9864fa79ae2f30345be158f71.json",
    "url": "https://3.basecampapi.com/195539477/projects/2085958498.json",
    "app_url": "https://3.basecamp.com/195539477/projects/2085958498",
    "dock": [
      {
        "id": 9007199254741443,
        "title": "Campfire",
        "name": "chat",
        "enabled": true,
        "position": 1,
        "url": "https://3.basecampapi.com/195539477/buckets/2085958498/chats/9007199254741443.json",
        "app_url": "https://3.basecamp.com/195539477/buckets/2085958498/chats/9007199254741443"
      },
      {
        "id": 9007199254741444,
        "title": "Message Board",
        "name": "message_board",
        "enabled": true,
        "position": 2,
        "url": "https://3.basecampapi.com/195539477/buckets/2085958498/message_boards/9007199254741444.json",
        "app_url": "https://3.basecamp.com/195539477/buckets/2085958498/message_boards/9007199254741444"
      },
      {
        "id": 9007199254741445,
        "title": "To-dos",
        "name": "todoset",
        "enabled": true,
        "position": 3,
        "url": "https://3.basecampapi.com/195539477/buckets/2085958498/todosets/9007199254741445.json",
        "app_url": "https://3.basecamp.com/195539477/buckets/2085958498/todosets/9007199254741445"
      },
      {
        "id": 9007199254741446,
        "title": "Schedule",
        "name": "schedule",
        "enabled": true,
        "position": 4,
        "url": "https://3.basecampapi.com/195539477/buckets/2085958498/schedules/9007199254741446.json",
        "app_url": "https://3.basecamp.com/195539477/buckets/2085958498/schedules/9007199254741446"
      },
      {
        "id": 9007199254741447,
        "title": "Automatic Check-ins",
        "name": "questionnaire",
        "enabled": true,
        "position": 5,
        "url": "https://3.basecampapi.com/195539477/buckets/2085958498/questionnaires/9007199254741447.json",
        "app_url": "https://3.basecamp.com/195539477/buckets/2085958498/questionnaires/9007199254741447"
      },
      {
        "id": 9007199254741452,
        "title": "Docs & Files",
        "name": "vault",
        "enabled": true,
        "position": 6,
        "url": "https://3.basecampapi.com/195539477/buckets/2085958498/vaults/9007199254741452.json",
        "app_url": "https://3.basecamp.com/195539477/buckets/2085958498/vaults/9007199254741452"
      },
      {
        "id": 9007199254741453,
        "title": "Forwards",
        "name": "inbox",
        "enabled": false,
        "position": null,
        "url": "https://3.basecampapi.com/195539477/buckets/2085958498/inboxes/9007199254741453.json",
        "app_url": "https://3.basecamp.com/195539477/buckets/2085958498/inboxes/9007199254741453"
      }
    ],
    "bookmarked": false
  },
  {
    "id": 2085958500,
    "status": "active",
    "created_at": "2018-02-27T11:11:55.423Z",
    "updated_at": "2018-02-27T11:13:46.317Z",
    "name": "The Leto Locator",
    "description": "New software and hardware built for locating and securing Leto products.",
    "purpose": "topic",
    "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7CEkiCGdpZAY6BkVUSSIrZ2lkOi8vYmMzL0J1Y2tldC8yMDg1OTU4NTAwP2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg1yZWFkYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--0a4a96352e7a1f0a1ab7ed7fd35dfa9b41a28d06.json",
    "url": "https://3.basecampapi.com/195539477/projects/2085958500.json",
    "app_url": "https://3.basecamp.com/195539477/projects/2085958500",
    "client_company": {
      "id": 1033447819,
      "name": "Leto Brand"
    },
    "clientside": {
      "url": "https://3.basecampapi.com/195539477/buckets/2085958500/client/board.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958500/client/board"
    },
    "dock": [
      {
        "id": 1064091258,
        "title": "Campfire",
        "name": "chat",
        "enabled": true,
        "position": 1,
        "url": "https://3.basecampapi.com/195539477/buckets/2085958500/chats/1064091258.json",
        "app_url": "https://3.basecamp.com/195539477/buckets/2085958500/chats/1064091258"
      },
      {
        "id": 1064091259,
        "title": "Message Board",
        "name": "message_board",
        "enabled": true,
        "position": 2,
        "url": "https://3.basecampapi.com/195539477/buckets/2085958500/message_boards/1064091259.json",
        "app_url": "https://3.basecamp.com/195539477/buckets/2085958500/message_boards/1064091259"
      },
      {
        "id": 1064091260,
        "title": "To-dos",
        "name": "todoset",
        "enabled": true,
        "position": 3,
        "url": "https://3.basecampapi.com/195539477/buckets/2085958500/todosets/1064091260.json",
        "app_url": "https://3.basecamp.com/195539477/buckets/2085958500/todosets/1064091260"
      },
      {
        "id": 1064091261,
        "title": "Schedule",
        "name": "schedule",
        "enabled": true,
        "position": 4,
        "url": "https://3.basecampapi.com/195539477/buckets/2085958500/schedules/1064091261.json",
        "app_url": "https://3.basecamp.com/195539477/buckets/2085958500/schedules/1064091261"
      },
      {
        "id": 1064091262,
        "title": "Automatic Check-ins",
        "name": "questionnaire",
        "enabled": true,
        "position": 5,
        "url": "https://3.basecampapi.com/195539477/buckets/2085958500/questionnaires/1064091262.json",
        "app_url": "https://3.basecamp.com/195539477/buckets/2085958500/questionnaires/1064091262"
      },
      {
        "id": 1064091265,
        "title": "Docs & Files",
        "name": "vault",
        "enabled": true,
        "position": 6,
        "url": "https://3.basecampapi.com/195539477/buckets/2085958500/vaults/1064091265.json",
        "app_url": "https://3.basecamp.com/195539477/buckets/2085958500/vaults/1064091265"
      },
      {
        "id": 1064091266,
        "title": "Email Forwards",
        "name": "inbox",
        "enabled": false,
        "position": null,
        "url": "https://3.basecampapi.com/195539477/buckets/2085958500/inboxes/1064091266.json",
        "app_url": "https://3.basecamp.com/195539477/buckets/2085958500/inboxes/1064091266"
      }
    ],
    "bookmarked": false
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
  "id": 2085958498,
  "status": "active",
  "created_at": "2016-09-20T14:34:10.467Z",
  "updated_at": "2016-09-20T14:50:48.007Z",
  "name": "The Leto Laptop",
  "description": "Laptop product launch.",
  "purpose": "topic",
  "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7CEkiCGdpZAY6BkVUSSIrZ2lkOi8vYmMzL0J1Y2tldC8yMDg1OTU4NDk4P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg1yZWFkYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--c8e1a465de900eb9864fa79ae2f30345be158f71.json",
  "url": "https://3.basecampapi.com/195539477/projects/2085958498.json",
  "app_url": "https://3.basecamp.com/195539477/projects/2085958498",
  "dock": [
    {
      "id": 9007199254741443,
      "title": "Campfire",
      "name": "chat",
      "enabled": true,
      "position": 1,
      "url": "https://3.basecampapi.com/195539477/buckets/2085958498/chats/9007199254741443.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958498/chats/9007199254741443"
    },
    {
      "id": 9007199254741444,
      "title": "Message Board",
      "name": "message_board",
      "enabled": true,
      "position": 2,
      "url": "https://3.basecampapi.com/195539477/buckets/2085958498/message_boards/9007199254741444.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958498/message_boards/9007199254741444"
    },
    {
      "id": 9007199254741445,
      "title": "To-dos",
      "name": "todoset",
      "enabled": true,
      "position": 3,
      "url": "https://3.basecampapi.com/195539477/buckets/2085958498/todosets/9007199254741445.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958498/todosets/9007199254741445"
    },
    {
      "id": 9007199254741446,
      "title": "Schedule",
      "name": "schedule",
      "enabled": true,
      "position": 4,
      "url": "https://3.basecampapi.com/195539477/buckets/2085958498/schedules/9007199254741446.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958498/schedules/9007199254741446"
    },
    {
      "id": 9007199254741447,
      "title": "Automatic Check-ins",
      "name": "questionnaire",
      "enabled": true,
      "position": 5,
      "url": "https://3.basecampapi.com/195539477/buckets/2085958498/questionnaires/9007199254741447.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958498/questionnaires/9007199254741447"
    },
    {
      "id": 9007199254741452,
      "title": "Docs & Files",
      "name": "vault",
      "enabled": true,
      "position": 6,
      "url": "https://3.basecampapi.com/195539477/buckets/2085958498/vaults/9007199254741452.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958498/vaults/9007199254741452"
    },
    {
      "id": 9007199254741453,
      "title": "Forwards",
      "name": "inbox",
      "enabled": false,
      "position": null,
      "url": "https://3.basecampapi.com/195539477/buckets/2085958498/inboxes/9007199254741453.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958498/inboxes/9007199254741453"
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

Trashed projects will be deleted from Basecamp 3 after 30 days. No parameters required. Returns `204 No Content` if successful.

###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -H "Content-Type: application/json" -X DELETE \
  https://3.basecampapi.com/$ACCOUNT_ID/projects/2085958507.json
```

[pagination]: https://github.com/basecamp/bc3-api/blob/master/README.md#pagination
