Uploads
=======

Endpoints:

- [Get uploads](#get-uploads)
- [Get an upload](#get-an-upload)
- [Create an upload](#create-an-upload)
- [Update an upload](#update-an-upload)
- [Trash an upload][trash]

Get uploads
-----------

* `GET /buckets/1/vaults/2/uploads.json` will return a [paginated list][pagination] of active uploads in the project with an ID of `1` and the [vault][vaults] with ID of `2`.

###### Example JSON Response
<!-- START GET /buckets/1/vaults/2/uploads.json -->
```json
[
  {
    "id": 1069479848,
    "status": "active",
    "visible_to_clients": false,
    "created_at": "2022-11-22T08:25:04.400Z",
    "updated_at": "2022-11-22T08:25:04.408Z",
    "title": "company-logo.png",
    "inherits_status": true,
    "type": "Upload",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958499/uploads/1069479848.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958499/uploads/1069479848",
    "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7CEkiCGdpZAY6BkVUSSIuZ2lkOi8vYmMzL1JlY29yZGluZy8xMDY5NDc5ODQ4P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg1yZWFkYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--b125776d2d29e638ecfefc0fd5bf4957f79ae0d5.json",
    "subscription_url": "https://3.basecampapi.com/195539477/buckets/2085958499/recordings/1069479848/subscription.json",
    "comments_count": 0,
    "comments_url": "https://3.basecampapi.com/195539477/buckets/2085958499/recordings/1069479848/comments.json",
    "position": 1,
    "parent": {
      "id": 1069479340,
      "title": "Docs & Files",
      "type": "Vault",
      "url": "https://3.basecampapi.com/195539477/buckets/2085958499/vaults/1069479340.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958499/vaults/1069479340"
    },
    "bucket": {
      "id": 2085958499,
      "name": "The Leto Laptop",
      "type": "Project"
    },
    "creator": {
      "id": 1049715914,
      "attachable_sgid": "BAh7CEkiCGdpZAY6BkVUSSIrZ2lkOi8vYmMzL1BlcnNvbi8xMDQ5NzE1OTE0P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg9hdHRhY2hhYmxlBjsAVEkiD2V4cGlyZXNfYXQGOwBUMA==--ff006accb6e013cca785190fa38f42c091d24f1e",
      "name": "Victor Cooper",
      "email_address": "victor@honchodesign.com",
      "personable_type": "User",
      "title": "Chief Strategist",
      "bio": "Don’t let your dreams be dreams",
      "location": "Chicago, IL",
      "created_at": "2022-11-22T08:23:21.732Z",
      "updated_at": "2022-11-22T08:23:21.904Z",
      "admin": true,
      "owner": true,
      "client": false,
      "employee": true,
      "time_zone": "America/Chicago",
      "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBMpkkT4=--5520caeec1845b5090bbfc993ffe8eca8d138e14/avatar?v=1",
      "company": {
        "id": 1033447817,
        "name": "Honcho Design"
      },
      "can_manage_projects": true,
      "can_manage_people": true
    },
    "description": "<div>Check out the new logo</div>",
    "content_type": "image/png",
    "byte_size": 1281,
    "filename": "company-logo.png",
    "download_url": "https://3.basecampapi.com/195539477/buckets/2085958499/uploads/1069479848/download/company-logo.png",
    "app_download_url": "http://storage.3.basecamp.test/195539477/buckets/2085958499/uploads/1069479848/download/company-logo.png",
    "width": 164,
    "height": 39
  }
]
```
<!-- END GET /buckets/1/vaults/2/uploads.json -->
###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/vaults/2/uploads.json
```

Get an upload
-------------

* `GET /buckets/1/uploads/2.json` will return the upload with an ID of `2` in the project with an ID of `1`.

###### Example JSON Response
<!-- START GET /buckets/1/uploads/2.json -->
```json
{
  "id": 1069479848,
  "status": "active",
  "visible_to_clients": false,
  "created_at": "2022-11-22T08:25:04.400Z",
  "updated_at": "2022-11-22T08:25:04.408Z",
  "title": "company-logo.png",
  "inherits_status": true,
  "type": "Upload",
  "url": "https://3.basecampapi.com/195539477/buckets/2085958499/uploads/1069479848.json",
  "app_url": "https://3.basecamp.com/195539477/buckets/2085958499/uploads/1069479848",
  "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7CEkiCGdpZAY6BkVUSSIuZ2lkOi8vYmMzL1JlY29yZGluZy8xMDY5NDc5ODQ4P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg1yZWFkYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--b125776d2d29e638ecfefc0fd5bf4957f79ae0d5.json",
  "subscription_url": "https://3.basecampapi.com/195539477/buckets/2085958499/recordings/1069479848/subscription.json",
  "comments_count": 0,
  "comments_url": "https://3.basecampapi.com/195539477/buckets/2085958499/recordings/1069479848/comments.json",
  "position": 1,
  "parent": {
    "id": 1069479340,
    "title": "Docs & Files",
    "type": "Vault",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958499/vaults/1069479340.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958499/vaults/1069479340"
  },
  "bucket": {
    "id": 2085958499,
    "name": "The Leto Laptop",
    "type": "Project"
  },
  "creator": {
    "id": 1049715914,
    "attachable_sgid": "BAh7CEkiCGdpZAY6BkVUSSIrZ2lkOi8vYmMzL1BlcnNvbi8xMDQ5NzE1OTE0P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg9hdHRhY2hhYmxlBjsAVEkiD2V4cGlyZXNfYXQGOwBUMA==--ff006accb6e013cca785190fa38f42c091d24f1e",
    "name": "Victor Cooper",
    "email_address": "victor@honchodesign.com",
    "personable_type": "User",
    "title": "Chief Strategist",
    "bio": "Don’t let your dreams be dreams",
    "location": "Chicago, IL",
    "created_at": "2022-11-22T08:23:21.732Z",
    "updated_at": "2022-11-22T08:23:21.904Z",
    "admin": true,
    "owner": true,
    "client": false,
    "employee": true,
    "time_zone": "America/Chicago",
    "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBMpkkT4=--5520caeec1845b5090bbfc993ffe8eca8d138e14/avatar?v=1",
    "company": {
      "id": 1033447817,
      "name": "Honcho Design"
    },
    "can_manage_projects": true,
    "can_manage_people": true
  },
  "description": "<div>Check out the new logo</div>",
  "content_type": "image/png",
  "byte_size": 1281,
  "filename": "company-logo.png",
  "download_url": "https://3.basecampapi.com/195539477/buckets/2085958499/uploads/1069479848/download/company-logo.png",
  "app_download_url": "http://storage.3.basecamp.test/195539477/buckets/2085958499/uploads/1069479848/download/company-logo.png",
  "width": 164,
  "height": 39
}
```
<!-- END GET /buckets/1/uploads/2.json -->

###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/uploads/2.json
```

Create an upload
----------------

* `POST /buckets/1/vaults/2/uploads.json` creates an upload in the project with ID `1` and under the vault with an ID of `2`.

**Required parameters**: `attachable_sgid` for an uploaded attachment. See the [Create an attachment][attachments] endpoint for more info on uploading attachments.

_Optional parameters_:
* `description` - containing information about the upload. See our [Rich text guide][rich] for what HTML tags allowed.
* `base_name` - an new file name for the upload. `base_name` should be a file name *without* an extension (e.g. `"pizza"` for `"pizza.png"`).

This endpoint will return `201 Created` with the current JSON representation of the upload if the creation was a success. See the [Get an upload](#get-an-upload) endpoint for more info on the payload.

###### Example JSON Request

``` json
{
  "attachable_sgid": "BAh2CEkiCGdpZAY6BkVUSSIsZ2lkOi7vYmMzL0F0dGFjaG1lbnQvNzM4NDcyNj9leHBpcmVzX2luBjsAVEkiDHB1cnBvc2UGOwBUSSIPYXR0YWNoYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--13982201abe18044c897e32979c7dccfe8add9c1",
  "description": "<div><strong>Yum</strong></div>",
  "base_name": "yummy_pizza"
}
```

###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -H "Content-Type: application/json" \
  -d '{"attachable_sgid":"BAh…9c1","description":"<div><strong>Yum</strong></div>","base_name":"yummy_pizza"}' \
  https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/vaults/2/uploads.json
```

Update an upload
----------------

* `PUT /buckets/1/uploads/2.json` allows changing the `description` and `base_name` of the upload with an ID of `2` in the project with ID `1`.

This endpoint will return `200 OK` with the current JSON representation of the upload if the update was a success. See the [Get an upload](#get-an-upload) endpoint for more info on the payload.

###### Example JSON Request

``` json
{
  "description": "<div>Meh</div>",
  "base_name": "old_pizza"
}
```

###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -H "Content-Type: application/json" \
  -d '{"description":"<div>Meh</div>","base_name":"old_pizza"}' -X PUT \
  https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/uploads/2.json
```

[pagination]: https://github.com/basecamp/bc3-api/blob/master/README.md#pagination
[attachments]: https://github.com/basecamp/bc3-api/blob/master/sections/attachments.md#create-an-attachment
[trash]: https://github.com/basecamp/bc3-api/blob/master/sections/recordings.md#trash-a-recording
[vaults]: https://github.com/basecamp/bc3-api/blob/master/sections/vaults.md#vaults
[rich]: https://github.com/basecamp/bc3-api/blob/master/sections/rich_text.md
