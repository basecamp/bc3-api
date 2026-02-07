Inbox replies
==============

Inbox replies are nested under the recording ID of a [forward][forwards].

Endpoints:

- [Get inbox replies](#get-inbox-replies)
- [Get an inbox reply](#get-an-inbox-reply)

Get inbox replies
-------------------

* `GET /buckets/1/inbox_forwards/2/replies.json` will return a [paginated list][pagination] of inbox replies in the project with an ID of `1` and the forward with ID of `2`.

###### Example JSON Response
<!-- START GET /buckets/1/inbox_forwards/2/replies.json -->
```json
[
  {
    "id": 1069479086,
    "status": "active",
    "visible_to_clients": false,
    "created_at": "2025-11-13T01:32:00.000Z",
    "updated_at": "2025-11-13T01:32:00.000Z",
    "title": "Re: Can we make the logo pop?",
    "inherits_status": true,
    "type": "Inbox::Reply",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958502/inbox_replies/1069479086.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958502/inbox_forwards/1069479085#__recording_1069479086",
    "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiLmdpZDovL2JjMy9SZWNvcmRpbmcvMTA2OTQ3OTA4Nj9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg1yZWFkYWJsZQY7AFQ=--549cad1a70fa7d9365abbbd3b7e1bf5100c2b0fe.json",
    "boosts_count": 0,
    "boosts_url": "https://3.basecampapi.com/195539477/buckets/2085958502/recordings/1069479086/boosts.json",
    "parent": {
      "id": 1069479085,
      "title": "Can we make the logo pop?",
      "type": "Inbox::Forward",
      "url": "https://3.basecampapi.com/195539477/buckets/2085958502/inbox_forwards/1069479085.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958502/inbox_forwards/1069479085"
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
    "content": "Hey Henry!<br><br>Thanks for the quick feedback re: the logo. I know what you mean about feeling \"flat,\" but I'm not quite sure a rainbow is the way to go. I'll ping the design team and see what they can come up with later today. We'll post designs here in Basecamp when they're ready!<br><br><br>--VC"
  }
]
```
<!-- END GET /buckets/1/inbox_forwards/2/replies.json -->
###### Copy as cURL

```shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/inbox_forwards/2/replies.json
```

Get an inbox reply
-------------------

* `GET /buckets/1/inbox_forwards/2/replies/3.json` will return the inbox reply with an ID of `3` for the forward with an ID of `2` in the project with an ID of `1`.

###### Example JSON Response
<!-- START GET /buckets/1/inbox_forwards/2/replies/3.json -->
```json
{
  "id": 1069479089,
  "status": "active",
  "visible_to_clients": false,
  "created_at": "2025-11-13T03:12:00.000Z",
  "updated_at": "2025-11-13T03:12:00.000Z",
  "title": "Re: Can we make the logo pop?",
  "inherits_status": true,
  "type": "Inbox::Reply",
  "url": "https://3.basecampapi.com/195539477/buckets/2085958502/inbox_replies/1069479089.json",
  "app_url": "https://3.basecamp.com/195539477/buckets/2085958502/inbox_forwards/1069479085#__recording_1069479089",
  "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiLmdpZDovL2JjMy9SZWNvcmRpbmcvMTA2OTQ3OTA4OT9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg1yZWFkYWJsZQY7AFQ=--980876c579f6871de55c47d306bb5507f01e537d.json",
  "boosts_count": 0,
  "boosts_url": "https://3.basecampapi.com/195539477/buckets/2085958502/recordings/1069479089/boosts.json",
  "parent": {
    "id": 1069479085,
    "title": "Can we make the logo pop?",
    "type": "Inbox::Forward",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958502/inbox_forwards/1069479085.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958502/inbox_forwards/1069479085"
  },
  "bucket": {
    "id": 2085958502,
    "name": "Honcho Design Newsroom",
    "type": "Project"
  },
  "creator": {
    "id": 1049715934,
    "attachable_sgid": "BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiK2dpZDovL2JjMy9QZXJzb24vMTA0OTcxNTkzND9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg9hdHRhY2hhYmxlBjsAVA==--7d5db20d1c81088ab8e6377a3d5a9ce48a0e0966",
    "name": "henry@letobrand.com",
    "email_address": "henry@letobrand.com",
    "personable_type": "Outsider",
    "title": null,
    "bio": null,
    "location": null,
    "created_at": "2026-01-31T08:29:42.654Z",
    "updated_at": "2026-01-31T08:29:42.654Z",
    "admin": false,
    "owner": false,
    "client": false,
    "employee": false,
    "time_zone": "Etc/UTC",
    "avatar_url": "https://3.basecampapi.com/195539477/people/BAhpBN5kkT4=--f1717e24836df2add6c33af21bd7b02493a0b95c/avatar?v=1",
    "can_ping": true,
    "can_manage_projects": false,
    "can_manage_people": false,
    "can_access_timesheet": false,
    "can_access_hill_charts": false
  },
  "content": "Awesome, sounds good Victor!<br><br>Thanks again,<br>Henry"
}
```
<!-- END GET /buckets/1/inbox_forwards/2/replies/3.json -->
###### Copy as cURL

```shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/inbox_forwards/2/replies/3.json
```

[pagination]: https://github.com/basecamp/bc3-api/blob/master/README.md#pagination
[forwards]: https://github.com/basecamp/bc3-api/blob/master/sections/forwards.md#forwards
