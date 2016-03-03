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

* `GET /buckets/1/messages.json` will return a [paginated list][1] of active messages in the Basecamp with an ID of `1`.

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
      "subject" : "What's on your plate this week?",
      "parent" : {
         "id" : 9007199254741044,
         "url" : "https://3.basecamp.com/195539477/buckets/2085958496/message_boards/9007199254741044",
         "title" : "Message Board"
      },
      "content" : "<div>Let's get it all on the table.</div>"
   },
   ...
]
```

###### Copy as cURL:

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecamp.com/$ACCOUNT_ID/buckets/2085958506/messages.json
```


Get a message
-------------

* `GET /buckets/1/messages/2.json` will return the message with an ID of `2` in the Basecamp with an ID of `1`.

``` json
{
   "status" : "active",
   "creator" : {
      "avatar_url" : "https://3.basecamp-static.com/195539477/people/BAhpBEgqCjw=--8266bb0507508f3d46050d57b65924d5e2a005f3/avatar-64-x4",
      "id" : 1007299144,
      "email_address" : "victor@honchodesign.com",
      "name" : "Victor Cooper"
   },
   "content" : "Hey team - a couple of weeks ago we asked a question in Know Your Company - 'What have we gotten worse at over the last year?'<br/><br/>\n\n  Of course I had hoped nothing, but that's probably not realistic. 😬 I read a lot of great feedback, but the general theme is that we've gotten much worse with overwork. That our clients demand even more of our time, and we haven't grown necessarily.<br/><br/>\n\n  That means more work across the same amount of people, which means longer days, more weekend work, and ultimately more burn out. And as our clients have grown, so has our geographic dispersal - bigger clients means more travel. And that's not helping us get any more done either.<br/><br/>\n\n  I want you to know I hear you. This is unacceptable from my perspective. I knew we were taking a hit work wise and couldn't sustain it, but I didn't know it was this bad. That's my fault.<br/><br/>\n\n  So here's what we going to do, immediately:\n  <ul>\n    <li>If you know you're working more than 45 hours a week, just stop. Seriously, just stop. The work will still be there, and it will be better for it if you take some time away from it. I know this is easier said than done.</li>\n    <li>Talk to your manager, ASAP. Honestly, if deadlines need to move, so be it. If deliverables need to be cut, so be it.</li>\n    <li>Plan vacation, now. Stop procrastinating and say you'll figure it out later. You won't. Plan with your teams and get a slot of at minimum 3-4 days off in row, preferably a week or more.</li>\n    <li>Myself and the management team are looking at clients across the board. We're going to strongly consider firing the least profitable clients. We're at a good size and aren't going to grow for the sake of it. This is longer term planning. We can't ditch clients overnight, but in the next 6 months expect reduction in low-profit, or painful clients.</li>\n    <li>Try to avoid working weekends at all costs. I know an email or two might have to be sent. Resist the urge.</li>\n    <li>We're bringing on more contractors to ease the burden of work across more people.</li>\n  </ul><br/>\n\n  I know this sounds a bit like I'm preaching -- that in reality, the client work can't just stop. But believe me, it can. We can manage our clients if we know what we need to do. The quality of our work, and the quality of your lives has always been what has made us great. We're not about to just give that up, even though I've failed to recognize it until it got to this point. For that, I'm sorry. But I think we can turn it around.<br/><br/>\n\n  I'll update you soon on where everything stands soon. Thanks for all your hard work. Now go take a breather.<br/><br/>\n\n  -Victor",
   "bookmark_url" : "https://3.basecamp.com/195539477/my/bookmarks/BAh7CEkiCGdpZAY6BkVUSSI0Z2lkOi8vYmMzL1JlY29yZGluZy85MDA3MTk5MjU0NzQxMjg0P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg1yZWFkYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--cc06ad7b09ccc6ab6f6bda67b01ba0bfd651e221",
   "subject" : "Know Your Company: What we've gotten worse at",
   "bucket_path" : "/195539477/buckets/2085958496",
   "type" : "Message",
   "comments_count" : 10,
   "subscription_url" : "https://3.basecamp.com/195539477/buckets/2085958496/recordings/9007199254741284/subscription",
   "updated_at" : "2016-01-27T11:01:39.368-06:00",
   "url" : "https://3.basecamp.com/195539477/buckets/2085958496/messages/9007199254741284",
   "bucket" : {
      "updated_at" : "2015-10-27T12:00:28.313-05:00",
      "id" : 1042979250,
      "account_id" : 31989850,
      "client_company_id" : null,
      "created_at" : "2015-10-27T12:00:28.313-05:00",
      "name" : "Honcho Design Newsroom",
      "creator_id" : 1007299144,
      "description" : "Let's talk about the company!"
   },
   "id" : 9007199254741284,
   "created_at" : "2016-01-20T14:26:28.313-06:00"
}
```

###### Copy as cURL:

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecamp.com/$ACCOUNT_ID/buckets/1/messages/2.json
```


Create a message
----------------

* `POST /buckets/1/messages.json` publishes a message with the given `subject` and optionally, some HTML `content` in the Basecamp with ID `1`.

``` json
{
  "subject": "Kickoff",
  "content": "<div><strong>Welcome to Basecamp, everyone.</strong></div>"
}
```

This will return `201 Created` with the current JSON representation of the message if the creation was a success. See the [Get a message](#get-a-message) endpoint for more info on the payload, and check out what is allowed in the `content` field in our [Rich content][2] guide.

###### Copy as cURL:

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -H "Content-Type: application/json" \
  -d '{"subject":"Kickoff","content":"<div><strong>Welcome to Basecamp, everyone.</strong></div>"}' \
  https://basecamp.com/$ACCOUNT_ID/buckets/2085958506/messages.json
```


Update a message
-----------------

* `PUT /buckets/1/messages/2.json` allows changing the subject and content of the message with an ID of `2` in the Basecamp with ID `1`.

``` json
{
  "subject": "Spin-down",
  "content": "<div><strong>Oops, we lost that client.</strong></div>"
}
```

This will return `200 OK` with the current JSON representation of the message if the update was a success. See the [Get a message](#get-a-message) endpoint for more info.

###### Copy as cURL:

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -H "Content-Type: application/json" \
  -d '{"name":"Spin-down","description":"<div><strong>Oops, we lost that client.</strong></div>"}' -X PUT \
  https://3.basecamp.com/$ACCOUNT_ID/buckets/2085958506.json
```


[1]: https://github.com/basecamp/bc3-api/blob/master/README.md#pagination
[2]: https://github.com/basecamp/bc3-api/blob/master/README.md#rich-content
