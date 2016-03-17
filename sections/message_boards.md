Message Boards
==============

All messages under a Basecamp are children of a Message Board resource.

Endpoints:

- [Get message board](#get-message-board)
- [Hide message board tool](#hide-message-board)


Get message board
-----------------

* `GET /buckets/1/message_boards/2.json` will return the message board for the Basecamp with an ID of `1`.

To get the message board ID for a Basecamp, see the [Get a Basecamp][1] endpoint's `dock` payload. To retrieve its messages, see the [Get messages][2] endpoint.

###### Example JSON Response

``` json
{
  "id": 9007199254741044,
  "created_at": "2016-01-27T11:00:28.446-06:00",
  "updated_at": "2016-03-15T13:14:41.883-05:00",
  "status": "active",
  "url": "https://3.basecamp.com/195539477/buckets/2085958496/message_boards/9007199254741044",
  "title": "Message Board",
  "messages_count": 16,
  "messages_url": "https://3.basecamp.com/195539477/buckets/2085958496/message_boards/9007199254741044/messages.json",
  "type": "Message::Board",
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
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecamp.com/$ACCOUNT_ID/buckets/1/message_boards/2.json
```


Hide message board tool
-----------------------

If you'd like to remove the message board from the list of active tools for a Basecamp, use the [Trash a recording][3] endpoint with the ID of the message board as the recording ID.


[1]: https://github.com/basecamp/bc3-api/blob/master/sections/basecamps.md#get-a-basecamp
[2]: https://github.com/basecamp/bc3-api/blob/master/sections/messages.md#get-messages
[3]: https://github.com/basecamp/bc3-api/blob/master/sections/recordings.md#trash-a-recording
