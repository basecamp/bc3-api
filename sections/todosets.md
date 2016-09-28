To-do sets
==========

All to-do lists under a Basecamp are children of a to-do set resource.

Endpoints:

- [Get to-do set](#get-to-do-set)


Get to-do set
-------------

* `GET /buckets/1/todosets/2.json` will return the to-do set for the Basecamp with an ID of `1`.

To get the to-do set ID for a Basecamp, see the [Get a Basecamp][1] endpoint's `dock` payload. To retrieve its to-do lists, see the [Get to-do lists][2] endpoint.

###### Example JSON Response
<!-- START GET /buckets/1/todosets/2.json -->
```json
{
  "id": 9007199254741445,
  "status": "active",
  "created_at": "2016-09-28T14:25:24.543Z",
  "updated_at": "2016-09-28T14:25:52.344Z",
  "type": "Todoset",
  "url": "https://3.basecampapi.com/195539477/buckets/2085958498/todosets/9007199254741445.json",
  "app_url": "https://3.basecamp.com/195539477/buckets/2085958498/todosets/9007199254741445",
  "bucket": {
    "id": 2085958498,
    "name": "The Leto Laptop",
    "type": "Project"
  },
  "creator": {
    "id": 1007299144,
    "attachable_sgid": "BAh7CEkiCGdpZAY6BkVUSSIrZ2lkOi8vYmMzL1BlcnNvbi8xMDA3Mjk5MTQ0P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg9hdHRhY2hhYmxlBjsAVEkiD2V4cGlyZXNfYXQGOwBUMA==--2e34d7611a9fcaeb82342d015a671cf5e998c036",
    "name": "Victor Cooper",
    "email_address": "victor@honchodesign.com",
    "personable_type": "User",
    "title": "Chief Strategist",
    "bio": "Don't let your dreams be dreams",
    "created_at": "2016-09-28T14:24:20.217Z",
    "updated_at": "2016-09-28T14:24:23.289Z",
    "admin": true,
    "owner": true,
    "time_zone": "America/Chicago",
    "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBEgqCjw=--8266bb0507508f3d46050d57b65924d5e2a005f3/avatar-64-x4",
    "company": {
      "id": 1033447817,
      "name": "Honcho Design"
    }
  },
  "completed": false,
  "completed_ratio": "14/60",
  "name": "To-dos",
  "todolists_count": 10,
  "todolists_url": "https://3.basecampapi.com/195539477/buckets/2085958498/todosets/9007199254741445/todolists.json",
  "app_todoslists_url": "https://3.basecamp.com/195539477/buckets/2085958498/todosets/9007199254741445/todolists"
}
```
<!-- END GET /buckets/1/todosets/2.json -->
###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/todosets/2.json
```


[1]: https://github.com/basecamp/bc3-api/blob/master/sections/basecamps.md#get-a-basecamp
[2]: https://github.com/basecamp/bc3-api/blob/master/sections/todolists.md#get-to-do-lists
[3]: https://github.com/basecamp/bc3-api/blob/master/sections/recordings.md#trash-a-recording
