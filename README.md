The Basecamp 3 API
==================

Welcome to the Basecamp 3 API! Looking to integrate your service with Basecamp 3, or create your own app in concert with data inside of Basecamp 3? We're happy to have you!

If you have a specific feature request or if you found a bug, [please open a GitHub issue](https://github.com/basecamp/bc3-api/issues/new). We encourage forking these docs for local reference, and will happily accept pull request with improvements.

To talk with us and other developers about the API, [post a question on StackOverflow](http://stackoverflow.com/questions/ask) tagged `basecamp` or [open a support ticket](https://basecamp.com/support) if you need help from us directly.

Compatibility with previous Basecamp APIs
-----------------------------------------

The Basecamp 3 API is not compatible with the [Basecamp Classic API](https://github.com/basecamp/basecamp-classic-api) or the [Basecamp 2 API](https://github.com/basecamp/bcx-api). All integrations will start fresh with the new API. The core ingredients are the same, though: this is a REST-style API that uses JSON for serialization and OAuth 2 for authentication.


What's different?
-----------------

If you've used a previous version of the Basecamp API, you will need to adapt your integration code. Here's a quick summary of changes:

- "Projects" are now [Basecamps][1].
- We're requiring OAuth for [authentication](#authentication)
- All requests must end in `.json`
- Many IDs are numeric, but many are now [Signed Global IDs (SGIDs)](https://github.com/rails/globalid#signed-global-ids), also known as "Squids"
- Most data structures are "Recordables", which tie back to a [Recording][1]

More on "Recordings" and "Recordables":

What is a recording? Recordable?

- Tree structure
- Children

Making a request
----------------

All URLs start with `https://3.basecampapi.com/999999999/`. **HTTPS only**. The path is prefixed with the account ID, but no `/api/v1` API prefix.

To make a request for all the projects on your account, you'd append the projects index path to the base url to form something like https://3.basecampapi.com/999999999/basecamps.json. In cURL, that looks like:

``` shell
curl -H "Authorization: Bearer $ACCESS_TOKEN" -H 'User-Agent: MyApp (yourname@example.com)' https://3.basecampapi.com/999999999/basecamps.json
```

To create something, it's the same deal except you also have to include the `Content-Type` header and the JSON data:

``` shell
curl -H "Authorization: Bearer $ACCESS_TOKEN" \
  -H 'Content-Type: application/json' \
  -H 'User-Agent: MyApp (yourname@example.com)' \
  -d '{ "name": "My new project!" }' \
  https://3.basecampapi.com/999999999/basecamps.json
```

That's all! Throughout this guide we've included "Copy as cURL" examples. If you'd like to try this out in your shell, copy your OAuth Access token into your clipboard and run:

``` shell
export ACCESS_TOKEN=PASTE_ACCESS_TOKEN_HERE
export ACCOUNT_ID=999999999
```

Then you should be able to easily copy + paste any example from our docs. After pasting a cURL example, you could pipe it to a JSON pretty printer to make it a little more readable. Try [jsonpp](https://jmhodges.github.io/jsonpp/) or `json_pp` on OSX:

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecamp.com/195539477/basecamps.json | json_pp
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

Most collection APIs paginate their results. The first request returns up to 50 records. Check the next page for more results by adding `&page=2`, then `&page=3`, and so on until you get an empty response.


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


API ready for use
-----------------

* [Basecamps][1]
* [Messages][2]
* [Comments][3]
* [To-do lists][4]
* [To-dos][5]
* [Recordings][6]


API libraries
-------------

If you've got an API library for Basecamp 3, just [open a Pull Request](https://github.com/basecamp/bc3-api/compare) and let us know! We'd be happy to add it here.


Conduct
-------

Please note that this project is released with a [Contributor Code of Conduct](https://github.com/basecamp/bc3-api/blob/master/CONDUCT.md). By participating in discussions about the Basecamp 3 API, you agree to abide by its terms.


License
-------

These API docs are licensed under [Creative Commons (CC BY-SA 4.0)](http://creativecommons.org/licenses/by-sa/4.0/). Please feel free to share (alike), remix, and distribute as you see fit.


[1]: https://github.com/basecamp/bc3-api/blob/master/sections/basecamps.md#basecamps
[2]: https://github.com/basecamp/bc3-api/blob/master/sections/messages.md#messages
[3]: https://github.com/basecamp/bc3-api/blob/master/sections/comments.md#comments
[4]: https://github.com/basecamp/bc3-api/blob/master/sections/todolists.md#todolists
[5]: https://github.com/basecamp/bc3-api/blob/master/sections/todos.md#todos
[6]: https://github.com/basecamp/bc3-api/blob/master/sections/recordings.md#recordings
