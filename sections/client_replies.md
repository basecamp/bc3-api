Client replies
==============

Client replies are nested under the recording ID of a [client correspondence][correspondences] or [client approval][approvals].

Endpoints:

- [Get client replies](#get-client-replies)
- [Get a client reply](#get-a-client-reply)

Get client replies
------------------

* `GET /buckets/1/client/recordings/2/replies.json` will return a [paginated list][pagination] of client replies in the project with an ID of `1` and the recording with ID of `2`.

###### Example JSON Response
<!-- START GET /buckets/1/client/recordings/2/replies.json -->
```json
[
  {
    "id": 9007199254741656,
    "status": "active",
    "created_at": "2016-07-19T23:13:10.515Z",
    "updated_at": "2016-07-19T23:13:10.515Z",
    "type": "Client::Reply",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958499/client/replies/9007199254741656.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958499/client/correspondences/9007199254741655#__recording_9007199254741656",
    "parent": {
      "id": 9007199254741655,
      "title": "Project kickoff!",
      "type": "Client::Correspondence",
      "url": "https://3.basecampapi.com/195539477/buckets/2085958499/client/correspondences/9007199254741655.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958499/client/correspondences/9007199254741655"
    },
    "bucket": {
      "id": 2085958499,
      "name": "The Leto Locator",
      "type": "Project"
    },
    "creator": {
      "id": 1007299170,
      "attachable_sgid": "BAh7CEkiCGdpZAY6BkVUSSIrZ2lkOi8vYmMzL1BlcnNvbi8xMDA3Mjk5MTcwP2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg9hdHRhY2hhYmxlBjsAVEkiD2V4cGlyZXNfYXQGOwBUMA==--c2668ff0d13534b0b05c2059e4307c7b2b8506de",
      "name": "Stephen Early",
      "email_address": "stephen@letobrand.com",
      "personable_type": "Client",
      "title": "National Directives Director",
      "bio": null,
      "created_at": "2016-09-09T22:58:30.384Z",
      "updated_at": "2016-09-09T22:58:30.384Z",
      "admin": false,
      "owner": false,
      "time_zone": "Etc/UTC",
      "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBGIqCjw=--30a34b0522d7ba3484b8c4dcd65d9087a1baef0e/avatar-64-x4",
      "company": {
        "id": 1033447818,
        "name": "Leto Brand"
      }
    },
    "content": "<div>Hi all - we're excited to get started too.</div>"
  }
]
```
<!-- END GET /buckets/1/client/recordings/2/replies.json -->
###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/client/recordings/2/replies.json
```

Get a client reply
------------------

* `GET /buckets/1/client/recordings/2/replies/3.json` will return the client reply with an ID of `3` for the recording with an ID of `2` in the project with an ID of `1`.

###### Example JSON Response
<!-- START GET /buckets/1/client/recordings/2/replies/3.json -->
```json
{
  "id": 9007199254741660,
  "status": "active",
  "created_at": "2016-07-19T22:58:11.089Z",
  "updated_at": "2016-07-19T22:58:11.089Z",
  "type": "Client::Reply",
  "url": "https://3.basecampapi.com/195539477/buckets/2085958499/client/replies/9007199254741660.json",
  "app_url": "https://3.basecamp.com/195539477/buckets/2085958499/client/correspondences/9007199254741655#__recording_9007199254741660",
  "parent": {
    "id": 9007199254741655,
    "title": "Project kickoff!",
    "type": "Client::Correspondence",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958499/client/correspondences/9007199254741655.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958499/client/correspondences/9007199254741655"
  },
  "bucket": {
    "id": 2085958499,
    "name": "The Leto Locator",
    "type": "Project"
  },
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
  },
  "content": "<div>Hi Leto team, this it's Annie. I'll be your day to day contact for the project, so keep me on your speed dial (or speed email, perhaps more accurately!) Feel free to reach out to me with any questions at all, and I'll be posting up some outlines, timelines, etc. very shortly.</div>"
}
```
<!-- END GET /buckets/1/client/recordings/2/replies/3.json -->
###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/client/recordings/2/replies/3.json
```

[pagination]: https://github.com/basecamp/bc3-api/blob/master/README.md#pagination
[correspondences]: https://github.com/basecamp/bc3-api/blob/master/sections/client_correspondences.md#client-correspondences
[approvals]: https://github.com/basecamp/bc3-api/blob/master/sections/client_approvals.md#client-approvals
