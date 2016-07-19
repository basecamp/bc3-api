Rich Text
=========

Many resources, including messages, documents, and comments, represent their content as rich text in HTML. Rich text content may contain lists, block quotes, simple formatting, and inline attachments such as mentions, images, and files.


Working with rich text HTML
---------------------------

If your application reads Basecamp rich text content, it must be able to process HTML. Use a web view component to render rich text content unmodified. Or, if your application needs a plain-text representation of rich text content, first decode any HTML entities, then replace `<br>` tags with line breaks, and finally strip the remaining HTML tags.

Similarly, if your application writes rich text content, it must be able to generate well-formed HTML. At a minimum, this means properly encoding HTML entities and replacing line breaks with `<br>` tags.

Applications that modify existing rich text content should take special care not to discard any formatting or attachments during processing. Consider using a full HTML parser to manipulate rich text content. Libraries such as [Nokogiri](http://www.nokogiri.org) (Ruby) and [Cheerio](https://github.com/cheeriojs/cheerio) (Node.js) are good fits for this scenario.


Allowed HTML tags
-----------------

You may use the following standard HTML tags in rich text content: `div`, `br`, `strong`, `em`, `strike`, `a` (with an `href` attribute), `pre`, `ol`, `ul`, `li`, and `blockquote`. Any other tags will be removed automatically.

The special `<bc-attachment>` tag allows you to insert an inline attachment. Each `<bc-attachment>` has an `sgid` attribute which points to the `attachable_sgid` value of an attachable Basecamp resource. Your application will receive a rendered representation of the attachable resource inside the `<bc-attachment>` tag in API responses.


Inserting a mention
-------------------

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


Inserting an image or file attachment
-------------------------------------

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
