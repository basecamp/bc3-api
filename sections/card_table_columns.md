Card table columns
================

Endpoints:

- [Get a column](#get-a-column)
- [Create a column](#create-a-column)
- [Update a column](#update-a-column)
- [Move a column](#move-a-column)
- [Watch a column](#watch-a-column)
- [Change on hold on a column](#change-on-hold-on-a-column)
- [Change color of a column](#change-color-of-a-column)

Get a column
-------------

* `GET /buckets/1/card_tables/columns/2.json` will return the column with an ID of `2` in the project with an ID of `1`.

###### Example JSON Response
<!-- START GET /buckets/1/card_tables/columns/2.json -->
```json
{
  "id": 1069482092,
  "status": "active",
  "visible_to_clients": false,
  "created_at": "2022-11-18T09:51:27.242Z",
  "updated_at": "2022-11-18T09:51:41.806Z",
  "title": "Triage",
  "inherits_status": true,
  "type": "Kanban::Triage",
  "url": "https://3.basecampapi.com/195539477/buckets/2085958499/card_tables/columns/1069482092.json",
  "app_url": "https://3.basecamp.com/195539477/buckets/2085958499/card_tables/columns/1069482092",
  "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7CEkiCGdpZAY6BkVUSSIuZ2lkOi8vYmMzL1JlY29yZGluZy8xMDY5NDgyMDkyP2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg1yZWFkYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--4e5003c6ebe9d448a770f00a1b3da52b6f668c65.json",
  "parent": {
    "id": 1069482091,
    "title": "Card Table",
    "type": "Kanban::Board",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958499/card_tables/1069482091.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958499/card_tables/1069482091"
  },
  "bucket": {
    "id": 2085958499,
    "name": "The Leto Laptop",
    "type": "Project"
  },
  "creator": {
    "id": 1049716070,
    "attachable_sgid": "BAh7CEkiCGdpZAY6BkVUSSIrZ2lkOi8vYmMzL1BlcnNvbi8xMDQ5NzE2MDcwP2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg9hdHRhY2hhYmxlBjsAVEkiD2V4cGlyZXNfYXQGOwBUMA==--5cfb1d97d8544362aa74062bc84b66fbf1d7a853",
    "name": "Victor Cooper",
    "email_address": "victor@honchodesign.com",
    "personable_type": "User",
    "title": "Chief Strategist",
    "bio": "Don’t let your dreams be dreams",
    "location": "Chicago, IL",
    "created_at": "2022-11-18T09:50:54.566Z",
    "updated_at": "2022-11-18T09:50:54.760Z",
    "admin": true,
    "owner": true,
    "client": false,
    "employee": true,
    "time_zone": "America/Chicago",
    "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBGZlkT4=--b295b0b432557d4a03760f78668284d4f39bf563/avatar?v=1",
    "company": {
      "id": 1033447825,
      "name": "Honcho Design"
    },
    "can_manage_projects": true,
    "can_manage_people": true
  },
  "description": null,
  "subscribers": [

  ],
  "color": null,
  "cards_count": 1,
  "comment_count": 0,
  "cards_url": "https://3.basecampapi.com/195539477/buckets/2085958499/card_tables/lists/1069482092/cards.json"
}
```
<!-- END GET /buckets/1/card_tables/columns/2.json -->
###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/card_tables/columns/2.json
```

Create a column
-------------------------

* `POST /buckets/1/card_tables/2/columns.json` creates a column within the card table with ID `2` in the project with id `1`.

**Required parameters**: `title` of the column.

_Optional parameters_:

* `description` - containing information about the column.

This endpoint will return `201 Created` with the current JSON representation of the column if the creation was a success. See the [Get a column](#get-a-column) endpoint for more info on the payload.

###### Example JSON Request

``` json
{
  "kanban_column": {
    "title": "In progress",
    "description": "Stuff we are working on actively"
  }
}
```

###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -H "Content-Type: application/json" \
  -d '{"title":"In progress"}' \
  https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/card_tables/2/columns.json
```

Update a column
-----------------------

* `PUT /buckets/1/card_tables/columns/2.json` allows changing of the column with an ID of `2` in the project with ID `1`.

This endpoint will return `200 OK` with the current JSON representation of the column if the update was a success. See the [Get a column](#get-a-column) endpoint for more info on the payload.

###### Example JSON Request

``` json
{
  "kanban_column": {
    "title": "On it",
    "description": "Stuff we are doing right now"
  }
}
```

###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -H "Content-Type: application/json" \
  -d '{"title":"On it", "description":"Stuff we are doing right now"}' -X PUT \
  https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/card_tables/columns/2.json
```

Move a column
-----------------------

* `POST /buckets/1/card_tables/2/moves.json` allows moving of a column in the card table with id `2` in the project with ID `1`.

**Required parameters**:

* `source_id` - the id of the column to move
* `target_id` - the id of the card table

_Optional parameters_:

* `position` - index among the columns (ignoring Triage, Not Now or Done). Default: `1`

This endpoint will return `204 No content` if the update was a success.

###### Example JSON Request

``` json
{
  "source_id": 3,
  "targed_id": 4,
  "position": 2
}
```
###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -H "Content-Type: application/json" \
  -d '{"source_id": 3, "target_id":4, "position": 2}' \
  https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/card_tables/2/moves.json
```

Watch a column
-----------------------
* `POST /buckets/1/card_tables/lists/2/subscription.json` starts watching the column with id `2` in the project with ID `1`.
* `DELETE /buckets/1/card_tables/lists/2/subscription.json` stops watching the column with id `2` in the project with ID `1`.

This endpoint will return `204 No content` if the update was a success.

###### Copy as cURL
``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -H "Content-Type: application/json" \
  -X POST \
  https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/card_tables/lists/2/subscription.json
```
``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -H "Content-Type: application/json" \
  -X DELETE \
  https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/card_tables/lists/2/subscription.json
```

Change on hold on a column
-----------------------

* `POST /buckets/1/card_tables/columns/2/on_hold.json` creates an on_hold section in the column with ID `2` in the project with id `1`.
* `DELETE /buckets/1/card_tables/columns/2/on_hold.json` removes an on_hold section in the column with ID `2` in the project with id `1`.

This endpoint will return `200 Success` with the current JSON representation of the column if the operation was a success. See the [Get a column](#get-a-column) endpoint for more info on the payload.

###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -H "Content-Type: application/json" \
  -X POST \
  https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/card_tables/columns/2/on_hold.json
```
``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -H "Content-Type: application/json" \
  -X DELETE \
  https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/card_tables/columns/2/on_hold.json
```

Change color of a column
-----------------------

* `PUT /buckets/1/card_tables/columns/2/color.json` allows changing the color of the column with an ID of `2` in the project with ID `1`.

This endpoint will return `200 OK` with the current JSON representation of the column if the update was a success. See the [Get a column](#get-a-column) endpoint for more info on the payload.


**Required parameters**:

* `color` - the color. Available values: `[ white red orange yellow green blue aqua purple gray pink brown ]`

###### Example JSON Request

``` json
{
  "color": "orange"
}
```

###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -H "Content-Type: application/json" \
  -d '{"color":"orange"}' -X PUT \
  https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/card_tables/columns/2/color.json
```

