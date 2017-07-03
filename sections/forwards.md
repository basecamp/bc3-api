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
    "id": 9007199254741145,
    "status": "active",
    "created_at": "2016-09-20T14:32:57.168Z",
    "updated_at": "2016-09-20T14:32:58.104Z",
    "type": "Inbox::Forward",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958496/inbox_forwards/9007199254741145.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958496/inbox_forwards/9007199254741145",
    "parent": {
      "id": 9007199254741055,
      "title": "Forwards",
      "type": "Inbox",
      "url": "https://3.basecampapi.com/195539477/buckets/2085958496/inboxes/9007199254741055.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958496/inboxes/9007199254741055"
    },
    "bucket": {
      "id": 2085958496,
      "name": "Honcho Design Newsroom",
      "type": "Project"
    },
    "creator": {
      "id": 1007299143,
      "attachable_sgid": "BAh7CEkiCGdpZAY6BkVUSSIrZ2lkOi8vYmMzL1BlcnNvbi8xMDA3Mjk5MTQzP2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg9hdHRhY2hhYmxlBjsAVEkiD2V4cGlyZXNfYXQGOwBUMA==--919d2c8b11ff403eefcab9db42dd26846d0c3102",
      "name": "Victor Cooper",
      "email_address": "victor@honchodesign.com",
      "personable_type": "User",
      "title": "Chief Strategist",
      "bio": "Don't let your dreams be dreams",
      "created_at": "2016-09-20T14:32:21.421Z",
      "updated_at": "2016-09-20T14:32:26.986Z",
      "admin": true,
      "owner": true,
      "time_zone": "America/Chicago",
      "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBEcqCjw=--c632b967cec296b87363a697a67a87f9cc1e5b45/avatar-64-x4",
      "company": {
        "id": 1033447817,
        "name": "Honcho Design"
      }
    },
    "content": "Hey Victor,\n\nI know it's late at night, but I had a quick thought about the logo. It feels, I dunno, flat. Is there anything you could do to make it pop? I'm thinking it needs more sizzle. More... SOMETHING. Maybe we could try adding a rainbow?\n\nLet's take a look mid-day tomorrow and re-group with the rest of the team.\n\nCheers,\nHenry",
    "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7CEkiCGdpZAY6BkVUSSI0Z2lkOi8vYmMzL1JlY29yZGluZy85MDA3MTk5MjU0NzQxMTQ1P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg1yZWFkYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--5e4e8dc00837d110504a8bdeb9a07bc75db16853.json",
    "subscription_url": "https://3.basecampapi.com/195539477/buckets/2085958496/recordings/9007199254741145/subscription.json",
    "subject": "Can we make the logo pop?",
    "from": "henry@letobrand.com",
    "replies_count": 2,
    "replies_url": "https://3.basecampapi.com/195539477/buckets/2085958496/inbox_forwards/9007199254741145/replies.json"
  }
]
```
<!-- END GET /buckets/1/inboxes/3/forwards.json -->

###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/inboxes/3/forwards.json
```


Get a forward
-------------

* `GET /buckets/1/inbox_forwards/2.json` will return the forward with an ID of `2` in the project with an ID of `1`.

###### Example JSON Response
<!-- START GET /buckets/1/inbox_forwards/2.json -->
```json
{
  "id": 9007199254741144,
  "status": "active",
  "created_at": "2016-09-20T14:32:55.810Z",
  "updated_at": "2016-09-20T14:32:55.888Z",
  "type": "Inbox::Forward",
  "url": "https://3.basecampapi.com/195539477/buckets/2085958496/inbox_forwards/9007199254741144.json",
  "app_url": "https://3.basecamp.com/195539477/buckets/2085958496/inbox_forwards/9007199254741144",
  "parent": {
    "id": 9007199254741055,
    "title": "Forwards",
    "type": "Inbox",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958496/inboxes/9007199254741055.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958496/inboxes/9007199254741055"
  },
  "bucket": {
    "id": 2085958496,
    "name": "Honcho Design Newsroom",
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
    "created_at": "2016-09-20T14:32:21.623Z",
    "updated_at": "2016-09-20T14:32:21.623Z",
    "admin": false,
    "owner": false,
    "time_zone": "America/Chicago",
    "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBEgqCjw=--8266bb0507508f3d46050d57b65924d5e2a005f3/avatar-64-x4",
    "company": {
      "id": 1033447817,
      "name": "Honcho Design"
    }
  },
  "content": "Hey Team Honcho,\n\nJust wanted to let you know I'm a big fan of your blog. Your writing is so inspiring. Thanks for sharing!",
  "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7CEkiCGdpZAY6BkVUSSI0Z2lkOi8vYmMzL1JlY29yZGluZy85MDA3MTk5MjU0NzQxMTQ0P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg1yZWFkYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--66b8dce4e70f3854809cf9a4ac1e47d353e405b8.json",
  "subscription_url": "https://3.basecampapi.com/195539477/buckets/2085958496/recordings/9007199254741144/subscription.json",
  "subject": "Some technical details",
  "from": "beth@letobrand.com",
  "replies_count": 0,
  "replies_url": "https://3.basecampapi.com/195539477/buckets/2085958496/inbox_forwards/9007199254741144/replies.json"
}
```
<!-- END GET /buckets/1/inbox_forwards/2.json -->

###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/inbox_forwards/2.json
```


[1]: https://github.com/basecamp/bc3-api/blob/master/sections/recordings.md#trash-a-recording
[2]: https://github.com/basecamp/bc3-api/blob/master/README.md#pagination
[3]: https://github.com/basecamp/bc3-api/blob/master/sections/inboxes.md#inboxes
