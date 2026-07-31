Folders
=======

Available since Basecamp 5: **folders** group [projects][projects] together on a
person's home screen. Folders are per-user — each person arranges their own home
into folders, and filing a project into a folder for yourself doesn't change how
anyone else sees it. Membership, ordering, and appearance all belong to the
authenticated user.

For historical reasons the path and the wire type say `stack(s)` rather than
`folder(s)`; they are the same thing.

Endpoints:

- [Get folders](#get-folders)
- [Get a folder](#get-a-folder)
- [Create a folder](#create-a-folder)
- [Update a folder](#update-a-folder)
- [Delete a folder](#delete-a-folder)

Get folders
-----------

* `GET /stacks.json` returns the authenticated user's folders, in the order
  they appear on the home screen.

###### Example JSON Response
<!-- START GET /stacks.json -->
```json
[
  {
    "id": 2085958513,
    "name": "Client work",
    "type": "Stack",
    "created_at": "2026-07-27T10:16:49.312Z",
    "updated_at": "2026-07-27T10:16:49.325Z",
    "bucket_ids": [],
    "is_emoji_only_name": false,
    "star_url": "https://3.basecampapi.com/195539477/buckets/2085958513/stars.json",
    "gauges_url": null,
    "color": null,
    "image_url": null,
    "url": "https://3.basecampapi.com/195539477/stacks/2085958513.json"
  }
]
```
<!-- END GET /stacks.json -->

###### Copy as cURL

```shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/stacks.json
```

Get a folder
------------

* `GET /stacks/2.json` returns the folder with an ID of `2`, including the
  [projects][projects] grouped inside it under `projects`.

###### Example JSON Response
<!-- START GET /stacks/2.json -->
```json
{
  "id": 2085958513,
  "name": "Client work",
  "type": "Stack",
  "created_at": "2026-07-27T10:16:49.312Z",
  "updated_at": "2026-07-27T10:16:49.325Z",
  "bucket_ids": [],
  "is_emoji_only_name": false,
  "star_url": "https://3.basecampapi.com/195539477/buckets/2085958513/stars.json",
  "gauges_url": null,
  "color": null,
  "image_url": null,
  "url": "https://3.basecampapi.com/195539477/stacks/2085958513.json",
  "projects": []
}
```
<!-- END GET /stacks/2.json -->

###### Copy as cURL

```shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/stacks/2.json
```

Create a folder
---------------

* `POST /stacks.json` creates a new folder for the authenticated user and
  files the given [projects][projects] into it. The folder is placed at the top
  of the home screen.

###### Optional parameters

| Param         | Type            | Description |
| ------------- | --------------- | ----------- |
| `name`        | String          | The folder's name. Defaults to `New folder` when blank or omitted. |
| `project_ids` | Array<Integer> | IDs of the projects to file into the folder — the same ids the folder reports back as `bucket_ids`. Each must be a project the user can access, or an all-access project they're eligible to join — filing an all-access project the user isn't yet a member of also grants them access to it. Archived, trashed, or invitation-only projects the user isn't on are rejected: the whole request returns `404 Not Found` and nothing is created. Omit it, or send `null` or an empty array, for an empty folder. |

###### Example JSON Request
<!-- START POST PAYLOAD /stacks.json -->
```json
{
  "name": "Client work",
  "project_ids": []
}
```
<!-- END POST PAYLOAD /stacks.json -->

A successful create returns `201 Created` with the new folder's JSON shape,
including its grouped `projects`:

###### Example JSON Response
<!-- START POST /stacks.json -->
```json
{
  "id": 2085958513,
  "name": "Client work",
  "type": "Stack",
  "created_at": "2026-07-27T10:16:49.312Z",
  "updated_at": "2026-07-27T10:16:49.325Z",
  "bucket_ids": [],
  "is_emoji_only_name": false,
  "star_url": "https://3.basecampapi.com/195539477/buckets/2085958513/stars.json",
  "gauges_url": null,
  "color": null,
  "image_url": null,
  "url": "https://3.basecampapi.com/195539477/stacks/2085958513.json",
  "projects": []
}
```
<!-- END POST /stacks.json -->

###### Copy as cURL

```shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -H "Content-Type: application/json" \
  -d '{"name":"Client work","project_ids":[]}' \
  https://3.basecampapi.com/$ACCOUNT_ID/stacks.json
```

Update a folder
---------------

* `PUT /stacks/2.json` renames the folder with an ID of `2`. Only `name` can
  be changed; a folder's projects, ordering, and image are managed elsewhere.

###### Permitted parameters

| Param  | Type   | Description |
| ------ | ------ | ----------- |
| `name` | String | The folder's new name. |

###### Example JSON Request
<!-- START PUT PAYLOAD /stacks/2.json -->
```json
{
  "name": "Active client work"
}
```
<!-- END PUT PAYLOAD /stacks/2.json -->

Returns `200 OK` with the updated folder's JSON shape:

###### Example JSON Response
<!-- START PUT /stacks/2.json -->
```json
{
  "id": 2085958513,
  "name": "Active client work",
  "type": "Stack",
  "created_at": "2026-07-27T10:16:49.312Z",
  "updated_at": "2026-07-27T10:16:50.464Z",
  "bucket_ids": [],
  "is_emoji_only_name": false,
  "star_url": "https://3.basecampapi.com/195539477/buckets/2085958513/stars.json",
  "gauges_url": null,
  "color": null,
  "image_url": null,
  "url": "https://3.basecampapi.com/195539477/stacks/2085958513.json",
  "projects": []
}
```
<!-- END PUT /stacks/2.json -->

###### Copy as cURL

```shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -H "Content-Type: application/json" \
  -d '{"name":"Active client work"}' -X PUT \
  https://3.basecampapi.com/$ACCOUNT_ID/stacks/2.json
```

Delete a folder
---------------

* `DELETE /stacks/2.json` deletes the folder with an ID of `2` and returns
  `204 No Content`. Deleting a folder **unpins its projects** from the person's
  home screen — the projects themselves are not deleted, and they are not moved
  back out onto the home screen; they simply stop appearing there until pinned
  again.

###### Copy as cURL

```shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -X DELETE \
  https://3.basecampapi.com/$ACCOUNT_ID/stacks/2.json
```

[projects]: projects.md
