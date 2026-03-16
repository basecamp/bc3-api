Lineup Markers
================

Endpoints:

- [List markers](#list-markers)
- [Create a marker](#create-a-marker)
- [Update a marker](#update-a-marker)
- [Destroy a marker](#destroy-a-step)

List markers
-----------------------

* `GET /lineup/markers.json` returns all markers for the account.

###### Example JSON Response

```json
[
  {
    "id": 1,
    "name": "Anniversary",
    "date": "2021-01-01",
    "created_at": "2020-12-15T10:30:00.000Z",
    "updated_at": "2020-12-15T10:30:00.000Z"
  }
]
```

###### Copy as cURL

```shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -H "Content-Type: application/json" \
  https://3.basecampapi.com/$ACCOUNT_ID/lineup/markers.json
```

Create a marker
-------------------------

* `POST /lineup/markers.json` creates an account wide marker that shows up in the Lineup.

**Required parameters**:

* `name` of the marker.
* `date` of the marker iso8601 formatted without a time part.

This endpoint will return `201 Created` with an empty response body.

###### Example JSON Request

```json
{
  "name": "Anniversary",
  "date": "2021-01-01"
}
```

###### Copy as cURL

```shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -H "Content-Type: application/json" \
  -d '{"name": "Anniversary", "date": "2021-01-01"}' \
  https://3.basecampapi.com/$ACCOUNT_ID/lineup/markers.json
```

Update a marker
-----------------------

* `PUT /lineup/markers/1.json` change name and/or date of the marker with an ID of `1`.

_Optional parameters_:

* `name` of the marker.
* `date` of the marker iso8601 formatted without a time part.

This endpoint will return `200 OK` with an empty response body.

###### Example JSON Request

```json
{
  "name": "Updated anniversary"
}
```

###### Copy as cURL

```shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -H "Content-Type: application/json" \
  -d '{"name": "Updated anniversary"}' -X PUT \
  https://3.basecampapi.com/$ACCOUNT_ID/lineup/markers/1.json
```

Destroy a marker
-----------------------

* `DELETE /lineup/markers/1.json` permanently destroys the marker with an ID of `1` immediately.

This endpoint will return `204 No Content`.

###### Copy as cURL

```shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -H "Content-Type: application/json" \
  -X DELETE \
  https://3.basecampapi.com/$ACCOUNT_ID/lineup/markers/1.json
```
