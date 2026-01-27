Timeline
========

The timeline shows recent activity across your Basecamp account or within a specific project. It provides a chronological feed of events like messages posted, to-dos completed, files uploaded, and more.

Endpoints:

- [Get timeline](#get-timeline)
- [Get project timeline](#get-project-timeline)
- [Get person's timeline](#get-persons-timeline)

Get timeline
------------

* `GET /reports/progress.json` will return a [paginated list][pagination] of timeline events across all projects the authenticated user can access.

###### Example JSON Response
<!-- START GET /reports/progress.json -->
```json
[
  {
    "id": 1069480455,
    "created_at": "2025-10-29T10:17:58.169Z",
    "kind": "message_created",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958503/messages/1069480455.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958503/messages/1069480455",
    "creator": {
      "id": 1049715955,
      "attachable_sgid": "BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiK2dpZDovL2JjMy9QZXJzb24vMTA0OTcxNTk1NT9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg9hdHRhY2hhYmxlBjsAVA==--6a8affd82c540e7c1f7e846b2b02fedb01bcd3f0",
      "name": "Victor Cooper",
      "email_address": "victor@honchodesign.com",
      "personable_type": "User",
      "title": "Chief Strategist",
      "bio": "Don't let your dreams be dreams",
      "location": "Chicago, IL",
      "created_at": "2025-10-10T11:41:42.284Z",
      "updated_at": "2025-10-10T11:41:43.054Z",
      "admin": true,
      "owner": true,
      "client": false,
      "employee": true,
      "time_zone": "America/Chicago",
      "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBPNkkT4=--5049939da9ea89df60ade5a1c42d324c1651c66c/avatar?v=1",
      "company": {
        "id": 1033447819,
        "name": "Honcho Design"
      },
      "can_ping": true,
      "can_manage_projects": true,
      "can_manage_people": true,
      "can_access_timesheet": true,
      "can_access_hill_charts": true
    },
    "action": "Victor added a new message called",
    "target": "We won Leto!",
    "title": "Victor added a new message called \"We won Leto!\"",
    "summary_excerpt": "It took a while, but we finally got the contract signed...",
    "avatars_sample": [],
    "bucket": {
      "id": 2085958503,
      "name": "The Leto Laptop",
      "url": "https://3.basecampapi.com/195539477/projects/2085958503.json",
      "app_url": "https://3.basecamp.com/195539477/projects/2085958503"
    },
    "attachments": []
  },
  {
    "id": 1069480522,
    "created_at": "2025-10-28T14:30:00.000Z",
    "kind": "todo_completed",
    "parent_recording_id": 1069479340,
    "url": "https://3.basecampapi.com/195539477/buckets/2085958503/todos/1069480522.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958503/todos/1069480522",
    "creator": {
      "id": 1049715936,
      "attachable_sgid": "BAh7CEkiCGdpZAY6BkVUSSIrZ2lkOi8vYmMzL1BlcnNvbi8xMDQ5NzE1OTM2P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg9hdHRhY2hhYmxlBjsAVEkiD2V4cGlyZXNfYXQGOwBUMA==--49bf4c17af8bc53bf5ecc54cfe98e24cc45aeaa0",
      "name": "Matt Donahue",
      "email_address": "matt@honchodesign.com",
      "personable_type": "User",
      "title": "Global Data Strategist",
      "bio": null,
      "location": null,
      "created_at": "2025-10-10T11:41:42.205Z",
      "updated_at": "2025-10-10T11:41:42.205Z",
      "admin": false,
      "owner": false,
      "client": false,
      "employee": false,
      "time_zone": "Etc/UTC",
      "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBOBkkT4=--78fb2ba7c3091268f41638ef90dee7dd32f395d6/avatar?v=1",
      "can_ping": true,
      "can_manage_projects": true,
      "can_manage_people": true,
      "can_access_timesheet": true,
      "can_access_hill_charts": true
    },
    "action": "Matt checked off a to-do",
    "target": "Launch planning",
    "title": "On \"Launch planning\", Matt checked off a to-do",
    "summary_excerpt": "Finalize press release copy",
    "avatars_sample": [],
    "bucket": {
      "id": 2085958503,
      "name": "The Leto Laptop",
      "url": "https://3.basecampapi.com/195539477/projects/2085958503.json",
      "app_url": "https://3.basecamp.com/195539477/projects/2085958503"
    },
    "attachments": []
  },
  {
    "id": 1069480600,
    "created_at": "2025-10-27T09:15:00.000Z",
    "kind": "schedule_entry_created",
    "parent_recording_id": 1069479345,
    "url": "https://3.basecampapi.com/195539477/buckets/2085958503/schedule_entries/1069480600.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958503/schedule_entries/1069480600",
    "creator": {
      "id": 1049715955,
      "attachable_sgid": "BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiK2dpZDovL2JjMy9QZXJzb24vMTA0OTcxNTk1NT9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg9hdHRhY2hhYmxlBjsAVA==--6a8affd82c540e7c1f7e846b2b02fedb01bcd3f0",
      "name": "Victor Cooper",
      "email_address": "victor@honchodesign.com",
      "personable_type": "User",
      "title": "Chief Strategist",
      "bio": "Don't let your dreams be dreams",
      "location": "Chicago, IL",
      "created_at": "2025-10-10T11:41:42.284Z",
      "updated_at": "2025-10-10T11:41:43.054Z",
      "admin": true,
      "owner": true,
      "client": false,
      "employee": true,
      "time_zone": "America/Chicago",
      "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBPNkkT4=--5049939da9ea89df60ade5a1c42d324c1651c66c/avatar?v=1",
      "company": {
        "id": 1033447819,
        "name": "Honcho Design"
      },
      "can_ping": true,
      "can_manage_projects": true,
      "can_manage_people": true,
      "can_access_timesheet": true,
      "can_access_hill_charts": true
    },
    "action": "Victor added an event",
    "target": "Project Schedule",
    "title": "On \"Project Schedule\", Victor added an event",
    "summary_excerpt": "Team kickoff meeting",
    "avatars_sample": [],
    "bucket": {
      "id": 2085958503,
      "name": "The Leto Laptop",
      "url": "https://3.basecampapi.com/195539477/projects/2085958503.json",
      "app_url": "https://3.basecamp.com/195539477/projects/2085958503"
    },
    "data": {
      "all_day": false,
      "starts_at": "2025-10-30T10:00:00.000-05:00",
      "ends_at": "2025-10-30T11:00:00.000-05:00"
    },
    "attachments": []
  },
  {
    "id": 1069480700,
    "created_at": "2025-10-26T16:45:00.000Z",
    "kind": "upload_created",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958503/uploads/1069480700.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958503/uploads/1069480700",
    "creator": {
      "id": 1049715936,
      "attachable_sgid": "BAh7CEkiCGdpZAY6BkVUSSIrZ2lkOi8vYmMzL1BlcnNvbi8xMDQ5NzE1OTM2P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg9hdHRhY2hhYmxlBjsAVEkiD2V4cGlyZXNfYXQGOwBUMA==--49bf4c17af8bc53bf5ecc54cfe98e24cc45aeaa0",
      "name": "Matt Donahue",
      "email_address": "matt@honchodesign.com",
      "personable_type": "User",
      "title": "Global Data Strategist",
      "bio": null,
      "location": null,
      "created_at": "2025-10-10T11:41:42.205Z",
      "updated_at": "2025-10-10T11:41:42.205Z",
      "admin": false,
      "owner": false,
      "client": false,
      "employee": false,
      "time_zone": "Etc/UTC",
      "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBOBkkT4=--78fb2ba7c3091268f41638ef90dee7dd32f395d6/avatar?v=1",
      "can_ping": true,
      "can_manage_projects": true,
      "can_manage_people": true,
      "can_access_timesheet": true,
      "can_access_hill_charts": true
    },
    "action": "Matt added a new file called",
    "target": "Product specs.pdf",
    "title": "Matt added a new file called \"Product specs.pdf\"",
    "summary_excerpt": null,
    "avatars_sample": [],
    "bucket": {
      "id": 2085958503,
      "name": "The Leto Laptop",
      "url": "https://3.basecampapi.com/195539477/projects/2085958503.json",
      "app_url": "https://3.basecamp.com/195539477/projects/2085958503"
    },
    "attachments": [
      {
        "id": 1069480700,
        "status": "active",
        "visible_to_clients": false,
        "created_at": "2025-10-26T16:45:00.000Z",
        "updated_at": "2025-10-26T16:45:00.000Z",
        "title": "Product specs.pdf",
        "inherits_status": true,
        "type": "Upload",
        "url": "https://3.basecampapi.com/195539477/buckets/2085958503/uploads/1069480700.json",
        "app_url": "https://3.basecamp.com/195539477/buckets/2085958503/uploads/1069480700",
        "content_type": "application/pdf",
        "byte_size": 245678,
        "filename": "Product specs.pdf",
        "download_url": "https://3.basecampapi.com/195539477/buckets/2085958503/uploads/1069480700/download/Product%20specs.pdf"
      }
    ]
  },
  {
    "id": 1069480800,
    "created_at": "2025-10-25T11:20:00.000Z",
    "kind": "chat_transcript_rollup",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958503/chats/1069479350.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958503/chats/1069479350",
    "creator": {
      "id": 1049715955,
      "attachable_sgid": "BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiK2dpZDovL2JjMy9QZXJzb24vMTA0OTcxNTk1NT9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg9hdHRhY2hhYmxlBjsAVA==--6a8affd82c540e7c1f7e846b2b02fedb01bcd3f0",
      "name": "Victor Cooper",
      "email_address": "victor@honchodesign.com",
      "personable_type": "User",
      "title": "Chief Strategist",
      "bio": "Don't let your dreams be dreams",
      "location": "Chicago, IL",
      "created_at": "2025-10-10T11:41:42.284Z",
      "updated_at": "2025-10-10T11:41:43.054Z",
      "admin": true,
      "owner": true,
      "client": false,
      "employee": true,
      "time_zone": "America/Chicago",
      "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBPNkkT4=--5049939da9ea89df60ade5a1c42d324c1651c66c/avatar?v=1",
      "company": {
        "id": 1033447819,
        "name": "Honcho Design"
      },
      "can_ping": true,
      "can_manage_projects": true,
      "can_manage_people": true,
      "can_access_timesheet": true,
      "can_access_hill_charts": true
    },
    "action": "3 people were chatting",
    "target": "Campfire",
    "title": "3 people were chatting",
    "summary_excerpt": "Victor, Matt, Annie",
    "avatars_sample": [
      "https://3.basecamp-static.com/195539477/people/BAhpBPNkkT4=--5049939da9ea89df60ade5a1c42d324c1651c66c/avatar?v=1",
      "https://3.basecamp-static.com/195539477/people/BAhpBOBkkT4=--78fb2ba7c3091268f41638ef90dee7dd32f395d6/avatar?v=1",
      "https://3.basecamp-static.com/195539477/people/BAhpBMtkkT4=--9927c47a4cbee30a7f9aea667882496aba799149/avatar?v=1"
    ],
    "bucket": {
      "id": 2085958503,
      "name": "The Leto Laptop",
      "url": "https://3.basecampapi.com/195539477/projects/2085958503.json",
      "app_url": "https://3.basecamp.com/195539477/projects/2085958503"
    },
    "attachments": []
  }
]
```
<!-- END GET /reports/progress.json -->

###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/reports/progress.json
```

Get project timeline
--------------------

* `GET /projects/1/timeline.json` will return a [paginated list][pagination] of timeline events in the project with an ID of `1`.

###### Example JSON Response
<!-- START GET /projects/1/timeline.json -->
```json
[
  {
    "id": 1069480455,
    "created_at": "2025-10-29T10:17:58.169Z",
    "kind": "message_created",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958503/messages/1069480455.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958503/messages/1069480455",
    "creator": {
      "id": 1049715955,
      "attachable_sgid": "BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiK2dpZDovL2JjMy9QZXJzb24vMTA0OTcxNTk1NT9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg9hdHRhY2hhYmxlBjsAVA==--6a8affd82c540e7c1f7e846b2b02fedb01bcd3f0",
      "name": "Victor Cooper",
      "email_address": "victor@honchodesign.com",
      "personable_type": "User",
      "title": "Chief Strategist",
      "bio": "Don't let your dreams be dreams",
      "location": "Chicago, IL",
      "created_at": "2025-10-10T11:41:42.284Z",
      "updated_at": "2025-10-10T11:41:43.054Z",
      "admin": true,
      "owner": true,
      "client": false,
      "employee": true,
      "time_zone": "America/Chicago",
      "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBPNkkT4=--5049939da9ea89df60ade5a1c42d324c1651c66c/avatar?v=1",
      "company": {
        "id": 1033447819,
        "name": "Honcho Design"
      },
      "can_ping": true,
      "can_manage_projects": true,
      "can_manage_people": true,
      "can_access_timesheet": true,
      "can_access_hill_charts": true
    },
    "action": "Victor added a new message called",
    "target": "We won Leto!",
    "title": "Victor added a new message called \"We won Leto!\"",
    "summary_excerpt": "It took a while, but we finally got the contract signed...",
    "avatars_sample": [],
    "bucket": {
      "id": 2085958503,
      "name": "The Leto Laptop",
      "url": "https://3.basecampapi.com/195539477/projects/2085958503.json",
      "app_url": "https://3.basecamp.com/195539477/projects/2085958503"
    },
    "attachments": []
  },
  {
    "id": 1069480522,
    "created_at": "2025-10-28T14:30:00.000Z",
    "kind": "todo_completed",
    "parent_recording_id": 1069479340,
    "url": "https://3.basecampapi.com/195539477/buckets/2085958503/todos/1069480522.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958503/todos/1069480522",
    "creator": {
      "id": 1049715936,
      "attachable_sgid": "BAh7CEkiCGdpZAY6BkVUSSIrZ2lkOi8vYmMzL1BlcnNvbi8xMDQ5NzE1OTM2P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg9hdHRhY2hhYmxlBjsAVEkiD2V4cGlyZXNfYXQGOwBUMA==--49bf4c17af8bc53bf5ecc54cfe98e24cc45aeaa0",
      "name": "Matt Donahue",
      "email_address": "matt@honchodesign.com",
      "personable_type": "User",
      "title": "Global Data Strategist",
      "bio": null,
      "location": null,
      "created_at": "2025-10-10T11:41:42.205Z",
      "updated_at": "2025-10-10T11:41:42.205Z",
      "admin": false,
      "owner": false,
      "client": false,
      "employee": false,
      "time_zone": "Etc/UTC",
      "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBOBkkT4=--78fb2ba7c3091268f41638ef90dee7dd32f395d6/avatar?v=1",
      "can_ping": true,
      "can_manage_projects": true,
      "can_manage_people": true,
      "can_access_timesheet": true,
      "can_access_hill_charts": true
    },
    "action": "Matt checked off a to-do",
    "target": "Launch planning",
    "title": "On \"Launch planning\", Matt checked off a to-do",
    "summary_excerpt": "Finalize press release copy",
    "avatars_sample": [],
    "bucket": {
      "id": 2085958503,
      "name": "The Leto Laptop",
      "url": "https://3.basecampapi.com/195539477/projects/2085958503.json",
      "app_url": "https://3.basecamp.com/195539477/projects/2085958503"
    },
    "attachments": []
  }
]
```
<!-- END GET /projects/1/timeline.json -->

###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/projects/1/timeline.json
```

Get person's timeline
---------------------

* `GET /reports/users/progress/1.json` will return a JSON object containing the person plus a [paginated list][pagination] (`events`) of timeline events created by the person with an ID of `1`.

###### Example JSON Response
<!-- START GET /reports/users/progress/1.json -->
```json
{
  "person": {
    "id": 1049715914,
    "attachable_sgid": "BAh7CEkiCGdpZAY6BkVUSSIrZ2lkOi8vYmMzL1BlcnNvbi8xMDQ5NzE1OTE0P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg9hdHRhY2hhYmxlBjsAVEkiD2V4cGlyZXNfYXQGOwBUMA==--ff006accb6e013cca785190fa38f42c091d24f1e",
    "name": "Victor Cooper",
    "email_address": "victor@honchodesign.com",
    "personable_type": "User",
    "title": "Chief Strategist",
    "bio": "Don't let your dreams be dreams",
    "location": "Chicago, IL",
    "created_at": "2025-10-10T11:41:42.284Z",
    "updated_at": "2025-10-10T11:41:43.054Z",
    "admin": true,
    "owner": true,
    "client": false,
    "employee": true,
    "time_zone": "America/Chicago",
    "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBPNkkT4=--5049939da9ea89df60ade5a1c42d324c1651c66c/avatar?v=1",
    "company": {
      "id": 1033447819,
      "name": "Honcho Design"
    },
    "can_ping": true,
    "can_manage_projects": true,
    "can_manage_people": true,
    "can_access_timesheet": true,
    "can_access_hill_charts": true
  },
  "events": [
    {
      "id": 1069479890,
      "created_at": "2025-10-10T14:23:58.169Z",
      "kind": "message_created",
      "url": "https://3.basecampapi.com/195539477/buckets/2085958499/messages/1069479455.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958499/messages/1069479455",
      "creator": {
        "id": 1049715914,
        "attachable_sgid": "BAh7CEkiCGdpZAY6BkVUSSIrZ2lkOi8vYmMzL1BlcnNvbi8xMDQ5NzE1OTE0P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg9hdHRhY2hhYmxlBjsAVEkiD2V4cGlyZXNfYXQGOwBUMA==--ff006accb6e013cca785190fa38f42c091d24f1e",
        "name": "Victor Cooper",
        "email_address": "victor@honchodesign.com",
        "personable_type": "User",
        "title": "Chief Strategist",
        "bio": "Don't let your dreams be dreams",
        "location": "Chicago, IL",
        "created_at": "2025-10-10T11:41:42.284Z",
        "updated_at": "2025-10-10T11:41:43.054Z",
        "admin": true,
        "owner": true,
        "client": false,
        "employee": true,
        "time_zone": "America/Chicago",
        "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBPNkkT4=--5049939da9ea89df60ade5a1c42d324c1651c66c/avatar?v=1",
        "company": {
          "id": 1033447819,
          "name": "Honcho Design"
        },
        "can_ping": true,
        "can_manage_projects": true,
        "can_manage_people": true,
        "can_access_timesheet": true,
        "can_access_hill_charts": true
      },
      "action": "posted",
      "target": "We won Leto!",
      "title": "posted We won Leto!",
      "summary_excerpt": "Great news everyone...",
      "avatars_sample": [],
      "bucket": {
        "id": 2085958499,
        "name": "The Leto Laptop",
        "url": "https://3.basecampapi.com/195539477/projects/2085958499.json",
        "app_url": "https://3.basecamp.com/195539477/projects/2085958499"
      }
    }
  ]
}
```
<!-- END GET /reports/users/progress/1.json -->

###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/reports/users/progress/1.json
```

Event kinds
-----------

The `kind` field indicates what type of activity occurred. Common values include:

| Kind | Description |
|------|-------------|
| `message_created` | A new message was posted |
| `comment_created` | A comment was added |
| `todo_created` | A new to-do was added |
| `todo_completed` | A to-do was checked off |
| `upload_created` | A file was uploaded |
| `document_created` | A document was created |
| `schedule_entry_created` | A calendar event was added |
| `schedule_entry_rescheduled` | A calendar event was rescheduled |
| `question_created` | An automatic check-in was started |
| `question_answer_created` | Someone answered a check-in |
| `chat_transcript_rollup` | A summary of Campfire chat activity |
| `kanban_card_created` | A card was added to a Card Table |
| `kanban_card_completed` | A card was completed |
| `inbox_forward_created` | An email was forwarded |
| `client_correspondence_created` | A message was sent to a client |

Event fields
------------

Each timeline event includes these fields:

| Field | Description |
|-------|-------------|
| `id` | Unique identifier for the event |
| `created_at` | When the event occurred |
| `kind` | The type of activity (see [Event kinds](#event-kinds)) |
| `parent_recording_id` | ID of the parent container (e.g., to-do list for a to-do), if applicable |
| `url` | API URL to fetch the item |
| `app_url` | Link to view the item in Basecamp |
| `creator` | The [person][person] who performed the action |
| `action` | Human-readable description of the action |
| `target` | The name of the parent container or item affected |
| `title` | Combined action and target as a complete sentence |
| `summary_excerpt` | A brief excerpt of the content, if available |
| `avatars_sample` | Array of avatar URLs (used for chat rollups showing participants) |
| `bucket` | The [project][project] where the event occurred |
| `data` | Additional event-specific data (e.g., schedule entry times) |
| `attachments` | Array of attached files, if any |

Schedule entry data
-------------------

Events with `kind` of `schedule_entry_created` or `schedule_entry_rescheduled` include a `data` object with schedule details:

```json
{
  "data": {
    "all_day": false,
    "starts_at": "2025-10-30T10:00:00.000-05:00",
    "ends_at": "2025-10-30T11:00:00.000-05:00"
  }
}
```

[pagination]: https://github.com/basecamp/bc3-api/blob/master/README.md#pagination
[person]: https://github.com/basecamp/bc3-api/blob/master/sections/people.md#people
[project]: https://github.com/basecamp/bc3-api/blob/master/sections/projects.md#projects
