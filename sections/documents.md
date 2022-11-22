Documents
=========

Endpoints:

- [Get documents](#get-documents)
- [Get a document](#get-a-document)
- [Create a document](#create-a-document)
- [Update a document](#update-a-document)
- [Trash a document][trash]

Get documents
-------------

* `GET /buckets/1/vaults/2/documents.json` will return a [paginated list][pagination] of active documents in the project with an ID of `1` and the [vault][vaults] with ID of `2`.

###### Example JSON Response
<!-- START GET /buckets/1/vaults/2/documents.json -->
```json
[
  {
    "id": 1069479093,
    "status": "active",
    "visible_to_clients": false,
    "created_at": "2022-10-11T09:08:24.930Z",
    "updated_at": "2022-11-22T08:24:37.813Z",
    "title": "New Hire Info, Benefits Summary, and Forms",
    "inherits_status": true,
    "type": "Document",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958497/documents/1069479093.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958497/documents/1069479093",
    "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7CEkiCGdpZAY6BkVUSSIuZ2lkOi8vYmMzL1JlY29yZGluZy8xMDY5NDc5MDkzP2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg1yZWFkYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--d5a19e835d576ed355c002664a8ea7a1567c362f.json",
    "subscription_url": "https://3.basecampapi.com/195539477/buckets/2085958497/recordings/1069479093/subscription.json",
    "comments_count": 1,
    "comments_url": "https://3.basecampapi.com/195539477/buckets/2085958497/recordings/1069479093/comments.json",
    "position": 1,
    "parent": {
      "id": 1069479098,
      "title": "HR Stuff",
      "type": "Vault",
      "url": "https://3.basecampapi.com/195539477/buckets/2085958497/vaults/1069479098.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958497/vaults/1069479098"
    },
    "bucket": {
      "id": 2085958497,
      "name": "Honcho Design Newsroom",
      "type": "Project"
    },
    "creator": {
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
    },
    "content": "<strong>Health Insurance</strong>\n  We have just one health insurance policy. The company pays most of the premium, and you cover the rest. Domestic partnerships are covered, as well as marriages. Open enrollment starts in January.<br><br>\n\n  <strong>401K Retirement Plan</strong>\n  We match dollar-for-dollar up to 10% of your salary that you contribute to the plan. You are eligible to enroll in the 401K plan after your first paycheck.<br><br>\n\n  <strong>Flexible Spending Account (FSA)</strong>\n  The FSA is an account where you can set aside pre-tax money for out-of-pocket medical expenses, such as prescriptions, OTC medicine, vision care, etc.  You have to decide up front how much money you want to put in the account, and the max is $2500/year.<br><br>\n\n  <strong>Continuing Education Allowance</strong>\n  We provide you with $500 a year to take classes that help you professionally. Really, anything that helps you with your job.<br><br>\n\n  <strong>Matching Charitable Gifts</strong>\n  When you donate money to a qualified charity, we will make a matching gift to that charity on your behalf. The maximum for the year is $500 per employee.<br><br>\n\n  <strong>Paid Time Off</strong>\n  Paid time off doesn't really exist here - if you need a day (or week!) off, you just need to clear it with your team or others who would be affected by your absence. You should try to take at least 3 weeks off a year."
  }
]
```
<!-- END GET /buckets/1/vaults/2/documents.json -->
###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/vaults/2/documents.json
```

Get a document
--------------

* `GET /buckets/1/documents/2.json` will return the document with an ID of `2` in the project with an ID of `1`.

###### Example JSON Response
<!-- START GET /buckets/1/documents/2.json -->
```json
{
  "id": 1069479844,
  "status": "active",
  "visible_to_clients": false,
  "created_at": "2022-11-22T08:24:27.213Z",
  "updated_at": "2022-11-22T08:24:27.213Z",
  "title": "Meetups - schedule/protocol",
  "inherits_status": true,
  "type": "Document",
  "url": "https://3.basecampapi.com/195539477/buckets/2085958503/documents/1069479844.json",
  "app_url": "https://3.basecamp.com/195539477/buckets/2085958503/documents/1069479844",
  "bookmark_url": "https://3.basecampapi.com/195539477/my/bookmarks/BAh7CEkiCGdpZAY6BkVUSSIuZ2lkOi8vYmMzL1JlY29yZGluZy8xMDY5NDc5ODQ0P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg1yZWFkYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--bbb92805fb8e8bebab7b6b1db2265355db1f7e9e.json",
  "subscription_url": "https://3.basecampapi.com/195539477/buckets/2085958503/recordings/1069479844/subscription.json",
  "comments_count": 0,
  "comments_url": "https://3.basecampapi.com/195539477/buckets/2085958503/recordings/1069479844/comments.json",
  "position": 2,
  "parent": {
    "id": 1069479695,
    "title": "Docs & Files",
    "type": "Vault",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958503/vaults/1069479695.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958503/vaults/1069479695"
  },
  "bucket": {
    "id": 2085958503,
    "name": "Customer Support",
    "type": "Project"
  },
  "creator": {
    "id": 1049715948,
    "attachable_sgid": "BAh7CEkiCGdpZAY6BkVUSSIrZ2lkOi8vYmMzL1BlcnNvbi8xMDQ5NzE1OTQ4P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg9hdHRhY2hhYmxlBjsAVEkiD2V4cGlyZXNfYXQGOwBUMA==--6c901c238dc342abb5415ee4d64309e44526e213",
    "name": "Melissa Vasquez",
    "email_address": "melissavasquez@example.com",
    "personable_type": "DummyUser",
    "title": null,
    "bio": null,
    "location": null,
    "created_at": "2022-11-22T08:24:24.573Z",
    "updated_at": "2022-11-22T08:24:24.573Z",
    "admin": false,
    "owner": false,
    "client": false,
    "employee": false,
    "time_zone": "Etc/UTC",
    "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBOxkkT4=--e059cc49b1e3717e79b4ea0f745254637f63b45d/avatar?v=1",
    "can_manage_projects": false,
    "can_manage_people": false
  },
  "content": "<h1>Support Team Scheduling - The Low Down</h1><br>\n        Everyone generally works one, four hour shift per day. There are a few different shifts in a day, and they all work together in a way that allows for shifts to be balanced and offer enough coverage.<br><br>\n        <h1>Meetup Scheduling Example</h1><br>\n        <strong>Morning shifts:</strong><br>\n        7am - 11am: (2 people)<br>\n        8am -12pm: (4 people)<br><br>\n        <strong>Midday shift:</strong><br>\n        10am - 2pm (3 people)<br><br>\n        <strong>Afternoon shifts:</strong><br>\n        12 pm - 4pm: (3 people)<br>\n        1pm - 5pm: (2 people)<br><br>\n        <h1>Preparation for the Meetup</h1><br>\n        <strong>Friday before meetup:</strong><br>\n        Ask Matt to set up announcement on the Support page letting users know we are answering emails M-F 7am - 5pm CST due to a company meetup.<br><br>\n        <strong>Monday - Friday of the meetup:</strong><br>\n        Shifts will look like the example above, with an afternoon off to have a support outing.<br><br>\n        <strong>Sunday after:</strong><br>\n        Coverage by US support team member (take following Friday off)<br><br>\n        <strong>Monday after:</strong><br>\n        Those travelling to the other side of the world have the day off<br>\n        recruit 2-3 people from the company to help with cases<br><br>\n        <h1>FAQs</h1><br>\n        <strong>When will we know the schedule?</strong><br>\n        Exact schedules for meetups will be shared at least 2-3 weeks before the meetup<br><br>\n        <strong>Where will the schedule be posted?</strong><br>\n        In the schedule section of the Support Team project.<br><br>\n        <strong>What if I'm unhappy with my shifts?</strong><br>\n        You can swap out shifts if needed - swapping will be done between people who want to swap. Let Kurt know your changes so he can update that in the schedule.<br><br>\n        <strong>What are the expectations for the meetup as a member of Support?</strong>\n        The overall expectation is to work when you are scheduled - for a few focused hours per day. After those hours are done, you are free to mingle with the Basecamp crew! Everyone is on call Monday to help with cases as it's usually the busiest day of the week with talks, events and a backlog of cases.<br><br>\n        The most important expectation is to have fun, get to know more of your non support teammates if you are so inclined and have time to relax off cases.<br><br>\n        <strong>When you are working:</strong><br>\n        When there’s a talk going on by Liza/Matthew or something else, feel free to stop working until the talk is over and then swarm the cases when it is through.<br><br>\n        <strong>When you are not scheduled for cases (excluding Mondays):</strong><br>\n        On your time not scheduled for cases, feel free to mingle and get to know your company teammates! Go get coffee with a teammate, play games, talk one on one at the office. If you need clarification regarding this, ask <bc-attachment sgid=\"BAh7CEkiCGdpZAY6BkVUSSIrZ2lkOi8vYmMzL1BlcnNvbi8xMDQ5NzE1OTQ4P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg9hdHRhY2hhYmxlBjsAVEkiD2V4cGlyZXNfYXQGOwBUMA==--6c901c238dc342abb5415ee4d64309e44526e213\" content-type=\"application/vnd.basecamp.mention\"><figure>\n  <img data-avatar-for-person-id=\"1049715948\" alt=\"Melissa Vasquez\" title=\"Melissa Vasquez\" class=\"avatar\" src=\"https://3.basecamp-static.com/195539477/people/BAhpBOxkkT4=--e059cc49b1e3717e79b4ea0f745254637f63b45d/avatar?v=1\" width=\"20\" height=\"20\">\n  <figcaption>\n    Melissa\n  </figcaption>\n</figure></bc-attachment>!<br><br>\n        <strong>Swarming and being on call on Mondays:</strong>\n        On Mondays, more people might be needed to clear the case queue throughout the day. In that case, everyone is considered on call on Mondays and someone will ask everyone in Campfire to come onto cases to swarm them. This will typically only happen after talks done by Jason and David. Let's work together to get those cases clear!<br><br>\n        <strong>Phones</strong> - They will be OFF<br>\n        <strong>Twitter</strong> - Will be scheduled<br>\n        <strong>Meals</strong> - If you are scheduled to be on cases during a meal, feel free to take a break to eat and swarm the cases after you are done eating. Staggering meals might also work, but it's up to you!<br>\n        <strong>Talks</strong> - If you are scheduled to be on cases during a talk, feel free to listen and swarm the cases after the talk is over.<br>\n        <strong>Extra Events</strong> - There are events during the day and after work - feel free to join them if you are not scheduled for cases - see if someone will switch shifts with you if you are scheduled and you want to go to an event. They will usually be scheduled into the support schedule already."
}
```
<!-- END GET /buckets/1/documents/2.json -->

###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/documents/2.json
```

Create a document
-----------------

* `POST /buckets/1/vaults/2/documents.json` publishes a document in the project with ID `1` and under the vault with an ID of `2`.

**Required parameters**: `title` as the title of the document, and `content` as the body of the document. See our [Rich text guide][rich] for what HTML tags are allowed.

_Optional parameters_: . `status`, set to `active` to publish immediately.

This endpoint will return `201 Created` with the current JSON representation of the document if the creation was a success. See the [Get a document](#get-a-document) endpoint for more info on the payload.

###### Example JSON Request

``` json
{
  "title": "New Hire Info",
  "content": "<div><strong>Getting started</strong></div>",
  "status": "active"
}
```

###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -H "Content-Type: application/json" \
  -d '{"title":"New Hire Info","content":"<div><strong>Getting started</strong></div>","status":"active"}' \
  https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/vaults/2/documents.json
```

Update a document
-----------------

* `PUT /buckets/1/documents/2.json` allows changing the title and content of the document with an ID of `2` in the project with ID `1`.

This endpoint will return `200 OK` with the current JSON representation of the document if the update was a success. See the [Get a document](#get-a-document) endpoint for more info on the payload.

###### Example JSON Request

``` json
{
  "title": "New Hire Information",
  "content": "<div><strong>Let's get started</strong></div>"
}
```

###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -H "Content-Type: application/json" \
  -d '{"title":"New Hire Information","content":"<div><strong>Let's get started</strong></div>"}' -X PUT \
  https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/documents/2.json
```

[pagination]: https://github.com/basecamp/bc3-api/blob/master/README.md#pagination
[trash]: https://github.com/basecamp/bc3-api/blob/master/sections/recordings.md#trash-a-recording
[vaults]: https://github.com/basecamp/bc3-api/blob/master/sections/vaults.md#vaults
[rich]: https://github.com/basecamp/bc3-api/blob/master/sections/rich_text.md
