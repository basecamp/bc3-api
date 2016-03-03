Messages
========

Endpoints:

- [Get messages](#get-messages)
- [Get a message](#get-a-message)
- [Create a message](#create-a-message)
- [Update a message](#update-a-message)
- [Trash a message](#trash-a-message)

Get messages
------------

* `GET /buckets/1/messages.json` will return a [paginated list][1] of active messages in the basecamp with an ID of `1`.

``` json
[
   {
      "type" : "Message",
      "creator" : {
         "id" : 1007299145,
         "name" : "Annie Bryan",
         "avatar_url" : "https://3.basecamp-static.com/195539477/people/BAhpBEkqCjw=--7e8e5d9e90e4898faee5f69e72def9e58da85fbe/avatar-64-x4",
         "email_address" : "annie@honchodesign.com"
      },
      "comments_count" : 5,
      "bucket" : {
         "description" : "Let's talk about the company!",
         "updated_at" : "2015-10-27T12:00:28.313-05:00",
         "name" : "Honcho Design Newsroom",
         "client_company_id" : null,
         "id" : 1042979250,
         "account_id" : 31989850,
         "creator_id" : 1007299144,
         "created_at" : "2015-10-27T12:00:28.313-05:00"
      },
      "status" : "active",
      "created_at" : "2016-02-03T12:22:46.082-06:00",
      "id" : 9007199254741871,
      "url" : "https://3.basecamp.com/195539477/buckets/2085958496/messages/9007199254741871",
      "updated_at" : "2016-02-03T12:48:48.704-06:00",
      "bucket_path" : "/195539477/buckets/2085958496",
      "subject" : "Another one",
      "parent" : {
         "id" : 9007199254741044,
         "url" : "https://3.basecamp.com/195539477/buckets/2085958496/message_boards/9007199254741044",
         "title" : "Message Board"
      },
      "content" : "<div>wow</div>"
   },
   {
      "bucket_path" : "/195539477/buckets/2085958496",
      "content" : "We thought it would be cool to see how we all have our home screens on our phones organized. Please add your homescreen if you'd like me to include it in a blog post this Friday. Thanks!",
      "parent" : {
         "id" : 9007199254741044,
         "title" : "Message Board",
         "url" : "https://3.basecamp.com/195539477/buckets/2085958496/message_boards/9007199254741044"
      },
      "subject" : "Home screens at Honcho",
      "created_at" : "2016-01-23T12:09:28.313-06:00",
      "id" : 9007199254741318,
      "status" : "active",
      "type" : "Message",
      "creator" : {
         "avatar_url" : "https://3.basecamp-static.com/195539477/people/BAhpBEsqCjw=--628b01c4d4d8909d3ef57844195aeaa302338966/avatar-64-x4",
         "name" : "Jared Davis",
         "email_address" : "jared@honchodesign.com",
         "id" : 1007299147
      },
      "comments_count" : 17,
      "bucket" : {
         "updated_at" : "2015-10-27T12:00:28.313-05:00",
         "name" : "Honcho Design Newsroom",
         "id" : 1042979250,
         "created_at" : "2015-10-27T12:00:28.313-05:00",
         "account_id" : 31989850,
         "creator_id" : 1007299144,
         "client_company_id" : null,
         "description" : "Let's talk about the company!"
      },
      "updated_at" : "2016-01-27T11:01:57.926-06:00",
      "url" : "https://3.basecamp.com/195539477/buckets/2085958496/messages/9007199254741318"
   },
   ...
]
```

###### Copy as cURL:

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecamp.com/$ACCOUNT_ID/buckets/1/messages.json
```

Pagination?

Get message
-----------

[1]: https://github.com/basecamp/bc3-api/blob/master/README.md#pagination
