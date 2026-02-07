Events
======

An event is created any time a [recording][recordings] changes.

Some events are **boostable**: events with an action of `completed`, `adopted`, or `column_changed`. Boostable events include `boosts_count` and `boosts_url` attributes in their JSON responses. See the [Boosts][boosts] section for details on boosting events.

Endpoints:

- [Get events](#get-events)

Get events
----------

* `GET /buckets/1/recordings/2/events.json` will return a [paginated list][pagination] of events for the recording with an ID of `2` in the project with an ID of `1`.

Boostable events (`completed`, `adopted`, `column_changed`) include additional attributes:

- `boosts_count` - the number of boosts on this event
- `boosts_url` - the URL to list or create boosts on this event (see [Boosts][boosts])

###### Example JSON Response
<!-- START GET /buckets/1/recordings/2/events.json -->
```json
[
  {
    "id": 1071915906,
    "recording_id": 1069479576,
    "action": "uncompleted",
    "details": {},
    "created_at": "2026-02-06T22:56:33.502Z",
    "creator": {
      "id": 1049715930,
      "attachable_sgid": "BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiK2dpZDovL2JjMy9QZXJzb24vMTA0OTcxNTkzMD9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg9hdHRhY2hhYmxlBjsAVA==--322099b137f9e0b6bc944b5b9fe7a2692da94814",
      "name": "Sharon Bradford",
      "email_address": "sharon@honchodesign.com",
      "personable_type": "User",
      "title": "Principal Branding Administrator",
      "bio": null,
      "location": null,
      "created_at": "2026-01-31T08:29:40.859Z",
      "updated_at": "2026-01-31T08:29:40.859Z",
      "admin": false,
      "owner": false,
      "client": false,
      "employee": false,
      "time_zone": "America/Chicago",
      "avatar_url": "https://3.basecampapi.com/195539477/people/BAhpBNpkkT4=--789594e5e542ab99e467a51c9dec0a9035abc0e0/avatar?v=1",
      "can_ping": true,
      "can_manage_projects": true,
      "can_manage_people": true,
      "can_access_timesheet": true,
      "can_access_hill_charts": true
    }
  },
  {
    "id": 1071915905,
    "recording_id": 1069479576,
    "action": "completed",
    "details": {
      "notified_recipient_ids": [
        1049715938
      ]
    },
    "created_at": "2026-02-06T22:56:33.043Z",
    "creator": {
      "id": 1049715930,
      "attachable_sgid": "BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiK2dpZDovL2JjMy9QZXJzb24vMTA0OTcxNTkzMD9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg9hdHRhY2hhYmxlBjsAVA==--322099b137f9e0b6bc944b5b9fe7a2692da94814",
      "name": "Sharon Bradford",
      "email_address": "sharon@honchodesign.com",
      "personable_type": "User",
      "title": "Principal Branding Administrator",
      "bio": null,
      "location": null,
      "created_at": "2026-01-31T08:29:40.859Z",
      "updated_at": "2026-01-31T08:29:40.859Z",
      "admin": false,
      "owner": false,
      "client": false,
      "employee": false,
      "time_zone": "America/Chicago",
      "avatar_url": "https://3.basecampapi.com/195539477/people/BAhpBNpkkT4=--789594e5e542ab99e467a51c9dec0a9035abc0e0/avatar?v=1",
      "can_ping": true,
      "can_manage_projects": true,
      "can_manage_people": true,
      "can_access_timesheet": true,
      "can_access_hill_charts": true
    },
    "boosts_count": 0,
    "boosts_url": "https://3.basecampapi.com/195539477/buckets/2085958504/recordings/1069479576/events/1071915905/boosts.json"
  },
  {
    "id": 1071915865,
    "recording_id": 1069479576,
    "action": "uncompleted",
    "details": {},
    "created_at": "2026-02-06T22:45:49.905Z",
    "creator": {
      "id": 1049715930,
      "attachable_sgid": "BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiK2dpZDovL2JjMy9QZXJzb24vMTA0OTcxNTkzMD9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg9hdHRhY2hhYmxlBjsAVA==--322099b137f9e0b6bc944b5b9fe7a2692da94814",
      "name": "Sharon Bradford",
      "email_address": "sharon@honchodesign.com",
      "personable_type": "User",
      "title": "Principal Branding Administrator",
      "bio": null,
      "location": null,
      "created_at": "2026-01-31T08:29:40.859Z",
      "updated_at": "2026-01-31T08:29:40.859Z",
      "admin": false,
      "owner": false,
      "client": false,
      "employee": false,
      "time_zone": "America/Chicago",
      "avatar_url": "https://3.basecampapi.com/195539477/people/BAhpBNpkkT4=--789594e5e542ab99e467a51c9dec0a9035abc0e0/avatar?v=1",
      "can_ping": true,
      "can_manage_projects": true,
      "can_manage_people": true,
      "can_access_timesheet": true,
      "can_access_hill_charts": true
    }
  },
  {
    "id": 1071915864,
    "recording_id": 1069479576,
    "action": "completed",
    "details": {
      "notified_recipient_ids": [
        1049715938
      ]
    },
    "created_at": "2026-02-06T22:45:49.427Z",
    "creator": {
      "id": 1049715930,
      "attachable_sgid": "BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiK2dpZDovL2JjMy9QZXJzb24vMTA0OTcxNTkzMD9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg9hdHRhY2hhYmxlBjsAVA==--322099b137f9e0b6bc944b5b9fe7a2692da94814",
      "name": "Sharon Bradford",
      "email_address": "sharon@honchodesign.com",
      "personable_type": "User",
      "title": "Principal Branding Administrator",
      "bio": null,
      "location": null,
      "created_at": "2026-01-31T08:29:40.859Z",
      "updated_at": "2026-01-31T08:29:40.859Z",
      "admin": false,
      "owner": false,
      "client": false,
      "employee": false,
      "time_zone": "America/Chicago",
      "avatar_url": "https://3.basecampapi.com/195539477/people/BAhpBNpkkT4=--789594e5e542ab99e467a51c9dec0a9035abc0e0/avatar?v=1",
      "can_ping": true,
      "can_manage_projects": true,
      "can_manage_people": true,
      "can_access_timesheet": true,
      "can_access_hill_charts": true
    },
    "boosts_count": 0,
    "boosts_url": "https://3.basecampapi.com/195539477/buckets/2085958504/recordings/1069479576/events/1071915864/boosts.json"
  },
  {
    "id": 1071915793,
    "recording_id": 1069479576,
    "action": "uncompleted",
    "details": {},
    "created_at": "2026-02-06T22:19:46.800Z",
    "creator": {
      "id": 1049715930,
      "attachable_sgid": "BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiK2dpZDovL2JjMy9QZXJzb24vMTA0OTcxNTkzMD9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg9hdHRhY2hhYmxlBjsAVA==--322099b137f9e0b6bc944b5b9fe7a2692da94814",
      "name": "Sharon Bradford",
      "email_address": "sharon@honchodesign.com",
      "personable_type": "User",
      "title": "Principal Branding Administrator",
      "bio": null,
      "location": null,
      "created_at": "2026-01-31T08:29:40.859Z",
      "updated_at": "2026-01-31T08:29:40.859Z",
      "admin": false,
      "owner": false,
      "client": false,
      "employee": false,
      "time_zone": "America/Chicago",
      "avatar_url": "https://3.basecampapi.com/195539477/people/BAhpBNpkkT4=--789594e5e542ab99e467a51c9dec0a9035abc0e0/avatar?v=1",
      "can_ping": true,
      "can_manage_projects": true,
      "can_manage_people": true,
      "can_access_timesheet": true,
      "can_access_hill_charts": true
    }
  },
  {
    "id": 1071915792,
    "recording_id": 1069479576,
    "action": "completed",
    "details": {
      "notified_recipient_ids": [
        1049715938
      ]
    },
    "created_at": "2026-02-06T22:19:46.349Z",
    "creator": {
      "id": 1049715930,
      "attachable_sgid": "BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiK2dpZDovL2JjMy9QZXJzb24vMTA0OTcxNTkzMD9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg9hdHRhY2hhYmxlBjsAVA==--322099b137f9e0b6bc944b5b9fe7a2692da94814",
      "name": "Sharon Bradford",
      "email_address": "sharon@honchodesign.com",
      "personable_type": "User",
      "title": "Principal Branding Administrator",
      "bio": null,
      "location": null,
      "created_at": "2026-01-31T08:29:40.859Z",
      "updated_at": "2026-01-31T08:29:40.859Z",
      "admin": false,
      "owner": false,
      "client": false,
      "employee": false,
      "time_zone": "America/Chicago",
      "avatar_url": "https://3.basecampapi.com/195539477/people/BAhpBNpkkT4=--789594e5e542ab99e467a51c9dec0a9035abc0e0/avatar?v=1",
      "can_ping": true,
      "can_manage_projects": true,
      "can_manage_people": true,
      "can_access_timesheet": true,
      "can_access_hill_charts": true
    },
    "boosts_count": 0,
    "boosts_url": "https://3.basecampapi.com/195539477/buckets/2085958504/recordings/1069479576/events/1071915792/boosts.json"
  },
  {
    "id": 1071915753,
    "recording_id": 1069479576,
    "action": "uncompleted",
    "details": {},
    "created_at": "2026-02-06T21:44:49.092Z",
    "creator": {
      "id": 1049715930,
      "attachable_sgid": "BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiK2dpZDovL2JjMy9QZXJzb24vMTA0OTcxNTkzMD9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg9hdHRhY2hhYmxlBjsAVA==--322099b137f9e0b6bc944b5b9fe7a2692da94814",
      "name": "Sharon Bradford",
      "email_address": "sharon@honchodesign.com",
      "personable_type": "User",
      "title": "Principal Branding Administrator",
      "bio": null,
      "location": null,
      "created_at": "2026-01-31T08:29:40.859Z",
      "updated_at": "2026-01-31T08:29:40.859Z",
      "admin": false,
      "owner": false,
      "client": false,
      "employee": false,
      "time_zone": "America/Chicago",
      "avatar_url": "https://3.basecampapi.com/195539477/people/BAhpBNpkkT4=--789594e5e542ab99e467a51c9dec0a9035abc0e0/avatar?v=1",
      "can_ping": true,
      "can_manage_projects": true,
      "can_manage_people": true,
      "can_access_timesheet": true,
      "can_access_hill_charts": true
    }
  },
  {
    "id": 1071915752,
    "recording_id": 1069479576,
    "action": "completed",
    "details": {
      "notified_recipient_ids": [
        1049715938
      ]
    },
    "created_at": "2026-02-06T21:44:48.563Z",
    "creator": {
      "id": 1049715930,
      "attachable_sgid": "BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiK2dpZDovL2JjMy9QZXJzb24vMTA0OTcxNTkzMD9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg9hdHRhY2hhYmxlBjsAVA==--322099b137f9e0b6bc944b5b9fe7a2692da94814",
      "name": "Sharon Bradford",
      "email_address": "sharon@honchodesign.com",
      "personable_type": "User",
      "title": "Principal Branding Administrator",
      "bio": null,
      "location": null,
      "created_at": "2026-01-31T08:29:40.859Z",
      "updated_at": "2026-01-31T08:29:40.859Z",
      "admin": false,
      "owner": false,
      "client": false,
      "employee": false,
      "time_zone": "America/Chicago",
      "avatar_url": "https://3.basecampapi.com/195539477/people/BAhpBNpkkT4=--789594e5e542ab99e467a51c9dec0a9035abc0e0/avatar?v=1",
      "can_ping": true,
      "can_manage_projects": true,
      "can_manage_people": true,
      "can_access_timesheet": true,
      "can_access_hill_charts": true
    },
    "boosts_count": 0,
    "boosts_url": "https://3.basecampapi.com/195539477/buckets/2085958504/recordings/1069479576/events/1071915752/boosts.json"
  },
  {
    "id": 1071915662,
    "recording_id": 1069479576,
    "action": "uncompleted",
    "details": {},
    "created_at": "2026-02-01T02:53:47.037Z",
    "creator": {
      "id": 1049715930,
      "attachable_sgid": "BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiK2dpZDovL2JjMy9QZXJzb24vMTA0OTcxNTkzMD9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg9hdHRhY2hhYmxlBjsAVA==--322099b137f9e0b6bc944b5b9fe7a2692da94814",
      "name": "Sharon Bradford",
      "email_address": "sharon@honchodesign.com",
      "personable_type": "User",
      "title": "Principal Branding Administrator",
      "bio": null,
      "location": null,
      "created_at": "2026-01-31T08:29:40.859Z",
      "updated_at": "2026-01-31T08:29:40.859Z",
      "admin": false,
      "owner": false,
      "client": false,
      "employee": false,
      "time_zone": "America/Chicago",
      "avatar_url": "https://3.basecampapi.com/195539477/people/BAhpBNpkkT4=--789594e5e542ab99e467a51c9dec0a9035abc0e0/avatar?v=1",
      "can_ping": true,
      "can_manage_projects": true,
      "can_manage_people": true,
      "can_access_timesheet": true,
      "can_access_hill_charts": true
    }
  },
  {
    "id": 1071915661,
    "recording_id": 1069479576,
    "action": "completed",
    "details": {
      "notified_recipient_ids": [
        1049715938
      ]
    },
    "created_at": "2026-02-01T02:53:46.588Z",
    "creator": {
      "id": 1049715930,
      "attachable_sgid": "BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiK2dpZDovL2JjMy9QZXJzb24vMTA0OTcxNTkzMD9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg9hdHRhY2hhYmxlBjsAVA==--322099b137f9e0b6bc944b5b9fe7a2692da94814",
      "name": "Sharon Bradford",
      "email_address": "sharon@honchodesign.com",
      "personable_type": "User",
      "title": "Principal Branding Administrator",
      "bio": null,
      "location": null,
      "created_at": "2026-01-31T08:29:40.859Z",
      "updated_at": "2026-01-31T08:29:40.859Z",
      "admin": false,
      "owner": false,
      "client": false,
      "employee": false,
      "time_zone": "America/Chicago",
      "avatar_url": "https://3.basecampapi.com/195539477/people/BAhpBNpkkT4=--789594e5e542ab99e467a51c9dec0a9035abc0e0/avatar?v=1",
      "can_ping": true,
      "can_manage_projects": true,
      "can_manage_people": true,
      "can_access_timesheet": true,
      "can_access_hill_charts": true
    },
    "boosts_count": 0,
    "boosts_url": "https://3.basecampapi.com/195539477/buckets/2085958504/recordings/1069479576/events/1071915661/boosts.json"
  },
  {
    "id": 1071915233,
    "recording_id": 1069479576,
    "action": "assignment_changed",
    "details": {
      "added_person_ids": [
        1049715930
      ],
      "removed_person_ids": []
    },
    "created_at": "2026-01-15T07:20:00.000Z",
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
    }
  },
  {
    "id": 1071915232,
    "recording_id": 1069479576,
    "action": "created",
    "details": {
      "notified_recipient_ids": []
    },
    "created_at": "2026-01-15T07:20:00.000Z",
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
    }
  }
]
```
<!-- END GET /buckets/1/recordings/2/events.json -->
###### Copy as cURL

```shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/recordings/2/events.json
```

[boosts]: https://github.com/basecamp/bc3-api/blob/master/sections/boosts.md#boosts
[recordings]: https://github.com/basecamp/bc3-api/blob/master/sections/recordings.md#recordings
[pagination]: https://github.com/basecamp/bc3-api/blob/master/README.md#pagination
