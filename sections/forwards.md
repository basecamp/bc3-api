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
    "id": 1069479031,
    "status": "active",
    "visible_to_clients": false,
    "created_at": "2022-09-01T10:16:24.930Z",
    "updated_at": "2022-09-01T10:16:24.930Z",
    "title": "Fwd: Some technical details",
    "inherits_status": true,
    "type": "Inbox::Forward",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958497/inbox_forwards/1069479031.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958497/inbox_forwards/1069479031",
    "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7CEkiCGdpZAY6BkVUSSIuZ2lkOi8vYmMzL1JlY29yZGluZy8xMDY5NDc5MDMxP2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg1yZWFkYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--4891627f80344c55f5a27c306dff50d689e6cbf1.json",
    "subscription_url": "https://3.basecampapi.com/195539477/buckets/2085958497/recordings/1069479031/subscription.json",
    "parent": {
      "id": 1069478936,
      "title": "Email Forwards",
      "type": "Inbox",
      "url": "https://3.basecampapi.com/195539477/buckets/2085958497/inboxes/1069478936.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958497/inboxes/1069478936"
    },
    "bucket": {
      "id": 2085958497,
      "name": "Honcho Design Newsroom",
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
    "content": "---------- Forwarded message ----------\nFrom: \"Beth Allen\" \nDate: Oct 13, 2013 1:38 PM\nSubject: Some technical details\nTo: \"Annie Bryan\" \n\nHey Team Honcho,\n\nJust wanted to let you know I'm a big fan of your blog. Your writing is so inspiring. Thanks for sharing!",
    "subject": "Fwd: Some technical details",
    "from": "beth@letobrand.com",
    "replies_count": 0,
    "replies_url": "https://3.basecampapi.com/195539477/buckets/2085958497/inbox_forwards/1069479031/replies.json"
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
  "id": 1069479032,
  "status": "active",
  "visible_to_clients": false,
  "created_at": "2022-09-01T09:04:24.930Z",
  "updated_at": "2022-11-22T08:23:32.496Z",
  "title": "Fwd: Can we make the logo pop?",
  "inherits_status": true,
  "type": "Inbox::Forward",
  "url": "https://3.basecampapi.com/195539477/buckets/2085958497/inbox_forwards/1069479032.json",
  "app_url": "https://3.basecamp.com/195539477/buckets/2085958497/inbox_forwards/1069479032",
  "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7CEkiCGdpZAY6BkVUSSIuZ2lkOi8vYmMzL1JlY29yZGluZy8xMDY5NDc5MDMyP2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg1yZWFkYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--22643a88456d69fada6fdb7e215bdc16aaa20b84.json",
  "subscription_url": "https://3.basecampapi.com/195539477/buckets/2085958497/recordings/1069479032/subscription.json",
  "parent": {
    "id": 1069478936,
    "title": "Email Forwards",
    "type": "Inbox",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958497/inboxes/1069478936.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958497/inboxes/1069478936"
  },
  "bucket": {
    "id": 2085958497,
    "name": "Honcho Design Newsroom",
    "type": "Project"
  },
  "creator": {
    "id": 1049715914,
    "attachable_sgid": "BAh7CEkiCGdpZAY6BkVUSSIrZ2lkOi8vYmMzL1BlcnNvbi8xMDQ5NzE1OTE0P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg9hdHRhY2hhYmxlBjsAVEkiD2V4cGlyZXNfYXQGOwBUMA==--ff006accb6e013cca785190fa38f42c091d24f1e",
    "name": "Victor Cooper",
    "email_address": "victor@honchodesign.com",
    "personable_type": "User",
    "title": "Chief Strategist",
    "bio": "Don’t let your dreams be dreams",
    "location": "Chicago, IL",
    "created_at": "2022-11-22T08:23:21.732Z",
    "updated_at": "2022-11-22T08:23:21.904Z",
    "admin": true,
    "owner": true,
    "client": false,
    "employee": true,
    "time_zone": "America/Chicago",
    "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBMpkkT4=--5520caeec1845b5090bbfc993ffe8eca8d138e14/avatar?v=1",
    "company": {
      "id": 1033447817,
      "name": "Honcho Design"
    },
    "can_manage_projects": true,
    "can_manage_people": true
  },
  "content": "---------- Forwarded message ----------\nFrom: \"Henry Bowman\" \nDate: Oct 15, 2013 1:13 AM\nSubject: Can we make the logo pop?\nTo: \"Victor Cooper\" \n\nHey Victor,\n\nI know it's late at night, but I had a quick thought about the logo. It feels, I dunno, flat. Is there anything you could do to make it pop? I'm thinking it needs more sizzle. More... SOMETHING. Maybe we could try adding a rainbow?\n\nLet's take a look mid-day tomorrow and re-group with the rest of the team.\n\nCheers,\nHenry",
  "subject": "Fwd: Can we make the logo pop?",
  "from": "henry@letobrand.com",
  "replies_count": 2,
  "replies_url": "https://3.basecampapi.com/195539477/buckets/2085958497/inbox_forwards/1069479032/replies.json"
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
