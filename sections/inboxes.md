Inboxes
=======

All forwards in a project are children of an Inbox resource.

Endpoints:

- [Get inbox](#get-inbox)


Get inbox
---------

* `GET /inboxes/2.json` will return the inbox with an ID of `2`.

To get the inbox ID for a project, see the [Get a project][1] endpoint's `dock` payload. To retrieve its forwards, see the [Get forwards][2] endpoint.

###### Example JSON Response
<!-- START GET /inboxes/2.json -->
```json
{
  "id": 1069478988,
  "status": "active",
  "visible_to_clients": false,
  "created_at": "2026-02-12T06:09:02.464Z",
  "updated_at": "2026-02-12T06:09:09.085Z",
  "title": "Email Forwards",
  "inherits_status": true,
  "type": "Inbox",
  "url": "https://3.basecampapi.com/195539477/buckets/2085958502/inboxes/1069478988.json",
  "app_url": "https://3.basecamp.com/195539477/buckets/2085958502/inboxes/1069478988",
  "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiLmdpZDovL2JjMy9SZWNvcmRpbmcvMTA2OTQ3ODk4OD9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg1yZWFkYWJsZQY7AFQ=--c30a3b3a7389e33d17a5e10f6c82070ad9efa4e8.json",
  "position": 6,
  "bucket": {
    "id": 2085958502,
    "name": "Honcho Design Newsroom",
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
    "created_at": "2026-02-12T06:08:49.342Z",
    "updated_at": "2026-02-12T06:08:50.871Z",
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
    "can_access_timesheet": false,
    "can_access_hill_charts": true
  },
  "forwards_count": 2,
  "forwards_url": "https://3.basecampapi.com/195539477/buckets/2085958502/inboxes/1069478988/forwards.json"
}
```
<!-- END GET /inboxes/2.json -->

###### Copy as cURL

```shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/inboxes/2.json
```


Legacy project-scoped routes
-----------------------------

The following project-scoped routes are still supported and will remain available, but flat routes above are the canonical form for new integrations.

* `GET /buckets/1/inboxes/2.json` → [Get inbox](#get-inbox)

[1]: https://github.com/basecamp/bc3-api/blob/master/sections/projects.md#get-a-project
[2]: https://github.com/basecamp/bc3-api/blob/master/sections/forwards.md#get-forwards
