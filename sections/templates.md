Templates
=========

Endpoints:

- [Get Templates](#get-templates)
- [Get a Template](#get-a-template)
- [Create a Template](#create-a-template)
- [Update a Template](#update-a-template)
- [Trash a Template](#trash-a-template)
- [Create a Project Construction](#create-a-project-construction)
- [Get a Project Construction](#create-a-project-construction)

Get Templates
-------------

* `GET /templates.json` will return a [paginated list][pagination] of active Templates visible to the current user sorted by most recently created Template first.

_Optional parameters_:

* `status` - when set to `archived` or `trashed`, will return archived or trashed Templates visible to the current user.

###### Example JSON Response
<!-- START GET /templates.json -->
```json
[
  {
    "id": 2085958503,
    "status": "active",
    "created_at": "2016-12-02T14:18:44.436Z",
    "updated_at": "2016-12-02T14:19:13.683Z",
    "name": "Templated",
    "description": "asdasd",
    "url": "https://3.basecampapi.com/195539477/templates/2085958503.json",
    "app_url": "https://3.basecamp.com/195539477/templates/2085958503"
  }
]
```
<!-- END GET /templates.json -->
###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/templates.json
```

Get a Template
--------------

* `GET /templates/1.json` will return the Template with the given ID, granted they have access to it.

###### Example JSON Response
<!-- START GET /templates/1.json -->
```json
{
  "id": 2085958503,
  "status": "active",
  "created_at": "2016-12-02T14:18:44.436Z",
  "updated_at": "2016-12-02T14:19:13.683Z",
  "name": "Templated",
  "description": "asdasd",
  "url": "https://3.basecampapi.com/195539477/templates/2085958503.json",
  "app_url": "https://3.basecamp.com/195539477/templates/2085958503"
}
```
<!-- END GET /templates/1.json -->
###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/templates/1.json
```


Create a Template
-----------------

* `POST /templates.json` with at least a `name`, and optionally a `description`, to create a new Template.

###### Example JSON Request

``` json
{
  "name": "New Starter Checklist",
  "description": "Things every new starter should do"
}
```

###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -H "Content-Type: application/json" \
  -d '{"name":"New Starter Checklist","description":"Things every new starter should do in their first week"}' \
  https://3.basecampapi.com/$ACCOUNT_ID/templates.json
```

This will return `201 Created` with the current JSON representation of the Template if the creation was a success. See the [Get a Template](#get-a-template) endpoint for more info. Templates follow the same account limits as projects. If the account is on a free subscription and you're trying to create a new Template you'll see a `507 Insufficient Storage` and a response of:

``` json
{
  "error": "The project/team limit for this account has been reached."
}
```

If you hit that error, the user will need to upgrade their subscription to any plan, which all have unlimited Templates.


Update a Template
-----------------

* `PUT /templates/1.json` will allow updating of a Template's name and description.

###### Example JSON Request

``` json
{
  "name": "New Starter First Week Checklist",
  "description": "Things every new starter should do in their first week"
}
```

This will return `200 OK` with the current JSON representation of the Template if the update was a success. See the [Get a Template](#get-a-template) endpoint for more info.

###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -H "Content-Type: application/json" \
  -d '{"name":"New Starter First Week Checklist","description":"Things every new starter should do in their first week"}' -X PUT \
  https://3.basecampapi.com/$ACCOUNT_ID/templates/2085958506.json
```

Trash a Template
----------------

* `DELETE /templates/1.json` will mark the Template with the given ID as trashed.

Trashed Templates will be deleted from Basecamp 3 after 30 days. No parameters required. Returns `204 No Content` if successful.

###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -H "Content-Type: application/json" -X DELETE \
  https://3.basecampapi.com/$ACCOUNT_ID/templates/2085958507.json
```


Create a Project Construction
--------------------------------

To create a project given a template, you need to create a project construction.

* `POST /templates/:template_id/project_constructions.json` with at least a project `name`, and optionally a `description`.

###### Example JSON Request

``` json
{
  "project": {
    "name": "Marketing ",
    "description": "2016-2017 Strategy"
  }
}
```

###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -H "Content-Type: application/json" -d '{"project":{"name":"Marketing Campaign","description":"For Client: Xyz Corp Conference"}}' -X POST \
  https://3.basecampapi.com/$ACCOUNT_ID/templates/2085958507/project_constructions.json
```


If creation was successful, this returns `201 Created` along with the current JSON representation of the project construction.

<!-- START POST /templates/1/project_constructions.json -->
```json
{
  "id": 3,
  "status": "pending",
  "url": "https://3.basecampapi.com/195539477/templates/2085958503/project_constructions/3.json"
}
```
<!-- END POST /templates/1/project_constructions.json -->

Get a Project Construction
--------------------------------

* `GET /templates/1/project_constructions/1.json` will return the current state of the project construction.

This endpoint can be polled at regular intervals (no more than once a second) to see when the project is complete. When complete, the construction will have a status of "completed" and look like this, including the url of the
created project:

<!-- START GET /templates/1/project_constructions/1.json -->
```json
{
  "id": 3,
  "status": "completed",
  "url": "https://3.basecampapi.com/195539477/templates/2085958503/project_constructions/3.json",
  "project": {
    "id": 2085958506,
    "status": "active",
    "created_at": "2016-12-05T14:32:45.234Z",
    "updated_at": "2016-12-05T14:32:45.797Z",
    "name": "New project from template",
    "description": "asdasd",
    "purpose": "topic",
    "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7CEkiCGdpZAY6BkVUSSIrZ2lkOi8vYmMzL0J1Y2tldC8yMDg1OTU4NTA2P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg1yZWFkYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--430f36c61cd197c9e0cb73997e61481e2c22b26b.json",
    "url": "https://3.basecampapi.com/195539477/projects/2085958506.json",
    "app_url": "https://3.basecamp.com/195539477/projects/2085958506",
    "dock": [
      {
        "id": 9007199254741962,
        "title": "Campfire",
        "name": "chat",
        "enabled": true,
        "position": 1,
        "url": "https://3.basecampapi.com/195539477/buckets/2085958506/chats/9007199254741962.json",
        "app_url": "https://3.basecamp.com/195539477/buckets/2085958506/chats/9007199254741962"
      },
      {
        "id": 9007199254741963,
        "title": "Message Board",
        "name": "message_board",
        "enabled": true,
        "position": 2,
        "url": "https://3.basecampapi.com/195539477/buckets/2085958506/message_boards/9007199254741963.json",
        "app_url": "https://3.basecamp.com/195539477/buckets/2085958506/message_boards/9007199254741963"
      },
      {
        "id": 9007199254741964,
        "title": "To-dos",
        "name": "todoset",
        "enabled": true,
        "position": 3,
        "url": "https://3.basecampapi.com/195539477/buckets/2085958506/todosets/9007199254741964.json",
        "app_url": "https://3.basecamp.com/195539477/buckets/2085958506/todosets/9007199254741964"
      },
      {
        "id": 9007199254741965,
        "title": "Schedule",
        "name": "schedule",
        "enabled": true,
        "position": 4,
        "url": "https://3.basecampapi.com/195539477/buckets/2085958506/schedules/9007199254741965.json",
        "app_url": "https://3.basecamp.com/195539477/buckets/2085958506/schedules/9007199254741965"
      },
      {
        "id": 9007199254741966,
        "title": "Automatic Check-ins",
        "name": "questionnaire",
        "enabled": true,
        "position": 5,
        "url": "https://3.basecampapi.com/195539477/buckets/2085958506/questionnaires/9007199254741966.json",
        "app_url": "https://3.basecamp.com/195539477/buckets/2085958506/questionnaires/9007199254741966"
      },
      {
        "id": 9007199254741969,
        "title": "Docs & Files",
        "name": "vault",
        "enabled": true,
        "position": 6,
        "url": "https://3.basecampapi.com/195539477/buckets/2085958506/vaults/9007199254741969.json",
        "app_url": "https://3.basecamp.com/195539477/buckets/2085958506/vaults/9007199254741969"
      },
      {
        "id": 9007199254741970,
        "title": "Email Forwards",
        "name": "inbox",
        "enabled": false,
        "position": null,
        "url": "https://3.basecampapi.com/195539477/buckets/2085958506/inboxes/9007199254741970.json",
        "app_url": "https://3.basecamp.com/195539477/buckets/2085958506/inboxes/9007199254741970"
      }
    ]
  }
}
```
<!-- END GET /templates/1/project_constructions/1.json -->

[pagination]: https://github.com/basecamp/bc3-api/blob/master/README.md#pagination
