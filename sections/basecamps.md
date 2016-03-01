Basecamps
=========

**Projects are now Basecamps in the BC3 API.**

Endpoints:

- [Get basecamps](#get-basecamps)
- [Get a basecamp](#get-a-basecamp)
- [Create a basecamp](#create-a-basecamp)
- [Update a basecamp](#update-a-basecamp)
- [Archive a basecamp](#archive-a-basecamp)
- [Trash a basecamp](#trash-a-basecamp)
- [Activate a basecamp](#activate-a-basecamp)

Get basecamps
-------------

* `GET /basecamps.json` will return all active basecamps visible to the current user.
* `GET /basecamps/archive.json` will return all archived basecamps visible to the current user.
* `GET /basecamps/trash.json` will return all trashed basecamps visible to the current user.

```json
[
   {
      "vault_url" : "https://3.basecamp.com/195539477/buckets/2085958495/vaults/9007199254741021",
      "id" : 2085958495,
      "bookmark_url" : "https://3.basecamp.com/195539477/my/bookmarks/BAh7CEkiCGdpZAY6BkVUSSIrZ2lkOi8vYmMzL0J1Y2tldC8yMDg1OTU4NDk1P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg1yZWFkYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--06a5145963152c63ea56090695ec59e6d83fb21a",
      "created_at" : "2016-01-27T11:00:20.701-06:00",
      "name" : "Annie's Corner",
      "updated_at" : "2016-02-11T09:49:52.878-06:00",
      "status" : "active",
      "description" : "Annie's Stuff. Keep Out. 😁",
      "bookmarked" : false,
      "url" : "https://3.basecamp.com/195539477/basecamps/2085958495"
   },
   {
      "name" : "Honcho Design Newsroom",
      "created_at" : "2016-01-27T11:00:28.325-06:00",
      "bookmark_url" : "https://3.basecamp.com/195539477/my/bookmarks/BAh7CEkiCGdpZAY6BkVUSSIrZ2lkOi8vYmMzL0J1Y2tldC8yMDg1OTU4NDk2P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg1yZWFkYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--456eaced982bc4da97ac830c019a4af1d250bb21",
      "vault_url" : "https://3.basecamp.com/195539477/buckets/2085958496/vaults/9007199254741052",
      "id" : 2085958496,
      "url" : "https://3.basecamp.com/195539477/basecamps/2085958496",
      "bookmarked" : false,
      "status" : "active",
      "description" : "Let's talk about the company!",
      "updated_at" : "2016-02-09T22:40:55.279-06:00"
   },
   {
      "status" : "active",
      "description" : "Looking for the best!",
      "updated_at" : "2016-02-11T09:49:55.177-06:00",
      "url" : "https://3.basecamp.com/195539477/basecamps/2085958497",
      "bookmarked" : false,
      "bookmark_url" : "https://3.basecamp.com/195539477/my/bookmarks/BAh7CEkiCGdpZAY6BkVUSSIrZ2lkOi8vYmMzL0J1Y2tldC8yMDg1OTU4NDk3P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg1yZWFkYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--9a7b024a94ef1e7abaa92676ceb712dff9de6885",
      "created_at" : "2016-01-27T11:01:58.074-06:00",
      "vault_url" : "https://3.basecamp.com/195539477/buckets/2085958497/vaults/9007199254741364",
      "id" : 2085958497,
      "name" : "Honcho Recruiting and Hiring"
   },
   {
      "name" : "The Leto Laptop",
      "created_at" : "2016-01-27T11:02:32.061-06:00",
      "bookmark_url" : "https://3.basecamp.com/195539477/my/bookmarks/BAh7CEkiCGdpZAY6BkVUSSIrZ2lkOi8vYmMzL0J1Y2tldC8yMDg1OTU4NDk4P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg1yZWFkYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--c8e1a465de900eb9864fa79ae2f30345be158f71",
      "vault_url" : "https://3.basecamp.com/195539477/buckets/2085958498/vaults/9007199254741442",
      "id" : 2085958498,
      "url" : "https://3.basecamp.com/195539477/basecamps/2085958498",
      "bookmarked" : false,
      "status" : "active",
      "description" : "Laptop product launch.",
      "updated_at" : "2016-01-27T11:03:32.570-06:00"
   }
]
```

###### Copy as cURL:

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecamp.com/$ACCOUNT_ID/basecamps.json
```


Get a basecamp
--------------

* `GET /basecamps/1.json` will return the basecamp with the given ID, granted they have access to it.


``` json
{
   "bookmark_url" : "https://3.basecamp.com/195539477/my/bookmarks/BAh7CEkiCGdpZAY6BkVUSSIrZ2lkOi8vYmMzL0J1Y2tldC8yMDg1OTU4NDk2P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg1yZWFkYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--456eaced982bc4da97ac830c019a4af1d250bb21",
   "created_at" : "2016-01-27T11:00:28.325-06:00",
   "updated_at" : "2016-02-09T22:40:55.279-06:00",
   "vault_url" : "https://3.basecamp.com/195539477/buckets/2085958496/vaults/9007199254741052",
   "url" : "https://3.basecamp.com/195539477/basecamps/2085958496",
   "id" : 2085958496,
   "name" : "Honcho Design Newsroom",
   "description" : "Let's talk about the company!",
   "status" : "active"
}
```

###### Copy as cURL:

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecamp.com/$ACCOUNT_ID/basecamps/1.json
```


Create a basecamp
-----------------

* `POST /basecamps.json` with at least a name, and optionally a description, to kick off a new basecamp.

``` json
{
  "name": "Marketing Campaign",
  "description": "For Client: Xyz Corp Conference"
}
```

This will return `201 Created`, with the location of the new basecamp in the `Location` header along with the current JSON representation of the basecamp if the creation was a success. See the [Get a basecamp](#get-a-basecamp) endpoint for more info. If the account has reached the basecamp limit you'll see a `507 Insufficient Storage` and a response of:

``` json
{
  "error": "The basecamp limit for this account has been reached."
}
```

If you hit that error, you'll need to either archive or trash projects, or upgrade your subscription to a bigger plan. After creating a basecamp, you'll  want to [allow people to get in][1]. Or maybe, [add some to-dos][2]?

###### Copy as cURL:

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -H "Content-Type: application/json" \
  -d '{"name":"Marketing Campaign","description":"For Client: Xyz Corp Conference"}' \
  http://bc3.dev/$ACCOUNT_ID/basecamps.json
```


Update a basecamp
-----------------

* `PUT /basecamps/1.json` will allow updating of a basecamp's name and description.

``` json
{
  "name": "Marketing Campaign for Xyz Corp",
  "description": "2016-2017 Strategy"
}
```

This will return `200 OK`, with the location of the new basecamp in the `Location` header along with the current JSON representation of the basecamp if the update was a success. See the [Get a basecamp](#get-a-basecamp) endpoint for more info.

###### Copy as cURL:

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -H "Content-Type: application/json" \
  -d '{"name":"Marketing Campaign for Xyz Corp","description":"2016-2017 Strategy"}' -X PUT \
  http://bc3.dev/$ACCOUNT_ID/basecamps/2085958506.json
```


Archive a basecamp
------------------

* `PUT /basecamps/1/archive.json` will archive the basecamp with the given ID. Archived basecamps do not count against the current basecamp limit for an account.


Trash a basecamp
----------------

* `PUT /basecamps/1/trash.json` will mark the basecamp with the given ID as trashed. Trashed basecamps will be deleted from Basecamp 3 after 30 days.


Activate a basecamp
------------------

* `PUT /basecamps/1/active.json` will mark the basecamp as active, removing it from the trashed or archived state.

[1]: https://github.com/basecamp/bc3-api/blob/master/sections/accesses.md#accesses
[2]: https://github.com/basecamp/bc3-api/blob/master/sections/todos.md#todos
