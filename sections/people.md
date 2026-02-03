People
======

Endpoints:

- [Get all people](#get-all-people)
- [Get people on a project](#get-people-on-a-project)
- [Update who can access a project](#update-who-can-access-a-project)
- [Get pingable people](#get-pingable-people)
- [Get person](#get-person)
- [Get my personal info](#get-my-personal-info)

Get all people
--------------

* `GET /people.json` will return all people visible to the current user.

###### Example JSON Response
<!-- START GET /people.json -->
```json
[
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
]
```
<!-- END GET /people.json -->
###### Copy as cURL

```shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/people.json
```


Get people on a project
------------------------

* `GET /projects/1/people.json` will return all active people on the project with the given ID.

See the [Get all people](#get-all-people) endpoint for an example of the JSON response.

###### Copy as cURL

```shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/projects/1/people.json
```

Update who can access a project
--------------------------------

* `PUT /projects/1/people/users.json` allows granting new and existing people access to a project, and revoking access from existing people.

**Parameters**: Requests should include at least one of the following parameters.

* `grant` - an array of people IDs.
* `revoke` - an array of people IDs.
* `create` - an array of new people with `name` and `email_address` properties, and optional `title` and `company_name` properties.

###### Example JSON Request
<!-- START PUT PAYLOAD /projects/1/people/users.json -->
```json
{
  "grant": [
    1049715915
  ],
  "revoke": [
    1049715944
  ],
  "create": [
    {
      "name": "Victor Copper",
      "email_address": "victor@hanchodesign.com",
      "title": "Prankster",
      "company_name": "Hancho Design"
    }
  ]
}
```
<!-- END PUT PAYLOAD /projects/1/people/users.json -->
###### Copy as cURL

```shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -H "Content-Type: application/json" \
  -d '{"grant":[2],"revoke":[3,4]}' -X PUT \
  https://3.basecampapi.com/$ACCOUNT_ID/projects/1/people/users.json
```

###### Example JSON Response
<!-- START PUT /projects/1/people/users.json -->
```json
{
  "granted": [
    {
      "id": 1049715915,
      "attachable_sgid": "BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiK2dpZDovL2JjMy9QZXJzb24vMTA0OTcxNTkxNT9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg9hdHRhY2hhYmxlBjsAVA==--56bb1f99675fd8fe08f93a706a5d2ddaa8412625",
      "name": "Amy Rivera",
      "email_address": "amy@honchodesign.com",
      "personable_type": "User",
      "title": "Central Web Coordinator",
      "bio": "I never said most of the things I said",
      "location": null,
      "created_at": "2026-01-31T08:29:32.987Z",
      "updated_at": "2026-01-31T08:29:32.987Z",
      "admin": false,
      "owner": false,
      "client": false,
      "employee": false,
      "time_zone": "America/Chicago",
      "avatar_url": "https://3.basecampapi.com/195539477/people/BAhpBMtkkT4=--9927c47a4cbee30a7f9aea667882496aba799149/avatar?v=1",
      "can_ping": true,
      "can_manage_projects": true,
      "can_manage_people": true,
      "can_access_timesheet": true,
      "can_access_hill_charts": true
    },
    {
      "id": 1049715955,
      "attachable_sgid": "BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiK2dpZDovL2JjMy9QZXJzb24vMTA0OTcxNTk1NT9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg9hdHRhY2hhYmxlBjsAVA==--6a8affd82c540e7c1f7e846b2b02fedb01bcd3f0",
      "name": "Victor Copper",
      "email_address": "victor@hanchodesign.com",
      "personable_type": "User",
      "title": "Prankster",
      "bio": null,
      "location": null,
      "created_at": "2026-02-01T02:53:35.423Z",
      "updated_at": "2026-02-01T02:53:35.423Z",
      "admin": false,
      "owner": false,
      "client": false,
      "employee": false,
      "time_zone": "America/Chicago",
      "avatar_url": "https://3.basecampapi.com/195539477/people/BAhpBPNkkT4=--5049939da9ea89df60ade5a1c42d324c1651c66c/avatar?v=1",
      "company": {
        "id": 1033447819,
        "name": "Hancho Design"
      },
      "can_ping": true,
      "can_manage_projects": true,
      "can_manage_people": true,
      "can_access_timesheet": true,
      "can_access_hill_charts": true
    }
  ],
  "revoked": [
    {
      "id": 1049715944,
      "attachable_sgid": "BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiK2dpZDovL2JjMy9QZXJzb24vMTA0OTcxNTk0ND9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg9hdHRhY2hhYmxlBjsAVA==--5c49e7f857f7a2aea319ae399f8b00eb63123ef9",
      "name": "Steve Marsh",
      "email_address": "steve@honchodesign.com",
      "personable_type": "User",
      "title": "Legacy Directives Strategist",
      "bio": "You can do it!",
      "location": null,
      "created_at": "2026-01-31T08:29:46.012Z",
      "updated_at": "2026-01-31T08:29:46.012Z",
      "admin": false,
      "owner": false,
      "client": false,
      "employee": true,
      "time_zone": "America/Chicago",
      "avatar_url": "https://3.basecampapi.com/195539477/people/BAhpBOhkkT4=--b169e35b345bcc26eca6964b7ef7de2c16b6f238/avatar?v=1",
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
  ]
}
```
<!-- END PUT /projects/1/people/users.json -->

Get pingable people
-------------------

* `GET /circles/people.json` will return all people on this Basecamp account who can be pinged.

See the [Get all people](#get-all-people) endpoint for an example of the JSON response.

**Note:** This endpoint is currently not paginated.

###### Copy as cURL

```shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/circles/people.json
```


Get person
----------

* `GET /people/2.json` will return the profile for the user with the given ID.

###### Example JSON Response
<!-- START GET /people/2.json -->
```json
{
  "id": 1049715928,
  "attachable_sgid": "BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiK2dpZDovL2JjMy9QZXJzb24vMTA0OTcxNTkyOD9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg9hdHRhY2hhYmxlBjsAVA==--35b1370e6239e9a565c0e8f66bed307c7cc488b6",
  "name": "Mark Campbell",
  "email_address": "mark@honchodesign.com",
  "personable_type": "User",
  "title": "Principal Markets Supervisor",
  "bio": null,
  "location": null,
  "created_at": "2026-01-31T08:29:39.861Z",
  "updated_at": "2026-01-31T08:29:39.861Z",
  "admin": false,
  "owner": false,
  "client": false,
  "employee": false,
  "time_zone": "America/Chicago",
  "avatar_url": "https://3.basecampapi.com/195539477/people/BAhpBNhkkT4=--cef810620a2f44a2144ab788d90679e478ea2344/avatar?v=1",
  "can_ping": true,
  "can_manage_projects": true,
  "can_manage_people": true,
  "can_access_timesheet": true,
  "can_access_hill_charts": true
}
```
<!-- END GET /people/2.json -->
###### Copy as cURL

```shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/people/2.json
```


Get my personal info
--------------------

* `GET /my/profile.json` will return the current user's personal info.

See the [Get person](#get-person) endpoint for an example of the JSON response.

###### Copy as cURL

```shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/my/profile.json
```
