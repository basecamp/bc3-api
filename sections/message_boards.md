Message Boards
==============

Endpoints:

- [Get message boards](#get-message-boards)

Get message boards
------------------

* `GET /buckets/1/message_boards.json` will return an array, with the first entry being the message board for the Basecamp with an ID of `1`.

This payload includes the most recent 10 messages in the `entries` key. To retrieve more, see the [Get messages][1] endpoint.

``` json
[
   {
      "created_at" : "2016-01-27T11:00:28.446-06:00",
      "creator" : {
         "name" : "Victor Cooper",
         "avatar_url" : "https://3.basecamp-static.com/195539477/people/BAhpBEgqCjw=--8266bb0507508f3d46050d57b65924d5e2a005f3/avatar-64-x4",
         "id" : 1007299144,
         "email_address" : "victor@honchodesign.com"
      },
      "bucket_path" : "/195539477/buckets/2085958496",
      "updated_at" : "2016-02-03T15:40:39.036-06:00",
      "messages_count" : 16,
      "bucket" : {
         "account_id" : 31989850,
         "created_at" : "2015-10-27T12:00:28.313-05:00",
         "description" : "Let's talk about the company!",
         "client_company_id" : null,
         "id" : 1042979250,
         "creator_id" : 1007299144,
         "updated_at" : "2015-10-27T12:00:28.313-05:00",
         "name" : "Honcho Design Newsroom"
      },
      "comments_count" : 0,
      "title" : "Message Board",
      "status" : "active",
      "type" : "Message::Board",
      "url" : "https://3.basecamp.com/195539477/buckets/2085958496/message_boards/9007199254741044",
      "id" : 9007199254741044,
      "entries" : [
         {
            "id" : 9007199254741256,
            "url" : "https://3.basecamp.com/195539477/buckets/2085958496/messages/9007199254741256",
            "subject" : "Next Quarterly meeting",
            "type" : "Message",
            "updated_at" : "2016-01-27T11:01:29.606-06:00",
            "bucket" : {
               "id" : 1042979250,
               "client_company_id" : null,
               "description" : "Let's talk about the company!",
               "updated_at" : "2015-10-27T12:00:28.313-05:00",
               "name" : "Honcho Design Newsroom",
               "creator_id" : 1007299144,
               "created_at" : "2015-10-27T12:00:28.313-05:00",
               "account_id" : 31989850
            },
            "comments_count" : 10,
            "status" : "active",
            "parent" : {
               "title" : "Message Board",
               "url" : "https://3.basecamp.com/195539477/buckets/2085958496/message_boards/9007199254741044",
               "id" : 9007199254741044
            },
            "bucket_path" : "/195539477/buckets/2085958496",
            "created_at" : "2016-01-15T13:50:28.313-06:00",
            "content" : "Hey all - we're planning our next quarterly get together.",
            "creator" : {
               "email_address" : "jennifer@honchodesign.com",
               "id" : 1007299148,
               "name" : "Jennifer Young",
               "avatar_url" : "https://3.basecamp-static.com/195539477/people/BAhpBEwqCjw=--6d75c96cdfed6528797fe38d7b07ed9b8cc630c8/avatar-64-x4"
            }
         },
         ...
      ]
   }
]
```

###### Copy as cURL:

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecamp.com/$ACCOUNT_ID/buckets/2085958506/message_boards.json
```


[1]: https://github.com/basecamp/bc3-api/blob/master/sections/messages.md#get-messages
