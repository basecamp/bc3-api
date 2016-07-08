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
    "id": 1007299208,
    "name": "Victor Cooper",
    "email_address": "victor@honchodesign.com",
    "personable_type": "User",
    "title": null,
    "created_at": "2016-07-08T16:48:02.496Z",
    "updated_at": "2016-07-08T16:48:02.592Z",
    "admin": true,
    "owner": true,
    "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBIgqCjw=--719e3f2aa4406cf5806c2c1522259710deb788e4/avatar-64-x4",
    "company": {
      "id": 1033447822,
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

* `PUT /projects/1/people/users.json` allows granting new and existing people access to a Basecamp, and revoking access from existing people.

**Parameters**: Requests should include at least one of the following parameters.

* `grant` - an array of people IDs.
* `revoke` - an array of people IDs.
* `create` - an array of new people with `name` and `email_address` properties, and optional `title` and `company_name` properties.

###### Example JSON Request
<!-- START PUT PAYLOAD /projects/1/people/users.json -->
```json
{
  "grant": [
    1007299216
  ],
  "revoke": [
    1007299215
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

``` shell
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
      "id": 1007299216,
      "name": "Amy Rivera",
      "email_address": "amy@honchodesign.com",
      "personable_type": "User",
      "title": "Central Web Coordinator",
      "created_at": "2016-07-08T16:48:03.671Z",
      "updated_at": "2016-07-08T16:48:03.671Z",
      "admin": false,
      "owner": false,
      "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBJAqCjw=--8d75d03d706bcee8a1165d52f5ef9fdaaee5d0c9/avatar-64-x4"
    },
    {
      "id": 1007299238,
      "name": "Victor Copper",
      "email_address": "victor@hanchodesign.com",
      "personable_type": "User",
      "title": "Prankster",
      "created_at": "2016-07-08T16:50:31.360Z",
      "updated_at": "2016-07-08T16:50:31.482Z",
      "admin": false,
      "owner": false,
      "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBKYqCjw=--50cd369c3cc7f8c0c15174977d26f51925a7f268/avatar-64-x4",
      "company": {
        "id": 1033447824,
        "name": "Hancho Design"
      }
    }
  ],
  "revoked": [
    {
      "id": 1007299215,
      "name": "Steve Marsh",
      "email_address": "steve@honchodesign.com",
      "personable_type": "User",
      "title": "Legacy Directives Strategist",
      "created_at": "2016-07-08T16:48:03.518Z",
      "updated_at": "2016-07-08T16:48:03.518Z",
      "admin": false,
      "owner": false,
      "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBI8qCjw=--855220f904d26ccbc249233674ddb77b635aa8ba/avatar-64-x4",
      "company": {
        "id": 1033447822,
        "name": "Honcho Design"
      }
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
  "id": 1007299234,
  "name": "Zach Settles",
  "email_address": "zach@honchodesign.com",
  "personable_type": "User",
  "title": "Customer Paradigm Supervisor",
  "created_at": "2016-07-08T16:48:06.590Z",
  "updated_at": "2016-07-08T16:48:06.590Z",
  "admin": false,
  "owner": false,
  "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBKIqCjw=--9febe99a5684d0d37541b642ff3a5b6985cf229f/avatar-64-x4"
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
