Boosts
======

To determine if a resource can be boosted, check for the presence of `boosts_count` and `boosts_url` attributes in its JSON response.

Boosts can be applied to recordings and to specific [events][events] on a recording. Boostable events are those with an action of `completed`, `adopted`, or `column_changed`. When an event is boostable, its JSON response will include `boosts_count` and `boosts_url` attributes.

Endpoints:

- [Get boosts](#get-boosts)
- [Get a boost](#get-a-boost)
- [Create a boost](#create-a-boost)
- [Destroy a boost](#destroy-a-boost)

Get boosts
----------

* `GET /buckets/1/recordings/2/boosts.json` will return a [paginated list][pagination] of active boosts in the project with an ID of `1` and the recording with ID of `2`.
* `GET /buckets/1/recordings/2/events/3/boosts.json` will return a [paginated list][pagination] of active boosts on the event with ID of `3` on the recording with ID of `2` in the project with an ID of `1`.

###### Example JSON Response
<!-- START GET /buckets/1/recordings/2/boosts.json -->
```json
[
  {
    "id": 971636438,
    "content": "Yay!",
    "created_at": "2026-01-31T08:32:05.950Z",
    "booster": {
      "id": 1049715916,
      "attachable_sgid": "BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiK2dpZDovL2JjMy9QZXJzb24vMTA0OTcxNTkxNj9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg9hdHRhY2hhYmxlBjsAVA==--6414c77c0a206bc7d45987b8335318b768e8651f",
      "name": "Andrew Wong",
      "email_address": "andrew@honchodesign.com",
      "personable_type": "User",
      "title": "Senior Branding Strategist",
      "bio": null,
      "location": null,
      "created_at": "2026-01-31T08:29:33.483Z",
      "updated_at": "2026-01-31T08:29:33.483Z",
      "admin": false,
      "owner": false,
      "client": false,
      "employee": false,
      "time_zone": "America/Chicago",
      "avatar_url": "https://3.basecampapi.com/195539477/people/BAhpBMxkkT4=--0ea74d7e5d39ad2d120da79250b179b7e0b00c44/avatar?v=1",
      "can_ping": true,
      "can_manage_projects": true,
      "can_manage_people": true,
      "can_access_timesheet": true,
      "can_access_hill_charts": true
    }
  }
]
```
<!-- END GET /buckets/1/recordings/2/boosts.json -->
###### Copy as cURL

```shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/recordings/2/boosts.json
```


Get a boost
-----------

* `GET /buckets/1/boosts/2.json` will return the boost with an ID of `2` in the project with an ID of `1`.

###### Example JSON Response
<!-- START GET /buckets/1/boosts/2.json -->
```json
{
  "id": 971636442,
  "content": "Congrats!",
  "created_at": "2026-01-31T08:32:06.277Z",
  "booster": {
    "id": 1049715923,
    "attachable_sgid": "BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiK2dpZDovL2JjMy9QZXJzb24vMTA0OTcxNTkyMz9leHBpcmVzX2luBjsAVEkiCHB1cgY7AFRJIg9hdHRhY2hhYmxlBjsAVA==--cd47d2c8e0331392dba60ca41aec78611b6f2f2e",
    "name": "Jerry Gibson",
    "email_address": "jerry@honchodesign.com",
    "personable_type": "User",
    "title": "Principal Configuration Planner",
    "bio": null,
    "location": null,
    "created_at": "2026-01-31T08:29:37.254Z",
    "updated_at": "2026-01-31T08:29:37.254Z",
    "admin": false,
    "owner": false,
    "client": false,
    "employee": false,
    "time_zone": "America/Chicago",
    "avatar_url": "https://3.basecampapi.com/195539477/people/BAhpBNNkkT4=--e3c2676dde30e7c13f87642e3a3dd46ad657f731/avatar?v=1",
    "can_ping": true,
    "can_manage_projects": true,
    "can_manage_people": true,
    "can_access_timesheet": true,
    "can_access_hill_charts": true
  },
  "recording": {
    "id": 1069479406,
    "title": "We won Leto!",
    "type": "Message",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958504/messages/1069479406.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958504/messages/1069479406"
  }
}
```
<!-- END GET /buckets/1/boosts/2.json -->
###### Copy as cURL

```shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/boosts/2.json
```


Create a boost
--------------

* `POST /buckets/1/recordings/2/boosts.json` publishes a boost in the project with ID `1` and under the recording with an ID of `2`.
* `POST /buckets/1/recordings/2/events/3/boosts.json` publishes a boost on the event with ID `3` on the recording with ID of `2` in the project with ID `1`. Only boostable events (`completed`, `adopted`, `column_changed`) accept boosts; other events will return `403 Forbidden`.

**Required parameters**: `content` as the body of the boost.

This endpoint will return `201 Created` with the current JSON representation of the boost if the creation was a success. See the [Get a boost](#get-a-boost) endpoint for more info on the payload.

###### Example JSON Request

```json
{
  "content": "Great work!"
}
```

###### Copy as cURL

```shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -H "Content-Type: application/json" \
  -d '{"content":"Great work!"}' \
  https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/recordings/2/boosts.json
```


Destroy a boost
---------------

* `DELETE /buckets/1/boosts/2.json` will destroy the boost with an ID of `2` in the project with an ID of `1`.

Only the boost's creator or an admin can destroy a boost. Returns `204 No Content` on success, or `403 Forbidden` if the authenticated user does not have permission.

###### Copy as cURL

```shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -X DELETE \
  https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/boosts/2.json
```


[events]: https://github.com/basecamp/bc3-api/blob/master/sections/events.md#events
[pagination]: https://github.com/basecamp/bc3-api/blob/master/README.md#pagination
