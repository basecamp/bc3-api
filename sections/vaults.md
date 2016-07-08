Vaults
======

All Basecamps have a primary vault (folder), to get its ID see the [Get a Basecamp][basecamp] endpoint's `dock` payload. Additional vaults may be nested under the primary vault or any child vault.

Endpoints:

- [Get vaults](#get-vaults)
- [Get a vault](#get-a-vault)
- [Create a vault](#create-a-vault)
- [Update a vault](#create-a-vault)

Get vaults
----------

* `GET /buckets/1/vaults/2/vaults.json` will return a [paginated list][pagination] of vaults in the Basecamp with an ID of `1` and the vault with ID of `2`.

###### Example JSON Response
<!-- START GET /buckets/1/vaults/2/vaults.json -->
```json
[
  {
    "id": 9007199254741202,
    "status": "active",
    "created_at": "2016-05-28T04:51:15.137Z",
    "updated_at": "2016-07-08T02:16:35.662Z",
    "type": "Vault",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958496/vaults/9007199254741202.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958496/vaults/9007199254741202",
    "bucket": {
      "id": 2085958496,
      "type": "Project"
    },
    "parent": {
      "id": 9007199254741052,
      "type": "Vault",
      "url": "https://3.basecampapi.com/195539477/buckets/2085958496/vaults/9007199254741052.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958496/vaults/9007199254741052"
    },
    "creator": {
      "id": 1007299143,
      "name": "Victor Cooper",
      "email_address": "victor@honchodesign.com",
      "personable_type": "User",
      "title": null,
      "created_at": "2016-07-08T02:16:07.483Z",
      "updated_at": "2016-07-08T02:16:11.821Z",
      "admin": true,
      "owner": true,
      "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBEcqCjw=--c632b967cec296b87363a697a67a87f9cc1e5b45/avatar-64-x4",
      "company": {
        "id": 1033447817,
        "name": "Honcho Design"
      }
    },
    "title": "HR Stuff",
    "documents_count": 1,
    "documents_url": "https://3.basecampapi.com/195539477/buckets/2085958496/vaults/9007199254741202/documents.json",
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

* `GET /buckets/1/vaults/2.json` will return the vault with an ID of `2` in the Basecamp with an ID of `1`.

###### Example JSON Response
<!-- START GET /buckets/1/vaults/2.json -->
```json
{
  "id": 9007199254741052,
  "status": "active",
  "created_at": "2016-07-08T02:16:15.367Z",
  "updated_at": "2016-07-08T02:16:35.670Z",
  "type": "Vault",
  "url": "https://3.basecampapi.com/195539477/buckets/2085958496/vaults/9007199254741052.json",
  "app_url": "https://3.basecamp.com/195539477/buckets/2085958496/vaults/9007199254741052",
  "bucket": {
    "id": 2085958496,
    "type": "Project"
  },
  "creator": {
    "id": 1007299143,
    "name": "Victor Cooper",
    "email_address": "victor@honchodesign.com",
    "personable_type": "User",
    "title": null,
    "created_at": "2016-07-08T02:16:07.483Z",
    "updated_at": "2016-07-08T02:16:11.821Z",
    "admin": true,
    "owner": true,
    "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBEcqCjw=--c632b967cec296b87363a697a67a87f9cc1e5b45/avatar-64-x4",
    "company": {
      "id": 1033447817,
      "name": "Honcho Design"
    }
  },
  "title": "Docs & Files",
  "documents_count": 0,
  "documents_url": "https://3.basecampapi.com/195539477/buckets/2085958496/vaults/9007199254741052/documents.json",
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

* `POST /buckets/1/vaults/2/vaults.json` creates a vault in the Basecamp with ID `1` and under the vault with an ID of `2`.

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

* `PUT /buckets/1/vaults/3.json` allows changing the title of the vault with an ID of `3` in the Basecamp with ID `1`.

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

[basecamp]: https://github.com/basecamp/bc3-api/blob/master/sections/basecamps.md#get-a-basecamp
[pagination]: https://github.com/basecamp/bc3-api/blob/master/README.md#pagination
