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

* `GET /vaults/2/vaults.json` will return a [paginated list][pagination] of vaults under the vault with ID of `2`.

###### Example JSON Response
<!-- START GET /vaults/2/vaults.json -->
```json
[
  {
    "id": 1069479146,
    "status": "active",
    "visible_to_clients": false,
    "created_at": "2026-01-04T04:22:00.000Z",
    "updated_at": "2026-02-12T06:09:14.204Z",
    "title": "HR Stuff",
    "inherits_status": true,
    "type": "Vault",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958502/vaults/1069479146.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958502/vaults/1069479146",
    "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiLmdpZDovL2JjMy9SZWNvcmRpbmcvMTA2OTQ3OTE0Nj9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg1yZWFkYWJsZQY7AFQ=--941dcb6e999d60ec335f682604c92689a0e87d3d.json",
    "position": 1,
    "parent": {
      "id": 1069478984,
      "title": "Docs & Files",
      "type": "Vault",
      "url": "https://3.basecampapi.com/195539477/buckets/2085958502/vaults/1069478984.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958502/vaults/1069478984"
    },
    "bucket": {
      "id": 2085958502,
      "name": "Honcho Design Newsroom",
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
      "created_at": "2026-02-12T06:08:49.342Z",
      "updated_at": "2026-02-12T06:08:50.871Z",
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
      "can_access_timesheet": false,
      "can_access_hill_charts": true
    },
    "documents_count": 1,
    "documents_url": "https://3.basecampapi.com/195539477/vaults/1069479146/documents.json",
    "uploads_count": 0,
    "uploads_url": "https://3.basecampapi.com/195539477/vaults/1069479146/uploads.json",
    "vaults_count": 0,
    "vaults_url": "https://3.basecampapi.com/195539477/vaults/1069479146/vaults.json"
  }
]
```
<!-- END GET /vaults/2/vaults.json -->
###### Copy as cURL

```shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/vaults/2/vaults.json
```

Get a vault
-----------

* `GET /vaults/2.json` will return the vault with an ID of `2`.

###### Example JSON Response
<!-- START GET /vaults/2.json -->
```json
{
  "id": 1069478984,
  "status": "active",
  "visible_to_clients": false,
  "created_at": "2026-02-12T06:09:02.382Z",
  "updated_at": "2026-02-12T06:09:14.205Z",
  "title": "Docs & Files",
  "inherits_status": true,
  "type": "Vault",
  "url": "https://3.basecampapi.com/195539477/buckets/2085958502/vaults/1069478984.json",
  "app_url": "https://3.basecamp.com/195539477/buckets/2085958502/vaults/1069478984",
  "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiLmdpZDovL2JjMy9SZWNvcmRpbmcvMTA2OTQ3ODk4ND9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg1yZWFkYWJsZQY7AFQ=--80168f167479a9067841aa2e6ffd2928c2e9ece1.json",
  "position": 3,
  "bucket": {
    "id": 2085958502,
    "name": "Honcho Design Newsroom",
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
    "created_at": "2026-02-12T06:08:49.342Z",
    "updated_at": "2026-02-12T06:08:50.871Z",
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
    "can_access_timesheet": false,
    "can_access_hill_charts": true
  },
  "documents_count": 0,
  "documents_url": "https://3.basecampapi.com/195539477/vaults/1069478984/documents.json",
  "uploads_count": 0,
  "uploads_url": "https://3.basecampapi.com/195539477/vaults/1069478984/uploads.json",
  "vaults_count": 1,
  "vaults_url": "https://3.basecampapi.com/195539477/vaults/1069478984/vaults.json"
}
```
<!-- END GET /vaults/2.json -->
###### Copy as cURL

```shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/vaults/2.json
```

Create a vault
--------------

* `POST /vaults/2/vaults.json` creates a vault under the vault with an ID of `2`.

**Required parameters**: `title` for the name of the vault.

This endpoint will return `201 Created` with the current JSON representation of the vault if the creation was a success. See the [Get a vault](#get-a-vault) endpoint for more info on the payload.

###### Example JSON Request

```json
{
  "title": "Materials"
}
```

###### Copy as cURL

```shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -H "Content-Type: application/json" \
  -d '{"title":"Materials"}' \
  https://3.basecampapi.com/$ACCOUNT_ID/vaults/2/vaults.json
```

Update a vault
--------------

* `PUT /vaults/3.json` allows changing the title of the vault with an ID of `3`.

This endpoint will return `200 OK` with the current JSON representation of the to-do if the update was a success. See the [Get a vault](#get-a-vault) endpoint for more info on the payload.

###### Example JSON Request

```json
{
  "title": "Important Materials"
}
```

###### Copy as cURL

```shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -H "Content-Type: application/json" \
  -d '{"title":"Important Materials"}' -X PUT \
  https://3.basecampapi.com/$ACCOUNT_ID/vaults/3.json
```

Legacy project-scoped routes
-----------------------------

The following project-scoped routes are still supported and will remain available, but flat routes above are the canonical form for new integrations.

* `GET /buckets/1/vaults/2/vaults.json` → [Get vaults](#get-vaults)
* `GET /buckets/1/vaults/2.json` → [Get a vault](#get-a-vault)
* `POST /buckets/1/vaults/2/vaults.json` → [Create a vault](#create-a-vault)
* `PUT /buckets/1/vaults/3.json` → [Update a vault](#update-a-vault)

[project]: https://github.com/basecamp/bc3-api/blob/master/sections/projects.md#get-a-project
[pagination]: https://github.com/basecamp/bc3-api/blob/master/README.md#pagination
