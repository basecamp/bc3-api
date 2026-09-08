Backlinks
=========

A backlink records that one [recording][recordings] references another in its rich text content. The backlinks endpoint lists the recordings that reference a given recording — the "references to this" shown in the Basecamp UI.

Only backlinks from projects and pings the current user can access are returned, so two people requesting the same recording's backlinks may see different lists.

Endpoints:

- [Get backlinks](#get-backlinks)

Get backlinks
-------------

* `GET /recordings/2/backlinks.json` will return the most recent 20 recordings that reference the recording with an ID of `2`, newest first.

Each entry is a [recording][recordings] — the referencing recording, not the backlink itself.

###### Example JSON Response
```json
[
  {
    "id": 1069480024,
    "status": "active",
    "visible_to_clients": false,
    "created_at": "2026-07-19T14:22:11.000Z",
    "updated_at": "2026-07-19T14:22:11.000Z",
    "title": "Finalize launch checklist",
    "inherits_status": true,
    "type": "Todo",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958505/todos/1069480024.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958505/todos/1069480024",
    "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiLmdpZDovL2JjMy9SZWNvcmRpbmcvMTA2OTQ4MDAyND9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg1yZWFkYWJsZQY7AFQ=--0000000000000000000000000000000000000000.json",
    "subscription_url": "https://3.basecampapi.com/195539477/buckets/2085958505/recordings/1069480024/subscription.json",
    "parent": {
      "id": 1069479830,
      "title": "Launch",
      "type": "Todolist",
      "url": "https://3.basecampapi.com/195539477/buckets/2085958505/todolists/1069479830.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958505/todolists/1069479830"
    },
    "bucket": {
      "id": 2085958505,
      "name": "The Leto Laptop",
      "type": "Project"
    },
    "creator": {
      "id": 1049715929,
      "attachable_sgid": "BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiK2dpZDovL2JjMy9QZXJzb24vMTA0OTcxNTkyOT9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg9hdHRhY2hhYmxlBjsAVA==--0000000000000000000000000000000000000000",
      "name": "Matt Donahue",
      "personable_type": "User",
      "title": "Global Data Strategist",
      "tagline": null,
      "location": null,
      "created_at": "2026-05-28T17:22:27.821Z",
      "updated_at": "2026-05-28T17:22:27.821Z",
      "email_address": "matt@honchodesign.com",
      "bio": null,
      "admin": false,
      "owner": false,
      "client": false,
      "employee": false,
      "time_zone": "America/Chicago",
      "avatar_url": "https://3.basecampapi.com/195539477/people/BAhpBNlkkT4=--0000000000000000000000000000000000000000/avatar",
      "can_ping": true,
      "can_manage_projects": true,
      "can_manage_people": true,
      "can_access_timesheet": true,
      "can_access_hill_charts": true
    }
  }
]
```

###### Copy as cURL

```shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/recordings/2/backlinks.json
```

Legacy project-scoped routes
-----------------------------

The following project-scoped routes are still supported and will remain available, but flat routes above are the canonical form for new integrations.

* `GET /buckets/1/recordings/2/backlinks.json` → [Get backlinks](#get-backlinks)

[recordings]: recordings.md#recordings
