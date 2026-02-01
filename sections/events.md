Events
======

An event is created any time a [recording][recordings] changes.

Endpoints:

- [Get events](#get-events)

Get events
----------

* `GET /buckets/1/recordings/2/events.json` will return a [paginated list][pagination] of events for the recording with an ID of `2` in the project with an ID of `1`.

###### Example JSON Response
<!-- START GET /buckets/1/recordings/2/events.json -->
```json
[
  {
    "id": 1071915468,
    "recording_id": 1069479766,
    "action": "adopted",
    "details": {
      "new_parent_id": 1069479743,
      "parent_id_was": 1069479745,
      "notified_recipient_ids": []
    },
    "created_at": "2026-01-31T08:33:38.190Z",
    "creator": {
      "id": 1049715945,
      "attachable_sgid": "BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiK2dpZDovL2JjMy9QZXJzb24vMTA0OTcxNTk0NT9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg9hdHRhY2hhYmxlBjsAVA==--573c6935f53af21625ccfd45e28af57c2bbeff49",
      "name": "Victor Cooper",
      "email_address": null,
      "personable_type": "DummyUser",
      "title": null,
      "bio": null,
      "location": null,
      "created_at": "2026-01-31T08:33:28.806Z",
      "updated_at": "2026-01-31T08:33:28.806Z",
      "admin": false,
      "owner": false,
      "client": false,
      "employee": false,
      "time_zone": "America/Chicago",
      "avatar_url": "https://3.basecampapi.com/195539477/people/BAhpBOlkkT4=--eebbe1ab1b28f5fcf32a1c0ff3644e06931fbcfa/avatar?v=1",
      "can_ping": true,
      "can_manage_projects": false,
      "can_manage_people": false,
      "can_access_timesheet": false,
      "can_access_hill_charts": false
    }
  },
  {
    "id": 1071915469,
    "recording_id": 1069479766,
    "action": "completed",
    "details": {
      "notified_recipient_ids": []
    },
    "created_at": "2026-01-26T17:43:00.000Z",
    "creator": {
      "id": 1049715945,
      "attachable_sgid": "BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiK2dpZDovL2JjMy9QZXJzb24vMTA0OTcxNTk0NT9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg9hdHRhY2hhYmxlBjsAVA==--573c6935f53af21625ccfd45e28af57c2bbeff49",
      "name": "Victor Cooper",
      "email_address": null,
      "personable_type": "DummyUser",
      "title": null,
      "bio": null,
      "location": null,
      "created_at": "2026-01-31T08:33:28.806Z",
      "updated_at": "2026-01-31T08:33:28.806Z",
      "admin": false,
      "owner": false,
      "client": false,
      "employee": false,
      "time_zone": "America/Chicago",
      "avatar_url": "https://3.basecampapi.com/195539477/people/BAhpBOlkkT4=--eebbe1ab1b28f5fcf32a1c0ff3644e06931fbcfa/avatar?v=1",
      "can_ping": true,
      "can_manage_projects": false,
      "can_manage_people": false,
      "can_access_timesheet": false,
      "can_access_hill_charts": false
    }
  },
  {
    "id": 1071915467,
    "recording_id": 1069479766,
    "action": "adopted",
    "details": {
      "new_parent_id": 1069479745,
      "parent_id_was": 1069479742,
      "notified_recipient_ids": []
    },
    "created_at": "2026-01-25T17:43:00.000Z",
    "creator": {
      "id": 1049715945,
      "attachable_sgid": "BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiK2dpZDovL2JjMy9QZXJzb24vMTA0OTcxNTk0NT9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg9hdHRhY2hhYmxlBjsAVA==--573c6935f53af21625ccfd45e28af57c2bbeff49",
      "name": "Victor Cooper",
      "email_address": null,
      "personable_type": "DummyUser",
      "title": null,
      "bio": null,
      "location": null,
      "created_at": "2026-01-31T08:33:28.806Z",
      "updated_at": "2026-01-31T08:33:28.806Z",
      "admin": false,
      "owner": false,
      "client": false,
      "employee": false,
      "time_zone": "America/Chicago",
      "avatar_url": "https://3.basecampapi.com/195539477/people/BAhpBOlkkT4=--eebbe1ab1b28f5fcf32a1c0ff3644e06931fbcfa/avatar?v=1",
      "can_ping": true,
      "can_manage_projects": false,
      "can_manage_people": false,
      "can_access_timesheet": false,
      "can_access_hill_charts": false
    }
  },
  {
    "id": 1071915466,
    "recording_id": 1069479766,
    "action": "adopted",
    "details": {
      "new_parent_id": 1069479742,
      "parent_id_was": 1069479744,
      "notified_recipient_ids": []
    },
    "created_at": "2026-01-23T17:43:00.000Z",
    "creator": {
      "id": 1049715945,
      "attachable_sgid": "BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiK2dpZDovL2JjMy9QZXJzb24vMTA0OTcxNTk0NT9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg9hdHRhY2hhYmxlBjsAVA==--573c6935f53af21625ccfd45e28af57c2bbeff49",
      "name": "Victor Cooper",
      "email_address": null,
      "personable_type": "DummyUser",
      "title": null,
      "bio": null,
      "location": null,
      "created_at": "2026-01-31T08:33:28.806Z",
      "updated_at": "2026-01-31T08:33:28.806Z",
      "admin": false,
      "owner": false,
      "client": false,
      "employee": false,
      "time_zone": "America/Chicago",
      "avatar_url": "https://3.basecampapi.com/195539477/people/BAhpBOlkkT4=--eebbe1ab1b28f5fcf32a1c0ff3644e06931fbcfa/avatar?v=1",
      "can_ping": true,
      "can_manage_projects": false,
      "can_manage_people": false,
      "can_access_timesheet": false,
      "can_access_hill_charts": false
    }
  },
  {
    "id": 1071915465,
    "recording_id": 1069479766,
    "action": "adopted",
    "details": {
      "new_parent_id": 1069479744,
      "parent_id_was": 1069479741,
      "notified_recipient_ids": []
    },
    "created_at": "2026-01-21T17:43:00.000Z",
    "creator": {
      "id": 1049715945,
      "attachable_sgid": "BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiK2dpZDovL2JjMy9QZXJzb24vMTA0OTcxNTk0NT9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg9hdHRhY2hhYmxlBjsAVA==--573c6935f53af21625ccfd45e28af57c2bbeff49",
      "name": "Victor Cooper",
      "email_address": null,
      "personable_type": "DummyUser",
      "title": null,
      "bio": null,
      "location": null,
      "created_at": "2026-01-31T08:33:28.806Z",
      "updated_at": "2026-01-31T08:33:28.806Z",
      "admin": false,
      "owner": false,
      "client": false,
      "employee": false,
      "time_zone": "America/Chicago",
      "avatar_url": "https://3.basecampapi.com/195539477/people/BAhpBOlkkT4=--eebbe1ab1b28f5fcf32a1c0ff3644e06931fbcfa/avatar?v=1",
      "can_ping": true,
      "can_manage_projects": false,
      "can_manage_people": false,
      "can_access_timesheet": false,
      "can_access_hill_charts": false
    }
  },
  {
    "id": 1071915464,
    "recording_id": 1069479766,
    "action": "adopted",
    "details": {
      "new_parent_id": 1069479741,
      "parent_id_was": 1069479739,
      "notified_recipient_ids": []
    },
    "created_at": "2026-01-21T17:43:00.000Z",
    "creator": {
      "id": 1049715945,
      "attachable_sgid": "BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiK2dpZDovL2JjMy9QZXJzb24vMTA0OTcxNTk0NT9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg9hdHRhY2hhYmxlBjsAVA==--573c6935f53af21625ccfd45e28af57c2bbeff49",
      "name": "Victor Cooper",
      "email_address": null,
      "personable_type": "DummyUser",
      "title": null,
      "bio": null,
      "location": null,
      "created_at": "2026-01-31T08:33:28.806Z",
      "updated_at": "2026-01-31T08:33:28.806Z",
      "admin": false,
      "owner": false,
      "client": false,
      "employee": false,
      "time_zone": "America/Chicago",
      "avatar_url": "https://3.basecampapi.com/195539477/people/BAhpBOlkkT4=--eebbe1ab1b28f5fcf32a1c0ff3644e06931fbcfa/avatar?v=1",
      "can_ping": true,
      "can_manage_projects": false,
      "can_manage_people": false,
      "can_access_timesheet": false,
      "can_access_hill_charts": false
    }
  },
  {
    "id": 1071915463,
    "recording_id": 1069479766,
    "action": "created",
    "details": {
      "notified_recipient_ids": []
    },
    "created_at": "2026-01-11T17:43:00.000Z",
    "creator": {
      "id": 1049715945,
      "attachable_sgid": "BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiK2dpZDovL2JjMy9QZXJzb24vMTA0OTcxNTk0NT9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg9hdHRhY2hhYmxlBjsAVA==--573c6935f53af21625ccfd45e28af57c2bbeff49",
      "name": "Victor Cooper",
      "email_address": null,
      "personable_type": "DummyUser",
      "title": null,
      "bio": null,
      "location": null,
      "created_at": "2026-01-31T08:33:28.806Z",
      "updated_at": "2026-01-31T08:33:28.806Z",
      "admin": false,
      "owner": false,
      "client": false,
      "employee": false,
      "time_zone": "America/Chicago",
      "avatar_url": "https://3.basecampapi.com/195539477/people/BAhpBOlkkT4=--eebbe1ab1b28f5fcf32a1c0ff3644e06931fbcfa/avatar?v=1",
      "can_ping": true,
      "can_manage_projects": false,
      "can_manage_people": false,
      "can_access_timesheet": false,
      "can_access_hill_charts": false
    }
  }
]
```
<!-- END GET /buckets/1/recordings/2/events.json -->
###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/recordings/2/events.json
```

[recordings]: https://github.com/basecamp/bc3-api/blob/master/sections/recordings.md#recordings
[pagination]: https://github.com/basecamp/bc3-api/blob/master/README.md#pagination
