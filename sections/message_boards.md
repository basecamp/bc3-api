Message Boards
==============

All messages under a Basecamp are children of a Message Board resource.

Endpoints:

- [Get message board](#get-message-board)


Get message board
-----------------

* `GET /buckets/1/message_boards/2.json` will return the message board for the Basecamp with an ID of `1`.

To get the message board ID for a Basecamp, see the [Get a Basecamp][1] endpoint's `dock` payload. To retrieve its messages, see the [Get messages][2] endpoint.

###### Example JSON Response
<!-- START GET /buckets/1/message_boards/2.json -->
```json
{
  "id": 9007199254741434,
  "status": "active",
  "created_at": "2016-07-08T16:49:11.562Z",
  "updated_at": "2016-07-08T16:49:43.917Z",
  "type": "Message::Board",
  "url": "https://3.basecampapi.com/195539477/buckets/2085958498/message_boards/9007199254741434.json",
  "app_url": "https://3.basecamp.com/195539477/buckets/2085958498/message_boards/9007199254741434",
  "bucket": {
    "id": 2085958498,
    "name": "The Leto Laptop",
    "type": "Project"
  },
  "creator": {
    "id": 1007299208,
    "name": "Victor Cooper",
    "email_address": "victor@honchodesign.com",
    "personable_type": "User",
    "title": null,
    "created_at": "2016-07-08T16:48:02.496Z",
    "updated_at": "2016-07-08T16:48:02.592Z",
    "admin": true,
    "owner": true,
    "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBIgqCjw=--719e3f2aa4406cf5806c2c1522259710deb788e4/avatar-64-x4",
    "company": {
      "id": 1033447822,
      "name": "Honcho Design"
    }
  },
  "title": "Message Board",
  "messages_count": 9,
  "messages_url": "https://3.basecampapi.com/195539477/buckets/2085958498/message_boards/9007199254741434/messages.json",
  "app_messages_url": "https://3.basecamp.com/195539477/buckets/2085958498/message_boards/9007199254741434/messages"
}
```
<!-- END GET /buckets/1/message_boards/2.json -->
###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/message_boards/2.json
```


[1]: https://github.com/basecamp/bc3-api/blob/master/sections/basecamps.md#get-a-basecamp
[2]: https://github.com/basecamp/bc3-api/blob/master/sections/messages.md#get-messages
[3]: https://github.com/basecamp/bc3-api/blob/master/sections/recordings.md#trash-a-recording
