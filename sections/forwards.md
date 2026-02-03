Forwards
========

Endpoints:

- [Get forwards](#get-forwards)
- [Get a forward](#get-a-forward)
- [Trash a forward][1]


Get forwards
------------

* `GET /buckets/1/inboxes/3/forwards.json` will return a [paginated list][2] of active forwards in the project with an ID of `1` and the inbox with an ID of `3`.

To get the inbox ID for a project, see the [Get inbox][3] endpoint.

###### Example JSON Response
<!-- START GET /buckets/1/inboxes/3/forwards.json -->
```json
[
  {
    "id": 1069479085,
    "status": "active",
    "visible_to_clients": false,
    "created_at": "2026-01-31T08:30:27.890Z",
    "updated_at": "2026-01-31T08:30:28.904Z",
    "title": "Can we make the logo pop?",
    "inherits_status": true,
    "type": "Inbox::Forward",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958502/inbox_forwards/1069479085.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958502/inbox_forwards/1069479085",
    "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiLmdpZDovL2JjMy9SZWNvcmRpbmcvMTA2OTQ3OTA4NT9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg1yZWFkYWJsZQY7AFQ=--5dbe6f761324a7399d519608a8b79f9a518b791d.json",
    "subscription_url": "https://3.basecampapi.com/195539477/buckets/2085958502/recordings/1069479085/subscription.json",
    "parent": {
      "id": 1069478988,
      "title": "Email Forwards",
      "type": "Inbox",
      "url": "https://3.basecampapi.com/195539477/buckets/2085958502/inboxes/1069478988.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958502/inboxes/1069478988"
    },
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
    "content": "---------- Forwarded message ---------- From: \"Henry Bowman\"  Date: Oct 15, 2013 1:13 AM Subject: Can we make the logo pop? To: \"Victor Cooper\"  Hey Victor, I know it's late at night, but I had a quick thought about the logo. It feels, I dunno, flat. Is there anything you could do to make it pop? I'm thinking it needs more sizzle. More... SOMETHING. Maybe we could try adding a rainbow? Let's take a look mid-day tomorrow and re-group with the rest of the team. Cheers, Henry",
    "subject": "Can we make the logo pop?",
    "from": null,
    "replies_count": 2,
    "replies_url": "https://3.basecampapi.com/195539477/buckets/2085958502/inbox_forwards/1069479085/replies.json"
  }
]
```
<!-- END GET /buckets/1/inboxes/3/forwards.json -->

###### Copy as cURL

```shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/inboxes/3/forwards.json
```


Get a forward
-------------

* `GET /buckets/1/inbox_forwards/2.json` will return the forward with an ID of `2` in the project with an ID of `1`.

###### Example JSON Response
<!-- START GET /buckets/1/inbox_forwards/2.json -->
```json
{
  "id": 1069479084,
  "status": "active",
  "visible_to_clients": false,
  "created_at": "2026-01-31T08:30:27.536Z",
  "updated_at": "2026-01-31T08:30:27.564Z",
  "title": "Some technical details",
  "inherits_status": true,
  "type": "Inbox::Forward",
  "url": "https://3.basecampapi.com/195539477/buckets/2085958502/inbox_forwards/1069479084.json",
  "app_url": "https://3.basecamp.com/195539477/buckets/2085958502/inbox_forwards/1069479084",
  "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiLmdpZDovL2JjMy9SZWNvcmRpbmcvMTA2OTQ3OTA4ND9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg1yZWFkYWJsZQY7AFQ=--e82f515d3ab363490c1fe06e0d733db9d6f623e9.json",
  "subscription_url": "https://3.basecampapi.com/195539477/buckets/2085958502/recordings/1069479084/subscription.json",
  "parent": {
    "id": 1069478988,
    "title": "Email Forwards",
    "type": "Inbox",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958502/inboxes/1069478988.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958502/inboxes/1069478988"
  },
  "bucket": {
    "id": 2085958502,
    "name": "Honcho Design Newsroom",
    "type": "Project"
  },
  "creator": {
    "id": 1049715938,
    "attachable_sgid": "BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiK2dpZDovL2JjMy9QZXJzb24vMTA0OTcxNTkzOD9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg9hdHRhY2hhYmxlBjsAVA==--4ccc567a0a3b10e354bca909b704637b601f0b16",
    "name": "Annie Bryan",
    "email_address": "annie@honchodesign.com",
    "personable_type": "User",
    "title": "Central Markets Manager",
    "bio": "To open a store is easy, to keep it open is an art",
    "location": null,
    "created_at": "2026-01-31T08:29:42.795Z",
    "updated_at": "2026-01-31T08:29:42.795Z",
    "admin": false,
    "owner": false,
    "client": false,
    "employee": true,
    "time_zone": "America/Chicago",
    "avatar_url": "https://3.basecampapi.com/195539477/people/BAhpBOJkkT4=--732a71fbd28ec10d9bf4466abd3588a8bea40bdb/avatar?v=1",
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
  "content": "---------- Forwarded message ---------- From: \"Beth Allen\"  Date: Oct 13, 2013 1:38 PM Subject: Some technical details To: \"Annie Bryan\"  Hey Team Honcho, Just wanted to let you know I'm a big fan of your blog. Your writing is so inspiring. Thanks for sharing!",
  "subject": "Some technical details",
  "from": null,
  "replies_count": 0,
  "replies_url": "https://3.basecampapi.com/195539477/buckets/2085958502/inbox_forwards/1069479084/replies.json"
}
```
<!-- END GET /buckets/1/inbox_forwards/2.json -->

###### Copy as cURL

```shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/inbox_forwards/2.json
```


[1]: https://github.com/basecamp/bc3-api/blob/master/sections/recordings.md#trash-a-recording
[2]: https://github.com/basecamp/bc3-api/blob/master/README.md#pagination
[3]: https://github.com/basecamp/bc3-api/blob/master/sections/inboxes.md#inboxes
