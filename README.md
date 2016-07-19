The Basecamp 3 API
==================

Welcome to the Basecamp 3 API! Looking to integrate your service with Basecamp 3, or create your own app in concert with data inside of Basecamp 3? We're happy to have you!

If you have a specific feature request or if you found a bug, [please open a GitHub issue](https://github.com/basecamp/bc3-api/issues/new). We encourage forking these docs for local reference, and will happily accept pull request with improvements.

To talk with us and other developers about the API, [post a question on StackOverflow](http://stackoverflow.com/questions/ask) tagged `basecamp` or [open a support ticket](https://basecamp.com/support) if you need help from us directly.

**Please note:** During this early access period (while this repo is private), please hold on with announcing your API integration publicly. Once we're fully public you can go for it.

Compatibility with previous Basecamp APIs
-----------------------------------------

The Basecamp 3 API is not compatible with the [Basecamp Classic API](https://github.com/basecamp/basecamp-classic-api) or the [Basecamp 2 API](https://github.com/basecamp/bcx-api). All integrations will start fresh with the new API. The core ingredients are the same, though: this is a REST-style API that uses JSON for serialization and OAuth 2 for authentication.


What's different?
-----------------

If you've used a previous version of the Basecamp API, you will need to adapt your integration code. Here's a quick summary of changes:

- "Projects" are now Basecamps.
- We're requiring OAuth for [authentication](#authentication). No more Basic auth.
- All requests must end in `.json`
- Many IDs are numeric, but many are now [Signed Global IDs (SGIDs)](https://github.com/rails/globalid#signed-global-ids), also known as "Squids"
- [Pagination](#pagination) is now performed via the `Link` and `X-Total-Count` headers.


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

Most collection APIs paginate their results. The first request returns up to 50 records. The Basecamp 3 API follows the [RFC5988 convention](https://tools.ietf.org/html/rfc5988) of using the `Link` header to provide URLs for the `next` page. Follow this URLs to retrieve the next page of data, and please don't build the pagination URLs yourself! Here's an example from the [Messages API][2] for requesting the third page (of 50) when 300 are available:

```
<https://3.basecampapi.com/999999999/buckets/2085958496/messages.json?page=4>; rel="next"
```

Quick note: If the `Link` header is blank, and you have some results, then that's the only page of data! We also provide the `X-Total-Count` header, which displays the total amount of resources in the collection you are fetching.


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

Many resources, including messages, documents, and comments, represent their content as rich text in HTML. Rich text content may contain lists, block quotes, simple formatting, and inline attachments such as @mentions, images, and files.

If your application reads Basecamp rich text content, it must be able to process HTML. Use a web view component to render rich text content unmodified. Or, if your application needs a plain-text representation of rich text content, first decode any HTML entities, then replace `<br>` tags with line breaks, and finally strip the remaining HTML tags.

Similarly, if your application writes rich text content, it must be able to generate well-formed HTML. At a minimum, this means properly encoding HTML entities and replacing line breaks with `<br>` tags.

Applications that modify existing rich text content should take special care not to discard any formatting or attachments during processing. Consider using a full HTML parser to manipulate rich text content. Libraries such as [Nokogiri](http://www.nokogiri.org) (Ruby) and Cheerio (https://github.com/cheeriojs/cheerio) (Node.js) are good fits for this scenario.

### Allowed HTML tags

You may use the following standard HTML tags in rich text content: `div`, `br`, `strong`, `em`, `strike`, `a` (with an `href` attribute), `pre`, `ol`, `ul`, `li`, and `blockquote`. Any other tags will be removed automatically.

The special `<bc-attachment>` tag allows you to insert an inline attachment. Each `<bc-attachment>` has an `sgid` attribute which points to the `attachable_sgid` value of an attachable Basecamp resource. Your application will receive a rendered representation of the attachable resource inside the `<bc-attachment>` tag in API responses.

### Inserting a mention

Mentions in rich text content are attachments that reference a [Person](sections/people.md) on the current [Basecamp](sections/basecamps.md). When you submit rich text content with mentions, Basecamp delivers a special notification to each mentioned person.

Create a mention in Basecamp's rich text editor by typing "@" and selecting a person from the drop-down list. Create mentions with the API by inserting a `<bc-attachment>` tag with an `sgid` attribute pointing to the person's `attachable_sgid`.

For example, to mention this person:

```json
  {
    "id": 1007299208,
    "name": "Victor Cooper",
    "attachable_sgid": "BAh7CEkiCG..."
  }
```

Submit this rich text content:

```html
  <bc-attachment sgid="BAh7CEkiCG..."></bc-attachment>
```

The Basecamp API will return an expanded representation similar to the following:

```html
  <bc-attachment sgid="BAh7CEkiCG..." content-type="application/vnd.basecamp.mention">
    <figure>
      <img srcset="..." src="..." class="avatar" ...>
      <figcaption>Victor</figcaption>
    </figure>
  </bc-attachment>
```

### Inserting an image or file attachment

To insert an image or file attachment in rich text content, first [create an Attachment](sections/attachments.md#create-an-attachment). You will receive an `attachable_sgid` in response:

```json
  {
    "attachable_sgid": "BAh7CEkiCG..."
  }
````

Take this `attachable_sgid` and use it to submit rich text content with a `<bc-attachment>` tag:

```html
  <bc-attachment sgid="BAh7CEkiCG..."></bc-attachment>
```

If the attachment is an image, you may optionally include a `caption` attribute, which will appear below the attachment in rendered rich text content:

```html
  <bc-attachment sgid="BAh7CEkiCG..." caption="My photo"></bc-attachment>
```

The Basecamp API will return an expanded representation similar to the following:

```html
  <bc-attachment sgid="BAh7CEkiCG..." content-type="image/jpeg" width="2560" height="1536" url="..." href="..." filename="my-photo.jpg" caption="My photo">
    <figure>
      <img srcset="..." src="...">
      <figcaption>My photo</figcaption>
    </figure>
  </bc-attachment>
```

Be sure to provide an appropriate `Content-Type` header when creating image attachments. If the attachment's content type does not start with `image/`, it will be presented as a file instead of an image with a preview.


API endpoints
-------------
<!-- START API ENDPOINTS -->
- [Attachments](https://github.com/basecamp/bc3-api/blob/master/sections/attachments.md#attachments)
  - [Create an attachment](https://github.com/basecamp/bc3-api/blob/master/sections/attachments.md#create-an-attachment)
- [Basecamps](https://github.com/basecamp/bc3-api/blob/master/sections/basecamps.md#basecamps)
  - [Get Basecamps](https://github.com/basecamp/bc3-api/blob/master/sections/basecamps.md#get-basecamps)
  - [Get archived Basecamps](https://github.com/basecamp/bc3-api/blob/master/sections/basecamps.md#get-archived-basecamps)
  - [Get trashed Basecamps](https://github.com/basecamp/bc3-api/blob/master/sections/basecamps.md#get-trashed-basecamps)
  - [Get a Basecamp](https://github.com/basecamp/bc3-api/blob/master/sections/basecamps.md#get-a-basecamp)
  - [Create a Basecamp](https://github.com/basecamp/bc3-api/blob/master/sections/basecamps.md#create-a-basecamp)
  - [Update a Basecamp](https://github.com/basecamp/bc3-api/blob/master/sections/basecamps.md#update-a-basecamp)
  - [Trash a Basecamp](https://github.com/basecamp/bc3-api/blob/master/sections/basecamps.md#trash-a-basecamp)
- [Campfires](https://github.com/basecamp/bc3-api/blob/master/sections/campfires.md#campfires)
  - [Get Campfires](https://github.com/basecamp/bc3-api/blob/master/sections/campfires.md#get-campfires)
  - [Get a Campfire](https://github.com/basecamp/bc3-api/blob/master/sections/campfires.md#get-a-campfire)
  - [Get Campfire lines](https://github.com/basecamp/bc3-api/blob/master/sections/campfires.md#get-campfire-lines)
  - [Get a Campfire line](https://github.com/basecamp/bc3-api/blob/master/sections/campfires.md#get-a-campfire-line)
  - [Create a Campfire line](https://github.com/basecamp/bc3-api/blob/master/sections/campfires.md#create-a-campfire-line)
- [Client approvals](https://github.com/basecamp/bc3-api/blob/master/sections/client_approvals.md#client-approvals)
  - [Get client approvals](https://github.com/basecamp/bc3-api/blob/master/sections/client_approvals.md#get-client-approvals)
  - [Get a client approval](https://github.com/basecamp/bc3-api/blob/master/sections/client_approvals.md#get-a-client-approval)
- [Client correspondences](https://github.com/basecamp/bc3-api/blob/master/sections/client_correspondences.md#client-correspondences)
  - [Get client correspondences](https://github.com/basecamp/bc3-api/blob/master/sections/client_correspondences.md#get-client-correspondences)
  - [Get a client correspondence](https://github.com/basecamp/bc3-api/blob/master/sections/client_correspondences.md#get-a-client-correspondence)
- [Client replies](https://github.com/basecamp/bc3-api/blob/master/sections/client_replies.md#client-replies)
  - [Get client replies](https://github.com/basecamp/bc3-api/blob/master/sections/client_replies.md#get-client-replies)
  - [Get a client reply](https://github.com/basecamp/bc3-api/blob/master/sections/client_replies.md#get-a-client-reply)
- [Comments](https://github.com/basecamp/bc3-api/blob/master/sections/comments.md#comments)
  - [Get comments](https://github.com/basecamp/bc3-api/blob/master/sections/comments.md#get-comments)
  - [Get a comment](https://github.com/basecamp/bc3-api/blob/master/sections/comments.md#get-a-comment)
  - [Create a comment](https://github.com/basecamp/bc3-api/blob/master/sections/comments.md#create-a-comment)
  - [Update a comment](https://github.com/basecamp/bc3-api/blob/master/sections/comments.md#update-a-comment)
- [Documents](https://github.com/basecamp/bc3-api/blob/master/sections/documents.md#documents)
  - [Get documents](https://github.com/basecamp/bc3-api/blob/master/sections/documents.md#get-documents)
  - [Get a document](https://github.com/basecamp/bc3-api/blob/master/sections/documents.md#get-a-document)
  - [Create a document](https://github.com/basecamp/bc3-api/blob/master/sections/documents.md#create-a-document)
  - [Update a document](https://github.com/basecamp/bc3-api/blob/master/sections/documents.md#update-a-document)
- [Events](https://github.com/basecamp/bc3-api/blob/master/sections/events.md#events)
  - [Get events](https://github.com/basecamp/bc3-api/blob/master/sections/events.md#get-events)
- [Message Boards](https://github.com/basecamp/bc3-api/blob/master/sections/message_boards.md#message-boards)
  - [Get message board](https://github.com/basecamp/bc3-api/blob/master/sections/message_boards.md#get-message-board)
- [Messages](https://github.com/basecamp/bc3-api/blob/master/sections/messages.md#messages)
  - [Get messages](https://github.com/basecamp/bc3-api/blob/master/sections/messages.md#get-messages)
  - [Get a message](https://github.com/basecamp/bc3-api/blob/master/sections/messages.md#get-a-message)
  - [Create a message](https://github.com/basecamp/bc3-api/blob/master/sections/messages.md#create-a-message)
  - [Update a message](https://github.com/basecamp/bc3-api/blob/master/sections/messages.md#update-a-message)
- [People](https://github.com/basecamp/bc3-api/blob/master/sections/people.md#people)
  - [Get all people](https://github.com/basecamp/bc3-api/blob/master/sections/people.md#get-all-people)
  - [Get people on a Basecamp](https://github.com/basecamp/bc3-api/blob/master/sections/people.md#get-people-on-a-basecamp)
  - [Update who can access a Basecamp](https://github.com/basecamp/bc3-api/blob/master/sections/people.md#update-who-can-access-a-basecamp)
  - [Get pingable people](https://github.com/basecamp/bc3-api/blob/master/sections/people.md#get-pingable-people)
  - [Get person](https://github.com/basecamp/bc3-api/blob/master/sections/people.md#get-person)
  - [Get my personal info](https://github.com/basecamp/bc3-api/blob/master/sections/people.md#get-my-personal-info)
- [Question answers](https://github.com/basecamp/bc3-api/blob/master/sections/question_answers.md#question-answers)
  - [Get question answers](https://github.com/basecamp/bc3-api/blob/master/sections/question_answers.md#get-question-answers)
  - [Get a question answer](https://github.com/basecamp/bc3-api/blob/master/sections/question_answers.md#get-a-question-answer)
- [Questionnaires](https://github.com/basecamp/bc3-api/blob/master/sections/questionnaires.md#questionnaires)
  - [Get questionnaire](https://github.com/basecamp/bc3-api/blob/master/sections/questionnaires.md#get-questionnaire)
- [Questions](https://github.com/basecamp/bc3-api/blob/master/sections/questions.md#questions)
  - [Get questions](https://github.com/basecamp/bc3-api/blob/master/sections/questions.md#get-questions)
  - [Get a question](https://github.com/basecamp/bc3-api/blob/master/sections/questions.md#get-a-question)
- [Recordings](https://github.com/basecamp/bc3-api/blob/master/sections/recordings.md#recordings)
  - [Get recordings](https://github.com/basecamp/bc3-api/blob/master/sections/recordings.md#get-recordings)
  - [Trash a recording](https://github.com/basecamp/bc3-api/blob/master/sections/recordings.md#trash-a-recording)
- [Schedule entries](https://github.com/basecamp/bc3-api/blob/master/sections/schedule_entries.md#schedule-entries)
  - [Get schedule entries](https://github.com/basecamp/bc3-api/blob/master/sections/schedule_entries.md#get-schedule-entries)
  - [Get a schedule entry](https://github.com/basecamp/bc3-api/blob/master/sections/schedule_entries.md#get-a-schedule-entry)
  - [Create a schedule entry](https://github.com/basecamp/bc3-api/blob/master/sections/schedule_entries.md#create-a-schedule-entry)
  - [Update a schedule entry](https://github.com/basecamp/bc3-api/blob/master/sections/schedule_entries.md#update-a-schedule-entry)
- [Schedules](https://github.com/basecamp/bc3-api/blob/master/sections/schedules.md#schedules)
  - [Get schedule](https://github.com/basecamp/bc3-api/blob/master/sections/schedules.md#get-schedule)
- [To-do lists](https://github.com/basecamp/bc3-api/blob/master/sections/todolists.md#to-do-lists)
  - [Get to-do lists](https://github.com/basecamp/bc3-api/blob/master/sections/todolists.md#get-to-do-lists)
  - [Get a to-do list](https://github.com/basecamp/bc3-api/blob/master/sections/todolists.md#get-a-to-do-list)
  - [Create a to-do list](https://github.com/basecamp/bc3-api/blob/master/sections/todolists.md#create-a-to-do-list)
  - [Update a to-do list](https://github.com/basecamp/bc3-api/blob/master/sections/todolists.md#update-a-to-do-list)
- [To-dos](https://github.com/basecamp/bc3-api/blob/master/sections/todos.md#to-dos)
  - [Get to-dos](https://github.com/basecamp/bc3-api/blob/master/sections/todos.md#get-to-dos)
  - [Get a to-do](https://github.com/basecamp/bc3-api/blob/master/sections/todos.md#get-a-to-do)
  - [Create a to-do](https://github.com/basecamp/bc3-api/blob/master/sections/todos.md#create-a-to-do)
  - [Update a to-do](https://github.com/basecamp/bc3-api/blob/master/sections/todos.md#update-a-to-do)
  - [Complete a to-do](https://github.com/basecamp/bc3-api/blob/master/sections/todos.md#complete-a-to-do)
  - [Uncomplete a to-do](https://github.com/basecamp/bc3-api/blob/master/sections/todos.md#uncomplete-a-to-do)
  - [Reposition a to-do](https://github.com/basecamp/bc3-api/blob/master/sections/todos.md#move-a-to-do)
- [To-do sets](https://github.com/basecamp/bc3-api/blob/master/sections/todosets.md#to-do-sets)
  - [Get to-do set](https://github.com/basecamp/bc3-api/blob/master/sections/todosets.md#get-to-do-set)
- [Uploads](https://github.com/basecamp/bc3-api/blob/master/sections/uploads.md#uploads)
  - [Get uploads](https://github.com/basecamp/bc3-api/blob/master/sections/uploads.md#get-uploads)
  - [Get an upload](https://github.com/basecamp/bc3-api/blob/master/sections/uploads.md#get-an-upload)
  - [Create an upload](https://github.com/basecamp/bc3-api/blob/master/sections/uploads.md#create-an-upload)
  - [Update an upload](https://github.com/basecamp/bc3-api/blob/master/sections/uploads.md#update-an-upload)
- [Vaults](https://github.com/basecamp/bc3-api/blob/master/sections/vaults.md#vaults)
  - [Get vaults](https://github.com/basecamp/bc3-api/blob/master/sections/vaults.md#get-vaults)
  - [Get a vault](https://github.com/basecamp/bc3-api/blob/master/sections/vaults.md#get-a-vault)
  - [Create a vault](https://github.com/basecamp/bc3-api/blob/master/sections/vaults.md#create-a-vault)
  - [Update a vault](https://github.com/basecamp/bc3-api/blob/master/sections/vaults.md#update-a-vault)

<!-- END API ENDPOINTS -->

API libraries
-------------

If you've got an API library for Basecamp 3, just [open a Pull Request](https://github.com/basecamp/bc3-api/compare) and let us know! We'd be happy to add it here.

Conduct
-------

Please note that this project is released with a [Contributor Code of Conduct](https://github.com/basecamp/bc3-api/blob/master/CONDUCT.md). By participating in discussions about the Basecamp 3 API, you agree to abide by its terms.


License
-------

These API docs are licensed under [Creative Commons (CC BY-SA 4.0)](http://creativecommons.org/licenses/by-sa/4.0/). Please feel free to share (alike), remix, and distribute as you see fit.
