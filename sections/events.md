Events
======

An event is created any time a [recording][recordings] changes.

Endpoints:

- [Get events](#get-events)

Get events
----------

* `GET /buckets/1/recordings/2/events.json` will return a [paginated list][pagination] of events for the recording with an ID of `2` in the Basecamp with an ID of `1`.

###### Example JSON Response
<!-- START GET /buckets/1/recordings/2/events.json -->
```json
[
  {
    "id": 9007199254741030,
    "recording_id": 9007199254741027,
    "action": "completed",
    "details": {
    },
    "created_at": "2016-07-19T16:46:39.670Z",
    "creator": {
      "id": 1007299144,
      "attachable_sgid": "BAh7CEkiCGdpZAY6BkVUSSIrZ2lkOi8vYmMzL1BlcnNvbi8xMDA3Mjk5MTQ0P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg9hdHRhY2hhYmxlBjsAVEkiD2V4cGlyZXNfYXQGOwBUMA==--2e34d7611a9fcaeb82342d015a671cf5e998c036",
      "name": "Annie Bryan",
      "email_address": "annie@honchodesign.com",
      "personable_type": "User",
      "title": "Central Markets Manager",
      "bio": "To open a store is easy, to keep it open is an art",
      "created_at": "2016-09-09T22:58:27.734Z",
      "updated_at": "2016-09-09T22:58:27.734Z",
      "admin": false,
      "owner": false,
      "time_zone": "America/Chicago",
      "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBEgqCjw=--8266bb0507508f3d46050d57b65924d5e2a005f3/avatar-64-x4",
      "company": {
        "id": 1033447817,
        "name": "Honcho Design"
      }
    }
  },
  {
    "id": 9007199254741029,
    "recording_id": 9007199254741027,
    "action": "created",
    "details": {
    },
    "created_at": "2016-06-25T19:57:38.259Z",
    "creator": {
      "id": 1007299144,
      "attachable_sgid": "BAh7CEkiCGdpZAY6BkVUSSIrZ2lkOi8vYmMzL1BlcnNvbi8xMDA3Mjk5MTQ0P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg9hdHRhY2hhYmxlBjsAVEkiD2V4cGlyZXNfYXQGOwBUMA==--2e34d7611a9fcaeb82342d015a671cf5e998c036",
      "name": "Annie Bryan",
      "email_address": "annie@honchodesign.com",
      "personable_type": "User",
      "title": "Central Markets Manager",
      "bio": "To open a store is easy, to keep it open is an art",
      "created_at": "2016-09-09T22:58:27.734Z",
      "updated_at": "2016-09-09T22:58:27.734Z",
      "admin": false,
      "owner": false,
      "time_zone": "America/Chicago",
      "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBEgqCjw=--8266bb0507508f3d46050d57b65924d5e2a005f3/avatar-64-x4",
      "company": {
        "id": 1033447817,
        "name": "Honcho Design"
      }
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
