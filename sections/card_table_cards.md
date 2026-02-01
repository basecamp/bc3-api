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
  "id": 1069479602,
  "status": "active",
  "visible_to_clients": false,
  "created_at": "2026-01-17T17:39:00.000Z",
  "updated_at": "2026-01-31T08:33:00.671Z",
  "title": "New and fancy UI",
  "inherits_status": true,
  "type": "Kanban::Card",
  "url": "https://3.basecampapi.com/195539477/buckets/2085958504/card_tables/cards/1069479602.json",
  "app_url": "https://3.basecamp.com/195539477/buckets/2085958504/card_tables/cards/1069479602",
  "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiLmdpZDovL2JjMy9SZWNvcmRpbmcvMTA2OTQ3OTYwMj9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg1yZWFkYWJsZQY7AFQ=--01e3068d33dbdea13db18776ee65cba52606a42f.json",
  "subscription_url": "https://3.basecampapi.com/195539477/buckets/2085958504/recordings/1069479602/subscription.json",
  "comments_count": 0,
  "comments_url": "https://3.basecampapi.com/195539477/buckets/2085958504/recordings/1069479602/comments.json",
  "position": 1,
  "parent": {
    "id": 1069479400,
    "title": "Triage",
    "type": "Kanban::Triage",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958504/card_tables/columns/1069479400.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958504/card_tables/columns/1069479400"
  },
  "bucket": {
    "id": 2085958504,
    "name": "The Leto Laptop",
    "type": "Project"
  },
  "creator": {
    "id": 1049715913,
    "attachable_sgid": "BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiK2dpZDovL2JjMy9QZXJzb24vMTA0OTcxNTkxMz9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg9hdHRhY2hhYmxlBjsAVA==--e627c45e6b34e08862da23906862412620e4d5d9",
    "name": "Victor Cooper",
    "email_address": "victor@honchodesign.com",
    "personable_type": "User",
    "title": "Chief Strategist",
    "bio": "Don’t let your dreams be dreams",
    "location": "Chicago, IL",
    "created_at": "2026-01-31T08:29:28.365Z",
    "updated_at": "2026-01-31T08:29:32.599Z",
    "admin": true,
    "owner": true,
    "client": false,
    "employee": true,
    "time_zone": "America/Chicago",
    "avatar_url": "https://3.basecampapi.com/195539477/people/BAhpBMlkkT4=--5fe7b70fbee7a7f0e2e1e19df7579e5d880c753d/avatar?v=1",
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
  "description": "Design a new and fancy UI",
  "completed": false,
  "content": "Design a new and fancy UI",
  "due_on": null,
  "assignees": [],
  "completion_subscribers": [],
  "completion_url": "https://3.basecampapi.com/195539477/buckets/2085958504/todos/1069479602/completion.json",
  "comment_count": 0,
  "steps": [
    {
      "id": 1069479603,
      "status": "active",
      "visible_to_clients": false,
      "created_at": "2026-01-17T18:31:00.000Z",
      "updated_at": "2026-01-17T18:31:00.000Z",
      "title": "Find inspiration",
      "inherits_status": true,
      "type": "Kanban::Step",
      "url": "https://3.basecampapi.com/195539477/buckets/2085958504/card_tables/steps/1069479603.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958504/card_tables/cards/1069479602#__recording_1069479603",
      "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiLmdpZDovL2JjMy9SZWNvcmRpbmcvMTA2OTQ3OTYwMz9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg1yZWFkYWJsZQY7AFQ=--9177e066a0dca31ce3492f80287c43b48df9f482.json",
      "position": 1,
      "parent": {
        "id": 1069479602,
        "title": "New and fancy UI",
        "type": "Kanban::Card",
        "url": "https://3.basecampapi.com/195539477/buckets/2085958504/card_tables/cards/1069479602.json",
        "app_url": "https://3.basecamp.com/195539477/buckets/2085958504/card_tables/cards/1069479602"
      },
      "bucket": {
        "id": 2085958504,
        "name": "The Leto Laptop",
        "type": "Project"
      },
      "creator": {
        "id": 1049715913,
        "attachable_sgid": "BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiK2dpZDovL2JjMy9QZXJzb24vMTA0OTcxNTkxMz9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg9hdHRhY2hhYmxlBjsAVA==--e627c45e6b34e08862da23906862412620e4d5d9",
        "name": "Victor Cooper",
        "email_address": "victor@honchodesign.com",
        "personable_type": "User",
        "title": "Chief Strategist",
        "bio": "Don’t let your dreams be dreams",
        "location": "Chicago, IL",
        "created_at": "2026-01-31T08:29:28.365Z",
        "updated_at": "2026-01-31T08:29:32.599Z",
        "admin": true,
        "owner": true,
        "client": false,
        "employee": true,
        "time_zone": "America/Chicago",
        "avatar_url": "https://3.basecampapi.com/195539477/people/BAhpBMlkkT4=--5fe7b70fbee7a7f0e2e1e19df7579e5d880c753d/avatar?v=1",
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
      "completed": false,
      "due_on": "2026-02-04",
      "assignees": [
        {
          "id": 1049715931,
          "attachable_sgid": "BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiK2dpZDovL2JjMy9QZXJzb24vMTA0OTcxNTkzMT9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg9hdHRhY2hhYmxlBjsAVA==--0c0826b2c47fc879d171cb99aa564d38e5a54a67",
          "name": "Tashia Hughes",
          "email_address": "tashia@honchodesign.com",
          "personable_type": "User",
          "title": "District Integration Architect",
          "bio": null,
          "location": null,
          "created_at": "2026-01-31T08:29:41.371Z",
          "updated_at": "2026-01-31T08:29:41.371Z",
          "admin": false,
          "owner": false,
          "client": false,
          "employee": false,
          "time_zone": "America/Chicago",
          "avatar_url": "https://3.basecampapi.com/195539477/people/BAhpBNtkkT4=--b72a5df90f237e00570273b726a82176287186e4/avatar?v=1",
          "can_ping": true,
          "can_manage_projects": true,
          "can_manage_people": true,
          "can_access_timesheet": true,
          "can_access_hill_charts": true
        }
      ],
      "completion_url": "/195539477/buckets/2085958504/card_tables/steps/1069479603/completions.json"
    }
  ]
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
* `notify` - whether to notify assignees, value `true` or `false`. Defaults to `false`.

This endpoint will return `201 Created` with the current JSON representation of the card if the creation was a success. See the [Get a card](#get-a-card) endpoint for more info on the payload.

###### Example JSON Request

``` json
{
  "title": "Investigation",
  "content": "Investigate on an issue in our todo list.",
  "due_on": "2021-01-01"
}
```

###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -H "Content-Type: application/json" \
  -d '{"title":"Investigation", "content": "Investigate on an issue in our todo list.", "due_on": "2021-01-01"}' \
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
  "title": "Updated investigation"
}
```

###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -H "Content-Type: application/json" \
  -d '{"title":"Updated investigation"}' -X PUT \
  https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/card_tables/cards/2.json
```

Move a card
-----------------------

* `POST /buckets/1/card_tables/cards/2/moves.json` allows moving of a card with id `2` in the project with ID `1`.

**Required parameters**: `column_id` of the column destination

This endpoint will return `204 No Content` if the update was a success.

###### Example JSON Request

``` json
{
  "column_id": 3
}
```
###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -H "Content-Type: application/json" \
  -d '{"column_id": 3}' \
  https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/card_tables/cards/2/moves.json
```

[pagination]: https://github.com/basecamp/bc3-api/blob/master/README.md#pagination
[rich]: https://github.com/basecamp/bc3-api/blob/master/sections/rich_text.md
[people]: https://github.com/basecamp/bc3-api/blob/master/sections/people.md#get-all-people
