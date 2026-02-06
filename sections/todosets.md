To-do sets
==========

All to-do lists under a project are children of a to-do set resource.

Endpoints:

- [Get to-do set](#get-to-do-set)


Get to-do set
-------------

* `GET /buckets/1/todosets/2.json` will return the to-do set for the project with an ID of `1` and a to-do set ID of `2`.

To get the to-do set ID for a project, see the [Get a project][1] endpoint's `dock` payload. To retrieve its to-do lists, see the [Get to-do lists][2] endpoint.

###### Example JSON Response
<!-- START GET /buckets/1/todosets/2.json -->
```json
{
  "id": 1069479393,
  "status": "active",
  "visible_to_clients": false,
  "created_at": "2026-01-31T08:32:04.373Z",
  "updated_at": "2026-02-06T22:45:49.916Z",
  "title": "To-dos",
  "inherits_status": true,
  "type": "Todoset",
  "url": "https://3.basecampapi.com/195539477/buckets/2085958504/todosets/1069479393.json",
  "app_url": "https://3.basecamp.com/195539477/buckets/2085958504/todosets/1069479393",
  "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiLmdpZDovL2JjMy9SZWNvcmRpbmcvMTA2OTQ3OTM5Mz9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg1yZWFkYWJsZQY7AFQ=--99dc372e88c87df258903c62952b178106a4152e.json",
  "position": 2,
  "bucket": {
    "id": 2085958504,
    "name": "The Leto Laptop",
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
  "completed": false,
  "completed_ratio": "14/60",
  "name": "To-dos",
  "todolists_count": 10,
  "todolists": [
    {
      "id": 1069479573,
      "title": "Strategy ideas",
      "description": null,
      "completed": false,
      "completed_ratio": "2/5",
      "url": "https://3.basecampapi.com/195539477/buckets/2085958504/todolists/1069479573.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958504/todolists/1069479573"
    },
    {
      "id": 1069479511,
      "title": "Social stuff",
      "description": null,
      "completed": false,
      "completed_ratio": "8/17",
      "url": "https://3.basecampapi.com/195539477/buckets/2085958504/todolists/1069479511.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958504/todolists/1069479511"
    },
    {
      "id": 1069479496,
      "title": "Chowder",
      "description": null,
      "completed": false,
      "completed_ratio": "0/3",
      "url": "https://3.basecampapi.com/195539477/buckets/2085958504/todolists/1069479496.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958504/todolists/1069479496"
    },
    {
      "id": 1069479487,
      "title": "Android app",
      "description": null,
      "completed": false,
      "completed_ratio": "1/5",
      "url": "https://3.basecampapi.com/195539477/buckets/2085958504/todolists/1069479487.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958504/todolists/1069479487"
    },
    {
      "id": 1069479480,
      "title": "iOS app",
      "description": null,
      "completed": false,
      "completed_ratio": "1/6",
      "url": "https://3.basecampapi.com/195539477/buckets/2085958504/todolists/1069479480.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958504/todolists/1069479480"
    },
    {
      "id": 1069479475,
      "title": "Product page on company site",
      "description": null,
      "completed": false,
      "completed_ratio": "1/4",
      "url": "https://3.basecampapi.com/195539477/buckets/2085958504/todolists/1069479475.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958504/todolists/1069479475"
    },
    {
      "id": 1069479465,
      "title": "Landing page + Microsite",
      "description": null,
      "completed": false,
      "completed_ratio": "0/5",
      "url": "https://3.basecampapi.com/195539477/buckets/2085958504/todolists/1069479465.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958504/todolists/1069479465"
    },
    {
      "id": 1069479458,
      "title": "Promo video",
      "description": null,
      "completed": false,
      "completed_ratio": "1/6",
      "url": "https://3.basecampapi.com/195539477/buckets/2085958504/todolists/1069479458.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958504/todolists/1069479458"
    },
    {
      "id": 1069479436,
      "title": "Product shots",
      "description": null,
      "completed": false,
      "completed_ratio": "0/5",
      "url": "https://3.basecampapi.com/195539477/buckets/2085958504/todolists/1069479436.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958504/todolists/1069479436"
    },
    {
      "id": 1069479424,
      "title": "Background and research",
      "description": null,
      "completed": false,
      "completed_ratio": "0/4",
      "url": "https://3.basecampapi.com/195539477/buckets/2085958504/todolists/1069479424.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958504/todolists/1069479424"
    }
  ],
  "todolists_url": "https://3.basecampapi.com/195539477/buckets/2085958504/todosets/1069479393/todolists.json",
  "app_todoslists_url": "https://3.basecamp.com/195539477/buckets/2085958504/todosets/1069479393/todolists"
}
```
<!-- END GET /buckets/1/todosets/2.json -->
###### Copy as cURL

```shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/todosets/2.json
```


[1]: https://github.com/basecamp/bc3-api/blob/master/sections/projects.md#get-a-project
[2]: https://github.com/basecamp/bc3-api/blob/master/sections/todolists.md#get-to-do-lists
[3]: https://github.com/basecamp/bc3-api/blob/master/sections/recordings.md#trash-a-recording
