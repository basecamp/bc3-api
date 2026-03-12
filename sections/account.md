Account
=======

Endpoints:

- [Get account](#get-account)
- [Update account name](#update-account-name)

Get account
-----------

* `GET /account.json` will return the account for the current access token.

Account owners will see additional fields: `frozen` and `paused`. These fields are not included for non-owners.

The `logo` field is only present when the account has a logo configured. It is omitted entirely when no logo exists.

###### Example JSON Response
<!-- START GET /account.json -->
```json
{
  "id": 195539477,
  "name": "Honcho Design",
  "owner_name": "Victor Cooper",
  "active": true,
  "created_at": "2025-12-29T18:52:00.000Z",
  "updated_at": "2026-03-12T10:22:31.000Z",
  "trial": false,
  "trial_ends_on": null,
  "frozen": false,
  "paused": false,
  "can_create_projects": true,
  "can_pin_projects": true,
  "can_create_users": true,
  "can_upload_files": true,
  "plan": {
    "short_name": "business",
    "proper_name": "Basecamp Pro Unlimited",
    "project_limit": null,
    "teams": true,
    "clients": true,
    "templates": true,
    "logo": true,
    "timesheet": true
  },
  "settings": {
    "company_hq_enabled": true,
    "teams_enabled": true,
    "projects_enabled": true
  },
  "logo": {
    "id": 1037392521,
    "sgid": "BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiK2dpZDov...",
    "status_url": "https://3.basecampapi.com/195539477/logos/BAh7BkkiC19yYW.../status.json",
    "byte_size": 85231,
    "content_type": "image/png",
    "filename": "honcho-logo.png",
    "download_url": "https://3.basecampapi.com/195539477/blobs/...",
    "previewable": true,
    "preview_url": "https://3.basecampapi.com/195539477/blobs/...",
    "thumbnail_url": "https://3.basecampapi.com/195539477/blobs/..."
  },
  "trash_app_url": "https://3.basecamp.com/195539477/trash",
  "projects_trash_app_url": "https://3.basecamp.com/195539477/projects/trash"
}
```
<!-- END GET /account.json -->

###### Copy as cURL

```shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/account.json
```

Update account name
-------------------

* `PUT /account/name.json` will rename the current account. Only account owners can use this endpoint — returns `403 Forbidden` for non-owners.

**Required parameters**:

* `name` - the new name for the account. Returns `422 Unprocessable Entity` with an error when blank.

This endpoint returns `200 OK` with the full [account](#get-account) JSON representation on success.

###### Example JSON Request

```json
{
  "name": "Honcho Design Studio"
}
```

###### Example JSON Response
<!-- START PUT /account/name.json -->
```json
{
  "id": 195539477,
  "name": "Honcho Design Studio",
  "owner_name": "Victor Cooper",
  "active": true,
  "created_at": "2025-12-29T18:52:00.000Z",
  "updated_at": "2026-03-12T14:05:22.000Z",
  "trial": false,
  "trial_ends_on": null,
  "frozen": false,
  "paused": false,
  "can_create_projects": true,
  "can_pin_projects": true,
  "can_create_users": true,
  "can_upload_files": true,
  "plan": {
    "short_name": "business",
    "proper_name": "Basecamp Pro Unlimited",
    "project_limit": null,
    "teams": true,
    "clients": true,
    "templates": true,
    "logo": true,
    "timesheet": true
  },
  "settings": {
    "company_hq_enabled": true,
    "teams_enabled": true,
    "projects_enabled": true
  },
  "logo": {
    "id": 1037392521,
    "sgid": "BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiK2dpZDov...",
    "status_url": "https://3.basecampapi.com/195539477/logos/BAh7BkkiC19yYW.../status.json",
    "byte_size": 85231,
    "content_type": "image/png",
    "filename": "honcho-logo.png",
    "download_url": "https://3.basecampapi.com/195539477/blobs/...",
    "previewable": true,
    "preview_url": "https://3.basecampapi.com/195539477/blobs/...",
    "thumbnail_url": "https://3.basecampapi.com/195539477/blobs/..."
  },
  "trash_app_url": "https://3.basecamp.com/195539477/trash",
  "projects_trash_app_url": "https://3.basecamp.com/195539477/projects/trash"
}
```
<!-- END PUT /account/name.json -->

###### Copy as cURL

```shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" \
  -H "Content-Type: application/json" \
  -X PUT \
  -d '{"name":"Honcho Design Studio"}' \
  https://3.basecampapi.com/$ACCOUNT_ID/account/name.json
```
