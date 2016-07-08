Client replies
==============

Client replies are nested under the recording ID of a [client correspondence][correspondences] or [client approval][approvals].

Endpoints:

- [Get client replies](#get-client-replies)
- [Get a client reply](#get-a-client-reply)

Get client replies
------------------

* `GET /buckets/1/client/recordings/2/replies.json` will return a [paginated list][pagination] of client replies in the Basecamp with an ID of `1` and the recording with ID of `2`.

###### Example JSON Response
<!-- START GET /buckets/1/client/recordings/2/replies.json -->
```json
[
  {
    "id": 9007199254741656,
    "status": "active",
    "created_at": "2016-07-08T03:11:33.363Z",
    "updated_at": "2016-07-08T03:11:33.363Z",
    "type": "Client::Reply",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958499/client/replies/9007199254741656.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958499/client/correspondences/9007199254741655#__recording_9007199254741656",
    "bucket": {
      "id": 2085958499,
      "type": "Project"
    },
    "parent": {
      "id": 9007199254741655,
      "type": "Client::Correspondence",
      "url": "https://3.basecampapi.com/195539477/buckets/2085958499/client/correspondences/9007199254741655.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958499/client/correspondences/9007199254741655"
    },
    "creator": {
      "id": 1007299170,
      "name": "Stephen Early",
      "email_address": "stephen@letobrand.com",
      "personable_type": "Client",
      "title": "National Directives Director",
      "created_at": "2016-07-08T02:16:11.461Z",
      "updated_at": "2016-07-08T02:16:11.461Z",
      "admin": false,
      "owner": false,
      "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBGIqCjw=--30a34b0522d7ba3484b8c4dcd65d9087a1baef0e/avatar-64-x4",
      "company": {
        "id": 1033447818,
        "name": "Leto Brand"
      }
    },
    "content_html": "Hi all - we're excited to get started too.",
    "content_text": "Hi all - we're excited to get started too."
  }
]
```
<!-- END GET /buckets/1/client/recordings/2/replies.json -->
###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/client/recordings/2/replies.json
```

Get a client reply
------------------

* `GET /buckets/1/client/recordings/2/replies/3.json` will return the client reply with an ID of `3` for the recording with an ID of `2` in the Basecamp with an ID of `1`.

###### Example JSON Response
<!-- START GET /buckets/1/client/recordings/2/replies/3.json -->
```json
{
  "id": 9007199254741660,
  "status": "active",
  "created_at": "2016-07-08T02:39:33.832Z",
  "updated_at": "2016-07-08T02:39:33.832Z",
  "type": "Client::Reply",
  "url": "https://3.basecampapi.com/195539477/buckets/2085958499/client/replies/9007199254741660.json",
  "app_url": "https://3.basecamp.com/195539477/buckets/2085958499/client/correspondences/9007199254741655#__recording_9007199254741660",
  "bucket": {
    "id": 2085958499,
    "type": "Project"
  },
  "parent": {
    "id": 9007199254741655,
    "type": "Client::Correspondence",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958499/client/correspondences/9007199254741655.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958499/client/correspondences/9007199254741655"
  },
  "creator": {
    "id": 1007299144,
    "name": "Annie Bryan",
    "email_address": "annie@honchodesign.com",
    "personable_type": "User",
    "title": "Central Markets Manager",
    "created_at": "2016-07-08T02:16:07.615Z",
    "updated_at": "2016-07-08T02:16:07.615Z",
    "admin": false,
    "owner": false,
    "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBEgqCjw=--8266bb0507508f3d46050d57b65924d5e2a005f3/avatar-64-x4",
    "company": {
      "id": 1033447817,
      "name": "Honcho Design"
    }
  },
  "content_html": "Hi Leto team, this it's Annie. I'll be your day to day contact for the project, so keep me on your speed dial (or speed email, perhaps more accurately!) Feel free to reach out to me with any questions at all, and I'll be posting up some outlines, timelines, etc. very shortly.",
  "content_text": "Hi Leto team, this it's Annie. I'll be your day to day contact for the project, so keep me on your speed dial (or speed email, perhaps more accurately!) Feel free to reach out to me with any questions at all, and I'll be posting up some outlines, timelines, etc. very shortly."
}
```
<!-- END GET /buckets/1/client/recordings/2/replies/3.json -->
###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/client/recordings/2/replies/3.json
```

[pagination]: https://github.com/basecamp/bc3-api/blob/master/README.md#pagination
[correspondences]: https://github.com/basecamp/bc3-api/blob/master/sections/client_correspondences.md#client-correspondences
[approvals]: https://github.com/basecamp/bc3-api/blob/master/sections/client_approvals.md#client-approvals
