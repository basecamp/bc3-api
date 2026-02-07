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

* `GET /vaults/2/uploads.json` will return a [paginated list][pagination] of active uploads in the [vault][vaults] with ID of `2`.

###### Example JSON Response
<!-- START GET /vaults/2/uploads.json -->
```json
[
  {
    "id": 1069479913,
    "status": "active",
    "visible_to_clients": false,
    "created_at": "2026-01-31T08:36:22.481Z",
    "updated_at": "2026-01-31T08:36:22.528Z",
    "title": "company-logo.png",
    "inherits_status": true,
    "type": "Upload",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958504/uploads/1069479913.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958504/uploads/1069479913",
    "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiLmdpZDovL2JjMy9SZWNvcmRpbmcvMTA2OTQ3OTkxMz9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg1yZWFkYWJsZQY7AFQ=--b796a37ac3f19f619e8150d87b4a6a39882fdfd5.json",
    "subscription_url": "https://3.basecampapi.com/195539477/recordings/1069479913/subscription.json",
    "comments_count": 0,
    "comments_url": "https://3.basecampapi.com/195539477/recordings/1069479913/comments.json",
    "boosts_count": 0,
    "boosts_url": "https://3.basecampapi.com/195539477/buckets/2085958504/recordings/1069479913/boosts.json",
    "position": 1,
    "parent": {
      "id": 1069479394,
      "title": "Docs & Files",
      "type": "Vault",
      "url": "https://3.basecampapi.com/195539477/buckets/2085958504/vaults/1069479394.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958504/vaults/1069479394"
    },
    "bucket": {
      "id": 2085958504,
      "name": "The Leto Laptop",
      "type": "Project"
    },
    "creator": {
      "id": 1049715913,
      "attachable_sgid": "BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiK2dpZDovL2JjMy9QZXJzb24vMTA0OTcxNTkxMz9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg9hdHRhY2hhYmxlBjsAVA==--e627c45e6b34e08862da23906862412620e4d5d9",
      "name": "Victor Cooper",
      "email_address": "victor@honchodesign.com",
      "personable_type": "User",
      "title": "Chief Strategist",
      "bio": "Don’t let your dreams be dreams",
      "location": "Chicago, IL",
      "created_at": "2026-01-31T08:29:28.365Z",
      "updated_at": "2026-01-31T08:29:32.599Z",
      "admin": true,
      "owner": true,
      "client": false,
      "employee": true,
      "time_zone": "America/Chicago",
      "avatar_url": "https://3.basecampapi.com/195539477/people/BAhpBMlkkT4=--5fe7b70fbee7a7f0e2e1e19df7579e5d880c753d/avatar?v=1",
      "company": {
        "id": 1033447817,
        "name": "Honcho Design"
      },
      "can_ping": true,
      "can_manage_projects": true,
      "can_manage_people": true,
      "can_access_timesheet": true,
      "can_access_hill_charts": true
    },
    "description": "<div>Check out the new logo</div>",
    "content_type": "image/png",
    "byte_size": 1281,
    "filename": "company-logo.png",
    "download_url": "https://3.basecampapi.com/195539477/buckets/2085958504/uploads/1069479913/download/company-logo.png",
    "app_download_url": "https://3.basecamp-static.com/195539477/buckets/2085958504/uploads/1069479913/download/company-logo.png",
    "width": 164,
    "height": 39
  }
]
```
<!-- END GET /vaults/2/uploads.json -->
###### Copy as cURL

```shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/vaults/2/uploads.json
```

Get an upload
-------------

* `GET /uploads/2.json` will return the upload with an ID of `2`.

###### Example JSON Response
<!-- START GET /uploads/2.json -->
```json
{
  "id": 1069479913,
  "status": "active",
  "visible_to_clients": false,
  "created_at": "2026-01-31T08:36:22.481Z",
  "updated_at": "2026-01-31T08:36:22.528Z",
  "title": "company-logo.png",
  "inherits_status": true,
  "type": "Upload",
  "url": "https://3.basecampapi.com/195539477/buckets/2085958504/uploads/1069479913.json",
  "app_url": "https://3.basecamp.com/195539477/buckets/2085958504/uploads/1069479913",
  "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiLmdpZDovL2JjMy9SZWNvcmRpbmcvMTA2OTQ3OTkxMz9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg1yZWFkYWJsZQY7AFQ=--b796a37ac3f19f619e8150d87b4a6a39882fdfd5.json",
  "subscription_url": "https://3.basecampapi.com/195539477/recordings/1069479913/subscription.json",
  "comments_count": 0,
  "comments_url": "https://3.basecampapi.com/195539477/recordings/1069479913/comments.json",
  "boosts_count": 0,
  "boosts_url": "https://3.basecampapi.com/195539477/buckets/2085958504/recordings/1069479913/boosts.json",
  "position": 1,
  "parent": {
    "id": 1069479394,
    "title": "Docs & Files",
    "type": "Vault",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958504/vaults/1069479394.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958504/vaults/1069479394"
  },
  "bucket": {
    "id": 2085958504,
    "name": "The Leto Laptop",
    "type": "Project"
  },
  "creator": {
    "id": 1049715913,
    "attachable_sgid": "BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiK2dpZDovL2JjMy9QZXJzb24vMTA0OTcxNTkxMz9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg9hdHRhY2hhYmxlBjsAVA==--e627c45e6b34e08862da23906862412620e4d5d9",
    "name": "Victor Cooper",
    "email_address": "victor@honchodesign.com",
    "personable_type": "User",
    "title": "Chief Strategist",
    "bio": "Don’t let your dreams be dreams",
    "location": "Chicago, IL",
    "created_at": "2026-01-31T08:29:28.365Z",
    "updated_at": "2026-01-31T08:29:32.599Z",
    "admin": true,
    "owner": true,
    "client": false,
    "employee": true,
    "time_zone": "America/Chicago",
    "avatar_url": "https://3.basecampapi.com/195539477/people/BAhpBMlkkT4=--5fe7b70fbee7a7f0e2e1e19df7579e5d880c753d/avatar?v=1",
    "company": {
      "id": 1033447817,
      "name": "Honcho Design"
    },
    "can_ping": true,
    "can_manage_projects": true,
    "can_manage_people": true,
    "can_access_timesheet": true,
    "can_access_hill_charts": true
  },
  "description": "<div>Check out the new logo</div>",
  "content_type": "image/png",
  "byte_size": 1281,
  "filename": "company-logo.png",
  "download_url": "https://3.basecampapi.com/195539477/buckets/2085958504/uploads/1069479913/download/company-logo.png",
  "app_download_url": "https://3.basecamp-static.com/195539477/buckets/2085958504/uploads/1069479913/download/company-logo.png",
  "width": 164,
  "height": 39
}
```
<!-- END GET /uploads/2.json -->

###### Copy as cURL

```shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/uploads/2.json
```

Create an upload
----------------

* `POST /vaults/2/uploads.json` creates an upload under the vault with an ID of `2`.

**Required parameters**: `attachable_sgid` for an uploaded attachment. See the [Create an attachment][attachments] endpoint for more info on uploading attachments.

_Optional parameters_:
* `description` - containing information about the upload. See our [Rich text guide][rich] for what HTML tags allowed.
* `base_name` - an new file name for the upload. `base_name` should be a file name *without* an extension (e.g. `"pizza"` for `"pizza.png"`).

This endpoint will return `201 Created` with the current JSON representation of the upload if the creation was a success. See the [Get an upload](#get-an-upload) endpoint for more info on the payload.

###### Example JSON Request

```json
{
  "attachable_sgid": "BAh2CEkiCGdpZAY6BkVUSSIsZ2lkOi7vYmMzL0F0dGFjaG1lbnQvNzM4NDcyNj9leHBpcmVzX2luBjsAVEkiDHB1cnBvc2UGOwBUSSIPYXR0YWNoYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--13982201abe18044c897e32979c7dccfe8add9c1",
  "description": "<div><strong>Yum</strong></div>",
  "base_name": "yummy_pizza"
}
```

###### Copy as cURL

```shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -H "Content-Type: application/json" \
  -d '{"attachable_sgid":"BAh…9c1","description":"<div><strong>Yum</strong></div>","base_name":"yummy_pizza"}' \
  https://3.basecampapi.com/$ACCOUNT_ID/vaults/2/uploads.json
```

Update an upload
----------------

* `PUT /uploads/2.json` allows changing the `description` and `base_name` of the upload with an ID of `2`.

This endpoint will return `200 OK` with the current JSON representation of the upload if the update was a success. See the [Get an upload](#get-an-upload) endpoint for more info on the payload.

###### Example JSON Request

```json
{
  "description": "<div>Meh</div>",
  "base_name": "old_pizza"
}
```

###### Copy as cURL

```shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -H "Content-Type: application/json" \
  -d '{"description":"<div>Meh</div>","base_name":"old_pizza"}' -X PUT \
  https://3.basecampapi.com/$ACCOUNT_ID/uploads/2.json
```

Legacy project-scoped routes
-----------------------------

The following project-scoped routes are still supported and will remain available, but flat routes above are the canonical form for new integrations.

* `GET /buckets/1/vaults/2/uploads.json` → [Get uploads](#get-uploads)
* `GET /buckets/1/uploads/2.json` → [Get an upload](#get-an-upload)
* `POST /buckets/1/vaults/2/uploads.json` → [Create an upload](#create-an-upload)
* `PUT /buckets/1/uploads/2.json` → [Update an upload](#update-an-upload)

[pagination]: https://github.com/basecamp/bc3-api/blob/master/README.md#pagination
[attachments]: https://github.com/basecamp/bc3-api/blob/master/sections/attachments.md#create-an-attachment
[trash]: https://github.com/basecamp/bc3-api/blob/master/sections/recordings.md#trash-a-recording
[vaults]: https://github.com/basecamp/bc3-api/blob/master/sections/vaults.md#vaults
[rich]: https://github.com/basecamp/bc3-api/blob/master/sections/rich_text.md
