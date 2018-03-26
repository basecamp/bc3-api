Vaults
======

All projects have a primary vault (folder), to get its ID see the [Get a project][project] endpoint's `dock` payload. Additional vaults may be nested under the primary vault or any child vault.

Endpoints:

- [Get vaults](#get-vaults)
- [Get a vault](#get-a-vault)
- [Create a vault](#create-a-vault)
- [Update a vault](#update-a-vault)

Get vaults
----------

* `GET /buckets/1/vaults/2/vaults.json` will return a [paginated list][pagination] of vaults in the project with an ID of `1` and the vault with ID of `2`.

###### Example JSON Response
<!-- START GET /buckets/1/vaults/2/vaults.json -->
```json
[
  {
    "id": 9007199254741202,
    "status": "active",
    "created_at": "2016-06-08T19:00:41.933Z",
    "updated_at": "2016-07-19T16:47:00.621Z",
    "title": "HR Stuff",
    "inherits_status": true,
    "type": "Vault",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958496/vaults/9007199254741202.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958496/vaults/9007199254741202",
    "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7CEkiCGdpZAY6BkVUSSIuZ2lkOi8vYmMzL1JlY29yZGluZy8xMDY0MDkwODEzP2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg1yZWFkYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--664db16bee61b4238dcef9ae6e1f48cb51b70c69.json",
    "parent": {
      "id": 9007199254741052,
      "title": "Docs & Files",
      "type": "Vault",
      "url": "https://3.basecampapi.com/195539477/buckets/2085958496/vaults/9007199254741052.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958496/vaults/9007199254741052"
    },
    "bucket": {
      "id": 2085958496,
      "name": "Honcho Design Newsroom",
      "type": "Project"
    },
    "creator": {
      "id": 1007299143,
      "attachable_sgid": "BAh7CEkiCGdpZAY6BkVUSSIrZ2lkOi8vYmMzL1BlcnNvbi8xMDA3Mjk5MTQzP2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg9hdHRhY2hhYmxlBjsAVEkiD2V4cGlyZXNfYXQGOwBUMA==--919d2c8b11ff403eefcab9db42dd26846d0c3102",
      "name": "Victor Cooper",
      "email_address": "victor@honchodesign.com",
      "personable_type": "User",
      "title": "Chief Strategist",
      "bio": "Don't let your dreams be dreams",
      "created_at": "2016-09-09T22:58:27.559Z",
      "updated_at": "2016-09-09T22:58:31.296Z",
      "admin": true,
      "owner": true,
      "time_zone": "America/Chicago",
      "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBEcqCjw=--c632b967cec296b87363a697a67a87f9cc1e5b45/avatar-64-x4",
      "company": {
        "id": 1033447817,
        "name": "Honcho Design"
      }
    },
    "documents_count": 1,
    "documents_url": "https://3.basecampapi.com/195539477/buckets/2085958496/vaults/9007199254741202/documents.json",
    "uploads_count": 0,
    "uploads_url": "https://3.basecampapi.com/195539477/buckets/2085958496/vaults/9007199254741202/uploads.json",
    "vaults_count": 0,
    "vaults_url": "https://3.basecampapi.com/195539477/buckets/2085958496/vaults/9007199254741202/vaults.json"
  }
]
```
<!-- END GET /buckets/1/vaults/2/vaults.json -->
###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/vaults/2/vaults.json
```

Get a vault
-----------

* `GET /buckets/1/vaults/2.json` will return the vault with an ID of `2` in the project with an ID of `1`.

###### Example JSON Response
<!-- START GET /buckets/1/vaults/2.json -->
```json
{
  "id": 9007199254741052,
  "status": "active",
  "created_at": "2016-07-19T16:46:42.200Z",
  "updated_at": "2016-07-19T16:47:00.628Z",
  "title": "Docs & Files",
  "inherits_status": true,
  "type": "Vault",
  "url": "https://3.basecampapi.com/195539477/buckets/2085958496/vaults/9007199254741052.json",
  "app_url": "https://3.basecamp.com/195539477/buckets/2085958496/vaults/9007199254741052",
  "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7CEkiCGdpZAY6BkVUSSIuZ2lkOi8vYmMzL1JlY29yZGluZy8xMDY0MDkwNjU2P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg1yZWFkYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--4d5758765159e49b7d1a4076c78cbcc3a70faf4c.json",
  "bucket": {
    "id": 2085958496,
    "name": "Honcho Design Newsroom",
    "type": "Project"
  },
  "creator": {
    "id": 1007299143,
    "attachable_sgid": "BAh7CEkiCGdpZAY6BkVUSSIrZ2lkOi8vYmMzL1BlcnNvbi8xMDA3Mjk5MTQzP2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg9hdHRhY2hhYmxlBjsAVEkiD2V4cGlyZXNfYXQGOwBUMA==--919d2c8b11ff403eefcab9db42dd26846d0c3102",
    "name": "Victor Cooper",
    "email_address": "victor@honchodesign.com",
    "personable_type": "User",
    "title": "Chief Strategist",
    "bio": "Don't let your dreams be dreams",
    "created_at": "2016-09-09T22:58:27.559Z",
    "updated_at": "2016-09-09T22:58:31.296Z",
    "admin": true,
    "owner": true,
    "time_zone": "America/Chicago",
    "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBEcqCjw=--c632b967cec296b87363a697a67a87f9cc1e5b45/avatar-64-x4",
    "company": {
      "id": 1033447817,
      "name": "Honcho Design"
    }
  },
  "documents_count": 0,
  "documents_url": "https://3.basecampapi.com/195539477/buckets/2085958496/vaults/9007199254741052/documents.json",
  "uploads_count": 0,
  "uploads_url": "https://3.basecampapi.com/195539477/buckets/2085958496/vaults/9007199254741052/uploads.json",
  "vaults_count": 1,
  "vaults_url": "https://3.basecampapi.com/195539477/buckets/2085958496/vaults/9007199254741052/vaults.json"
}
```
<!-- END GET /buckets/1/vaults/2.json -->
###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/vaults/2.json
```

Create a vault
--------------

* `POST /buckets/1/vaults/2/vaults.json` creates a vault in the project with ID `1` and under the vault with an ID of `2`.

**Required parameters**: `title` for the name of the vault.

This endpoint will return `201 Created` with the current JSON representation of the vault if the creation was a success. See the [Get a vault](#get-a-vault) endpoint for more info on the payload.

###### Example JSON Request

``` json
{
  "title": "Materials"
}
```

###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -H "Content-Type: application/json" \
  -d '{"title":"Materials"}' \
  https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/vaults/2/vaults.json
```

Update a vault
--------------

* `PUT /buckets/1/vaults/3.json` allows changing the title of the vault with an ID of `3` in the project with ID `1`.

This endpoint will return `200 OK` with the current JSON representation of the to-do if the update was a success. See the [Get a vault](#get-a-vault) endpoint for more info on the payload.

###### Example JSON Request

``` json
{
  "title": "Important Materials"
}
```

###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -H "Content-Type: application/json" \
  -d '{"title":"Important Materials"}' -X PUT \
  https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/vaults/3.json
```

[project]: https://github.com/basecamp/bc3-api/blob/master/sections/projects.md#get-a-project
[pagination]: https://github.com/basecamp/bc3-api/blob/master/README.md#pagination
