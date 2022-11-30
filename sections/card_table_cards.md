Card table cards
================

Endpoints:

- [Get cards in a column](#get-cards-in-a-column)
- [Get a card](#get-a-card)
- [Create a card](#create-a-card)
- [Update a card](#update-a-card)
- [Move a card](#move-a-card)

Get cards in a column
--------------------

* `GET /buckets/1/card_tables/lists/3/cards.json` will return a [paginated list][pagination] of cards in the project with an ID of `1` and the column with ID of `3`.

###### Example JSON Response
<!-- START GET /buckets/1/card_tables/lists/3/cards.json -->
```json
[
  {
    "id": 1069482295,
    "status": "active",
    "visible_to_clients": false,
    "created_at": "2022-11-18T13:42:27.150Z",
    "updated_at": "2022-11-18T13:42:27.150Z",
    "title": "New and fancy UI",
    "inherits_status": true,
    "type": "Kanban::Card",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958499/card_tables/cards/1069482295.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958499/card_tables/cards/1069482295",
    "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7CEkiCGdpZAY6BkVUSSIuZ2lkOi8vYmMzL1JlY29yZGluZy8xMDY5NDgyMjk1P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg1yZWFkYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--6957f5ec7e664f8ae36f368e6e61e6d7ab20b3a7.json",
    "subscription_url": "https://3.basecampapi.com/195539477/buckets/2085958499/recordings/1069482295/subscription.json",
    "comments_count": 0,
    "comments_url": "https://3.basecampapi.com/195539477/buckets/2085958499/recordings/1069482295/comments.json",
    "position": 1,
    "parent": {
      "id": 1069482092,
      "title": "Triage",
      "type": "Kanban::Triage",
      "url": "https://3.basecampapi.com/195539477/buckets/2085958499/card_tables/columns/1069482092.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958499/card_tables/columns/1069482092"
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
    "description": "Design a new and fancy UI",
    "completed": false,
    "content": "Design a new and fancy UI",
    "due_on": null,
    "assignees": [

    ],
    "completion_subscribers": [

    ],
    "completion_url": "https://3.basecampapi.com/195539477/buckets/2085958499/todos/1069482295/completion.json",
    "comment_count": 0
  }
]
```
<!-- END GET /buckets/1/card_tables/lists/3/cards.json -->
###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/card_tables/lists/3/cards.json
```

Get a card
--------------------

* `GET /buckets/1/card_tables/cards/2.json` will return the card with an ID of `2` in the project with an ID of `1`.

###### Example JSON Response
<!-- START GET /buckets/1/card_tables/cards/2.json -->
```json
{
  "id": 1069482295,
  "status": "active",
  "visible_to_clients": false,
  "created_at": "2022-11-18T13:42:27.150Z",
  "updated_at": "2022-11-18T13:42:27.150Z",
  "title": "New and fancy UI",
  "inherits_status": true,
  "type": "Kanban::Card",
  "url": "https://3.basecampapi.com/195539477/buckets/2085958499/card_tables/cards/1069482295.json",
  "app_url": "https://3.basecamp.com/195539477/buckets/2085958499/card_tables/cards/1069482295",
  "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7CEkiCGdpZAY6BkVUSSIuZ2lkOi8vYmMzL1JlY29yZGluZy8xMDY5NDgyMjk1P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg1yZWFkYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--6957f5ec7e664f8ae36f368e6e61e6d7ab20b3a7.json",
  "subscription_url": "https://3.basecampapi.com/195539477/buckets/2085958499/recordings/1069482295/subscription.json",
  "comments_count": 0,
  "comments_url": "https://3.basecampapi.com/195539477/buckets/2085958499/recordings/1069482295/comments.json",
  "position": 1,
  "parent": {
    "id": 1069482092,
    "title": "Triage",
    "type": "Kanban::Triage",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958499/card_tables/columns/1069482092.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958499/card_tables/columns/1069482092"
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
  "description": "Design a new and fancy UI",
  "completed": false,
  "content": "Design a new and fancy UI",
  "due_on": null,
  "assignees": [

  ],
  "completion_subscribers": [

  ],
  "completion_url": "https://3.basecampapi.com/195539477/buckets/2085958499/todos/1069482295/completion.json",
  "comment_count": 0
}
```
<!-- END GET /buckets/1/card_tables/cards/2.json -->
###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/card_tables/cards/2.json
```

Create a card
-------------------------

* `POST /buckets/1/card_tables/lists/2/cards.json` creates a card within the column with ID `2` in the project with id `1`.

**Required parameters**: `title` of the card.

_Optional parameters_: 

* `content` - containing information about the card. See our [Rich text guide][rich] for what HTML tags are allowed.
* `due_on` - due date (ISO 8601) of the card

This endpoint will return `201 Created` with the current JSON representation of the card if the creation was a success. See the [Get a card](#get-a-card) endpoint for more info on the payload.

###### Example JSON Request

``` json
{
  "kanban_card": {
    "title": "Investigation",
    "content": "Investigate on an issue in our todo list.",
    "due_on": "2021-01-01"
  }
}
```

###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -H "Content-Type: application/json" \
  -d '{"kanban_card": {"title":"Investigation", "content": "Investigate on an issue in our todo list.", "due_on": "2021-01-01"}}' \
  https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/card_tables/lists/2/cards.json
```

Update a card
-----------------------

* `PUT /buckets/1/card_tables/cards/2.json` allows changing of the card with an ID of `2` in the project with ID `1`.

_Optional parameters_: 

* `title` - of the card.
* `content` - containing information about the card. See our [Rich text guide][rich] for what HTML tags are allowed.
* `due_on` - due date (ISO 8601) of the card
* `assignee_ids` - an array of people that will be assigned to this to-do. Please see the [Get people][people] endpoints to retrieve them.

This endpoint will return `200 OK` with the current JSON representation of the card if the update was a success. See the [Get a card](#get-a-card) endpoint for more info on the payload.

###### Example JSON Request

``` json
{
  "kanban_card": {
    "title": "Updated investigation"
  }
}
```

###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -H "Content-Type: application/json" \
  -d '{"kanban_card": {"title":"Updated investigation"}}' -X PUT \
  https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/card_tables/cards/2.json
```

Move a card
-----------------------

* `POST /buckets/1/card_tables/cards/2/moves.json` allows moving of a card with id `2` in the project with ID `1`.

**Required parameters**: `column_id` of the column destination

This endpoint will return `204 No content` if the update was a success.

###### Example JSON Request

``` json
{
  "column_id": 3,
}
```
###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -H "Content-Type: application/json" \
  -d '{"column_id": 3}' \
  https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/card_tables/2/moves.json
```

[pagination]: https://github.com/basecamp/bc3-api/blob/master/README.md#pagination
[rich]: https://github.com/basecamp/bc3-api/blob/master/sections/rich_text.md
[people]: https://github.com/basecamp/bc3-api/blob/master/sections/people.md#get-all-people
