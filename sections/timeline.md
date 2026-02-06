Timeline
========

The timeline shows recent activity across your Basecamp account or within a specific project. It provides a chronological feed of events like messages posted, to-dos completed, files uploaded, and more.

Endpoints:

- [Get timeline](#get-timeline)
- [Get project timeline](#get-project-timeline)
- [Get person's timeline](#get-persons-timeline)

Get timeline
------------

* `GET /reports/progress.json` will return a [paginated list][pagination] of timeline events across all projects the authenticated user can access.

###### Example JSON Response
<!-- START GET /reports/progress.json -->
```json
[
  {
    "id": 1071915901,
    "created_at": "2026-02-06T22:56:23.125Z",
    "kind": "project_access_changed",
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
    "action": "Victor C. changed who can access this project",
    "target": null,
    "title": "Victor C. changed who can access this project",
    "summary_excerpt": "Steve Marsh was granted access.",
    "avatars_sample": [],
    "bucket": {
      "id": 2085958504,
      "name": "The Leto Laptop",
      "url": "https://3.basecampapi.com/195539477/projects/2085958504.json",
      "app_url": "https://3.basecamp.com/195539477/projects/2085958504"
    }
  },
  {
    "id": 1071915899,
    "created_at": "2026-02-06T22:56:22.481Z",
    "kind": "project_access_changed",
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
    "action": "Victor C. changed who can access this project",
    "target": null,
    "title": "Victor C. changed who can access this project",
    "summary_excerpt": "Amy Rivera was granted access.",
    "avatars_sample": [],
    "bucket": {
      "id": 2085958504,
      "name": "The Leto Laptop",
      "url": "https://3.basecampapi.com/195539477/projects/2085958504.json",
      "app_url": "https://3.basecamp.com/195539477/projects/2085958504"
    }
  },
  {
    "id": 1071915883,
    "created_at": "2026-02-06T22:56:14.308Z",
    "kind": "todo_created",
    "parent_recording_id": 1069480097,
    "url": "https://3.basecampapi.com/195539477/buckets/2085958516/todos/1069480101.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958516/todos/1069480101",
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
    "action": "Victor C. added a to-do",
    "target": "First things first",
    "title": "On “First things first”, Victor C. added",
    "summary_excerpt": "Install ShipShape",
    "avatars_sample": [],
    "bucket": {
      "id": 2085958516,
      "name": "New project from template",
      "url": "https://3.basecampapi.com/195539477/projects/2085958516.json",
      "app_url": "https://3.basecamp.com/195539477/projects/2085958516"
    },
    "attachments": []
  },
  {
    "id": 1071915882,
    "created_at": "2026-02-06T22:56:14.192Z",
    "kind": "todo_created",
    "parent_recording_id": 1069480097,
    "url": "https://3.basecampapi.com/195539477/buckets/2085958516/todos/1069480100.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958516/todos/1069480100",
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
    "action": "Victor C. added a to-do",
    "target": "First things first",
    "title": "On “First things first”, Victor C. added",
    "summary_excerpt": "Talk to Jerry about holidays",
    "avatars_sample": [],
    "bucket": {
      "id": 2085958516,
      "name": "New project from template",
      "url": "https://3.basecampapi.com/195539477/projects/2085958516.json",
      "app_url": "https://3.basecamp.com/195539477/projects/2085958516"
    },
    "attachments": []
  },
  {
    "id": 1071915880,
    "created_at": "2026-02-06T22:56:13.958Z",
    "kind": "todo_created",
    "parent_recording_id": 1069480097,
    "url": "https://3.basecampapi.com/195539477/buckets/2085958516/todos/1069480098.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958516/todos/1069480098",
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
    "action": "Victor C. added a to-do",
    "target": "First things first",
    "title": "On “First things first”, Victor C. added",
    "summary_excerpt": "Talk to Cheryl about benefits",
    "avatars_sample": [],
    "bucket": {
      "id": 2085958516,
      "name": "New project from template",
      "url": "https://3.basecampapi.com/195539477/projects/2085958516.json",
      "app_url": "https://3.basecamp.com/195539477/projects/2085958516"
    },
    "attachments": []
  }
]
```
<!-- END GET /reports/progress.json -->

###### Copy as cURL

```shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/reports/progress.json
```

Get project timeline
--------------------

* `GET /projects/1/timeline.json` will return a [paginated list][pagination] of timeline events in the project with an ID of `1`.

###### Example JSON Response
<!-- START GET /projects/1/timeline.json -->
```json
[
  {
    "id": 1071915901,
    "created_at": "2026-02-06T22:56:23.125Z",
    "kind": "project_access_changed",
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
    "action": "Victor C. changed who can access this project",
    "target": null,
    "title": "Victor C. changed who can access this project",
    "summary_excerpt": "Steve Marsh was granted access.",
    "avatars_sample": [],
    "bucket": {
      "id": 2085958504,
      "name": "The Leto Laptop",
      "url": "https://3.basecampapi.com/195539477/projects/2085958504.json",
      "app_url": "https://3.basecamp.com/195539477/projects/2085958504"
    }
  },
  {
    "id": 1071915899,
    "created_at": "2026-02-06T22:56:22.481Z",
    "kind": "project_access_changed",
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
    "action": "Victor C. changed who can access this project",
    "target": null,
    "title": "Victor C. changed who can access this project",
    "summary_excerpt": "Amy Rivera was granted access.",
    "avatars_sample": [],
    "bucket": {
      "id": 2085958504,
      "name": "The Leto Laptop",
      "url": "https://3.basecampapi.com/195539477/projects/2085958504.json",
      "app_url": "https://3.basecamp.com/195539477/projects/2085958504"
    }
  }
]
```
<!-- END GET /projects/1/timeline.json -->

###### Copy as cURL

```shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/projects/1/timeline.json
```

Get person's timeline
---------------------

* `GET /reports/users/progress/1.json` will return a JSON object containing the person plus a [paginated list][pagination] (`events`) of timeline events created by the person with an ID of `1`.

###### Example JSON Response
<!-- START GET /reports/users/progress/1.json -->
```json
{
  "person": {
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
  "events": [
    {
      "id": 1071915901,
      "created_at": "2026-02-06T22:56:23.125Z",
      "kind": "project_access_changed",
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
      "action": "Victor C. changed who can access this project",
      "target": null,
      "title": "Victor C. changed who can access this project",
      "summary_excerpt": "Steve Marsh was granted access.",
      "avatars_sample": [],
      "bucket": {
        "id": 2085958504,
        "name": "The Leto Laptop",
        "url": "https://3.basecampapi.com/195539477/projects/2085958504.json",
        "app_url": "https://3.basecamp.com/195539477/projects/2085958504"
      }
    },
    {
      "id": 1071915899,
      "created_at": "2026-02-06T22:56:22.481Z",
      "kind": "project_access_changed",
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
      "action": "Victor C. changed who can access this project",
      "target": null,
      "title": "Victor C. changed who can access this project",
      "summary_excerpt": "Amy Rivera was granted access.",
      "avatars_sample": [],
      "bucket": {
        "id": 2085958504,
        "name": "The Leto Laptop",
        "url": "https://3.basecampapi.com/195539477/projects/2085958504.json",
        "app_url": "https://3.basecamp.com/195539477/projects/2085958504"
      }
    },
    {
      "id": 1071915883,
      "created_at": "2026-02-06T22:56:14.308Z",
      "kind": "todo_created",
      "parent_recording_id": 1069480097,
      "url": "https://3.basecampapi.com/195539477/buckets/2085958516/todos/1069480101.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958516/todos/1069480101",
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
      "action": "Victor C. added a to-do",
      "target": "First things first",
      "title": "On “First things first”, Victor C. added",
      "summary_excerpt": "Install ShipShape",
      "avatars_sample": [],
      "bucket": {
        "id": 2085958516,
        "name": "New project from template",
        "url": "https://3.basecampapi.com/195539477/projects/2085958516.json",
        "app_url": "https://3.basecamp.com/195539477/projects/2085958516"
      },
      "attachments": []
    },
    {
      "id": 1071915882,
      "created_at": "2026-02-06T22:56:14.192Z",
      "kind": "todo_created",
      "parent_recording_id": 1069480097,
      "url": "https://3.basecampapi.com/195539477/buckets/2085958516/todos/1069480100.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958516/todos/1069480100",
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
      "action": "Victor C. added a to-do",
      "target": "First things first",
      "title": "On “First things first”, Victor C. added",
      "summary_excerpt": "Talk to Jerry about holidays",
      "avatars_sample": [],
      "bucket": {
        "id": 2085958516,
        "name": "New project from template",
        "url": "https://3.basecampapi.com/195539477/projects/2085958516.json",
        "app_url": "https://3.basecamp.com/195539477/projects/2085958516"
      },
      "attachments": []
    },
    {
      "id": 1071915880,
      "created_at": "2026-02-06T22:56:13.958Z",
      "kind": "todo_created",
      "parent_recording_id": 1069480097,
      "url": "https://3.basecampapi.com/195539477/buckets/2085958516/todos/1069480098.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958516/todos/1069480098",
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
      "action": "Victor C. added a to-do",
      "target": "First things first",
      "title": "On “First things first”, Victor C. added",
      "summary_excerpt": "Talk to Cheryl about benefits",
      "avatars_sample": [],
      "bucket": {
        "id": 2085958516,
        "name": "New project from template",
        "url": "https://3.basecampapi.com/195539477/projects/2085958516.json",
        "app_url": "https://3.basecamp.com/195539477/projects/2085958516"
      },
      "attachments": []
    },
    {
      "id": 1071915874,
      "created_at": "2026-02-06T22:56:11.891Z",
      "kind": "dock_created",
      "url": "https://3.basecampapi.com/195539477/buckets/2085958516/dock.json",
      "app_url": "https://3.basecamp.com/195539477/projects/2085958516",
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
      "action": "Victor C. started a new project called New project from template",
      "target": "New project from template",
      "title": "Victor C. started a new project called “New project from template”",
      "summary_excerpt": null,
      "avatars_sample": [],
      "bucket": {
        "id": 2085958516,
        "name": "New project from template",
        "url": "https://3.basecampapi.com/195539477/projects/2085958516.json",
        "app_url": "https://3.basecamp.com/195539477/projects/2085958516"
      },
      "attachments": []
    },
    {
      "id": 1071915860,
      "created_at": "2026-02-06T22:45:38.643Z",
      "kind": "project_access_changed",
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
      "action": "Victor C. changed who can access this project",
      "target": null,
      "title": "Victor C. changed who can access this project",
      "summary_excerpt": "Steve Marsh was granted access.",
      "avatars_sample": [],
      "bucket": {
        "id": 2085958504,
        "name": "The Leto Laptop",
        "url": "https://3.basecampapi.com/195539477/projects/2085958504.json",
        "app_url": "https://3.basecamp.com/195539477/projects/2085958504"
      }
    },
    {
      "id": 1071915858,
      "created_at": "2026-02-06T22:45:37.863Z",
      "kind": "project_access_changed",
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
      "action": "Victor C. changed who can access this project",
      "target": null,
      "title": "Victor C. changed who can access this project",
      "summary_excerpt": "Amy Rivera was granted access.",
      "avatars_sample": [],
      "bucket": {
        "id": 2085958504,
        "name": "The Leto Laptop",
        "url": "https://3.basecampapi.com/195539477/projects/2085958504.json",
        "app_url": "https://3.basecamp.com/195539477/projects/2085958504"
      }
    },
    {
      "id": 1071915841,
      "created_at": "2026-02-06T22:45:32.261Z",
      "kind": "todo_created",
      "parent_recording_id": 1069480069,
      "url": "https://3.basecampapi.com/195539477/buckets/2085958515/todos/1069480072.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958515/todos/1069480072",
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
      "action": "Victor C. added a to-do",
      "target": "First things first",
      "title": "On “First things first”, Victor C. added",
      "summary_excerpt": "Install ShipShape",
      "avatars_sample": [],
      "bucket": {
        "id": 2085958515,
        "name": "New project from template",
        "url": "https://3.basecampapi.com/195539477/projects/2085958515.json",
        "app_url": "https://3.basecamp.com/195539477/projects/2085958515"
      },
      "attachments": []
    },
    {
      "id": 1071915840,
      "created_at": "2026-02-06T22:45:32.213Z",
      "kind": "todo_created",
      "parent_recording_id": 1069480069,
      "url": "https://3.basecampapi.com/195539477/buckets/2085958515/todos/1069480071.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958515/todos/1069480071",
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
      "action": "Victor C. added a to-do",
      "target": "First things first",
      "title": "On “First things first”, Victor C. added",
      "summary_excerpt": "Talk to Jerry about holidays",
      "avatars_sample": [],
      "bucket": {
        "id": 2085958515,
        "name": "New project from template",
        "url": "https://3.basecampapi.com/195539477/projects/2085958515.json",
        "app_url": "https://3.basecamp.com/195539477/projects/2085958515"
      },
      "attachments": []
    },
    {
      "id": 1071915839,
      "created_at": "2026-02-06T22:45:32.146Z",
      "kind": "todo_created",
      "parent_recording_id": 1069480069,
      "url": "https://3.basecampapi.com/195539477/buckets/2085958515/todos/1069480070.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958515/todos/1069480070",
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
      "action": "Victor C. added a to-do",
      "target": "First things first",
      "title": "On “First things first”, Victor C. added",
      "summary_excerpt": "Talk to Cheryl about benefits",
      "avatars_sample": [],
      "bucket": {
        "id": 2085958515,
        "name": "New project from template",
        "url": "https://3.basecampapi.com/195539477/projects/2085958515.json",
        "app_url": "https://3.basecamp.com/195539477/projects/2085958515"
      },
      "attachments": []
    },
    {
      "id": 1071915833,
      "created_at": "2026-02-06T22:45:31.892Z",
      "kind": "dock_created",
      "url": "https://3.basecampapi.com/195539477/buckets/2085958515/dock.json",
      "app_url": "https://3.basecamp.com/195539477/projects/2085958515",
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
      "action": "Victor C. started a new project called New project from template",
      "target": "New project from template",
      "title": "Victor C. started a new project called “New project from template”",
      "summary_excerpt": null,
      "avatars_sample": [],
      "bucket": {
        "id": 2085958515,
        "name": "New project from template",
        "url": "https://3.basecampapi.com/195539477/projects/2085958515.json",
        "app_url": "https://3.basecamp.com/195539477/projects/2085958515"
      },
      "attachments": []
    },
    {
      "id": 1071915810,
      "created_at": "2026-02-06T22:44:52.980Z",
      "kind": "todo_created",
      "parent_recording_id": 1069480044,
      "url": "https://3.basecampapi.com/195539477/buckets/2085958514/todos/1069480047.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958514/todos/1069480047",
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
      "action": "Victor C. added a to-do",
      "target": "First things first",
      "title": "On “First things first”, Victor C. added",
      "summary_excerpt": "Install ShipShape",
      "avatars_sample": [],
      "bucket": {
        "id": 2085958514,
        "name": "New project from template",
        "url": "https://3.basecampapi.com/195539477/projects/2085958514.json",
        "app_url": "https://3.basecamp.com/195539477/projects/2085958514"
      },
      "attachments": []
    },
    {
      "id": 1071915809,
      "created_at": "2026-02-06T22:44:52.919Z",
      "kind": "todo_created",
      "parent_recording_id": 1069480044,
      "url": "https://3.basecampapi.com/195539477/buckets/2085958514/todos/1069480046.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958514/todos/1069480046",
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
      "action": "Victor C. added a to-do",
      "target": "First things first",
      "title": "On “First things first”, Victor C. added",
      "summary_excerpt": "Talk to Jerry about holidays",
      "avatars_sample": [],
      "bucket": {
        "id": 2085958514,
        "name": "New project from template",
        "url": "https://3.basecampapi.com/195539477/projects/2085958514.json",
        "app_url": "https://3.basecamp.com/195539477/projects/2085958514"
      },
      "attachments": []
    },
    {
      "id": 1071915808,
      "created_at": "2026-02-06T22:44:52.863Z",
      "kind": "todo_created",
      "parent_recording_id": 1069480044,
      "url": "https://3.basecampapi.com/195539477/buckets/2085958514/todos/1069480045.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958514/todos/1069480045",
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
      "action": "Victor C. added a to-do",
      "target": "First things first",
      "title": "On “First things first”, Victor C. added",
      "summary_excerpt": "Talk to Cheryl about benefits",
      "avatars_sample": [],
      "bucket": {
        "id": 2085958514,
        "name": "New project from template",
        "url": "https://3.basecampapi.com/195539477/projects/2085958514.json",
        "app_url": "https://3.basecamp.com/195539477/projects/2085958514"
      },
      "attachments": []
    }
  ]
}
```
<!-- END GET /reports/users/progress/1.json -->

###### Copy as cURL

```shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/reports/users/progress/1.json
```

Event kinds
-----------

The `kind` field indicates what type of activity occurred. Common values include:

| Kind | Description |
|------|-------------|
| `message_created` | A new message was posted |
| `comment_created` | A comment was added |
| `todo_created` | A new to-do was added |
| `todo_completed` | A to-do was checked off |
| `upload_created` | A file was uploaded |
| `document_created` | A document was created |
| `schedule_entry_created` | A calendar event was added |
| `schedule_entry_rescheduled` | A calendar event was rescheduled |
| `question_created` | An automatic check-in was started |
| `question_answer_created` | Someone answered a check-in |
| `chat_transcript_rollup` | A summary of Campfire chat activity |
| `kanban_card_created` | A card was added to a Card Table |
| `kanban_card_completed` | A card was completed |
| `inbox_forward_created` | An email was forwarded |
| `client_correspondence_created` | A message was sent to a client |

Event fields
------------

Each timeline event includes these fields:

| Field | Description |
|-------|-------------|
| `id` | Unique identifier for the event |
| `created_at` | When the event occurred |
| `kind` | The type of activity (see [Event kinds](#event-kinds)) |
| `parent_recording_id` | ID of the parent container (e.g., to-do list for a to-do), if applicable |
| `url` | API URL to fetch the item |
| `app_url` | Link to view the item in Basecamp |
| `creator` | The [person][person] who performed the action |
| `action` | Human-readable description of the action |
| `target` | The name of the parent container or item affected |
| `title` | Combined action and target as a complete sentence |
| `summary_excerpt` | A brief excerpt of the content, if available |
| `avatars_sample` | Array of avatar URLs (used for chat rollups showing participants) |
| `bucket` | The [project][project] where the event occurred |
| `data` | Additional event-specific data (e.g., schedule entry times) |
| `attachments` | Array of attached files, if any |

Schedule entry data
-------------------

Events with `kind` of `schedule_entry_created` or `schedule_entry_rescheduled` include a `data` object with schedule details:

```json
{
  "data": {
    "all_day": false,
    "starts_at": "2025-10-30T10:00:00.000-05:00",
    "ends_at": "2025-10-30T11:00:00.000-05:00"
  }
}
```

[pagination]: https://github.com/basecamp/bc3-api/blob/master/README.md#pagination
[person]: https://github.com/basecamp/bc3-api/blob/master/sections/people.md#people
[project]: https://github.com/basecamp/bc3-api/blob/master/sections/projects.md#projects
