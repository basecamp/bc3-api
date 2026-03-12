My notifications
=================

The notifications endpoint returns the current user's notification inbox — the same data that powers the "Hey!" menu in Basecamp. Notifications are grouped into three categories: unread items, recently read items, and memorized items.

Each notification represents activity on a recording (message, to-do, comment, etc.) that the current user has been notified about. Notifications track unread state, unread counts, and timestamps for when items were read or received.

Endpoints:

- [Get notifications](#get-notifications)
- [Mark as read](#mark-as-read)


Get notifications
-----------------

* `GET /my/readings.json` will return the current user's notifications grouped into `unreads`, `reads`, and `memories`.

Reads are paginated with 50 items per page. Unreads are not paginated but are capped at 100 items. Memories are not paginated.

_Optional parameters_:

* `page` - page number for paginating through read items. Defaults to `1`.

Each notification in the response includes:

* `id` - the notification ID.
* `created_at` - when the notification was first created.
* `updated_at` - when the notification was last updated.
* `section` - the category: `inbox`, `chats`, `pings`, `remembered`, or `mentions`.
* `unread_count` - the number of unread updates on this item.
* `unread_at` - timestamp when the item was last marked unread, or `null` if read.
* `read_at` - timestamp when the item was last read, or `null` if unread.
* `readable_sgid` - signed global ID for the readable, used when marking items as read.
* `readable_identifier` - a human-readable identifier for the readable.
* `title` - the title of the readable item.
* `type` - the type of readable (e.g. `Recording`, `Event`).
* `bucket_name` - the name of the project this notification belongs to.
* `creator` - the person who created or last updated the readable (see [People][1] for the full person object).
* `content_excerpt` - a text excerpt of the content, when available.
* `app_url` - the URL to view this item in Basecamp.
* `unread_url` - the URL to mark this item as read.
* `bookmark_url` - the URL to bookmark this item.
* `memory_url` - the URL to memorize or forget this item (only present when the item is memorizable).
* `subscribed` - `true` if the current user is subscribed to the item's container.
* `subscription_url` - the URL to manage the subscription for this item's container.
* `previewable_attachments` - an array of previewable attachments, up to 10.

Pings additionally include:

* `participants` - an array of other people in the ping.
* `named` - whether the ping has a custom name.
* `image_url` - the ping's custom image, if one is set.

###### Example JSON Response
<!-- START GET /my/readings.json -->
```json
{
  "unreads": [
    {
      "id": 1069479012,
      "created_at": "2026-02-15T14:22:10.000Z",
      "updated_at": "2026-02-15T14:22:10.000Z",
      "section": "inbox",
      "unread_count": 3,
      "unread_at": "2026-02-15T14:22:10.000Z",
      "read_at": null,
      "readable_sgid": "BAh7BkkiC19yYWlscwY6BkVU...",
      "readable_identifier": "message_1069479012",
      "title": "Kickoff meeting notes",
      "type": "Recording",
      "bucket_name": "Honcho Design Newsroom",
      "creator": {
        "id": 1049715913,
        "attachable_sgid": "BAh7BkkiC19yYWlscwY6BkVU...",
        "name": "Victor Cooper",
        "email_address": "victor@honchodesign.com",
        "personable_type": "User",
        "title": "Chief Strategist",
        "bio": "Don't let your dreams be dreams",
        "location": "Chicago, IL",
        "created_at": "2026-02-12T06:08:49.342Z",
        "updated_at": "2026-02-12T06:08:50.871Z",
        "admin": true,
        "owner": true,
        "client": false,
        "employee": true,
        "time_zone": "America/Chicago",
        "avatar_url": "https://3.basecampapi.com/195539477/people/BAhpBMlkkT4=--5fe7b70fbee7a7f0e2e1e19df7579e5d880c753d/avatar",
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
      "content_excerpt": "Here are the notes from today's kickoff...",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958502/messages/1069479012",
      "unread_url": "https://3.basecampapi.com/195539477/my/readings/1069479012.json",
      "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7BkkiC19yYWlscwY6BkVU....json",
      "subscription_url": "https://3.basecampapi.com/195539477/buckets/2085958502/recordings/1069479012/subscription.json",
      "previewable_attachments": [],
      "subscribed": true
    }
  ],
  "reads": [
    {
      "id": 1069479005,
      "created_at": "2026-02-14T10:05:30.000Z",
      "updated_at": "2026-02-14T16:30:00.000Z",
      "section": "inbox",
      "unread_count": 0,
      "unread_at": "2026-02-14T10:05:30.000Z",
      "read_at": "2026-02-14T16:30:00.000Z",
      "readable_sgid": "BAh7BkkiC19yYWlscwY6BkVU...",
      "readable_identifier": "todo_1069479005",
      "title": "Update the homepage copy",
      "type": "Recording",
      "bucket_name": "Honcho Design Newsroom",
      "creator": {
        "id": 1049715914,
        "attachable_sgid": "BAh7BkkiC19yYWlscwY6BkVU...",
        "name": "Annie Bryan",
        "email_address": "annie@honchodesign.com",
        "personable_type": "User",
        "title": "Central Markets Manager",
        "bio": null,
        "location": null,
        "created_at": "2026-02-12T06:08:49.352Z",
        "updated_at": "2026-02-12T06:08:50.882Z",
        "admin": false,
        "owner": false,
        "client": false,
        "employee": true,
        "time_zone": "America/Chicago",
        "avatar_url": "https://3.basecampapi.com/195539477/people/BAhpBMpkkT4=--2bcbab2d5c2a2d5e2e1e19df7579e5d880c753d/avatar",
        "company": {
          "id": 1033447817,
          "name": "Honcho Design"
        },
        "can_ping": true,
        "can_manage_projects": false,
        "can_manage_people": false,
        "can_access_timesheet": true,
        "can_access_hill_charts": true
      },
      "content_excerpt": "Please review and update the copy on...",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958502/todos/1069479005",
      "unread_url": "https://3.basecampapi.com/195539477/my/readings/1069479005.json",
      "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7BkkiC19yYWlscwY6BkVU....json",
      "subscription_url": "https://3.basecampapi.com/195539477/buckets/2085958502/recordings/1069479005/subscription.json",
      "previewable_attachments": [],
      "subscribed": true
    }
  ],
  "memories": [
    {
      "id": 1069479001,
      "created_at": "2026-02-10T09:00:00.000Z",
      "updated_at": "2026-02-13T11:00:00.000Z",
      "section": "remembered",
      "unread_count": 0,
      "unread_at": "2026-02-10T09:00:00.000Z",
      "read_at": "2026-02-13T11:00:00.000Z",
      "readable_sgid": "BAh7BkkiC19yYWlscwY6BkVU...",
      "readable_identifier": "message_1069479001",
      "title": "Brand guidelines v2",
      "type": "Recording",
      "bucket_name": "Honcho Design Newsroom",
      "creator": {
        "id": 1049715913,
        "attachable_sgid": "BAh7BkkiC19yYWlscwY6BkVU...",
        "name": "Victor Cooper",
        "email_address": "victor@honchodesign.com",
        "personable_type": "User",
        "title": "Chief Strategist",
        "bio": "Don't let your dreams be dreams",
        "location": "Chicago, IL",
        "created_at": "2026-02-12T06:08:49.342Z",
        "updated_at": "2026-02-12T06:08:50.871Z",
        "admin": true,
        "owner": true,
        "client": false,
        "employee": true,
        "time_zone": "America/Chicago",
        "avatar_url": "https://3.basecampapi.com/195539477/people/BAhpBMlkkT4=--5fe7b70fbee7a7f0e2e1e19df7579e5d880c753d/avatar",
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
      "content_excerpt": "Attached are the updated brand guidelines...",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958502/messages/1069479001",
      "unread_url": "https://3.basecampapi.com/195539477/my/readings/1069479001.json",
      "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7BkkiC19yYWlscwY6BkVU....json",
      "memory_url": "https://3.basecampapi.com/195539477/my/readings/1069479001/memory.json",
      "subscription_url": "https://3.basecampapi.com/195539477/buckets/2085958502/recordings/1069479001/subscription.json",
      "previewable_attachments": [],
      "subscribed": true
    }
  ]
}
```
<!-- END GET /my/readings.json -->

###### Copy as cURL

```shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/my/readings.json
```

To paginate through read items:

```shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/my/readings.json?page=2
```


Mark as read
------------

* `PUT /my/unreads.json` will mark the specified items as read.

**Required parameters**:

* `readables` - an array of `readable_sgid` values from the notifications response. These identify the items to mark as read.

Returns `200 OK` on success with no body.

###### Example JSON Request

```json
{
  "readables": [
    "BAh7BkkiC19yYWlscwY6BkVU...",
    "BAh7BkkiC19yYWlscwY6BkVU..."
  ]
}
```

###### Copy as cURL

```shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" \
  -H 'Content-Type: application/json' \
  -X PUT \
  -d '{ "readables": ["BAh7BkkiC19yYWlscwY6BkVU..."] }' \
  https://3.basecampapi.com/$ACCOUNT_ID/my/unreads.json
```

[1]: https://github.com/basecamp/bc3-api/blob/master/sections/people.md#people
