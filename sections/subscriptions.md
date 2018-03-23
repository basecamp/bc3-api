Subscriptions
=============

Many of the resources in Basecamp 3 that can be commented on have _subscribers_, that is, people that will get notified when a new comment is added. To know if it's possible to modify the subscriptions for a recording, check its JSON response for the `subscription_url` attribute. This attribute contains the URL to hit to get information about current subscribers and to add/remove subscribers.

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
  "url": "https://3.basecampapi.com/195539477/buckets/2085958499/recordings/1064091058/subscription.json",
  "subscribers": [
    {
      "id": 1049715914,
      "attachable_sgid": "BAh7CEkiCGdpZAY6BkVUSSIrZ2lkOi8vYmMzL1BlcnNvbi8xMDQ5NzE1OTE0P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg9hdHRhY2hhYmxlBjsAVEkiD2V4cGlyZXNfYXQGOwBUMA==--52002cef7927fecc7f43df1d475f207f3640756a",
      "name": "Victor Cooper",
      "email_address": "victor@honchodesign.com",
      "personable_type": "User",
      "title": "Chief Strategist",
      "bio": "Don't let your dreams be dreams",
      "created_at": "2018-03-21T21:04:06.148Z",
      "updated_at": "2018-03-21T21:08:44.536Z",
      "admin": true,
      "owner": true,
      "time_zone": "America/Chicago",
      "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBMpkkT4=--86eedd88a242694f40fc5d74fd928eef41fcc219/avatar-64-x4?v=1",
      "company": {
        "id": 1033447817,
        "name": "Honcho Design"
      }
    },
    {
      "id": 1049715915,
      "attachable_sgid": "BAh7CEkiCGdpZAY6BkVUSSIrZ2lkOi8vYmMzL1BlcnNvbi8xMDQ5NzE1OTE1P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg9hdHRhY2hhYmxlBjsAVEkiD2V4cGlyZXNfYXQGOwBUMA==--5f103c46d4f123f0068fcd0192a0f7fea7f26193",
      "name": "Annie Bryan",
      "email_address": "annie@honchodesign.com",
      "personable_type": "User",
      "title": "Central Markets Manager",
      "bio": "To open a store is easy, to keep it open is an art",
      "created_at": "2018-03-21T21:04:07.465Z",
      "updated_at": "2018-03-21T21:04:07.465Z",
      "admin": false,
      "owner": false,
      "time_zone": "America/Chicago",
      "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBMtkkT4=--e609ef146e39f9ca5e4bb7242fdfd50aec4c3b3f/avatar-64-x4?v=1",
      "company": {
        "id": 1033447817,
        "name": "Honcho Design"
      }
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
  "url": "https://3.basecampapi.com/195539477/buckets/2085958499/recordings/1064091058/subscription.json",
  "subscribers": [
    {
      "id": 1049715915,
      "attachable_sgid": "BAh7CEkiCGdpZAY6BkVUSSIrZ2lkOi8vYmMzL1BlcnNvbi8xMDQ5NzE1OTE1P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg9hdHRhY2hhYmxlBjsAVEkiD2V4cGlyZXNfYXQGOwBUMA==--5f103c46d4f123f0068fcd0192a0f7fea7f26193",
      "name": "Annie Bryan",
      "email_address": "annie@honchodesign.com",
      "personable_type": "User",
      "title": "Central Markets Manager",
      "bio": "To open a store is easy, to keep it open is an art",
      "created_at": "2018-03-21T21:04:07.465Z",
      "updated_at": "2018-03-21T21:04:07.465Z",
      "admin": false,
      "owner": false,
      "time_zone": "America/Chicago",
      "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBMtkkT4=--e609ef146e39f9ca5e4bb7242fdfd50aec4c3b3f/avatar-64-x4?v=1",
      "company": {
        "id": 1033447817,
        "name": "Honcho Design"
      }
    },
    {
      "id": 1049715916,
      "attachable_sgid": "BAh7CEkiCGdpZAY6BkVUSSIrZ2lkOi8vYmMzL1BlcnNvbi8xMDQ5NzE1OTE2P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg9hdHRhY2hhYmxlBjsAVEkiD2V4cGlyZXNfYXQGOwBUMA==--4651a2fd15434417a2748b8d6b730d66ef8792a1",
      "name": "Cheryl Walters",
      "email_address": "cheryl@honchodesign.com",
      "personable_type": "User",
      "title": "Corporate Integration Director",
      "bio": "A joke is a very serious thing",
      "created_at": "2018-03-21T21:04:07.640Z",
      "updated_at": "2018-03-21T21:04:07.640Z",
      "admin": false,
      "owner": false,
      "time_zone": "America/Chicago",
      "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBMxkkT4=--7ebb5e400f6fd6bd650f725cc17f4ede6ac1b0ac/avatar-64-x4?v=1",
      "company": {
        "id": 1033447817,
        "name": "Honcho Design"
      }
    }
  ]
}
```
<!-- END PUT /buckets/1/recordings/2/subscription.json -->
