People
======

Endpoints:

- [Get all people](#get-all-people)
- [Get people on a Basecamp](#get-people-on-a-basecamp)
- [Get pingable people](#get-pingable-people)
- [Get person](#get-person)
- [Get my personal info](#get-my-personal-info)

Get all people
--------------

* `GET /people.json` will return all people on this account visible to the current user. This includes clients and people who may have been removed from the account.

###### Example JSON Response

``` json
[
  {
    "id": 1007299144,
    "created_at": "2016-01-27T11:00:15.486-06:00",
    "updated_at": "2016-03-26T19:30:59.746-05:00",
    "name": "Victor Cooper",
    "email_address": "victor@honchodesign.com",
    "personable_type": "User",
    "title": null,
    "admin": true,
    "owner": true,
    "avatar_url": "https://3.basecamp-assets.com/195539477/people/BAhpBEgqCjw=--8266bb0507508f3d46050d57b65924d5e2a005f3/avatar-64-x4",
    "company": {
      "id": 1033447818,
      "name": "Honcho Design"
    }
  },
  ...
]
```

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

Get pingable people
-------------------

* `GET /circles/people.json` will return all people on this Basecamp account who can be pinged.

See the [Get all people](#get-all-people) endpoint for an example of the JSON response.

###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/circles/people.json
```


Get person
----------

* `GET /people/2.json` will return the profile for the user with the given ID.

###### Example JSON Response

``` json
{
  "id": 1007299173,
  "created_at": "2016-01-27T11:00:20.599-06:00",
  "updated_at": "2016-01-27T11:00:20.599-06:00",
  "name": "Beth Allen",
  "email_address": "beth@letobrand.com",
  "personable_type": "Client",
  "title": "Product Tactics Architect",
  "admin": false,
  "owner": false,
  "avatar_url": "https://3.basecamp-assets.com/195539477/people/BAhpBGUqCjw=--e158da2fcd75374f7ef3d0c31d2995276e098296/avatar-64-x4",
  "company": {
    "id": 1033447819,
    "name": "Leto Brand"
  }
}
```

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
