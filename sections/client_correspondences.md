Client correspondences
======================

Endpoints:

- [Get client correspondences](#get-client-correspondences)
- [Get a client correspondence](#get-a-client-correspondence)

Get client correspondences
--------------------------

* `GET /buckets/1/client/correspondences.json` will return a [paginated list][pagination] of client correspondences in the project with an ID of `1`.

###### Example JSON Response
<!-- START GET /buckets/1/client/correspondences.json -->
```json
[
  {
    "id": 1069479645,
    "status": "active",
    "visible_to_clients": false,
    "created_at": "2022-11-17T12:20:14.049Z",
    "updated_at": "2022-11-22T08:24:20.989Z",
    "title": "Final deliverables and launch are right around the corner",
    "inherits_status": true,
    "type": "Client::Correspondence",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958500/client/correspondences/1069479645.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958500/client/correspondences/1069479645",
    "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7CEkiCGdpZAY6BkVUSSIuZ2lkOi8vYmMzL1JlY29yZGluZy8xMDY5NDc5NjQ1P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg1yZWFkYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--b97572c6fc1a6421db18970bedae2ed70392d269.json",
    "subscription_url": "https://3.basecampapi.com/195539477/buckets/2085958500/recordings/1069479645/subscription.json",
    "parent": {
      "id": 1069479564,
      "title": "The Clientside",
      "type": "Client::Board",
      "url": "https://3.basecampapi.com/195539477/buckets/2085958500/client/board.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958500/client/board.1069479564"
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
    "content": "<div>Hey everyone - we're in the home stretch! It's hard to believe how far we've come in just about 6 weeks. We've made incredible progress - created an in depth strategy and plan of attack, built an awesome experience and design, and backed it with incredible technology. We're so thrilled to be nearing the finish line - not just that we did it, but the way we did it.<br><br>\n\n  Of course, we're not quite there yet so we don't want to start celebrating just yet . We're running through our final bug fixes and those should be done today. We'll want one more pass by legal to take a look. And then of course, one more eyeball from the Leto team. In fact, we're in such good shape, we could even launch the site as-is - it's really solid.<br><br>\n\n  Please let us know if there's anything else on your minds before launch, but just wanted to report back that we're in good shape and on target to launch on schedule!</div>",
    "subject": "Final deliverables and launch are right around the corner",
    "replies_count": 5,
    "replies_url": "https://3.basecampapi.com/195539477/buckets/2085958500/client/recordings/1069479645/replies.json"
  }
]
```
<!-- END GET /buckets/1/client/correspondences.json -->
###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/client/correspondences.json
```

Get a client correspondence
---------------------------

* `GET /buckets/1/client/correspondences/2.json` will return the client correspondence with an ID of `2` in the project with an ID of `1`.

###### Example JSON Response
<!-- START GET /buckets/1/client/correspondences/2.json -->
```json
{
  "id": 1069479566,
  "status": "active",
  "visible_to_clients": false,
  "created_at": "2022-10-09T09:22:14.049Z",
  "updated_at": "2022-11-22T08:24:14.926Z",
  "title": "Project kickoff!",
  "inherits_status": true,
  "type": "Client::Correspondence",
  "url": "https://3.basecampapi.com/195539477/buckets/2085958500/client/correspondences/1069479566.json",
  "app_url": "https://3.basecamp.com/195539477/buckets/2085958500/client/correspondences/1069479566",
  "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7CEkiCGdpZAY6BkVUSSIuZ2lkOi8vYmMzL1JlY29yZGluZy8xMDY5NDc5NTY2P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg1yZWFkYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--fbfbc7c9428986404e1713f3335033f80b3c0313.json",
  "subscription_url": "https://3.basecampapi.com/195539477/buckets/2085958500/recordings/1069479566/subscription.json",
  "parent": {
    "id": 1069479564,
    "title": "The Clientside",
    "type": "Client::Board",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958500/client/board.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958500/client/board.1069479564"
  },
  "bucket": {
    "id": 2085958500,
    "name": "The Leto Locator",
    "type": "Project"
  },
  "creator": {
    "id": 1049715929,
    "attachable_sgid": "BAh7CEkiCGdpZAY6BkVUSSIrZ2lkOi8vYmMzL1BlcnNvbi8xMDQ5NzE1OTI5P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg9hdHRhY2hhYmxlBjsAVEkiD2V4cGlyZXNfYXQGOwBUMA==--d5a066a78ea37eba00e6590336eb23dd6717760b",
    "name": "Jay Edmonds",
    "email_address": "jay@honchodesign.com",
    "personable_type": "User",
    "title": "Internal Marketing Assistant",
    "bio": null,
    "location": null,
    "created_at": "2022-11-22T08:23:22.092Z",
    "updated_at": "2022-11-22T08:23:22.092Z",
    "admin": false,
    "owner": false,
    "client": false,
    "employee": false,
    "time_zone": "Etc/UTC",
    "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBNlkkT4=--0f3c77d8c13069d514fd3f0ad694a67e426bad0f/avatar?v=1",
    "can_manage_projects": true,
    "can_manage_people": true
  },
  "content": "<div>Hi everyone! Welcome to the Basecamp that we'll be using to collaboroate and manage the Leto Locator project.\n\n  We're particularly excited to bring on board our friends from Leto - Stephen, Miranda, and Beth. I know you guys have used Basecamp before, but so we're on the same page, we'll post a bunch of discussions, things for review, and todos to make sure we stay on the same page. We'll do our best to keep everyone looped in this way, instead of using email (which can be hard to keep people up to date on stuff.)\n\n  I also want to take a moment to introduce our team. It will be evolving and growing soon, but right now we've got some core team members: Myself as the Account Director, Annie as the Senior PM, Jared is our tech lead, Matt is our ACD, and Victor, of course, you know. A few people will be coming on to support us, but this will be your core team. You can, of course, reach out to any one of us at any time, but I'll ultimately be the one responsible for making sure you're happy with our work.\n\n  Again, can't tell you how excited we are to get started on this and all the other projects. Let's go, Leto!\n\n  -Jay</div>",
  "subject": "Project kickoff!",
  "replies_count": 5,
  "replies_url": "https://3.basecampapi.com/195539477/buckets/2085958500/client/recordings/1069479566/replies.json"
}
```
<!-- END GET /buckets/1/client/correspondences/2.json -->
###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/client/correspondences/2.json
```

[pagination]: https://github.com/basecamp/bc3-api/blob/master/README.md#pagination
