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
  "id": 1069479399,
  "status": "active",
  "visible_to_clients": false,
  "created_at": "2026-01-31T08:32:04.723Z",
  "updated_at": "2026-01-31T08:33:00.714Z",
  "title": "Card Table",
  "inherits_status": true,
  "type": "Kanban::Board",
  "url": "https://3.basecampapi.com/195539477/buckets/2085958504/card_tables/1069479399.json",
  "app_url": "https://3.basecamp.com/195539477/buckets/2085958504/card_tables/1069479399",
  "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiLmdpZDovL2JjMy9SZWNvcmRpbmcvMTA2OTQ3OTM5OT9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg1yZWFkYWJsZQY7AFQ=--4c62f9ab0364fa8feecc3d38b70fc066bfa6bdb9.json",
  "subscription_url": "https://3.basecampapi.com/195539477/buckets/2085958504/recordings/1069479399/subscription.json",
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
  "subscribers": [
    {
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
    }
  ],
  "public_link_url": "https://3.basecampapi.com/195539477/buckets/2085958504/recordings/1069479399/publication",
  "lists": [
    {
      "id": 1069479400,
      "status": "active",
      "visible_to_clients": false,
      "created_at": "2026-01-31T08:32:04.760Z",
      "updated_at": "2026-01-31T08:33:00.710Z",
      "title": "Triage",
      "inherits_status": true,
      "type": "Kanban::Triage",
      "url": "https://3.basecampapi.com/195539477/buckets/2085958504/card_tables/columns/1069479400.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958504/card_tables/columns/1069479400",
      "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiLmdpZDovL2JjMy9SZWNvcmRpbmcvMTA2OTQ3OTQwMD9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg1yZWFkYWJsZQY7AFQ=--76b2dfcd8a8eea46097d4f1ce80acf09d339e6d2.json",
      "subscription_url": "https://3.basecampapi.com/195539477/buckets/2085958504/recordings/1069479400/subscription.json",
      "parent": {
        "id": 1069479399,
        "title": "Card Table",
        "type": "Kanban::Board",
        "url": "https://3.basecampapi.com/195539477/buckets/2085958504/card_tables/1069479399.json",
        "app_url": "https://3.basecamp.com/195539477/buckets/2085958504/card_tables/1069479399"
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
      "description": null,
      "subscribers": [
        {
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
        }
      ],
      "color": null,
      "cards_count": 1,
      "comment_count": 0,
      "cards_url": "https://3.basecampapi.com/195539477/buckets/2085958504/card_tables/lists/1069479400/cards.json"
    },
    {
      "id": 1069479401,
      "status": "active",
      "visible_to_clients": false,
      "created_at": "2026-01-31T08:32:04.829Z",
      "updated_at": "2026-01-31T08:32:04.853Z",
      "title": "Not now",
      "inherits_status": true,
      "type": "Kanban::NotNowColumn",
      "url": "https://3.basecampapi.com/195539477/buckets/2085958504/card_tables/columns/1069479401.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958504/card_tables/columns/1069479401",
      "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiLmdpZDovL2JjMy9SZWNvcmRpbmcvMTA2OTQ3OTQwMT9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg1yZWFkYWJsZQY7AFQ=--c38ff652825662db3002123f804f6ff4d4ba010d.json",
      "subscription_url": "https://3.basecampapi.com/195539477/buckets/2085958504/recordings/1069479401/subscription.json",
      "parent": {
        "id": 1069479399,
        "title": "Card Table",
        "type": "Kanban::Board",
        "url": "https://3.basecampapi.com/195539477/buckets/2085958504/card_tables/1069479399.json",
        "app_url": "https://3.basecamp.com/195539477/buckets/2085958504/card_tables/1069479399"
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
      "description": null,
      "subscribers": [
        {
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
        }
      ],
      "color": null,
      "cards_count": 0,
      "comment_count": 0,
      "cards_url": "https://3.basecampapi.com/195539477/buckets/2085958504/card_tables/lists/1069479401/cards.json"
    },
    {
      "id": 1069479402,
      "status": "active",
      "visible_to_clients": false,
      "created_at": "2026-01-31T08:32:04.899Z",
      "updated_at": "2026-01-31T08:32:04.920Z",
      "title": "Figuring it out",
      "inherits_status": true,
      "type": "Kanban::Column",
      "url": "https://3.basecampapi.com/195539477/buckets/2085958504/card_tables/columns/1069479402.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958504/card_tables/columns/1069479402",
      "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiLmdpZDovL2JjMy9SZWNvcmRpbmcvMTA2OTQ3OTQwMj9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg1yZWFkYWJsZQY7AFQ=--ccb1881249e7c3823899fb63807fdf71e67a68ab.json",
      "subscription_url": "https://3.basecampapi.com/195539477/buckets/2085958504/recordings/1069479402/subscription.json",
      "position": 1,
      "parent": {
        "id": 1069479399,
        "title": "Card Table",
        "type": "Kanban::Board",
        "url": "https://3.basecampapi.com/195539477/buckets/2085958504/card_tables/1069479399.json",
        "app_url": "https://3.basecamp.com/195539477/buckets/2085958504/card_tables/1069479399"
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
      "description": null,
      "subscribers": [
        {
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
        }
      ],
      "color": "purple",
      "cards_count": 0,
      "comment_count": 0,
      "cards_url": "https://3.basecampapi.com/195539477/buckets/2085958504/card_tables/lists/1069479402/cards.json"
    },
    {
      "id": 1069479403,
      "status": "active",
      "visible_to_clients": false,
      "created_at": "2026-01-31T08:32:04.976Z",
      "updated_at": "2026-01-31T08:32:04.997Z",
      "title": "In progress",
      "inherits_status": true,
      "type": "Kanban::Column",
      "url": "https://3.basecampapi.com/195539477/buckets/2085958504/card_tables/columns/1069479403.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958504/card_tables/columns/1069479403",
      "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiLmdpZDovL2JjMy9SZWNvcmRpbmcvMTA2OTQ3OTQwMz9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg1yZWFkYWJsZQY7AFQ=--3f35474fda2b034850dd6f71da9aaf6e737fdfbf.json",
      "subscription_url": "https://3.basecampapi.com/195539477/buckets/2085958504/recordings/1069479403/subscription.json",
      "position": 2,
      "parent": {
        "id": 1069479399,
        "title": "Card Table",
        "type": "Kanban::Board",
        "url": "https://3.basecampapi.com/195539477/buckets/2085958504/card_tables/1069479399.json",
        "app_url": "https://3.basecamp.com/195539477/buckets/2085958504/card_tables/1069479399"
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
      "description": null,
      "subscribers": [
        {
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
        }
      ],
      "color": "orange",
      "cards_count": 0,
      "comment_count": 0,
      "cards_url": "https://3.basecampapi.com/195539477/buckets/2085958504/card_tables/lists/1069479403/cards.json"
    },
    {
      "id": 1069479404,
      "status": "active",
      "visible_to_clients": false,
      "created_at": "2026-01-31T08:32:05.051Z",
      "updated_at": "2026-01-31T08:32:05.073Z",
      "title": "Done",
      "inherits_status": true,
      "type": "Kanban::DoneColumn",
      "url": "https://3.basecampapi.com/195539477/buckets/2085958504/card_tables/columns/1069479404.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958504/card_tables/columns/1069479404",
      "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiLmdpZDovL2JjMy9SZWNvcmRpbmcvMTA2OTQ3OTQwND9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg1yZWFkYWJsZQY7AFQ=--999257f5e2a3be18e6cd145f0eb7b91e5f417d5e.json",
      "subscription_url": "https://3.basecampapi.com/195539477/buckets/2085958504/recordings/1069479404/subscription.json",
      "parent": {
        "id": 1069479399,
        "title": "Card Table",
        "type": "Kanban::Board",
        "url": "https://3.basecampapi.com/195539477/buckets/2085958504/card_tables/1069479399.json",
        "app_url": "https://3.basecamp.com/195539477/buckets/2085958504/card_tables/1069479399"
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
      "description": null,
      "subscribers": [
        {
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
        }
      ],
      "color": null,
      "cards_count": 0,
      "comment_count": 0,
      "cards_url": "https://3.basecampapi.com/195539477/buckets/2085958504/card_tables/lists/1069479404/cards.json"
    }
  ]
}
```
<!-- END GET /buckets/1/card_tables/2.json -->
###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/card_tables/2.json
```
