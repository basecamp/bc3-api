To-do sets
==========

All to-do lists under a Basecamp are children of a to-do set resource.

Endpoints:

- [Get to-do set](#get-to-do-set)
- [Hide to-dos tool](#hide-to-dos-tool)


Get to-do set
-------------

* `GET /buckets/1/todosets/2.json` will return the to-do set for the Basecamp with an ID of `1`.

To get the to-do set ID for a Basecamp, see the [Get a Basecamp][1] endpoint's `dock` payload. To retrieve its to-do lists, see the [Get to-do lists][2] endpoint.

###### Example JSON Response
<!-- START GET /buckets/1/todosets/2.json -->
```json
{
  "id": 9007199254741435,
  "status": "active",
  "created_at": "2016-06-27T17:30:10.574Z",
  "updated_at": "2016-06-27T17:30:35.589Z",
  "bucket_path": "/195539477/buckets/2085958498",
  "type": "Todoset",
  "comments_count": 0,
  "url": "https://3.basecampapi.com/195539477/buckets/2085958498/todosets/9007199254741435.json",
  "app_url": "https://3.basecamp.com/195539477/buckets/2085958498/todosets/9007199254741435",
  "creator": {
    "id": 1007299143,
    "name": "Victor Cooper",
    "email_address": "victor@honchodesign.com",
    "personable_type": "User",
    "title": null,
    "created_at": "2016-06-27T17:29:12.654Z",
    "updated_at": "2016-06-27T17:29:12.752Z",
    "admin": true,
    "owner": true,
    "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBEcqCjw=--c632b967cec296b87363a697a67a87f9cc1e5b45/avatar-64-x4",
    "company": {
      "id": 1033447817,
      "name": "Honcho Design"
    }
  },
  "bucket": {
    "id": 1042979252,
    "account_id": 1009501286,
    "name": "The Leto Laptop",
    "description": "Laptop product launch.",
    "created_at": "2016-06-02T17:30:10.480Z",
    "updated_at": "2016-06-02T17:30:10.480Z",
    "creator_id": 1007299143,
    "client_company_id": null
  },
  "name": "To-dos",
  "completed": false,
  "todolists_count": 10,
  "todolists_url": "https://3.basecampapi.com/195539477/buckets/2085958498/todosets/9007199254741435/todolists.json",
  "app_todoslists_url": "https://3.basecamp.com/195539477/buckets/2085958498/todosets/9007199254741435/todolists"
}
```
<!-- END GET /buckets/1/todosets/2.json -->
###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/todosets/2.json
```


Hide to-dos tool
----------------

If you'd like to remove to-dos from the list of active tools for a Basecamp, use the [Trash a recording][2] endpoint with the ID of the to-do set as the recording ID.


[1]: https://github.com/basecamp/bc3-api/blob/master/sections/basecamps.md#get-a-basecamp
[2]: https://github.com/basecamp/bc3-api/blob/master/sections/todolists.md#get-to-do-lists
[3]: https://github.com/basecamp/bc3-api/blob/master/sections/recordings.md#trash-a-recording
