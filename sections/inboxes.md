Inboxes
=======

All forwards in a Basecamp are children of an Inbox resource.

Endpoints:

- [Get inbox](#get-inbox)


Get inbox
---------

* `GET /buckets/1/inboxes/2.json` will return the inbox with an ID of `2` for the Basecamp with an ID of `1`.

To get the inbox ID for a Basecamp, see the [Get a Basecamp][1] endpoint's `dock` payload. To retrieve its forwards, see the [Get forwards][2] endpoint.

###### Example JSON Response
<!-- START GET /buckets/1/inboxes/2.json -->
```json
{
  "id": 9007199254741055,
  "status": "active",
  "created_at": "2016-09-20T14:32:33.236Z",
  "updated_at": "2016-09-20T14:32:58.127Z",
  "type": "Inbox",
  "url": "https://3.basecampapi.com/195539477/buckets/2085958496/inboxes/9007199254741055.json",
  "app_url": "https://3.basecamp.com/195539477/buckets/2085958496/inboxes/9007199254741055",
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
  "title": "Forwards",
  "forwards_count": 2,
  "forwards_url": "https://3.basecampapi.com/195539477/buckets/2085958496/inboxes/9007199254741055/forwards.json"
}
```
<!-- END GET /buckets/1/inboxes/2.json -->

###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/inboxes/2.json
```


[1]: https://github.com/basecamp/bc3-api/blob/master/sections/basecamps.md#get-a-basecamp
[2]: https://github.com/basecamp/bc3-api/blob/master/sections/forwards.md#get-forwards
