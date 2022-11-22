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
    "id": 1069479567,
    "status": "active",
    "visible_to_clients": false,
    "created_at": "2022-10-09T10:36:14.049Z",
    "updated_at": "2022-10-09T10:36:14.049Z",
    "title": "Re: Project kickoff!",
    "inherits_status": true,
    "type": "Client::Reply",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958500/client/replies/1069479567.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958500/client/correspondences/1069479566#__recording_1069479567",
    "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7CEkiCGdpZAY6BkVUSSIuZ2lkOi8vYmMzL1JlY29yZGluZy8xMDY5NDc5NTY3P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg1yZWFkYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--9ff5d4f77619de8b3657b8b4fbe22e9d0b7c2b5a.json",
    "parent": {
      "id": 1069479566,
      "title": "Project kickoff!",
      "type": "Client::Correspondence",
      "url": "https://3.basecampapi.com/195539477/buckets/2085958500/client/correspondences/1069479566.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958500/client/correspondences/1069479566"
    },
    "bucket": {
      "id": 2085958500,
      "name": "The Leto Locator",
      "type": "Project"
    },
    "creator": {
      "id": 1049715941,
      "attachable_sgid": "BAh7CEkiCGdpZAY6BkVUSSIrZ2lkOi8vYmMzL1BlcnNvbi8xMDQ5NzE1OTQxP2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg9hdHRhY2hhYmxlBjsAVEkiD2V4cGlyZXNfYXQGOwBUMA==--10099ab54fac5884db30b9bd897ea030023d4d0a",
      "name": "Stephen Early",
      "email_address": "stephen@letobrand.com",
      "personable_type": "Client",
      "title": "National Directives Director",
      "bio": null,
      "location": null,
      "created_at": "2022-11-22T08:23:22.341Z",
      "updated_at": "2022-11-22T08:23:22.341Z",
      "admin": false,
      "owner": false,
      "client": false,
      "employee": false,
      "time_zone": "Etc/UTC",
      "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBOVkkT4=--33e3fc268c87411378691c71b6f13658e0b40967/avatar?v=1",
      "company": {
        "id": 1033447818,
        "name": "Leto Brand"
      },
      "can_manage_projects": false,
      "can_manage_people": false
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
  "id": 1069479571,
  "status": "active",
  "visible_to_clients": false,
  "created_at": "2022-10-09T09:20:14.049Z",
  "updated_at": "2022-10-09T09:20:14.049Z",
  "title": "Re: Project kickoff!",
  "inherits_status": true,
  "type": "Client::Reply",
  "url": "https://3.basecampapi.com/195539477/buckets/2085958500/client/replies/1069479571.json",
  "app_url": "https://3.basecamp.com/195539477/buckets/2085958500/client/correspondences/1069479566#__recording_1069479571",
  "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7CEkiCGdpZAY6BkVUSSIuZ2lkOi8vYmMzL1JlY29yZGluZy8xMDY5NDc5NTcxP2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg1yZWFkYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--c711ae715330c9d458072698256fec0d86abd15e.json",
  "parent": {
    "id": 1069479566,
    "title": "Project kickoff!",
    "type": "Client::Correspondence",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958500/client/correspondences/1069479566.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958500/client/correspondences/1069479566"
  },
  "bucket": {
    "id": 2085958500,
    "name": "The Leto Locator",
    "type": "Project"
  },
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
