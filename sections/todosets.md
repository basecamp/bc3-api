To-do sets
==========

All to-do lists under a Basecamp are children of a to-do set resource.

Endpoints:

- [Get to-do sets](#get-to-do-sets)
- [Get to-do set](#get-to-do-set)
- [Hide to-dos tool](#hide-to-dos-tool)

Get to-do sets
--------------

* `GET /buckets/1/todosets.json` will return an array, with the first entry being the to-do set for the Basecamp with an ID of `1`.

This payload includes the first 10 todolists in the `todolists` key. To retrieve more, see the [Get to-do lists][1] endpoint.

###### Example JSON Response

``` json
[
  {
    "bucket": {
      "account_id": 31989850,
      "client_company_id": null,
      "created_at": "2015-12-27T11:00:20.687-06:00",
      "creator_id": 1007299144,
      "description": "Annie's Stuff. Keep Out. 😁",
      "id": 1042979249,
      "name": "Annie's Corner",
      "updated_at": "2015-12-27T11:00:20.687-06:00"
    },
    "bucket_path": "/195539477/buckets/2085958495",
    "comments_count": 0,
    "created_at": "2016-01-27T11:00:20.851-06:00",
    "creator": {
      "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBEgqCjw=--8266bb0507508f3d46050d57b65924d5e2a005f3/avatar-64-x4",
      "email_address": "victor@honchodesign.com",
      "id": 1007299144,
      "name": "Victor Cooper"
    },
    "description": null,
    "id": 9007199254741014,
    "name": "To-dos",
    "status": "active",
    "todolists": [
      ...
    ],
    "todolists_count": 2,
    "todolists_url": "https://3.basecamp.com/195539477/buckets/2085958495/todolists.json",
    "type": "Todoset",
    "updated_at": "2016-02-11T09:49:51.452-06:00",
    "url": "https://3.basecamp.com/195539477/buckets/2085958495/todosets/9007199254741014"
  }
]
```

###### Copy as cURL:

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecamp.com/$ACCOUNT_ID/buckets/1/todosets.json
```


Get to-do set
-------------

* `GET /buckets/1/todosets/2.json` will return the to-do set for the Basecamp with an ID of `1`.

The payload returned is the same as the [Get to-do sets](#get-to-do-set) endpoint, just not inside of an array.

###### Copy as cURL:

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecamp.com/$ACCOUNT_ID/buckets/1/todosets/2.json
```


Hide to-dos tool
----------------

If you'd like to remove to-dos from the list of active tools for a Basecamp, use the [Trash a recording][2] endpoint with the ID of the to-do set as the recording ID.


[1]: https://github.com/basecamp/bc3-api/blob/master/sections/todolists.md#todolists
[2]: https://github.com/basecamp/bc3-api/blob/master/sections/recordings.md#trash-a-recording
