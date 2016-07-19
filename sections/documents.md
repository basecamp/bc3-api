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

* `GET /buckets/1/vaults/2/documents.json` will return a [paginated list][pagination] of active documents in the Basecamp with an ID of `1` and the [vault][vaults] with ID of `2`.

###### Example JSON Response
<!-- START GET /buckets/1/vaults/2/documents.json -->
```json
[
  {
    "id": 9007199254741197,
    "status": "active",
    "created_at": "2016-06-08T18:41:41.933Z",
    "updated_at": "2016-07-19T16:47:00.592Z",
    "type": "Document",
    "url": "https://3.basecampapi.com/195539477/buckets/2085958496/documents/9007199254741197.json",
    "app_url": "https://3.basecamp.com/195539477/buckets/2085958496/documents/9007199254741197",
    "comments_count": 1,
    "comments_url": "https://3.basecampapi.com/195539477/buckets/2085958496/recordings/9007199254741197/comments.json",
    "parent": {
      "id": 9007199254741202,
      "title": "HR Stuff",
      "type": "Vault",
      "url": "https://3.basecampapi.com/195539477/buckets/2085958496/vaults/9007199254741202.json",
      "app_url": "https://3.basecamp.com/195539477/buckets/2085958496/vaults/9007199254741202"
    },
    "bucket": {
      "id": 2085958496,
      "name": "Honcho Design Newsroom",
      "type": "Project"
    },
    "creator": {
      "id": 1007299145,
      "attachable_sgid": "BAh7CEkiCGdpZAY6BkVUSSIrZ2lkOi8vYmMzL1BlcnNvbi8xMDA3Mjk5MTQ1P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg9hdHRhY2hhYmxlBjsAVEkiD2V4cGlyZXNfYXQGOwBUMA==--eabe63d5a75258e7be2ade823aa884b7fde00ab2",
      "name": "Cheryl Walters",
      "email_address": "cheryl@honchodesign.com",
      "personable_type": "User",
      "title": "Corporate Integration Director",
      "created_at": "2016-07-19T16:46:34.626Z",
      "updated_at": "2016-07-19T16:46:34.626Z",
      "admin": false,
      "owner": false,
      "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBEkqCjw=--7e8e5d9e90e4898faee5f69e72def9e58da85fbe/avatar-64-x4",
      "company": {
        "id": 1033447817,
        "name": "Honcho Design"
      }
    },
    "title": "New Hire Info, Benefits Summary, and Forms",
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

* `GET /buckets/1/documents/2.json` will return the document with an ID of `2` in the Basecamp with an ID of `1`.

###### Example JSON Response
<!-- START GET /buckets/1/documents/2.json -->
```json
{
  "id": 9007199254741716,
  "status": "active",
  "created_at": "2016-06-24T18:40:57.621Z",
  "updated_at": "2016-06-24T18:40:57.621Z",
  "type": "Document",
  "url": "https://3.basecampapi.com/195539477/buckets/2085958499/documents/9007199254741716.json",
  "app_url": "https://3.basecamp.com/195539477/buckets/2085958499/documents/9007199254741716",
  "comments_count": 0,
  "comments_url": "https://3.basecampapi.com/195539477/buckets/2085958499/recordings/9007199254741716/comments.json",
  "bucket": {
    "id": 2085958499,
    "name": "The Leto Locator",
    "type": "Project"
  },
  "creator": {
    "id": 1007299165,
    "attachable_sgid": "BAh7CEkiCGdpZAY6BkVUSSIrZ2lkOi8vYmMzL1BlcnNvbi8xMDA3Mjk5MTY1P2V4cGlyZXNfaW4GOwBUSSIMcHVycG9zZQY7AFRJIg9hdHRhY2hhYmxlBjsAVEkiD2V4cGlyZXNfYXQGOwBUMA==--c28a27d0c490353fc1a5c2a50ce8eda0fae07370",
    "name": "Matt Donahue",
    "email_address": "matt@honchodesign.com",
    "personable_type": "User",
    "title": "Global Data Strategist",
    "created_at": "2016-07-19T16:46:37.604Z",
    "updated_at": "2016-07-19T16:46:37.604Z",
    "admin": false,
    "owner": false,
    "avatar_url": "https://3.basecamp-static.com/195539477/people/BAhpBF0qCjw=--21513efb0cf6f64f7a0720b2c56ac6145ae6680c/avatar-64-x4"
  },
  "title": "Possible photos to show vulnerable laptops",
  "content": "We've been mulling over some possible photography and situations we want to show, particularly vulnerable laptops. Here are a few ideas, and we'll be adding to and changing this list quite a bit as it develops:<br><br>\n\n  <strong>Photography</strong><br>\n  <ol>\n    <li>Person at a coffee shop</li>\n    <li>Leaving laptop unsecured at work</li>\n    <li>Leaving laptop in hotel room out in the open, not in the safe</li>\n    <li>Animated gif of someone turning around and laptop being gone the next second</li>\n    <li>People leaving their computer in their bag and not paying attention</li>\n    <li>Security line at an airport, laptops out in the open</li>\n  </ol>"
}
```
<!-- END GET /buckets/1/documents/2.json -->

###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/documents/2.json
```

Create a document
-----------------

* `POST /buckets/1/vaults/2/documents.json` publishes a document in the Basecamp with ID `1` and under the vault with an ID of `2`.

**Required parameters**: `title` as the title of the document, and `content` as the body of the document. See our [Rich text content][rich] guide for what HTML tags are allowed.

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

* `PUT /buckets/1/documents/2.json` allows changing the title and content of the document with an ID of `2` in the Basecamp with ID `1`.

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
[rich]: https://github.com/basecamp/bc3-api/blob/master/README.md#rich-text-content
