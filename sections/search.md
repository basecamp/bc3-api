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

```shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -A 'MyApp (yourname@example.com)' \
  "https://3.basecampapi.com/$ACCOUNT_ID/searches/metadata.json"
```

###### Example JSON Response
<!-- START GET /searches/metadata.json -->
```json
{
  "recording_search_types": [
    {
      "key": null,
      "value": "Search Everything"
    },
    {
      "key": "Kanban::Card",
      "value": "Card tables"
    },
    {
      "key": "Chat::Transcript",
      "value": "Chats"
    },
    {
      "key": "Question",
      "value": "Check-ins"
    },
    {
      "key": "Client::Correspondence",
      "value": "Client emails"
    },
    {
      "key": "Comment",
      "value": "Comments"
    },
    {
      "key": "Document",
      "value": "Documents"
    },
    {
      "key": "Schedule::Entry",
      "value": "Events"
    },
    {
      "key": "Attachment",
      "value": "Files"
    },
    {
      "key": "Vault",
      "value": "Folders"
    },
    {
      "key": "Inbox::Forward",
      "value": "Forwarded emails"
    },
    {
      "key": "Message",
      "value": "Messages"
    },
    {
      "key": "Circle",
      "value": "Pings"
    },
    {
      "key": "Todo",
      "value": "To-dos"
    }
  ],
  "file_search_types": [
    {
      "key": null,
      "value": "All files"
    },
    {
      "key": "Image",
      "value": "Images"
    },
    {
      "key": "Audio",
      "value": "Audios"
    },
    {
      "key": "Video",
      "value": "Videos"
    },
    {
      "key": "PDF",
      "value": "PDFs"
    }
  ],
  "default_creator_label": "by Anyone",
  "default_bucket_label": "Everywhere",
  "default_circle_label": "with Anyone",
  "default_file_type_label": "All files",
  "default_type_label": "Search Everything"
}
```
<!-- END GET /searches/metadata.json -->

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

```shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -A 'MyApp (yourname@example.com)' \
  "https://3.basecampapi.com/$ACCOUNT_ID/search.json?q=authentication"
```

###### Example JSON Response
<!-- START GET /search.json -->
```json
[
  {
    "id": 1069480167,
    "status": "active",
    "visible_to_clients": false,
    "created_at": "2026-02-07T01:42:30.427Z",
    "updated_at": "2026-02-07T01:42:30.446Z",
    "title": "Triage",
    "inherits_status": true,
    "type": "Kanban::Triage",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958518/card_tables/columns/1069480167.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958518/card_tables/columns/1069480167",
    "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiLmdpZDovL2JjMy9SZWNvcmRpbmcvMTA2OTQ4MDE2Nz9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg1yZWFkYWJsZQY7AFQ=--fa6c69d588a42ee8088bfb8ab5ccaf8038eca3ac.json",
    "subscription_url": "https://3.basecampapi.com/195539477/recordings/1069480167/subscription.json",
    "parent": {
      "id": 1069480166,
      "title": "Card Table",
      "type": "Kanban::Board",
      "url": "https://3.basecampapi.com/195539477/buckets/2085958518/card_tables/1069480166.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958518/card_tables/1069480166"
    },
    "bucket": {
      "id": 2085958518,
      "name": "New project from template",
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
      "created_at": "2026-01-31T08:29:28.365Z",
      "updated_at": "2026-01-31T08:29:32.599Z",
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
      "can_access_timesheet": true,
      "can_access_hill_charts": true
    },
    "description": null,
    "subscribers": [
      {
        "id": 1049715913,
        "attachable_sgid": "BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiK2dpZDovL2JjMy9QZXJzb24vMTA0OTcxNTkxMz9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg9hdHRhY2hhYmxlBjsAVA==--e627c45e6b34e08862da23906862412620e4d5d9",
        "name": "Victor Cooper",
        "email_address": "victor@honchodesign.com",
        "personable_type": "User",
        "title": "Chief Strategist",
        "bio": "Don’t let your dreams be dreams",
        "location": "Chicago, IL",
        "created_at": "2026-01-31T08:29:28.365Z",
        "updated_at": "2026-01-31T08:29:32.599Z",
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
        "can_access_timesheet": true,
        "can_access_hill_charts": true
      }
    ],
    "color": null,
    "cards_count": 0,
    "comment_count": 0,
    "cards_url": "https://3.basecampapi.com/195539477/buckets/2085958518/card_tables/lists/1069480167/cards.json",
    "content": null
  }
]
```
<!-- END GET /search.json -->

The `plain_text_content` field contains HTML with search terms wrapped in `<em>` tags for highlighting. Be sure to escape this content appropriately when rendering.

[1]: https://github.com/basecamp/bc3-api/blob/master/README.md#pagination
[2]: https://github.com/basecamp/bc3-api/blob/master/sections/projects.md#projects
[3]: https://github.com/basecamp/bc3-api/blob/master/sections/people.md#people
[4]: https://github.com/basecamp/bc3-api/blob/master/sections/recordings.md#recordings
