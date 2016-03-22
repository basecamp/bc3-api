Basecamps
=========

**Projects are now called Basecamps in Basecamp 3.** However, the URLs use "projects" still.

Endpoints:

- [Get Basecamps](#get-basecamps)
- [Get archived Basecamps](#get-archived-basecamps)
- [Get trashed Basecamps](#get-trashed-basecamps)
- [Get a Basecamp](#get-a-basecamp)
- [Create a Basecamp](#create-a-basecamp)
- [Update a Basecamp](#update-a-basecamp)
- [Trash a Basecamp](#trash-a-basecamp)

Get Basecamps
-------------

* `GET /projects.json` will return all active Basecamps visible to the current user.

###### Example JSON Response

``` json
[
  {
    "id": 2085958498,
    "created_at": "2016-01-27T11:02:32.061-06:00",
    "updated_at": "2016-01-27T11:03:32.570-06:00",
    "status": "active",
    "url": "https://3.basecamp.com/195539477/projects/2085958498",
    "name": "The Leto Laptop",
    "description": "Laptop product launch.",
    "bookmarked": false,
    "bookmark_url": "https://3.basecamp.com/195539477/my/bookmarks/BAh7CEkiCGdpZAY6BkVUSSIrZ2lkOi8vYmMzL0J1Y2tldC8yMDg1OTU4NDk4P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg1yZWFkYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--c8e1a465de900eb9864fa79ae2f30345be158f71",
    "vault_url": "https://3.basecamp.com/195539477/buckets/2085958498/vaults/9007199254741442",
    "dock": [
      {
        "id": 9007199254741432,
        "title": "Campfire",
        "name": "chat",
        "url": "https://3.basecamp.com/195539477/buckets/2085958498/chats/9007199254741433.json",
        "enabled": true
      },
      {
        "id": 9007199254741434,
        "title": "Message Board",
        "name": "message_board",
        "url": "https://3.basecamp.com/195539477/buckets/2085958498/message_boards/9007199254741434.json",
        "enabled": true
      },
      {
        "id": 9007199254741436,
        "title": "To-dos",
        "name": "todoset",
        "url": "https://3.basecamp.com/195539477/buckets/2085958498/todosets/9007199254741435.json",
        "enabled": true
      },
      {
        "id": 9007199254741436,
        "title": "Schedule",
        "name": "schedule",
        "url": "https://3.basecamp.com/195539477/buckets/2085958498/schedules/9007199254741436.json",
        "enabled": true
      },
      {
        "id": 9007199254741436,
        "title": "Automatic Check-ins",
        "name": "questionnaire",
        "url": "https://3.basecamp.com/195539477/buckets/2085958498/questionnaires/9007199254741437.json",
        "enabled": true
      },
      {
        "id": 9007199254741442,
        "title": "Docs & Files",
        "name": "vault",
        "url": "https://3.basecamp.com/195539477/buckets/2085958498/vaults/9007199254741442.json",
        "enabled": false
      }
    ]
  },
  ...
]
```


###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecamp.com/$ACCOUNT_ID/projects.json
```

Get archived Basecamps
----------------------

* `GET /projects/archive.json` will return all archived Basecamps visible to the current user.

Get trashed Basecamps
---------------------

* `GET /projects/trash.json` will return all trashed Basecamps visible to the current user.


Get a Basecamp
--------------

* `GET /projects/1.json` will return the Basecamp with the given ID, granted they have access to it.

The `dock` key contains an array of the current tools for this Basecamp. The `enabled` flag will be `true` if the tool is turned on for use. You can use the `url` parameter from each tool to jump to the resources available inside of this Basecamp.

###### Example JSON Response

``` json
{
  "id": 2085958495,
  "created_at": "2016-01-27T11:00:20.701-06:00",
  "updated_at": "2016-03-09T11:50:54.324-06:00",
  "status": "active",
  "url": "https://3.basecamp.com/195539477/projects/2085958495",
  "name": "Annie's Corner",
  "description": "Annie's Stuff. Keep Out. 😁",
  "bookmarked": false,
  "bookmark_url": "https://3.basecamp.com/195539477/my/bookmarks/BAh7CEkiCGdpZAY6BkVUSSIrZ2lkOi8vYmMzL0J1Y2tldC8yMDg1OTU4NDk1P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg1yZWFkYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--06a5145963152c63ea56090695ec59e6d83fb21a",
  "vault_url": "https://3.basecamp.com/195539477/buckets/2085958495/vaults/9007199254741021",
  "dock": [
    {
      "id": 9007199254741012,
      "title": "Campfire",
      "name": "chat",
      "url": "https://3.basecamp.com/195539477/buckets/2085958495/chats/9007199254741012.json",
      "enabled": true
    },
    {
      "id": 9007199254741012,
      "title": "Message Board",
      "name": "message_board",
      "url": "https://3.basecamp.com/195539477/buckets/2085958495/message_boards/9007199254741013.json",
      "enabled": true
    },
    {
      "id": 9007199254741014,
      "title": "To-dos",
      "name": "todoset",
      "url": "https://3.basecamp.com/195539477/buckets/2085958495/todosets/9007199254741014.json",
      "enabled": true
    },
    {
      "id": 9007199254741016,
      "title": "Schedule",
      "name": "schedule",
      "url": "https://3.basecamp.com/195539477/buckets/2085958495/schedules/9007199254741015.json",
      "enabled": true
    },
    {
      "id": 9007199254741016,
      "title": "Automatic Check-ins",
      "name": "questionnaire",
      "url": "https://3.basecamp.com/195539477/buckets/2085958495/questionnaires/9007199254741016.json",
      "enabled": true
    },
    {
      "id": 9007199254741020,
      "title": "Docs & Files",
      "name": "vault",
      "url": "https://3.basecamp.com/195539477/buckets/2085958495/vaults/9007199254741021.json",
      "enabled": false
    }
  ]
}
```

###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecamp.com/$ACCOUNT_ID/projects/1.json
```


Create a Basecamp
-----------------

* `POST /projects.json` with at least a name, and optionally a description, to kick off a new Basecamp.

###### Example JSON Request

``` json
{
  "name": "Marketing Campaign",
  "description": "For Client: Xyz Corp Conference"
}
```

This will return `201 Created` with the current JSON representation of the Basecamp if the creation was a success. See the [Get a Basecamp](#get-a-basecamp) endpoint for more info. If your the account is on a free subscription and you're trying to create a new Basecamp you'll see a `507 Insufficient Storage` and a response of:

``` json
{
  "error": "The Basecamp limit for this account has been reached."
}
```

If you hit that error, the user will need to upgrade their subscription to any plan, which all have unlimited Basecamps. After creating a Basecamp, you'll  want to [allow people to get in][1]. Or maybe, [add some to-dos][2]!

###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -H "Content-Type: application/json" \
  -d '{"name":"Marketing Campaign","description":"For Client: Xyz Corp Conference"}' \
  https://3.basecamp.com/$ACCOUNT_ID/projects.json
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
  https://3.basecamp.com/$ACCOUNT_ID/projects/2085958506.json
```


Trash a Basecamp
----------------

* `DELETE /projects/1.json` will mark the Basecamp with the given ID as trashed.

Trashed Basecamps will be deleted from Basecamp 3 after 30 days. No parameters required. Returns `204 No Content` if successful.

###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -H "Content-Type: application/json" -X DELETE \
  https://3.basecamp.com/$ACCOUNT_ID/projects/2085958507.json
```

[1]: https://github.com/basecamp/bc3-api/blob/master/sections/accesses.md#accesses
[2]: https://github.com/basecamp/bc3-api/blob/master/sections/todos.md#todos
