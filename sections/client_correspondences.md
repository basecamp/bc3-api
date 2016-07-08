Client correspondences
======================

Endpoints:

- [Get client correspondences](#get-client-correspondences)
- [Get a client correspondence](#get-a-client-correspondence)

Get client correspondences
--------------------------

* `GET /buckets/1/client/correspondences.json` will return a [paginated list][pagination] of client correspondences in the Basecamp with an ID of `1`.

###### Example JSON Response
<!-- START GET /buckets/1/client/correspondences.json -->
```json
[
  {
    "id": 9007199254741734,
    "status": "active",
    "created_at": "2016-07-03T19:06:44.210Z",
    "updated_at": "2016-07-08T16:49:58.839Z",
    "type": "Client::Correspondence",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958499/client/correspondences/9007199254741734.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958499/client/correspondences/9007199254741734",
    "parent": {
      "id": 9007199254741653,
      "title": "The Clientside",
      "type": "Client::Board",
      "url": "https://3.basecampapi.com/195539477/buckets/2085958499/client/board.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958499/client/board"
    },
    "bucket": {
      "id": 2085958499,
      "name": "The Leto Locator",
      "type": "Project"
    },
    "creator": {
      "id": 1007299209,
      "name": "Annie Bryan",
      "email_address": "annie@honchodesign.com",
      "personable_type": "User",
      "title": "Central Markets Manager",
      "created_at": "2016-07-08T16:48:02.619Z",
      "updated_at": "2016-07-08T16:48:02.619Z",
      "admin": false,
      "owner": false,
      "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBIkqCjw=--003094c5a28c4331af92401ec3675148e81d7bc1/avatar-64-x4",
      "company": {
        "id": 1033447822,
        "name": "Honcho Design"
      }
    },
    "content_html": "Hey everyone - we're in the home stretch! It's hard to believe how far we've come in just about 6 weeks. We've made incredible progress - created an in depth strategy and plan of attack, built an awesome experience and design, and backed it with incredible technology. We're so thrilled to be nearing the finish line - not just that we did it, but the way we did it.<br><br>\n\n  Of course, we're not quite there yet so we don't want to start celebrating just yet . We're running through our final bug fixes and those should be done today. We'll want one more pass by legal to take a look. And then of course, one more eyeball from the Leto team. In fact, we're in such good shape, we could even launch the site as-is - it's really solid.<br><br>\n\n  Please let us know if there's anything else on your minds before launch, but just wanted to report back that we're in good shape and on target to launch on schedule!",
    "content_text": "Hey everyone - we're in the home stretch! It's hard to believe how far we've come in just about 6 weeks. We've made incredible progress - created an in depth strategy and plan of attack, built an awesome experience and design, and backed it with incredible technology. We're so thrilled to be nearing the finish line - not just that we did it, but the way we did it.\n\nOf course, we're not quite there yet so we don't want to start celebrating just yet . We're running through our final bug fixes and those should be done today. We'll want one more pass by legal to take a look. And then of course, one more eyeball from the Leto team. In fact, we're in such good shape, we could even launch the site as-is - it's really solid.\n\nPlease let us know if there's anything else on your minds before launch, but just wanted to report back that we're in good shape and on target to launch on schedule!",
    "subject": "Final deliverables and launch are right around the corner",
    "replies_count": 5,
    "replies_url": "https://3.basecampapi.com/195539477/buckets/2085958499/client/recordings/9007199254741734/replies.json"
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

* `GET /buckets/1/client/correspondences/2.json` will return the client correspondence with an ID of `2` in the Basecamp with an ID of `1`.

###### Example JSON Response
<!-- START GET /buckets/1/client/correspondences/2.json -->
```json
{
  "id": 9007199254741655,
  "status": "active",
  "created_at": "2016-05-25T19:11:44.210Z",
  "updated_at": "2016-07-08T16:49:46.615Z",
  "type": "Client::Correspondence",
  "url": "https://3.basecampapi.com/195539477/buckets/2085958499/client/correspondences/9007199254741655.json",
  "app_url": "https://3.basecamp.com/195539477/buckets/2085958499/client/correspondences/9007199254741655",
  "parent": {
    "id": 9007199254741653,
    "title": "The Clientside",
    "type": "Client::Board",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958499/client/board.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958499/client/board"
  },
  "bucket": {
    "id": 2085958499,
    "name": "The Leto Locator",
    "type": "Project"
  },
  "creator": {
    "id": 1007299223,
    "name": "Jay Edmonds",
    "email_address": "jay@honchodesign.com",
    "personable_type": "User",
    "title": "Internal Marketing Assistant",
    "created_at": "2016-07-08T16:48:04.750Z",
    "updated_at": "2016-07-08T16:48:04.750Z",
    "admin": false,
    "owner": false,
    "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBJcqCjw=--67aca445eea5616b64015b2fc306f6d654bc02cb/avatar-64-x4"
  },
  "content_html": "Hi everyone! Welcome to the Basecamp that we'll be using to collaboroate and manage the Leto Locator project.\n\n  We're particularly excited to bring on board our friends from Leto - Stephen, Miranda, and Beth. I know you guys have used Basecamp before, but so we're on the same page, we'll post a bunch of discussions, things for review, and todos to make sure we stay on the same page. We'll do our best to keep everyone looped in this way, instead of using email (which can be hard to keep people up to date on stuff.)\n\n  I also want to take a moment to introduce our team. It will be evolving and growing soon, but right now we've got some core team members: Myself as the Account Director, Annie as the Senior PM, Jared is our tech lead, Matt is our ACD, and Victor, of course, you know. A few people will be coming on to support us, but this will be your core team. You can, of course, reach out to any one of us at any time, but I'll ultimately be the one responsible for making sure you're happy with our work.\n\n  Again, can't tell you how excited we are to get started on this and all the other projects. Let's go, Leto!\n\n  -Jay",
  "content_text": "Hi everyone! Welcome to the Basecamp that we'll be using to collaboroate and manage the Leto Locator project.\n\nWe're particularly excited to bring on board our friends from Leto - Stephen, Miranda, and Beth. I know you guys have used Basecamp before, but so we're on the same page, we'll post a bunch of discussions, things for review, and todos to make sure we stay on the same page. We'll do our best to keep everyone looped in this way, instead of using email (which can be hard to keep people up to date on stuff.)\n\nI also want to take a moment to introduce our team. It will be evolving and growing soon, but right now we've got some core team members: Myself as the Account Director, Annie as the Senior PM, Jared is our tech lead, Matt is our ACD, and Victor, of course, you know. A few people will be coming on to support us, but this will be your core team. You can, of course, reach out to any one of us at any time, but I'll ultimately be the one responsible for making sure you're happy with our work.\n\nAgain, can't tell you how excited we are to get started on this and all the other projects. Let's go, Leto!\n\n-Jay",
  "subject": "Project kickoff!",
  "replies_count": 5,
  "replies_url": "https://3.basecampapi.com/195539477/buckets/2085958499/client/recordings/9007199254741655/replies.json"
}
```
<!-- END GET /buckets/1/client/correspondences/2.json -->
###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/client/correspondences/2.json
```

[pagination]: https://github.com/basecamp/bc3-api/blob/master/README.md#pagination
