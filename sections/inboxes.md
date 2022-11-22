Inboxes
=======

All forwards in a project are children of an Inbox resource.

Endpoints:

- [Get inbox](#get-inbox)


Get inbox
---------

* `GET /buckets/1/inboxes/2.json` will return the inbox with an ID of `2` for the project with an ID of `1`.

To get the inbox ID for a project, see the [Get a project][1] endpoint's `dock` payload. To retrieve its forwards, see the [Get forwards][2] endpoint.

###### Example JSON Response
<!-- START GET /buckets/1/inboxes/2.json -->
```json
{
  "id": 1069478936,
  "status": "active",
  "visible_to_clients": false,
  "created_at": "2022-11-22T08:23:25.010Z",
  "updated_at": "2022-11-22T08:23:32.501Z",
  "title": "Email Forwards",
  "inherits_status": true,
  "type": "Inbox",
  "url": "https://3.basecampapi.com/195539477/buckets/2085958497/inboxes/1069478936.json",
  "app_url": "https://3.basecamp.com/195539477/buckets/2085958497/inboxes/1069478936",
  "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7CEkiCGdpZAY6BkVUSSIuZ2lkOi8vYmMzL1JlY29yZGluZy8xMDY5NDc4OTM2P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg1yZWFkYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--02c84e4d8421bf89b7325129cbdabce35ac11eaf.json",
  "position": 6,
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
  "forwards_count": 2,
  "forwards_url": "https://3.basecampapi.com/195539477/buckets/2085958497/inboxes/1069478936/forwards.json"
}
```
<!-- END GET /buckets/1/inboxes/2.json -->

###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/inboxes/2.json
```


[1]: https://github.com/basecamp/bc3-api/blob/master/sections/projects.md#get-a-project
[2]: https://github.com/basecamp/bc3-api/blob/master/sections/forwards.md#get-forwards
