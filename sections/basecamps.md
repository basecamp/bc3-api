Basecamps
=========

**Projects are now called Basecamps in Basecamp 3.** However, the URLs use "projects" still.

Endpoints:

- [Get Basecamps](#get-basecamps)
- [Get a Basecamp](#get-a-basecamp)
- [Create a Basecamp](#create-a-basecamp)
- [Update a Basecamp](#update-a-basecamp)
- [Trash a Basecamp](#trash-a-basecamp)

Get Basecamps
-------------

* `GET /projects.json` will return a [paginated list][pagination] of active Basecamps visible to the current user.

_Optional parameters_:

* `status` - when set to `archived` or `trashed`, will return archived or trashed Basecamps visible to the current user.

###### Example JSON Response
<!-- START GET /projects.json -->
```json
[
  {
    "id": 2085958498,
    "status": "active",
    "created_at": "2016-07-19T16:47:30.497Z",
    "updated_at": "2016-07-19T17:20:48.090Z",
    "name": "The Leto Laptop",
    "description": "Laptop product launch.",
    "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7CEkiCGdpZAY6BkVUSSIrZ2lkOi8vYmMzL0J1Y2tldC8yMDg1OTU4NDk4P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg1yZWFkYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--c8e1a465de900eb9864fa79ae2f30345be158f71.json",
    "url": "https://3.basecampapi.com/195539477/projects/2085958498.json",
    "app_url": "https://3.basecamp.com/195539477/projects/2085958498",
    "dock": [
      {
        "id": 9007199254741433,
        "title": "Campfire",
        "name": "chat",
        "enabled": true,
        "position": 1,
        "url": "https://3.basecampapi.com/195539477/buckets/2085958498/chats/9007199254741433.json",
        "app_url": "https://3.basecamp.com/195539477/buckets/2085958498/chats/9007199254741433"
      },
      {
        "id": 9007199254741434,
        "title": "Message Board",
        "name": "message_board",
        "enabled": true,
        "position": 2,
        "url": "https://3.basecampapi.com/195539477/buckets/2085958498/message_boards/9007199254741434.json",
        "app_url": "https://3.basecamp.com/195539477/buckets/2085958498/message_boards/9007199254741434"
      },
      {
        "id": 9007199254741435,
        "title": "To-dos",
        "name": "todoset",
        "enabled": true,
        "position": 3,
        "url": "https://3.basecampapi.com/195539477/buckets/2085958498/todosets/9007199254741435.json",
        "app_url": "https://3.basecamp.com/195539477/buckets/2085958498/todosets/9007199254741435"
      },
      {
        "id": 9007199254741436,
        "title": "Schedule",
        "name": "schedule",
        "enabled": true,
        "position": 4,
        "url": "https://3.basecampapi.com/195539477/buckets/2085958498/schedules/9007199254741436.json",
        "app_url": "https://3.basecamp.com/195539477/buckets/2085958498/schedules/9007199254741436"
      },
      {
        "id": 9007199254741437,
        "title": "Automatic Check-ins",
        "name": "questionnaire",
        "enabled": true,
        "position": 5,
        "url": "https://3.basecampapi.com/195539477/buckets/2085958498/questionnaires/9007199254741437.json",
        "app_url": "https://3.basecamp.com/195539477/buckets/2085958498/questionnaires/9007199254741437"
      },
      {
        "id": 9007199254741442,
        "title": "Docs & Files",
        "name": "vault",
        "enabled": true,
        "position": 6,
        "url": "https://3.basecampapi.com/195539477/buckets/2085958498/vaults/9007199254741442.json",
        "app_url": "https://3.basecamp.com/195539477/buckets/2085958498/vaults/9007199254741442"
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


Get a Basecamp
--------------

* `GET /projects/1.json` will return the Basecamp with the given ID, granted they have access to it.

The `dock` key contains an array of the current tools for this Basecamp. The `enabled` flag will be `true` if the tool is turned on for use. You can use the `url` parameter from each tool to jump to the resources available inside of this Basecamp.

###### Example JSON Response
<!-- START GET /projects/1.json -->
```json
{
  "id": 2085958498,
  "status": "active",
  "created_at": "2016-07-19T16:47:30.497Z",
  "updated_at": "2016-07-19T17:20:48.090Z",
  "name": "The Leto Laptop",
  "description": "Laptop product launch.",
  "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7CEkiCGdpZAY6BkVUSSIrZ2lkOi8vYmMzL0J1Y2tldC8yMDg1OTU4NDk4P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg1yZWFkYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--c8e1a465de900eb9864fa79ae2f30345be158f71.json",
  "url": "https://3.basecampapi.com/195539477/projects/2085958498.json",
  "app_url": "https://3.basecamp.com/195539477/projects/2085958498",
  "dock": [
    {
      "id": 9007199254741433,
      "title": "Campfire",
      "name": "chat",
      "enabled": true,
      "position": 1,
      "url": "https://3.basecampapi.com/195539477/buckets/2085958498/chats/9007199254741433.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958498/chats/9007199254741433"
    },
    {
      "id": 9007199254741434,
      "title": "Message Board",
      "name": "message_board",
      "enabled": true,
      "position": 2,
      "url": "https://3.basecampapi.com/195539477/buckets/2085958498/message_boards/9007199254741434.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958498/message_boards/9007199254741434"
    },
    {
      "id": 9007199254741435,
      "title": "To-dos",
      "name": "todoset",
      "enabled": true,
      "position": 3,
      "url": "https://3.basecampapi.com/195539477/buckets/2085958498/todosets/9007199254741435.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958498/todosets/9007199254741435"
    },
    {
      "id": 9007199254741436,
      "title": "Schedule",
      "name": "schedule",
      "enabled": true,
      "position": 4,
      "url": "https://3.basecampapi.com/195539477/buckets/2085958498/schedules/9007199254741436.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958498/schedules/9007199254741436"
    },
    {
      "id": 9007199254741437,
      "title": "Automatic Check-ins",
      "name": "questionnaire",
      "enabled": true,
      "position": 5,
      "url": "https://3.basecampapi.com/195539477/buckets/2085958498/questionnaires/9007199254741437.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958498/questionnaires/9007199254741437"
    },
    {
      "id": 9007199254741442,
      "title": "Docs & Files",
      "name": "vault",
      "enabled": true,
      "position": 6,
      "url": "https://3.basecampapi.com/195539477/buckets/2085958498/vaults/9007199254741442.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958498/vaults/9007199254741442"
    }
  ]
}
```
<!-- END GET /projects/1.json -->
###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/projects/1.json
```


Create a Basecamp
-----------------

* `POST /projects.json` with at least a `name`, and optionally a `description`, to create a new Basecamp.

###### Example JSON Request

``` json
{
  "name": "Marketing Campaign",
  "description": "For Client: Xyz Corp Conference"
}
```

This will return `201 Created` with the current JSON representation of the Basecamp if the creation was a success. See the [Get a Basecamp](#get-a-basecamp) endpoint for more info. If the account is on a free subscription and you're trying to create a new Basecamp you'll see a `507 Insufficient Storage` and a response of:

``` json
{
  "error": "The Basecamp limit for this account has been reached."
}
```

If you hit that error, the user will need to upgrade their subscription to any plan, which all have unlimited Basecamps.

###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -H "Content-Type: application/json" \
  -d '{"name":"Marketing Campaign","description":"For Client: Xyz Corp Conference"}' \
  https://3.basecampapi.com/$ACCOUNT_ID/projects.json
```


Update a Basecamp
-----------------

* `PUT /projects/1.json` will allow updating of a Basecamp's name and description.

###### Example JSON Request

``` json
{
  "name": "Marketing Campaign for Xyz Corp",
  "description": "2016-2017 Strategy"
}
```

This will return `200 OK` with the current JSON representation of the Basecamp if the update was a success. See the [Get a Basecamp](#get-a-basecamp) endpoint for more info.

###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -H "Content-Type: application/json" \
  -d '{"name":"Marketing Campaign for Xyz Corp","description":"2016-2017 Strategy"}' -X PUT \
  https://3.basecampapi.com/$ACCOUNT_ID/projects/2085958506.json
```


Trash a Basecamp
----------------

* `DELETE /projects/1.json` will mark the Basecamp with the given ID as trashed.

Trashed Basecamps will be deleted from Basecamp 3 after 30 days. No parameters required. Returns `204 No Content` if successful.

###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -H "Content-Type: application/json" -X DELETE \
  https://3.basecampapi.com/$ACCOUNT_ID/projects/2085958507.json
```

[pagination]: https://github.com/basecamp/bc3-api/blob/master/README.md#pagination
