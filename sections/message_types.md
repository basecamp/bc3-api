Message Types
=============

Endpoints:

- [Get message types](#get-message-types)
- [Get a message type](#get-a-message-type)
- [Create a message type](#create-a-message-type)
- [Update a message type](#update-a-message-type)
- [Destroy a message type](#destroy-a-message-type)

Get message types
-----------------

* `GET /buckets/1/categories.json` will return a list of all the message types in the project with an ID of `1`.

###### Example JSON Response
<!-- START GET /buckets/1/categories.json -->
```json
[
  {
    "id": 823758568,
    "name": "Announcement",
    "icon": "📢",
    "created_at": "2026-02-12T06:09:34.617Z",
    "updated_at": "2026-02-12T06:09:34.617Z"
  },
  {
    "id": 823758569,
    "name": "FYI",
    "icon": "✨",
    "created_at": "2026-02-12T06:09:34.619Z",
    "updated_at": "2026-02-12T06:09:34.619Z"
  }
]
```
<!-- END GET /buckets/1/categories.json -->

###### Copy as cURL

```shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/categories.json
```

Get a message type
------------------

* `GET /buckets/1/categories/2.json` will return the message type with ID `2` in the project with an ID of `1`.

###### Example JSON Response
<!-- START GET /buckets/1/categories/2.json -->
```json
{
  "id": 823758568,
  "name": "Announcement",
  "icon": "📢",
  "created_at": "2026-02-12T06:09:34.617Z",
  "updated_at": "2026-02-12T06:09:34.617Z"
}
```
<!-- END GET /buckets/1/categories/2.json -->

###### Copy as cURL

```shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/categories/2.json
```

Create a message type
---------------------

* `POST /buckets/1/categories.json` creates a new message type in the project with an ID of `1`.

**Required parameters**: `name` and `icon` for the new message type.

This endpoint will return `201 Created` with the current JSON representation of the message type if the creation was a success. See the [Get a message type](#get-a-message-type) endpoint for more info on the payload.

###### Example JSON Request

```json
{
  "name": "Announcement",
  "icon": "📢"
}
```

###### Copy as cURL

```shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -H "Content-Type: application/json" \
  -d '{"name":"Announcement","icon": "📢"}' \
  https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/categories.json
```

Update a message type
---------------------

* `PUT /buckets/1/categories/2.json` allows changing the message type with an ID of `2` in the project with an ID of `1`.

This endpoint will return `200 OK` with the current JSON representation of the message type if the update was a success. See the [Get a message type](#get-a-message-type) endpoint for more info on the payload.

###### Example JSON Request

```json
{
  "name": "Quick Update",
  "icon": "📢"
}
```

###### Copy as cURL

```shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -H "Content-Type: application/json" \
  -d '{"name":"Quick Update","icon":"📢"}' -X PUT \
  https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/categories/2.json
```

Destroy a message type
----------------------

* `DELETE /buckets/1/categories/2.json` will delete the message type with an ID of `2` in the project with an ID of `1`.

No parameters required. Returns `204 No Content` if successful.

###### Copy as cURL

```shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -H "Content-Type: application/json" -X DELETE \
  https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/categories/2.json
```
