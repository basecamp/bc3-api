People
======

Endpoints:

- [Get all people](#get-all-people)
- [Get people on a Basecamp](#get-people-on-a-basecamp)
- [Update who can access a Basecamp](#update-who-can-access-a-basecamp)
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
    "id": 1007299143,
    "name": "Victor Cooper",
    "email_address": "victor@honchodesign.com",
    "personable_type": "User",
    "title": null,
    "created_at": "2016-06-22T16:37:56.840-05:00",
    "updated_at": "2016-06-22T16:38:02.871-05:00",
    "admin": true,
    "owner": true,
    "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBEcqCjw=--c632b967cec296b87363a697a67a87f9cc1e5b45/avatar-64-x4",
    "company": {
      "id": 1033447817,
      "name": "Honcho Design"
    }
  }
]
```
<!-- END GET /people.json -->
###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/people.json
```


Get people on a Basecamp
------------------------

* `GET /projects/1/people.json` will return all active people on the Basecamp with the given ID.

See the [Get all people](#get-all-people) endpoint for an example of the JSON response.

###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/projects/1/people.json
```

Update who can access a Basecamp
--------------------------------

* `PUT /buckets/1/people/users.json` allows granting new and existing people access to a Basecamp, and revoking access from existing people.

**Parameters**: Requests should include at least one of the following parameters.

* `grant` - an array of people IDs.
* `revoke` - an array of people IDs.
* `create` - an array of new people with `name` and `email_address` properties, and optional `title` and `company_name` properties.

###### Example JSON Request
<!-- START PUT PAYLOAD /buckets/1/people/users.json -->
```json
{
  "grant": [
    1007299151
  ],
  "revoke": [
    1007299150
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
<!-- END PUT PAYLOAD /buckets/1/people/users.json -->
###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -H "Content-Type: application/json" \
  -d '{"grant":[2],"revoke":[3,4]}' -X PUT \
  https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/people/users.json
```

###### Example JSON Response
<!-- START PUT /buckets/1/people/users.json -->
```json
{
  "granted": [
    {
      "id": 1007299151,
      "name": "Amy Rivera",
      "email_address": "amy@honchodesign.com",
      "personable_type": "User",
      "title": "Central Web Coordinator",
      "created_at": "2016-06-23T16:26:03.813-05:00",
      "updated_at": "2016-06-23T16:26:03.813-05:00",
      "admin": false,
      "owner": false,
      "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBE8qCjw=--44a343c4ec0f62daf82484ec3539efc8c74a336a/avatar-64-x4"
    },
    {
      "id": 1007299187,
      "name": "Victor Copper",
      "email_address": "victor@hanchodesign.com",
      "personable_type": "User",
      "title": "Prankster",
      "created_at": "2016-06-23T17:59:28.901-05:00",
      "updated_at": "2016-06-23T17:59:30.129-05:00",
      "admin": false,
      "owner": false,
      "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBHMqCjw=--ada9bcdfb67bedc03799c4a4cd0c1b621790a734/avatar-64-x4",
      "company": {
        "id": 1033447819,
        "name": "Hancho Design"
      }
    }
  ],
  "revoked": [
    {
      "id": 1007299150,
      "name": "Steve Marsh",
      "email_address": "steve@honchodesign.com",
      "personable_type": "User",
      "title": "Legacy Directives Strategist",
      "created_at": "2016-06-23T16:26:03.660-05:00",
      "updated_at": "2016-06-23T16:26:03.660-05:00",
      "admin": false,
      "owner": false,
      "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBE4qCjw=--b544b6a710bd76020abc076fc041895954025116/avatar-64-x4",
      "company": {
        "id": 1033447817,
        "name": "Honcho Design"
      }
    }
  ]
}
```
<!-- END PUT /buckets/1/people/users.json -->

Get pingable people
-------------------

* `GET /circles/people.json` will return all people on this Basecamp account who can be pinged.

See the [Get all people](#get-all-people) endpoint for an example of the JSON response.

**Note:** This endpoint is currently not paginated.

###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/circles/people.json
```


Get person
----------

* `GET /people/2.json` will return the profile for the user with the given ID.

###### Example JSON Response
<!-- START GET /people/2.json -->
```json
{
  "id": 1007299169,
  "name": "Zach Settles",
  "email_address": "zach@honchodesign.com",
  "personable_type": "User",
  "title": "Customer Paradigm Supervisor",
  "created_at": "2016-06-22T16:38:02.238-05:00",
  "updated_at": "2016-06-22T16:38:02.238-05:00",
  "admin": false,
  "owner": false,
  "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBGEqCjw=--f278ae7c0479355c2aa772cb3155e925954de561/avatar-64-x4"
}
```
<!-- END GET /people/2.json -->
###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/people/2.json
```


Get my personal info
--------------------

* `GET /my/profile.json` will return the current user's personal info.

See the [Get person](#get-person) endpoint for an example of the JSON response.

###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/my/profile.json
```
