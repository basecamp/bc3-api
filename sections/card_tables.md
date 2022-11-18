Card tables
================

A card table is made of multiple columns which contain cards.

Endpoints:

- [Get a card table](#get-a-card-table)

Get a card table
--------------------

* `GET /buckets/1/card_tables/2.json` will return the card_table with an ID of `2` in the project with an ID of `1`.

###### Example JSON Response
<!-- START GET /buckets/1/card_tables/2.json -->
```json
{
  "id": 1069482091,
  "status": "active",
  "visible_to_clients": false,
  "created_at": "2022-11-18T09:51:27.237Z",
  "updated_at": "2022-11-18T09:51:41.811Z",
  "title": "Card Table",
  "inherits_status": true,
  "type": "Kanban::Board",
  "url": "https://3.basecampapi.com/195539477/buckets/2085958499/card_tables/1069482091.json",
  "app_url": "https://3.basecamp.com/195539477/buckets/2085958499/card_tables/1069482091",
  "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7CEkiCGdpZAY6BkVUSSIuZ2lkOi8vYmMzL1JlY29yZGluZy8xMDY5NDgyMDkxP2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg1yZWFkYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--0ed00a78611ecabf76bf8e7149d8e3f78dd98555.json",
  "subscription_url": "https://3.basecampapi.com/195539477/buckets/2085958499/recordings/1069482091/subscription.json",
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
  "subscribers": [
    {
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
    }
  ],
  "lists": [
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
    },
    {
      "id": 1069482093,
      "status": "active",
      "visible_to_clients": false,
      "created_at": "2022-11-18T09:51:27.247Z",
      "updated_at": "2022-11-18T09:51:27.250Z",
      "title": "Not now",
      "inherits_status": true,
      "type": "Kanban::NotNowColumn",
      "url": "https://3.basecampapi.com/195539477/buckets/2085958499/card_tables/columns/1069482093.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958499/card_tables/columns/1069482093",
      "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7CEkiCGdpZAY6BkVUSSIuZ2lkOi8vYmMzL1JlY29yZGluZy8xMDY5NDgyMDkzP2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg1yZWFkYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--58c22d71802b9b3c8f058cccda881985f4f84a89.json",
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
      "cards_count": 0,
      "comment_count": 0,
      "cards_url": "https://3.basecampapi.com/195539477/buckets/2085958499/card_tables/lists/1069482093/cards.json"
    },
    {
      "id": 1069482094,
      "status": "active",
      "visible_to_clients": false,
      "created_at": "2022-11-18T09:51:27.255Z",
      "updated_at": "2022-11-18T09:51:27.257Z",
      "title": "Figuring it out",
      "inherits_status": true,
      "type": "Kanban::Column",
      "url": "https://3.basecampapi.com/195539477/buckets/2085958499/card_tables/columns/1069482094.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958499/card_tables/columns/1069482094",
      "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7CEkiCGdpZAY6BkVUSSIuZ2lkOi8vYmMzL1JlY29yZGluZy8xMDY5NDgyMDk0P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg1yZWFkYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--17f55109b47dc85455bd93900f5a6604a68a6448.json",
      "position": 1,
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
      "color": "purple",
      "cards_count": 0,
      "comment_count": 0,
      "cards_url": "https://3.basecampapi.com/195539477/buckets/2085958499/card_tables/lists/1069482094/cards.json"
    },
    {
      "id": 1069482095,
      "status": "active",
      "visible_to_clients": false,
      "created_at": "2022-11-18T09:51:27.264Z",
      "updated_at": "2022-11-18T09:51:27.266Z",
      "title": "In progress",
      "inherits_status": true,
      "type": "Kanban::Column",
      "url": "https://3.basecampapi.com/195539477/buckets/2085958499/card_tables/columns/1069482095.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958499/card_tables/columns/1069482095",
      "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7CEkiCGdpZAY6BkVUSSIuZ2lkOi8vYmMzL1JlY29yZGluZy8xMDY5NDgyMDk1P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg1yZWFkYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--22547510d80f012f6ad8c1b7431442cc75364ebc.json",
      "position": 2,
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
      "color": "orange",
      "cards_count": 0,
      "comment_count": 0,
      "cards_url": "https://3.basecampapi.com/195539477/buckets/2085958499/card_tables/lists/1069482095/cards.json"
    },
    {
      "id": 1069482096,
      "status": "active",
      "visible_to_clients": false,
      "created_at": "2022-11-18T09:51:27.272Z",
      "updated_at": "2022-11-18T09:51:27.275Z",
      "title": "Done",
      "inherits_status": true,
      "type": "Kanban::DoneColumn",
      "url": "https://3.basecampapi.com/195539477/buckets/2085958499/card_tables/columns/1069482096.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958499/card_tables/columns/1069482096",
      "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7CEkiCGdpZAY6BkVUSSIuZ2lkOi8vYmMzL1JlY29yZGluZy8xMDY5NDgyMDk2P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg1yZWFkYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--37f969426b3aa60935eab0201009485bb3a77d72.json",
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
      "cards_count": 0,
      "comment_count": 0,
      "cards_url": "https://3.basecampapi.com/195539477/buckets/2085958499/card_tables/lists/1069482096/cards.json"
    }
  ]
}
```
<!-- END GET /buckets/1/card_tables/2.json -->
###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/card_tables/2.json
```
