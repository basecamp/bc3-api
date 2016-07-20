The Basecamp 3 API
==================

Welcome to the Basecamp 3 API! Looking to integrate your service with Basecamp 3, or create your own app in concert with data inside of Basecamp 3? We're happy to have you!


Compatibility with previous Basecamp APIs
-----------------------------------------

The Basecamp 3 API is not compatible with the [Basecamp Classic API](https://github.com/basecamp/basecamp-classic-api) or the [Basecamp 2 API](https://github.com/basecamp/bcx-api). All integrations will start fresh with the new API. The core ingredients are the same, though: this is a REST-style API that uses JSON for serialization and OAuth 2 for authentication.


What's different?
-----------------

If you've used a previous version of the Basecamp API, you will need to adapt your integration code. Notable changes:

- We're requiring OAuth for [authentication](#authentication). No more Basic auth.
- All requests must end in `.json`
- [Pagination](#pagination) is now performed via the `Link` and `X-Total-Count` headers.
- Projects are now called Basecamps.


Making a request
----------------

All URLs start with **`https://3.basecampapi.com/999999999/`**. HTTPS only. The path is prefixed with the account ID, but no `/api/v1` API prefix. Also note the different domain!

To make a request for all the projects on your account, you'd append the projects index path to the base url to form something like https://3.basecampapi.com/999999999/projects.json. In cURL, that looks like:

``` shell
curl -H "Authorization: Bearer $ACCESS_TOKEN" -H 'User-Agent: MyApp (yourname@example.com)' https://3.basecampapi.com/999999999/projects.json
```

To create something, it's the same deal except you also have to include the `Content-Type` header and the JSON data:

``` shell
curl -H "Authorization: Bearer $ACCESS_TOKEN" \
  -H 'Content-Type: application/json' \
  -H 'User-Agent: MyApp (yourname@example.com)' \
  -d '{ "name": "My new project!" }' \
  https://3.basecampapi.com/999999999/projects.json
```

That's all! Throughout this guide we've included "Copy as cURL" examples. If you'd like to try this out in your shell, copy your OAuth Access token into your clipboard and run:

``` shell
export ACCESS_TOKEN=PASTE_ACCESS_TOKEN_HERE
export ACCOUNT_ID=999999999
```

Then you should be able to easily copy + paste any example from our docs. After pasting a cURL example, you could pipe it to a JSON pretty printer to make it a little more readable. Try [jsonpp](https://jmhodges.github.io/jsonpp/) or `json_pp` on OSX:

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/999999999/projects.json | json_pp
```

Authentication
--------------

If you're making a public integration with Basecamp for others to enjoy, you must use OAuth 2. This allows users to authorize your application to use Basecamp on their behalf without having to copy/paste API tokens or touch sensitive login info.

Read the [authentication guide](https://github.com/basecamp/api/blob/master/sections/authentication.md) to get started.


Identify your app
-----------------

You must include a `User-Agent` header with the name of your application and a link to it or your email address so we can get in touch in case you're doing something wrong (so we may warn you before you're blacklisted) or something awesome (so we may congratulate you). Here's a couple of examples:

    User-Agent: Freshbooks (http://freshbooks.com/contact.php)
    User-Agent: Fabian's Ingenious Integration (fabian@example.com)

If you don't supply this header, you will get a `400 Bad Request` response.


JSON only
---------

We use JSON for all API data. Style: no root element and snake\_case for object keys. This means that you have to send `Content-Type: application/json; charset=utf-8` when you're POSTing or PUTing data into Basecamp. All API URLs end in .json to indicate that they return JSON.

You'll receive a `415 Unsupported Media Type` response code if you attempt to use a different URL suffix or leave out the `Content-Type` header.


Pagination
----------

Most collection APIs paginate their results. The first request returns up to 50 records. The Basecamp 3 API follows the [RFC5988 convention](https://tools.ietf.org/html/rfc5988) of using the `Link` header to provide URLs for the `next` page. Follow this URLs to retrieve the next page of data, and please don't build the pagination URLs yourself! Here's an example response header from requesting the third page of [messages](sections/messages.md#messages):

```
Link: <https://3.basecampapi.com/999999999/buckets/2085958496/messages.json?page=4>; rel="next"
```

If the `Link` header is blank then that's the last page. We also provide the `X-Total-Count` header, which displays the total number of resources in the collection you are fetching.


Use HTTP caching
----------------

You must make use of the HTTP freshness headers to speed up your app and lighten the load on our servers. Most API responses will include an `ETag` or `Last-Modified` header. When you first request a resource, store these values. On subsequent requests, submit them back to us as `If-None-Match` and `If-Modified-Since`, respectively. If the resource hasn't changed since your last request, you'll get a `304 Not Modified` response with no body, saving you the time and bandwidth of sending something you already have.


Handling errors
---------------

If Basecamp is having trouble, you might see a 5xx error. `500` means that the app is entirely down, but you might also see `502 Bad Gateway`, `503 Service Unavailable`, or `504 Gateway Timeout`. It's your responsibility in all of these cases to retry your request later.


Rate limiting
-------------

You can perform up to 50 requests per 10 second period from the same IP address for the same account. If you exceed this limit, you'll get a [429 Too Many Requests](http://tools.ietf.org/html/draft-nottingham-http-new-status-02#section-4) response for subsequent requests. Check the `Retry-After` header to see how many seconds to wait before retrying the request.

We recommend baking 429 response handling in to your HTTP handling at a low level so your integration gracefully and automatically handles retries.


Rich text content
-----------------

Many resources, including messages, documents, and comments, represent their content as rich text in HTML. Rich text content may contain lists, block quotes, simple formatting, and inline attachments such as mentions, images, and files.

See the [Rich Text guide](sections/rich_text.md) for more details on working with HTML and attachments in rich text content.


API endpoints
-------------
<!-- START API ENDPOINTS -->
- [Attachments](https://github.com/basecamp/bc3-api/blob/master/sections/attachments.md#attachments)
- [Basecamps](https://github.com/basecamp/bc3-api/blob/master/sections/basecamps.md#basecamps)
- [Campfires](https://github.com/basecamp/bc3-api/blob/master/sections/campfires.md#campfires)
- [Client approvals](https://github.com/basecamp/bc3-api/blob/master/sections/client_approvals.md#client-approvals)
- [Client correspondences](https://github.com/basecamp/bc3-api/blob/master/sections/client_correspondences.md#client-correspondences)
- [Client replies](https://github.com/basecamp/bc3-api/blob/master/sections/client_replies.md#client-replies)
- [Comments](https://github.com/basecamp/bc3-api/blob/master/sections/comments.md#comments)
- [Documents](https://github.com/basecamp/bc3-api/blob/master/sections/documents.md#documents)
- [Events](https://github.com/basecamp/bc3-api/blob/master/sections/events.md#events)
- [Message Boards](https://github.com/basecamp/bc3-api/blob/master/sections/message_boards.md#message-boards)
- [Messages](https://github.com/basecamp/bc3-api/blob/master/sections/messages.md#messages)
- [People](https://github.com/basecamp/bc3-api/blob/master/sections/people.md#people)
- [Question answers](https://github.com/basecamp/bc3-api/blob/master/sections/question_answers.md#question-answers)
- [Questionnaires](https://github.com/basecamp/bc3-api/blob/master/sections/questionnaires.md#questionnaires)
- [Questions](https://github.com/basecamp/bc3-api/blob/master/sections/questions.md#questions)
- [Recordings](https://github.com/basecamp/bc3-api/blob/master/sections/recordings.md#recordings)
- [Schedule entries](https://github.com/basecamp/bc3-api/blob/master/sections/schedule_entries.md#schedule-entries)
- [Schedules](https://github.com/basecamp/bc3-api/blob/master/sections/schedules.md#schedules)
- [To-do lists](https://github.com/basecamp/bc3-api/blob/master/sections/todolists.md#to-do-lists)
- [To-dos](https://github.com/basecamp/bc3-api/blob/master/sections/todos.md#to-dos)
- [To-do sets](https://github.com/basecamp/bc3-api/blob/master/sections/todosets.md#to-do-sets)
- [Uploads](https://github.com/basecamp/bc3-api/blob/master/sections/uploads.md#uploads)
- [Vaults](https://github.com/basecamp/bc3-api/blob/master/sections/vaults.md#vaults)

<!-- END API ENDPOINTS -->


Conduct
-------

Please note that this project is released with a [Contributor Code of Conduct](https://github.com/basecamp/bc3-api/blob/master/CONDUCT.md). By participating in discussions about the Basecamp 3 API, you agree to abide by its terms.


License
-------

These API docs are licensed under [Creative Commons (CC BY-SA 4.0)](http://creativecommons.org/licenses/by-sa/4.0/). Please feel free to share (alike), remix, and distribute as you see fit.

---

If you have a specific feature request or if you found a bug, [please open a GitHub issue](https://github.com/basecamp/bc3-api/issues/new). We encourage forking these docs for local reference, and will happily accept pull request with improvements.

To talk with us and other developers about the API, [post a question on StackOverflow](http://stackoverflow.com/questions/ask) tagged `basecamp` or [open a support ticket](https://basecamp.com/support) if you need help from us directly.
