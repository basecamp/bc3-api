Subscriptions
=============

Many of the resources in Basecamp 4 that can be commented on have _subscribers_, that is, people that will get notified when a new comment is added. To know if it's possible to modify the subscriptions for a recording, check its JSON response for the `subscription_url` attribute. This attribute contains the URL to hit to get information about current subscribers and to add/remove subscribers.

Endpoints:

- [Get subscription](#get-subscription)
- [Subscribe current user](#subscribe-current-user)
- [Unsubscribe current user](#unsubscribe-current-user)
- [Update subscription](#update-subscription)


Get subscription
----------------

* `GET /buckets/1/recordings/2/subscription.json` will return subscription information for a recording with an ID of `2` in the bucket with ID `1`.

###### Example JSON Response
<!-- START GET /buckets/1/recordings/2/subscription.json -->
```json
{
  "subscribed": true,
  "count": 2,
  "url": "https://3.basecampapi.com/195539477/buckets/2085958499/recordings/1069479351/subscription.json",
  "subscribers": [
    {
      "id": 1049715914,
      "attachable_sgid": "BAh7CEkiCGdpZAY6BkVUSSIrZ2lkOi8vYmMzL1BlcnNvbi8xMDQ5NzE1OTE0P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg9hdHRhY2hhYmxlBjsAVEkiD2V4cGlyZXNfYXQGOwBUMA==--ff006accb6e013cca785190fa38f42c091d24f1e",
      "name": "Victor Cooper",
      "email_address": "victor@honchodesign.com",
      "personable_type": "User",
      "title": "Chief Strategist",
      "bio": "Don’t let your dreams be dreams",
      "location": "Chicago, IL",
      "created_at": "2022-11-22T08:23:21.732Z",
      "updated_at": "2022-11-22T08:23:21.904Z",
      "admin": true,
      "owner": true,
      "client": false,
      "employee": true,
      "time_zone": "America/Chicago",
      "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBMpkkT4=--5520caeec1845b5090bbfc993ffe8eca8d138e14/avatar?v=1",
      "company": {
        "id": 1033447817,
        "name": "Honcho Design"
      },
      "can_manage_projects": true,
      "can_manage_people": true
    },
    {
      "id": 1049715915,
      "attachable_sgid": "BAh7CEkiCGdpZAY6BkVUSSIrZ2lkOi8vYmMzL1BlcnNvbi8xMDQ5NzE1OTE1P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg9hdHRhY2hhYmxlBjsAVEkiD2V4cGlyZXNfYXQGOwBUMA==--aeb392ebf54ffd820e45f27add22bae3a8c7da56",
      "name": "Annie Bryan",
      "email_address": "annie@honchodesign.com",
      "personable_type": "User",
      "title": "Central Markets Manager",
      "bio": "To open a store is easy, to keep it open is an art",
      "location": null,
      "created_at": "2022-11-22T08:23:21.911Z",
      "updated_at": "2022-11-22T08:23:21.911Z",
      "admin": false,
      "owner": false,
      "client": false,
      "employee": true,
      "time_zone": "America/Chicago",
      "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBMtkkT4=--9927c47a4cbee30a7f9aea667882496aba799149/avatar?v=1",
      "company": {
        "id": 1033447817,
        "name": "Honcho Design"
      },
      "can_manage_projects": true,
      "can_manage_people": true
    }
  ]
}
```
<!-- END GET /buckets/1/recordings/2/subscription.json -->

###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/recordings/2/subscription.json
```

Subscribe current user
----------------------

* `POST /buckets/1/recordings/2/subscription.json` will subscribe the current user to the recording with an ID of `2` in the bucket with ID `1`. It returns `200 OK` with the current JSON representation of the recording subscriptions if the creation was a success. See the [Get subscription](#get-subscription) endpoint for an example of such response. 

###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -H "Content-Type: application/json" -X POST \
  https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/recordings/2/subscription.json
```

Unsubscribe current user
-----------------------

* `DELETE /buckets/1/recordings/2/subscription.json` will unsubscribe the current user from the recording with an ID of `2` in the bucket with ID `1`. It returns `204 No Content` in any case, even if the current user wasn't previously subscribed.

###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -H "Content-Type: application/json" -X DELETE \
  https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/recordings/2/subscription.json
```

Update subscription
-------------------

* `PUT /buckets/1/recordings/2/subscription.json` will add and remove the people given from the list of subscribers for the recording with an ID of `2` in the bucket with ID `1`. It returns `200 OK` with the current JSON representation of the recording subscriptions if the creation was a success.

**Parameters**: Requests should include at least one of the following parameters.

* `subscriptions` - an array of people IDs.
* `unsubscriptions` - an array of people IDs.

###### Example JSON Request
<!-- START PUT PAYLOAD /buckets/1/recordings/2/subscription.json -->
```json
{
  "subscriptions": [
    1049715916
  ],
  "unsubscriptions": [
    1049715914
  ]
}
```
<!-- END PUT PAYLOAD /buckets/1/recordings/2/subscription.json -->


###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -H "Content-Type: application/json" \
  -d '{"subscriptions":[1049715916], "unsubscriptions":[1049715914]}' -X PUT \
  https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/recordings/2/subscription.json
```

###### Example JSON Response
<!-- START PUT /buckets/1/recordings/2/subscription.json -->
```json
{
  "subscribed": false,
  "count": 2,
  "url": "https://3.basecampapi.com/195539477/buckets/2085958499/recordings/1069479351/subscription.json",
  "subscribers": [
    {
      "id": 1049715915,
      "attachable_sgid": "BAh7CEkiCGdpZAY6BkVUSSIrZ2lkOi8vYmMzL1BlcnNvbi8xMDQ5NzE1OTE1P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg9hdHRhY2hhYmxlBjsAVEkiD2V4cGlyZXNfYXQGOwBUMA==--aeb392ebf54ffd820e45f27add22bae3a8c7da56",
      "name": "Annie Bryan",
      "email_address": "annie@honchodesign.com",
      "personable_type": "User",
      "title": "Central Markets Manager",
      "bio": "To open a store is easy, to keep it open is an art",
      "location": null,
      "created_at": "2022-11-22T08:23:21.911Z",
      "updated_at": "2022-11-22T08:23:21.911Z",
      "admin": false,
      "owner": false,
      "client": false,
      "employee": true,
      "time_zone": "America/Chicago",
      "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBMtkkT4=--9927c47a4cbee30a7f9aea667882496aba799149/avatar?v=1",
      "company": {
        "id": 1033447817,
        "name": "Honcho Design"
      },
      "can_manage_projects": true,
      "can_manage_people": true
    },
    {
      "id": 1049715916,
      "attachable_sgid": "BAh7CEkiCGdpZAY6BkVUSSIrZ2lkOi8vYmMzL1BlcnNvbi8xMDQ5NzE1OTE2P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg9hdHRhY2hhYmxlBjsAVEkiD2V4cGlyZXNfYXQGOwBUMA==--c94599eef0a4237fbaa56ff2648f57f1dae89ffd",
      "name": "Cheryl Walters",
      "email_address": "cheryl@honchodesign.com",
      "personable_type": "User",
      "title": "Corporate Integration Director",
      "bio": "A joke is a very serious thing",
      "location": null,
      "created_at": "2022-11-22T08:23:21.926Z",
      "updated_at": "2022-11-22T08:23:21.926Z",
      "admin": false,
      "owner": false,
      "client": false,
      "employee": true,
      "time_zone": "Etc/UTC",
      "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBMxkkT4=--0ea74d7e5d39ad2d120da79250b179b7e0b00c44/avatar?v=1",
      "company": {
        "id": 1033447817,
        "name": "Honcho Design"
      },
      "can_manage_projects": true,
      "can_manage_people": true
    }
  ]
}
```
<!-- END PUT /buckets/1/recordings/2/subscription.json -->
