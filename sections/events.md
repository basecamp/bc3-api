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
    "id": 1071915175,
    "recording_id": 1069479523,
    "action": "assignment_changed",
    "details": {
      "added_person_ids": [
        1049715937
      ],
      "removed_person_ids": [

      ]
    },
    "created_at": "2022-12-11T13:25:58.169Z",
    "creator": {
      "id": 1049715915,
      "attachable_sgid": "BAh7CEkiCGdpZAY6BkVUSSIrZ2lkOi8vYmMzL1BlcnNvbi8xMDQ5NzE1OTE1P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg9hdHRhY2hhYmxlBjsAVEkiD2V4cGlyZXNfYXQGOwBUMA==--aeb392ebf54ffd820e45f27add22bae3a8c7da56",
      "name": "Annie Bryan",
      "email_address": "annie@honchodesign.com",
      "personable_type": "User",
      "title": "Central Markets Manager",
      "bio": "To open a store is easy, to keep it open is an art",
      "location": null,
      "created_at": "2022-11-22T08:23:21.911Z",
      "updated_at": "2022-11-22T08:23:21.911Z",
      "admin": false,
      "owner": false,
      "client": false,
      "employee": true,
      "time_zone": "America/Chicago",
      "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBMtkkT4=--9927c47a4cbee30a7f9aea667882496aba799149/avatar?v=1",
      "company": {
        "id": 1033447817,
        "name": "Honcho Design"
      },
      "can_manage_projects": true,
      "can_manage_people": true
    }
  },
  {
    "id": 1071915174,
    "recording_id": 1069479523,
    "action": "created",
    "details": {
      "notified_recipient_ids": [

      ]
    },
    "created_at": "2022-12-11T13:25:58.169Z",
    "creator": {
      "id": 1049715915,
      "attachable_sgid": "BAh7CEkiCGdpZAY6BkVUSSIrZ2lkOi8vYmMzL1BlcnNvbi8xMDQ5NzE1OTE1P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg9hdHRhY2hhYmxlBjsAVEkiD2V4cGlyZXNfYXQGOwBUMA==--aeb392ebf54ffd820e45f27add22bae3a8c7da56",
      "name": "Annie Bryan",
      "email_address": "annie@honchodesign.com",
      "personable_type": "User",
      "title": "Central Markets Manager",
      "bio": "To open a store is easy, to keep it open is an art",
      "location": null,
      "created_at": "2022-11-22T08:23:21.911Z",
      "updated_at": "2022-11-22T08:23:21.911Z",
      "admin": false,
      "owner": false,
      "client": false,
      "employee": true,
      "time_zone": "America/Chicago",
      "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBMtkkT4=--9927c47a4cbee30a7f9aea667882496aba799149/avatar?v=1",
      "company": {
        "id": 1033447817,
        "name": "Honcho Design"
      },
      "can_manage_projects": true,
      "can_manage_people": true
    }
  },
  {
    "id": 1071915870,
    "recording_id": 1069479523,
    "action": "uncompleted",
    "details": {
    },
    "created_at": "2022-11-22T17:56:31.272Z",
    "creator": {
      "id": 1049715937,
      "attachable_sgid": "BAh7CEkiCGdpZAY6BkVUSSIrZ2lkOi8vYmMzL1BlcnNvbi8xMDQ5NzE1OTM3P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg9hdHRhY2hhYmxlBjsAVEkiD2V4cGlyZXNfYXQGOwBUMA==--1255eb7c3d72232ea454ba0b42aaee71238c1d07",
      "name": "Sharon Bradford",
      "email_address": "sharon@honchodesign.com",
      "personable_type": "User",
      "title": "Principal Branding Administrator",
      "bio": null,
      "location": null,
      "created_at": "2022-11-22T08:23:22.231Z",
      "updated_at": "2022-11-22T08:23:22.231Z",
      "admin": false,
      "owner": false,
      "client": false,
      "employee": false,
      "time_zone": "Etc/UTC",
      "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBOFkkT4=--560f7fa1330d4341e3c089226bcb7fefb82dbfd1/avatar?v=1",
      "can_manage_projects": true,
      "can_manage_people": true
    }
  },
  {
    "id": 1071915869,
    "recording_id": 1069479523,
    "action": "completed",
    "details": {
      "notified_recipient_ids": [
        1049715915
      ]
    },
    "created_at": "2022-11-22T17:56:30.792Z",
    "creator": {
      "id": 1049715937,
      "attachable_sgid": "BAh7CEkiCGdpZAY6BkVUSSIrZ2lkOi8vYmMzL1BlcnNvbi8xMDQ5NzE1OTM3P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg9hdHRhY2hhYmxlBjsAVEkiD2V4cGlyZXNfYXQGOwBUMA==--1255eb7c3d72232ea454ba0b42aaee71238c1d07",
      "name": "Sharon Bradford",
      "email_address": "sharon@honchodesign.com",
      "personable_type": "User",
      "title": "Principal Branding Administrator",
      "bio": null,
      "location": null,
      "created_at": "2022-11-22T08:23:22.231Z",
      "updated_at": "2022-11-22T08:23:22.231Z",
      "admin": false,
      "owner": false,
      "client": false,
      "employee": false,
      "time_zone": "Etc/UTC",
      "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBOFkkT4=--560f7fa1330d4341e3c089226bcb7fefb82dbfd1/avatar?v=1",
      "can_manage_projects": true,
      "can_manage_people": true
    }
  },
  {
    "id": 1071915776,
    "recording_id": 1069479523,
    "action": "uncompleted",
    "details": {
    },
    "created_at": "2022-11-22T13:36:50.725Z",
    "creator": {
      "id": 1049715937,
      "attachable_sgid": "BAh7CEkiCGdpZAY6BkVUSSIrZ2lkOi8vYmMzL1BlcnNvbi8xMDQ5NzE1OTM3P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg9hdHRhY2hhYmxlBjsAVEkiD2V4cGlyZXNfYXQGOwBUMA==--1255eb7c3d72232ea454ba0b42aaee71238c1d07",
      "name": "Sharon Bradford",
      "email_address": "sharon@honchodesign.com",
      "personable_type": "User",
      "title": "Principal Branding Administrator",
      "bio": null,
      "location": null,
      "created_at": "2022-11-22T08:23:22.231Z",
      "updated_at": "2022-11-22T08:23:22.231Z",
      "admin": false,
      "owner": false,
      "client": false,
      "employee": false,
      "time_zone": "Etc/UTC",
      "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBOFkkT4=--560f7fa1330d4341e3c089226bcb7fefb82dbfd1/avatar?v=1",
      "can_manage_projects": true,
      "can_manage_people": true
    }
  },
  {
    "id": 1071915775,
    "recording_id": 1069479523,
    "action": "completed",
    "details": {
      "notified_recipient_ids": [
        1049715915
      ]
    },
    "created_at": "2022-11-22T13:36:50.255Z",
    "creator": {
      "id": 1049715937,
      "attachable_sgid": "BAh7CEkiCGdpZAY6BkVUSSIrZ2lkOi8vYmMzL1BlcnNvbi8xMDQ5NzE1OTM3P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg9hdHRhY2hhYmxlBjsAVEkiD2V4cGlyZXNfYXQGOwBUMA==--1255eb7c3d72232ea454ba0b42aaee71238c1d07",
      "name": "Sharon Bradford",
      "email_address": "sharon@honchodesign.com",
      "personable_type": "User",
      "title": "Principal Branding Administrator",
      "bio": null,
      "location": null,
      "created_at": "2022-11-22T08:23:22.231Z",
      "updated_at": "2022-11-22T08:23:22.231Z",
      "admin": false,
      "owner": false,
      "client": false,
      "employee": false,
      "time_zone": "Etc/UTC",
      "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBOFkkT4=--560f7fa1330d4341e3c089226bcb7fefb82dbfd1/avatar?v=1",
      "can_manage_projects": true,
      "can_manage_people": true
    }
  },
  {
    "id": 1071915743,
    "recording_id": 1069479523,
    "action": "uncompleted",
    "details": {
    },
    "created_at": "2022-11-22T13:32:44.529Z",
    "creator": {
      "id": 1049715937,
      "attachable_sgid": "BAh7CEkiCGdpZAY6BkVUSSIrZ2lkOi8vYmMzL1BlcnNvbi8xMDQ5NzE1OTM3P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg9hdHRhY2hhYmxlBjsAVEkiD2V4cGlyZXNfYXQGOwBUMA==--1255eb7c3d72232ea454ba0b42aaee71238c1d07",
      "name": "Sharon Bradford",
      "email_address": "sharon@honchodesign.com",
      "personable_type": "User",
      "title": "Principal Branding Administrator",
      "bio": null,
      "location": null,
      "created_at": "2022-11-22T08:23:22.231Z",
      "updated_at": "2022-11-22T08:23:22.231Z",
      "admin": false,
      "owner": false,
      "client": false,
      "employee": false,
      "time_zone": "Etc/UTC",
      "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBOFkkT4=--560f7fa1330d4341e3c089226bcb7fefb82dbfd1/avatar?v=1",
      "can_manage_projects": true,
      "can_manage_people": true
    }
  },
  {
    "id": 1071915742,
    "recording_id": 1069479523,
    "action": "completed",
    "details": {
      "notified_recipient_ids": [
        1049715915
      ]
    },
    "created_at": "2022-11-22T13:32:44.400Z",
    "creator": {
      "id": 1049715937,
      "attachable_sgid": "BAh7CEkiCGdpZAY6BkVUSSIrZ2lkOi8vYmMzL1BlcnNvbi8xMDQ5NzE1OTM3P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg9hdHRhY2hhYmxlBjsAVEkiD2V4cGlyZXNfYXQGOwBUMA==--1255eb7c3d72232ea454ba0b42aaee71238c1d07",
      "name": "Sharon Bradford",
      "email_address": "sharon@honchodesign.com",
      "personable_type": "User",
      "title": "Principal Branding Administrator",
      "bio": null,
      "location": null,
      "created_at": "2022-11-22T08:23:22.231Z",
      "updated_at": "2022-11-22T08:23:22.231Z",
      "admin": false,
      "owner": false,
      "client": false,
      "employee": false,
      "time_zone": "Etc/UTC",
      "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBOFkkT4=--560f7fa1330d4341e3c089226bcb7fefb82dbfd1/avatar?v=1",
      "can_manage_projects": true,
      "can_manage_people": true
    }
  },
  {
    "id": 1071915648,
    "recording_id": 1069479523,
    "action": "uncompleted",
    "details": {
    },
    "created_at": "2022-11-22T11:17:22.551Z",
    "creator": {
      "id": 1049715937,
      "attachable_sgid": "BAh7CEkiCGdpZAY6BkVUSSIrZ2lkOi8vYmMzL1BlcnNvbi8xMDQ5NzE1OTM3P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg9hdHRhY2hhYmxlBjsAVEkiD2V4cGlyZXNfYXQGOwBUMA==--1255eb7c3d72232ea454ba0b42aaee71238c1d07",
      "name": "Sharon Bradford",
      "email_address": "sharon@honchodesign.com",
      "personable_type": "User",
      "title": "Principal Branding Administrator",
      "bio": null,
      "location": null,
      "created_at": "2022-11-22T08:23:22.231Z",
      "updated_at": "2022-11-22T08:23:22.231Z",
      "admin": false,
      "owner": false,
      "client": false,
      "employee": false,
      "time_zone": "Etc/UTC",
      "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBOFkkT4=--560f7fa1330d4341e3c089226bcb7fefb82dbfd1/avatar?v=1",
      "can_manage_projects": true,
      "can_manage_people": true
    }
  },
  {
    "id": 1071915647,
    "recording_id": 1069479523,
    "action": "completed",
    "details": {
      "notified_recipient_ids": [
        1049715915
      ]
    },
    "created_at": "2022-11-22T11:17:22.362Z",
    "creator": {
      "id": 1049715937,
      "attachable_sgid": "BAh7CEkiCGdpZAY6BkVUSSIrZ2lkOi8vYmMzL1BlcnNvbi8xMDQ5NzE1OTM3P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg9hdHRhY2hhYmxlBjsAVEkiD2V4cGlyZXNfYXQGOwBUMA==--1255eb7c3d72232ea454ba0b42aaee71238c1d07",
      "name": "Sharon Bradford",
      "email_address": "sharon@honchodesign.com",
      "personable_type": "User",
      "title": "Principal Branding Administrator",
      "bio": null,
      "location": null,
      "created_at": "2022-11-22T08:23:22.231Z",
      "updated_at": "2022-11-22T08:23:22.231Z",
      "admin": false,
      "owner": false,
      "client": false,
      "employee": false,
      "time_zone": "Etc/UTC",
      "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBOFkkT4=--560f7fa1330d4341e3c089226bcb7fefb82dbfd1/avatar?v=1",
      "can_manage_projects": true,
      "can_manage_people": true
    }
  },
  {
    "id": 1071915610,
    "recording_id": 1069479523,
    "action": "uncompleted",
    "details": {
    },
    "created_at": "2022-11-22T11:15:57.430Z",
    "creator": {
      "id": 1049715937,
      "attachable_sgid": "BAh7CEkiCGdpZAY6BkVUSSIrZ2lkOi8vYmMzL1BlcnNvbi8xMDQ5NzE1OTM3P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg9hdHRhY2hhYmxlBjsAVEkiD2V4cGlyZXNfYXQGOwBUMA==--1255eb7c3d72232ea454ba0b42aaee71238c1d07",
      "name": "Sharon Bradford",
      "email_address": "sharon@honchodesign.com",
      "personable_type": "User",
      "title": "Principal Branding Administrator",
      "bio": null,
      "location": null,
      "created_at": "2022-11-22T08:23:22.231Z",
      "updated_at": "2022-11-22T08:23:22.231Z",
      "admin": false,
      "owner": false,
      "client": false,
      "employee": false,
      "time_zone": "Etc/UTC",
      "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBOFkkT4=--560f7fa1330d4341e3c089226bcb7fefb82dbfd1/avatar?v=1",
      "can_manage_projects": true,
      "can_manage_people": true
    }
  },
  {
    "id": 1071915609,
    "recording_id": 1069479523,
    "action": "completed",
    "details": {
      "notified_recipient_ids": [
        1049715915
      ]
    },
    "created_at": "2022-11-22T11:15:57.335Z",
    "creator": {
      "id": 1049715937,
      "attachable_sgid": "BAh7CEkiCGdpZAY6BkVUSSIrZ2lkOi8vYmMzL1BlcnNvbi8xMDQ5NzE1OTM3P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg9hdHRhY2hhYmxlBjsAVEkiD2V4cGlyZXNfYXQGOwBUMA==--1255eb7c3d72232ea454ba0b42aaee71238c1d07",
      "name": "Sharon Bradford",
      "email_address": "sharon@honchodesign.com",
      "personable_type": "User",
      "title": "Principal Branding Administrator",
      "bio": null,
      "location": null,
      "created_at": "2022-11-22T08:23:22.231Z",
      "updated_at": "2022-11-22T08:23:22.231Z",
      "admin": false,
      "owner": false,
      "client": false,
      "employee": false,
      "time_zone": "Etc/UTC",
      "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBOFkkT4=--560f7fa1330d4341e3c089226bcb7fefb82dbfd1/avatar?v=1",
      "can_manage_projects": true,
      "can_manage_people": true
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
