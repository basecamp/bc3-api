The Basecamp 3 API
==================

Welcome to the Basecamp 3 API! If you're looking to integrate your application with Basecamp 3 or create your own application in concert with data inside of Basecamp 3, you're in the right place. We're happy to have you!


Compatibility with previous Basecamp APIs
-----------------------------------------

The Basecamp 3 API is not compatible with the [Basecamp Classic API](https://github.com/basecamp/basecamp-classic-api) or the [Basecamp 2 API](https://github.com/basecamp/bcx-api). All integrations will start fresh with the new API. The core ingredients are the same, though: Basecamp 3 is a REST-style API that uses JSON for serialization and OAuth 2.0 for authentication.


What's different?
-----------------

If you've used a previous version of the Basecamp API, you need to adapt your integration code. Here are some notable changes for the Basecamp 3 API:

- We require OAuth 2.0 for [authentication](#authentication)—no more Basic authentication
- All requests must end in `.json`
- [Pagination](#pagination) is performed via the `Link` and `X-Total-Count` headers


Making a request
----------------

All URLs start with **`https://3.basecampapi.com/999999999/`**. URLs are HTTPS only. The path is prefixed with the account ID, but no `/api/v1` API prefix. Also, note the different domain!

To make a request for all the projects on your account, append the `projects` index path to the base URL to form something like `https://3.basecampapi.com/999999999/projects.json`. In cURL, it looks like this:

``` shell
curl -H "Authorization: Bearer $ACCESS_TOKEN" -H 'User-Agent: MyApp (yourname@example.com)' https://3.basecampapi.com/999999999/projects.json
```

To create something, it's the same idea, but you also have to include the `Content-Type` header and the JSON data:

``` shell
curl -H "Authorization: Bearer $ACCESS_TOKEN" \
  -H 'Content-Type: application/json' \
  -H 'User-Agent: MyApp (yourname@example.com)' \
  -d '{ "name": "My new project!" }' \
  https://3.basecampapi.com/999999999/projects.json
```

Throughout the Basecamp 3 API docs, we include "Copy as cURL" examples. To try the examples in your shell, copy your OAuth 2.0 access token into your clipboard and run:

``` shell
export ACCESS_TOKEN=PASTE_ACCESS_TOKEN_HERE
export ACCOUNT_ID=999999999
```

Then you should be able to copy/paste any example from the docs. After pasting a cURL example, you can pipe it to a JSON pretty printer to make it more readable. Try [jsonpp](https://jmhodges.github.io/jsonpp/) or `json_pp` on OSX:

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/999999999/projects.json | json_pp
```

Authentication
--------------

If you're making a public integration with Basecamp for others to enjoy, you must use OAuth 2.0. OAuth 2.0 allows users to authorize your application to use Basecamp on their behalf without having to copy/paste API tokens or touch sensitive login information.

Read the [authentication guide](https://github.com/basecamp/api/blob/master/sections/authentication.md) to get started.


Identifying your application
----------------------------

You must include a `User-Agent` header with **both**:

* The name of your application
* A link to your application or your email address

We use this information to get in touch if you're doing something wrong (so we can warn you before you're blacklisted) or something awesome (so we can congratulate you). Here are examples of acceptable `User-Agent` headers:

* `User-Agent: Freshbooks (http://freshbooks.com/contact.php)`
* `User-Agent: Fabian's Ingenious Integration (fabian@example.com)`

If you don't include a `User-Agent` header, you'll get a `400 Bad Request` response.


JSON only
---------

We use JSON for all API data. The style is no root element and snake\_case for object keys. This means that you have to send the `Content-Type` header `Content-Type: application/json; charset=utf-8` when you're POSTing or PUTing data into Basecamp. All API URLs end in `.json` to indicate that they return JSON.

You'll receive a `415 Unsupported Media Type` response code if you don't include the `Content-Type` header or you try to use a different URL suffix than `.json`.


Pagination
----------

Most collection APIs paginate their results. The number of requests that'll appear on each page is variable. In most cases, we use a [geared pagination ratio](https://github.com/basecamp/geared_pagination) with 15 results on page 1, 30 on page 2, 50 on 3, and then 100 on 4 and above. The Basecamp 3 API follows the [RFC5988 convention](https://tools.ietf.org/html/rfc5988) of using the `Link` header to provide URLs for the `next` page. Follow this convention to retrieve the next page of data—please don't build the pagination URLs yourself!

Here's an example response header from requesting the third page of [messages](sections/messages.md#messages):

```
Link: <https://3.basecampapi.com/999999999/buckets/2085958496/messages.json?page=4>; rel="next"
```

If the `Link` header is blank, that's the last page. The Basecamp 3 API also provides the `X-Total-Count` header, which displays the total number of resources in the collection you are fetching.


Using HTTP caching
------------------

You must use HTTP freshness headers to speed up your application and lighten the load on our servers. Most API responses will include an `ETag` or `Last-Modified` header. When you first request a resource, store these values. On subsequent requests, submit them back to us as `If-None-Match` and `If-Modified-Since`, respectively. If the resource hasn't changed since your last request, you'll get a `304 Not Modified` response with no body, saving you the time and bandwidth of sending something you already have.


Handling errors
---------------

API clients must expect and gracefully handle transient errors, such as rate limiting or server errors. We recommend baking 5xx and 429 response handling into your low-level HTTP client so your integration can handle most errors automatically.

### Rate limiting (429 Too Many Requests)

You can perform up to 50 requests per 10-second period from the same IP address for the same account. If you exceed this limit, you'll get a [429 Too Many Requests](http://tools.ietf.org/html/draft-nottingham-http-new-status-02#section-4) response for subsequent requests. Check the `Retry-After` header to see how many seconds to wait before retrying the request.

### [5xx server errors](https://en.wikipedia.org/wiki/List_of_HTTP_status_codes#5xx_Server_errors)

If Basecamp is having trouble, you will get a response with a 5xx status code indicating a server error. 500 (Internal Server Error), 502 (Bad Gateway), 503 (Service Unavailable), and 504 (Gateway Timeout) may be retried with [exponential backoff](https://en.wikipedia.org/wiki/Exponential_backoff).

### 404 Not Found

API requests may 404 due to deleted content, an inactive account, missing user permissions, etc. Detect these conditions to give your users a clear explanation about why they can't connect to Basecamp. Do not automatically retry these requests.

* Inactive account. 404 Not Found response with a `Reason: Account Inactive` header. Due to an expired trial or account suspension. All API requests to an inactive account will fail, so we recommend detecting and disabling the account in your integration as well.
* Inaccessible items. 404 Not Found response. Due to a deleted item or insufficient permissions.


Rich text content
-----------------

Many resources, including messages, documents, and comments, represent their content as rich text in HTML. Rich text content may contain lists, block quotes, simple formatting, and inline attachments such as mentions, images, and files.

See the [Rich text](sections/rich_text.md) section for more information about working with HTML and attachments in rich text content.


API endpoints
-------------
<!-- START API ENDPOINTS -->
- [Attachments](https://github.com/basecamp/bc3-api/blob/master/sections/attachments.md#attachments)
- [Campfires](https://github.com/basecamp/bc3-api/blob/master/sections/campfires.md#campfires)
- [Chatbots](https://github.com/basecamp/bc3-api/blob/master/sections/chatbots.md#chatbots)
- [Client approvals](https://github.com/basecamp/bc3-api/blob/master/sections/client_approvals.md#client-approvals)
- [Client correspondences](https://github.com/basecamp/bc3-api/blob/master/sections/client_correspondences.md#client-correspondences)
- [Client replies](https://github.com/basecamp/bc3-api/blob/master/sections/client_replies.md#client-replies)
- [Comments](https://github.com/basecamp/bc3-api/blob/master/sections/comments.md#comments)
- [Documents](https://github.com/basecamp/bc3-api/blob/master/sections/documents.md#documents)
- [Events](https://github.com/basecamp/bc3-api/blob/master/sections/events.md#events)
- [Forwards](https://github.com/basecamp/bc3-api/blob/master/sections/forwards.md#forwards)
- [Inboxes](https://github.com/basecamp/bc3-api/blob/master/sections/inboxes.md#inboxes)
- [Message Boards](https://github.com/basecamp/bc3-api/blob/master/sections/message_boards.md#message-boards)
- [Message Types](https://github.com/basecamp/bc3-api/blob/master/sections/message_types.md#message-types)
- [Messages](https://github.com/basecamp/bc3-api/blob/master/sections/messages.md#messages)
- [People](https://github.com/basecamp/bc3-api/blob/master/sections/people.md#people)
- [Projects](https://github.com/basecamp/bc3-api/blob/master/sections/projects.md#projects)
- [Question answers](https://github.com/basecamp/bc3-api/blob/master/sections/question_answers.md#question-answers)
- [Questionnaires](https://github.com/basecamp/bc3-api/blob/master/sections/questionnaires.md#questionnaires)
- [Questions](https://github.com/basecamp/bc3-api/blob/master/sections/questions.md#questions)
- [Recordings](https://github.com/basecamp/bc3-api/blob/master/sections/recordings.md#recordings)
- [Schedule entries](https://github.com/basecamp/bc3-api/blob/master/sections/schedule_entries.md#schedule-entries)
- [Schedules](https://github.com/basecamp/bc3-api/blob/master/sections/schedules.md#schedules)
- [Subscriptions](https://github.com/basecamp/bc3-api/blob/master/sections/subscriptions.md#subscriptions)
- [Templates](https://github.com/basecamp/bc3-api/blob/master/sections/templates.md#templates)
- [To-do list groups](https://github.com/basecamp/bc3-api/blob/master/sections/todolist_groups.md#to-do-list-groups)
- [To-do lists](https://github.com/basecamp/bc3-api/blob/master/sections/todolists.md#to-do-lists)
- [To-do sets](https://github.com/basecamp/bc3-api/blob/master/sections/todosets.md#to-do-sets)
- [To-dos](https://github.com/basecamp/bc3-api/blob/master/sections/todos.md#to-dos)
- [Uploads](https://github.com/basecamp/bc3-api/blob/master/sections/uploads.md#uploads)
- [Vaults](https://github.com/basecamp/bc3-api/blob/master/sections/vaults.md#vaults)
- [Webhooks](https://github.com/basecamp/bc3-api/blob/master/sections/webhooks.md#webhooks)

<!-- END API ENDPOINTS -->

Listing your application
------------------------

To add your application to our public list of Basecamp 3 integrations, go to [https://github.com/basecamp/bc3-integrations](https://github.com/basecamp/bc3-integrations) and open a pull request.


Conduct
-------

Please note that this project is released with a [Contributor Code of Conduct](https://github.com/basecamp/bc3-api/blob/master/CONDUCT.md). By participating in discussions about the Basecamp 3 API, you agree to abide by these terms.


License
-------

These API docs are licensed under [Creative Commons (CC BY-SA 4.0)](http://creativecommons.org/licenses/by-sa/4.0/). Please share, remix, and distribute as you see fit.

---

If you have a specific feature request or find a bug, [please open a GitHub issue](https://github.com/basecamp/bc3-api/issues/new). We encourage you to fork these docs for local reference and happily accept pull requests with improvements.

To talk with us and other developers about the API, [post a question on StackOverflow](http://stackoverflow.com/questions/ask) tagged `basecamp`. If you need help from us directly, please [open a support ticket](https://basecamp.com/support).
