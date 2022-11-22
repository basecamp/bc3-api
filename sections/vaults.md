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
    "id": 1069479099,
    "status": "active",
    "visible_to_clients": false,
    "created_at": "2022-10-14T17:36:37.216Z",
    "updated_at": "2022-10-14T17:36:37.216Z",
    "title": "Benefits",
    "inherits_status": true,
    "type": "Vault",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958497/vaults/1069479099.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958497/vaults/1069479099",
    "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7CEkiCGdpZAY6BkVUSSIuZ2lkOi8vYmMzL1JlY29yZGluZy8xMDY5NDc5MDk5P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg1yZWFkYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--339c1f524eabce1418819d1259d8b0b8804199c0.json",
    "position": 1,
    "parent": {
      "id": 1069479098,
      "title": "HR Stuff",
      "type": "Vault",
      "url": "https://3.basecampapi.com/195539477/buckets/2085958497/vaults/1069479098.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958497/vaults/1069479098"
    },
    "bucket": {
      "id": 2085958497,
      "name": "Honcho Design Newsroom",
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
      "created_at": "2022-11-25T16:24:33.557Z",
      "updated_at": "2022-11-25T16:24:33.854Z",
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
    "documents_count": 0,
    "documents_url": "https://3.basecampapi.com/195539477/buckets/2085958497/vaults/1069479099/documents.json",
    "uploads_count": 0,
    "uploads_url": "https://3.basecampapi.com/195539477/buckets/2085958497/vaults/1069479099/uploads.json",
    "vaults_count": 0,
    "vaults_url": "https://3.basecampapi.com/195539477/buckets/2085958497/vaults/1069479099/vaults.json"
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
  "id": 1069478932,
  "status": "active",
  "visible_to_clients": false,
  "created_at": "2022-11-25T16:24:37.280Z",
  "updated_at": "2022-11-25T16:24:50.564Z",
  "title": "Docs & Files",
  "inherits_status": true,
  "type": "Vault",
  "url": "https://3.basecampapi.com/195539477/buckets/2085958497/vaults/1069478932.json",
  "app_url": "https://3.basecamp.com/195539477/buckets/2085958497/vaults/1069478932",
  "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7CEkiCGdpZAY6BkVUSSIuZ2lkOi8vYmMzL1JlY29yZGluZy8xMDY5NDc4OTMyP2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg1yZWFkYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--019700aaa4b8222137474a665bd3f88dc0329ad1.json",
  "position": 3,
  "bucket": {
    "id": 2085958497,
    "name": "Honcho Design Newsroom",
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
    "created_at": "2022-11-25T16:24:33.557Z",
    "updated_at": "2022-11-25T16:24:33.854Z",
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
  "documents_count": 0,
  "documents_url": "https://3.basecampapi.com/195539477/buckets/2085958497/vaults/1069478932/documents.json",
  "uploads_count": 0,
  "uploads_url": "https://3.basecampapi.com/195539477/buckets/2085958497/vaults/1069478932/uploads.json",
  "vaults_count": 0,
  "vaults_url": "https://3.basecampapi.com/195539477/buckets/2085958497/vaults/1069478932/vaults.json"
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
