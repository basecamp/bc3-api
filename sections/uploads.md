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

* `GET /buckets/1/vaults/2/uploads.json` will return a [paginated list][pagination] of active uploads in the Basecamp with an ID of `1` and the [vault][vaults] with ID of `2`.

###### Example JSON Response
<!-- START GET /buckets/1/vaults/2/uploads.json -->
```json
[
  {
    "id": 9007199254741761,
    "status": "active",
    "created_at": "2016-07-19T21:36:12.137Z",
    "updated_at": "2016-07-19T21:36:15.412Z",
    "type": "Upload",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958498/uploads/9007199254741761.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958498/uploads/9007199254741761",
    "comments_count": 0,
    "comments_url": "https://3.basecampapi.com/195539477/buckets/2085958498/recordings/9007199254741761/comments.json",
    "parent": {
      "id": 9007199254741442,
      "title": "Docs & Files",
      "type": "Vault",
      "url": "https://3.basecampapi.com/195539477/buckets/2085958498/vaults/9007199254741442.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958498/vaults/9007199254741442"
    },
    "bucket": {
      "id": 2085958498,
      "name": "The Leto Laptop",
      "type": "Project"
    },
    "creator": {
      "id": 1007299143,
      "attachable_sgid": "BAh7CEkiCGdpZAY6BkVUSSIrZ2lkOi8vYmMzL1BlcnNvbi8xMDA3Mjk5MTQzP2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg9hdHRhY2hhYmxlBjsAVEkiD2V4cGlyZXNfYXQGOwBUMA==--919d2c8b11ff403eefcab9db42dd26846d0c3102",
      "name": "Victor Cooper",
      "email_address": "victor@honchodesign.com",
      "personable_type": "User",
      "title": null,
      "created_at": "2016-07-19T21:27:44.597Z",
      "updated_at": "2016-07-19T21:27:44.697Z",
      "admin": true,
      "owner": true,
      "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBEcqCjw=--c632b967cec296b87363a697a67a87f9cc1e5b45/avatar-64-x4",
      "company": {
        "id": 1033447817,
        "name": "Honcho Design"
      }
    },
    "description": "<div>Check out the new logo</div>",
    "filename": "company-logo.png",
    "content_type": "image/png",
    "byte_size": 1281,
    "width": 164,
    "height": 39,
    "download_url": "https://3.basecampapi.com/195539477/buckets/2085958498/uploads/9007199254741761/download/company-logo.png",
    "app_download_url": "https://3.basecamp.com/195539477/buckets/2085958498/uploads/9007199254741761/download/company-logo.png"
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

* `GET /buckets/1/uploads/2.json` will return the upload with an ID of `2` in the Basecamp with an ID of `1`.

###### Example JSON Response
<!-- START GET /buckets/1/uploads/2.json -->
```json
{
  "id": 9007199254741761,
  "status": "active",
  "created_at": "2016-07-19T21:36:12.137Z",
  "updated_at": "2016-07-19T21:36:15.412Z",
  "type": "Upload",
  "url": "https://3.basecampapi.com/195539477/buckets/2085958498/uploads/9007199254741761.json",
  "app_url": "https://3.basecamp.com/195539477/buckets/2085958498/uploads/9007199254741761",
  "comments_count": 0,
  "comments_url": "https://3.basecampapi.com/195539477/buckets/2085958498/recordings/9007199254741761/comments.json",
  "parent": {
    "id": 9007199254741442,
    "title": "Docs & Files",
    "type": "Vault",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958498/vaults/9007199254741442.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958498/vaults/9007199254741442"
  },
  "bucket": {
    "id": 2085958498,
    "name": "The Leto Laptop",
    "type": "Project"
  },
  "creator": {
    "id": 1007299143,
    "attachable_sgid": "BAh7CEkiCGdpZAY6BkVUSSIrZ2lkOi8vYmMzL1BlcnNvbi8xMDA3Mjk5MTQzP2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg9hdHRhY2hhYmxlBjsAVEkiD2V4cGlyZXNfYXQGOwBUMA==--919d2c8b11ff403eefcab9db42dd26846d0c3102",
    "name": "Victor Cooper",
    "email_address": "victor@honchodesign.com",
    "personable_type": "User",
    "title": null,
    "created_at": "2016-07-19T21:27:44.597Z",
    "updated_at": "2016-07-19T21:27:44.697Z",
    "admin": true,
    "owner": true,
    "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBEcqCjw=--c632b967cec296b87363a697a67a87f9cc1e5b45/avatar-64-x4",
    "company": {
      "id": 1033447817,
      "name": "Honcho Design"
    }
  },
  "description": "<div>Check out the new logo</div>",
  "filename": "company-logo.png",
  "content_type": "image/png",
  "byte_size": 1281,
  "width": 164,
  "height": 39,
  "download_url": "https://3.basecampapi.com/195539477/buckets/2085958498/uploads/9007199254741761/download/company-logo.png",
  "app_download_url": "https://3.basecamp.com/195539477/buckets/2085958498/uploads/9007199254741761/download/company-logo.png"
}
```
<!-- END GET /buckets/1/uploads/2.json -->

###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/uploads/2.json
```

Create an upload
----------------

* `POST /buckets/1/vaults/2/uploads.json` creates an upload in the Basecamp with ID `1` and under the vault with an ID of `2`.

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
  -d '{"attachable_sgid":"BAh…9c1","description":"content":"<div><strong>Yum</strong></div>","base_name":"yummy_pizza"}' \
  https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/vaults/2/uploads.json
```

Update an upload
----------------

* `PUT /buckets/1/uploads/2.json` allows changing the `description` and `base_name` of the upload with an ID of `2` in the Basecamp with ID `1`.

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
