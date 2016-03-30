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

``` json
{
  "id": 9007199254741044,
  "created_at": "2016-01-27T11:00:28.483-06:00",
  "updated_at": "2016-03-16T12:14:01.288-05:00",
  "status": "active",
  "url": "https://3.basecampapi.com/195539477/buckets/2085958496/todosets/9007199254741045",
  "name": "To-dos",
  "todolists_count": 4,
  "todolists_url": "https://3.basecampapi.com/195539477/buckets/2085958496/todolists.json",
  "type": "Todoset",
  "creator": {
    "id": 1007299144,
    "name": "Victor Cooper",
    "email_address": "victor@honchodesign.com",
    "avatar_url": "https://3.basecamp-assets.com/195539477/people/BAhpBEgqCjw=--8266bb0507508f3d46050d57b65924d5e2a005f3/avatar-64-x4"
  },
  "bucket": {
    "id": 1042979250,
    "account_id": 31989850,
    "name": "Honcho Design Newsroom",
    "description": "Let's talk about the company!",
    "created_at": "2015-10-27T12:00:28.313-05:00",
    "updated_at": "2015-10-27T12:00:28.313-05:00",
    "creator_id": 1007299144,
    "client_company_id": null
  },
  "bucket_path": "/195539477/buckets/2085958496"
}
```

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
