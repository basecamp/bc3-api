To-do list templates
====================

Endpoints:

- [Get the template library](#get-the-template-library)
- [Create a to-do list from a template](#create-a-to-do-list-from-a-template)
- [Get a template copy](#get-a-template-copy)

Get the template library
------------------------

* `GET /template_library.json` returns the account's to-do list template library, its to-do set, and its active to-do list templates in title order.

The bucket and to-do set IDs can be used with the existing [to-do list](todolists.md) and [to-do](todos.md) endpoints to create and manage template contents.

###### Example JSON Response
<!-- START GET /template_library.json -->
```json
{
  "bucket": {
    "id": 2085958495,
    "name": "To-do List Templates",
    "type": "TemplateLibrary"
  },
  "todoset": {
    "id": 1069478899,
    "title": "To-do List Templates",
    "type": "Todoset",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958495/todosets/1069478899.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958495/todosets/1069478899"
  },
  "todolists": [
    {
      "id": 1069480199,
      "status": "active",
      "visible_to_clients": false,
      "created_at": "2026-08-27T16:03:42.233Z",
      "updated_at": "2026-08-27T16:03:42.974Z",
      "title": "Assigned launch checklist",
      "inherits_status": true,
      "type": "Todolist",
      "url": "https://3.basecampapi.com/195539477/buckets/2085958495/todolists/1069480199.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958495/todolists/1069480199",
      "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiLmdpZDovL2JjMy9SZWNvcmRpbmcvMTA2OTQ4MDE5OT9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg1yZWFkYWJsZQY7AFQ=--c8f44544c2376fdb5fa8216cb38cbbd5afd3b95e.json",
      "comments_count": 0,
      "comments_url": "https://3.basecampapi.com/195539477/buckets/2085958495/recordings/1069480199/comments.json",
      "boosts_count": 0,
      "boosts_url": "https://3.basecampapi.com/195539477/buckets/2085958495/recordings/1069480199/boosts.json",
      "bubble_up_url": "https://3.basecampapi.com/195539477/buckets/2085958495/recordings/1069480199/bubble_up.json",
      "position": 1,
      "parent": {
        "id": 1069478899,
        "title": "To-do List Templates",
        "type": "Todoset",
        "url": "https://3.basecampapi.com/195539477/buckets/2085958495/todosets/1069478899.json",
        "app_url": "https://3.basecamp.com/195539477/buckets/2085958495/todosets/1069478899"
      },
      "bucket": {
        "id": 2085958495,
        "name": "To-do List Templates",
        "type": "TemplateLibrary"
      },
      "creator": {
        "id": 1049715913,
        "attachable_sgid": "BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiK2dpZDovL2JjMy9QZXJzb24vMTA0OTcxNTkxMz9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg9hdHRhY2hhYmxlBjsAVA==--e627c45e6b34e08862da23906862412620e4d5d9",
        "name": "Victor Cooper",
        "personable_type": "User",
        "title": "Chief Strategist",
        "tagline": "Don't let your dreams be dreams",
        "location": "Chicago, IL",
        "created_at": "2026-08-27T16:01:09.786Z",
        "updated_at": "2026-08-27T16:01:10.505Z",
        "email_address": "victor@honchodesign.com",
        "bio": "Don't let your dreams be dreams",
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
      "description": "",
      "description_attachments": [],
      "completed": false,
      "completed_ratio": "0/1",
      "name": "Assigned launch checklist",
      "color": null,
      "groups_url": "https://3.basecampapi.com/195539477/buckets/2085958495/todolists/1069480199/groups.json",
      "todos_url": "https://3.basecampapi.com/195539477/buckets/2085958495/todolists/1069480199/todos.json",
      "app_todos_url": "https://3.basecamp.com/195539477/buckets/2085958495/todolists/1069480199/todos",
      "comments_app_url": "https://3.basecamp.com/195539477/buckets/2085958495/recordings/1069480199/comments"
    },
    {
      "id": 1069480198,
      "status": "active",
      "visible_to_clients": false,
      "created_at": "2026-08-27T16:03:41.820Z",
      "updated_at": "2026-08-27T16:03:41.820Z",
      "title": "Project kickoff",
      "inherits_status": true,
      "type": "Todolist",
      "url": "https://3.basecampapi.com/195539477/buckets/2085958495/todolists/1069480198.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958495/todolists/1069480198",
      "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiLmdpZDovL2JjMy9SZWNvcmRpbmcvMTA2OTQ4MDE5OD9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg1yZWFkYWJsZQY7AFQ=--c8c70a454e67b2c5c3c2cb5edd7eef362e936011.json",
      "comments_count": 0,
      "comments_url": "https://3.basecampapi.com/195539477/buckets/2085958495/recordings/1069480198/comments.json",
      "boosts_count": 0,
      "boosts_url": "https://3.basecampapi.com/195539477/buckets/2085958495/recordings/1069480198/boosts.json",
      "bubble_up_url": "https://3.basecampapi.com/195539477/buckets/2085958495/recordings/1069480198/bubble_up.json",
      "position": 2,
      "parent": {
        "id": 1069478899,
        "title": "To-do List Templates",
        "type": "Todoset",
        "url": "https://3.basecampapi.com/195539477/buckets/2085958495/todosets/1069478899.json",
        "app_url": "https://3.basecamp.com/195539477/buckets/2085958495/todosets/1069478899"
      },
      "bucket": {
        "id": 2085958495,
        "name": "To-do List Templates",
        "type": "TemplateLibrary"
      },
      "creator": {
        "id": 1049715913,
        "attachable_sgid": "BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiK2dpZDovL2JjMy9QZXJzb24vMTA0OTcxNTkxMz9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg9hdHRhY2hhYmxlBjsAVA==--e627c45e6b34e08862da23906862412620e4d5d9",
        "name": "Victor Cooper",
        "personable_type": "User",
        "title": "Chief Strategist",
        "tagline": "Don't let your dreams be dreams",
        "location": "Chicago, IL",
        "created_at": "2026-08-27T16:01:09.786Z",
        "updated_at": "2026-08-27T16:01:10.505Z",
        "email_address": "victor@honchodesign.com",
        "bio": "Don't let your dreams be dreams",
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
      "description": "",
      "description_attachments": [],
      "completed": false,
      "completed_ratio": "0/0",
      "name": "Project kickoff",
      "color": null,
      "groups_url": "https://3.basecampapi.com/195539477/buckets/2085958495/todolists/1069480198/groups.json",
      "todos_url": "https://3.basecampapi.com/195539477/buckets/2085958495/todolists/1069480198/todos.json",
      "app_todos_url": "https://3.basecamp.com/195539477/buckets/2085958495/todolists/1069480198/todos",
      "comments_app_url": "https://3.basecamp.com/195539477/buckets/2085958495/recordings/1069480198/comments"
    }
  ]
}
```
<!-- END GET /template_library.json -->

###### Copy as cURL

```shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" \
  https://3.basecampapi.com/$ACCOUNT_ID/template_library.json
```

Create a to-do list from a template
------------------------------------

* `POST /template_library/copies.json` starts copying a to-do list template into a project's to-do set.

**Required parameters**:

* `template_recording_id` - the ID of a to-do list in the template library.
* `destination_parent_id` - the ID of the destination project's to-do set.

###### Example JSON Request

<!-- START POST PAYLOAD /template_library/copies.json -->
```json
{
  "template_recording_id": 1069480198,
  "destination_parent_id": 1069479838
}
```
<!-- END POST PAYLOAD /template_library/copies.json -->

###### Copy as cURL

```shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -H "Content-Type: application/json" \
  -d '{"template_recording_id":1069480198,"destination_parent_id":1069479838}' -X POST \
  https://3.basecampapi.com/$ACCOUNT_ID/template_library/copies.json
```

A successful request returns `201 Created` with a copy resource. Follow its `url` to track progress.

<!-- START POST /template_library/copies.json -->
```json
{
  "id": 3,
  "status": "pending",
  "source_recording_id": 1069480198,
  "destination_parent_id": 1069479838,
  "url": "https://3.basecampapi.com/195539477/template_library/copies/3.json"
}
```
<!-- END POST /template_library/copies.json -->

When the template contains assignments or completion subscriptions for people who do not have access to the destination project, the response is `422 Unprocessable Entity` and identifies the people who would be added:

<!-- START POST /template_library/copies.json (confirmation required) -->
```json
{
  "error": "people_confirmation_required",
  "people": [
    {
      "id": 1049715915,
      "name": "Amy Rivera",
      "avatar_url": "https://3.basecampapi.com/195539477/people/BAhpBMtkkT4=--9927c47a4cbee30a7f9aea667882496aba799149/avatar"
    }
  ]
}
```
<!-- END POST /template_library/copies.json (confirmation required) -->

Repeat the request with `adding_people_confirmed` set to `true` to grant those people access and start the copy.

Get a template copy
-------------------

* `GET /template_library/copies/1.json` returns the current state of a template copy.

Only the person who started the copy can retrieve it. Requests from anyone else return `404 Not Found`, so poll with the same credentials that created the copy.

The status is `pending`, `processing`, `completed`, or `failed`. Poll the URL no more than once per second while the copy is pending or processing. A completed response includes the newly created to-do list.

###### Example JSON Response
<!-- START GET /template_library/copies/1.json -->
```json
{
  "id": 3,
  "status": "completed",
  "source_recording_id": 1069480198,
  "destination_parent_id": 1069479838,
  "url": "https://3.basecampapi.com/195539477/template_library/copies/3.json",
  "destination_todolist": {
    "id": 1069480208,
    "status": "active",
    "visible_to_clients": false,
    "created_at": "2026-08-27T16:04:17.805Z",
    "updated_at": "2026-08-27T16:04:17.837Z",
    "title": "Project kickoff",
    "inherits_status": true,
    "type": "Todolist",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958504/todolists/1069480208.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958504/todolists/1069480208",
    "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiLmdpZDovL2JjMy9SZWNvcmRpbmcvMTA2OTQ4MDIwOD9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg1yZWFkYWJsZQY7AFQ=--0494faefccb620dc9b3828034fb8c1600bae73f6.json",
    "subscription_url": "https://3.basecampapi.com/195539477/buckets/2085958504/recordings/1069480208/subscription.json",
    "comments_count": 0,
    "comments_url": "https://3.basecampapi.com/195539477/buckets/2085958504/recordings/1069480208/comments.json",
    "boosts_count": 0,
    "boosts_url": "https://3.basecampapi.com/195539477/buckets/2085958504/recordings/1069480208/boosts.json",
    "bubble_up_url": "https://3.basecampapi.com/195539477/buckets/2085958504/recordings/1069480208/bubble_up.json",
    "position": 3,
    "parent": {
      "id": 1069479838,
      "title": "To-dos",
      "type": "Todoset",
      "url": "https://3.basecampapi.com/195539477/buckets/2085958504/todosets/1069479838.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958504/todosets/1069479838"
    },
    "bucket": {
      "id": 2085958504,
      "name": "The Leto Laptop",
      "type": "Project"
    },
    "creator": {
      "id": 1049715913,
      "attachable_sgid": "BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiK2dpZDovL2JjMy9QZXJzb24vMTA0OTcxNTkxMz9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg9hdHRhY2hhYmxlBjsAVA==--e627c45e6b34e08862da23906862412620e4d5d9",
      "name": "Victor Cooper",
      "personable_type": "User",
      "title": "Chief Strategist",
      "tagline": "Don't let your dreams be dreams",
      "location": "Chicago, IL",
      "created_at": "2026-08-27T16:01:09.786Z",
      "updated_at": "2026-08-27T16:01:10.505Z",
      "email_address": "victor@honchodesign.com",
      "bio": "Don't let your dreams be dreams",
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
    "description": "",
    "description_attachments": [],
    "completed": false,
    "completed_ratio": "0/0",
    "name": "Project kickoff",
    "color": null,
    "groups_url": "https://3.basecampapi.com/195539477/buckets/2085958504/todolists/1069480208/groups.json",
    "todos_url": "https://3.basecampapi.com/195539477/buckets/2085958504/todolists/1069480208/todos.json",
    "app_todos_url": "https://3.basecamp.com/195539477/buckets/2085958504/todolists/1069480208/todos",
    "comments_app_url": "https://3.basecamp.com/195539477/buckets/2085958504/recordings/1069480208/comments"
  }
}
```
<!-- END GET /template_library/copies/1.json -->

###### Copy as cURL

```shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" \
  https://3.basecampapi.com/$ACCOUNT_ID/template_library/copies/1.json
```
