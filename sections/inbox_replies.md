Inbox replies
==============

Inbox replies are nested under the recording ID of a [forward][forwards].

Endpoints:

- [Get inbox replies](#get-inbox-replies)
- [Get an inbox reply](#get-an-inbox-reply)

Get inbox replies
-------------------

* `GET /buckets/1/inbox_forwards/2/replies.json` will return a [paginated list][pagination] of inbox replies in the project with an ID of `1` and the forward with ID of `2`.

###### Example JSON Response
<!-- START GET /buckets/1/inbox_forwards/2/replies.json -->
```json
[
    {
        "id": 1660382161,
        "status": "active",
        "visible_to_clients": true,
        "created_at": "2019-03-14T09:17:34.481Z",
        "updated_at": "2019-03-14T09:17:34.498Z",
        "title": "Re: Project kickoff!",
        "inherits_status": true,
        "type": "Inbox::Reply",
        "url": "https://3.basecampapi.com/3714590/buckets/6883364/inbox_replies/1660382161.json",
        "app_url": "https://3.basecamp.com/3714590/buckets/6883364/inbox_forwards/1660377455#__recording_1660382161",
        "bookmark_url": "https://3.basecampapi.com/3714590/my/bookmarks/BAh7CEkiCGdpZAY6BkVUSSIuZ2lkOi8vYmMzL1JlY29yZGluZy8xNjYwMzgyMTYxP2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg1yZWFkYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--a3d7a6039ae477980c497c0d3d96ee7c16d45a06.json",
        "parent": {
            "id": 1660377455,
            "title": "Project kickoff!",
            "type": "Inbox::Forward",
            "url": "https://3.basecampapi.com/3714590/buckets/6883364/inbox_forwards/1660377455.json",
            "app_url": "https://3.basecamp.com/3714590/buckets/6883364/inbox_forwards/1660377455"
        },
        "bucket": {
            "id": 6883364,
            "name": "The Leto Laptop project",
            "type": "Project"
        },
        "creator": {
            "id": 11347030,
            "attachable_sgid": "BAh7CEkiCGdpZAY6BkVUSSIpZ2lkOi8vYmMzL1BlcnNvbi8xMTM0NzAzMD9leHBpcmVzX2luBjsAVEkiDHB1cnBvc2UGOwBUSSIPYXR0YWNoYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--b3910c4b417b73361601f8d2df454b526e9fc300",
            "name": "Stephen Early",
            "email_address": "stephen@letobrand.com",
            "personable_type": "User",
            "title": "",
            "bio": "",
            "created_at": "2017-04-04T20:27:07.226Z",
            "updated_at": "2019-03-12T10:58:16.269Z",
            "admin": true,
            "owner": true,
            "client": false,
            "time_zone": "Europe/Madrid",
            "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBGIqCjw=--30a34b0522d7ba3484b8c4dcd65d9087a1baef0e/avatar-64-x4",
            "company": {
              "id": 1033447818,
              "name": "Leto Brand"
            }
        },
        "content": "<div>Looking great!</div>"
    }
]
```
<!-- END GET /buckets/1/inbox_forwards/2/replies.json -->
###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/inbox_forwards/2/replies.json
```

Get an inbox reply
-------------------

* `GET /buckets/1/inbox_forwards/2/replies/3.json` will return the inbox reply with an ID of `3` for the forward with an ID of `2` in the project with an ID of `1`.

###### Example JSON Response
<!-- START GET /buckets/1/inbox_forwards/2/replies/3.json -->
```json
{
    "id": 1660382161,
    "status": "active",
    "visible_to_clients": true,
    "created_at": "2019-03-14T09:17:34.481Z",
    "updated_at": "2019-03-14T09:17:34.498Z",
    "title": "Re: Project kickoff!",
    "inherits_status": true,
    "type": "Inbox::Reply",
    "url": "https://3.basecampapi.com/3714590/buckets/6883364/inbox_replies/1660382161.json",
    "app_url": "https://3.basecamp.com/3714590/buckets/6883364/inbox_forwards/1660377455#__recording_1660382161",
    "bookmark_url": "https://3.basecampapi.com/3714590/my/bookmarks/BAh7CEkiCGdpZAY6BkVUSSIuZ2lkOi8vYmMzL1JlY29yZGluZy8xNjYwMzgyMTYxP2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg1yZWFkYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--a3d7a6039ae477980c497c0d3d96ee7c16d45a06.json",
    "parent": {
        "id": 1660377455,
        "title": "Project kickoff!",
        "type": "Inbox::Forward",
        "url": "https://3.basecampapi.com/3714590/buckets/6883364/inbox_forwards/1660377455.json",
        "app_url": "https://3.basecamp.com/3714590/buckets/6883364/inbox_forwards/1660377455"
    },
    "bucket": {
        "id": 6883364,
        "name": "The Leto Laptop project",
        "type": "Project"
    },
    "creator": {
        "id": 11347030,
        "attachable_sgid": "BAh7CEkiCGdpZAY6BkVUSSIpZ2lkOi8vYmMzL1BlcnNvbi8xMTM0NzAzMD9leHBpcmVzX2luBjsAVEkiDHB1cnBvc2UGOwBUSSIPYXR0YWNoYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--b3910c4b417b73361601f8d2df454b526e9fc300",
        "name": "Stephen Early",
        "email_address": "stephen@letobrand.com",
        "personable_type": "User",
        "title": "",
        "bio": "",
        "created_at": "2017-04-04T20:27:07.226Z",
        "updated_at": "2019-03-12T10:58:16.269Z",
        "admin": true,
        "owner": true,
        "client": false,
        "time_zone": "Europe/Madrid",
        "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBGIqCjw=--30a34b0522d7ba3484b8c4dcd65d9087a1baef0e/avatar-64-x4",
        "company": {
          "id": 1033447818,
          "name": "Leto Brand"
        }
    },
    "content": "<div>Looking great!</div>"
}
```
<!-- END GET /buckets/1/inbox_forwards/2/replies/3.json -->
###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/inbox_forwards/2/replies/3.json
```

[pagination]: https://github.com/basecamp/bc3-api/blob/master/README.md#pagination
[forwards]: https://github.com/basecamp/bc3-api/blob/master/sections/forwards.md#forwards
