Search
======

Search across all content in the account that the authenticated user has access to.

Endpoints:

- [Get search metadata](#get-search-metadata)
- [Search recordings](#search-recordings)

Get search metadata
-------------------

* `GET /searches/metadata.json` returns valid filter options for search.

Use this endpoint to discover valid values for the `type` and `file_type` parameters before searching. The available types may vary, so always fetch this endpoint rather than hardcoding values.

###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -A 'MyApp (yourname@example.com)' \
  "https://3.basecampapi.com/$ACCOUNT_ID/searches/metadata.json"
```

###### Example JSON Response

``` json
{
  "recording_search_types": [
    { "key": null, "value": "Search Everything" },
    { "key": "Attachment", "value": "Files & images" },
    { "key": "Chat::Transcript", "value": "Chats" },
    { "key": "Comment", "value": "Comments" },
    { "key": "Document", "value": "Docs" },
    { "key": "Kanban::Card", "value": "Card tables" },
    { "key": "Message", "value": "Messages" },
    { "key": "Question", "value": "Questions" },
    { "key": "Schedule::Entry", "value": "Schedule events" },
    { "key": "Todo", "value": "To-dos" },
    { "key": "Vault", "value": "Folders" }
  ],
  "file_search_types": [
    { "key": null, "value": "All files" },
    { "key": "image", "value": "images" },
    { "key": "video", "value": "videos" },
    { "key": "document", "value": "documents" },
    { "key": "audio", "value": "audio" },
    { "key": "archive", "value": "archives" },
    { "key": "other", "value": "other" }
  ],
  "default_creator_label": "by Anyone",
  "default_bucket_label": "Everywhere",
  "default_circle_label": "with Anyone",
  "default_file_type_label": "All files",
  "default_type_label": "Search Everything"
}
```

Entries with `"key": null` represent the default "search everything" option. Omit the `type` or `file_type` parameter entirely to search without filtering.

Search recordings
-----------------

* `GET /search.json` will return a [paginated list][1] of recordings matching the search query.

**Required parameters**: `q` - the search query string.

_Optional parameters_:

* `type` - Filter by recording type. Use `key` values from the `recording_search_types` array returned by [Get search metadata](#get-search-metadata).
* `bucket_id` - Filter by [project][2] ID. Note: this differs from the [recordings][4] endpoint which uses `bucket`.
* `creator_id` - Filter by creator [person][3] ID.
* `file_type` - Filter attachments by type. Use `key` values from the `file_search_types` array returned by [Get search metadata](#get-search-metadata).
* `exclude_chat` - Set to `1` to exclude chat results.
* `page` - Page number for pagination (default: 1).
* `per_page` - Number of results per page (default: 50).

Results are ordered by relevance with a recency boost.

###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -A 'MyApp (yourname@example.com)' \
  "https://3.basecampapi.com/$ACCOUNT_ID/search.json?q=authentication"
```

###### Example JSON Response

``` json
[
  {
    "id": 9007199254741620,
    "status": "active",
    "visible_to_clients": false,
    "created_at": "2024-01-15T10:30:00.000Z",
    "updated_at": "2024-01-15T10:30:00.000Z",
    "title": "Fix authentication token expiry",
    "inherits_status": true,
    "type": "Todo",
    "url": "https://3.basecampapi.com/999999999/buckets/2085958496/todos/9007199254741620.json",
    "app_url": "https://3.basecamp.com/999999999/buckets/2085958496/todos/9007199254741620",
    "bookmark_url": "https://3.basecampapi.com/999999999/my/bookmarks/BAh7CEkiCGdpZAY6BkVUSSIuZ2lkOi8vYmMzL1JlY29yZGluZy85MDA3MTk5MjU0NzQxNjIwP2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg1yZWFkYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--aeb043c5d84c03f04f7dd573c6f57a9da29a77c7.json",
    "subscription_url": "https://3.basecampapi.com/999999999/buckets/2085958496/recordings/9007199254741620/subscription.json",
    "comments_count": 2,
    "comments_url": "https://3.basecampapi.com/999999999/buckets/2085958496/recordings/9007199254741620/comments.json",
    "content": null,
    "description": null,
    "plain_text_content": "Handle token refresh when the OAuth <em>authentication</em> token expires...",
    "parent": {
      "id": 9007199254741434,
      "title": "Backend Tasks",
      "type": "Todolist",
      "url": "https://3.basecampapi.com/999999999/buckets/2085958496/todolists/9007199254741434.json",
      "app_url": "https://3.basecamp.com/999999999/buckets/2085958496/todolists/9007199254741434"
    },
    "bucket": {
      "id": 2085958496,
      "name": "Backend Project",
      "type": "Project"
    },
    "creator": {
      "id": 1049715914,
      "attachable_sgid": "BAh7CEkiCGdpZAY6BkVUSSIrZ2lkOi8vYmMzL1BlcnNvbi8xMDQ5NzE1OTE0P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg9hdHRhY2hhYmxlBjsAVEkiD2V4cGlyZXNfYXQGOwBUMA==--aeb043c5d84c03f04f7dd573c6f57a9da29a77c7",
      "name": "Annie Bryan",
      "email_address": "annie@honchodesign.com",
      "personable_type": "User",
      "title": "Central Markets Manager",
      "bio": "To open a store is easy, to keep it open is an art",
      "location": null,
      "created_at": "2024-01-15T10:30:00.000Z",
      "updated_at": "2024-01-15T10:30:00.000Z",
      "admin": false,
      "owner": false,
      "client": false,
      "employee": false,
      "time_zone": "America/Chicago",
      "avatar_url": "https://3.basecamp-static.com/...",
      "can_ping": true,
      "can_manage_projects": true,
      "can_manage_people": false
    },
    "starts_on": null,
    "due_on": null,
    "assignees": [],
    "completion_subscribers": [],
    "completion_url": "https://3.basecampapi.com/999999999/buckets/2085958496/todos/9007199254741620/completion.json"
  }
]
```

The `plain_text_content` field contains HTML with search terms wrapped in `<em>` tags for highlighting. Be sure to escape this content appropriately when rendering.

[1]: https://github.com/basecamp/bc3-api/blob/master/README.md#pagination
[2]: https://github.com/basecamp/bc3-api/blob/master/sections/projects.md#projects
[3]: https://github.com/basecamp/bc3-api/blob/master/sections/people.md#people
[4]: https://github.com/basecamp/bc3-api/blob/master/sections/recordings.md#recordings
