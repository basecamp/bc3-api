Attachments
===========

Endpoints:

- [Create an attachment](#create-an-attachment)


Create an attachment
--------------------

* `POST /attachments.json` uploads a file.

**Required request data**: The request body should be the file's raw binary data.

**Required request headers**: `Content-Type` and `Content-Length` for to the file.

**Required URI query parameters**: `name` as the file name.

This endpoint will return `201 Created` with the attachment's `attachable_sgid` in the JSON representation.

###### Example JSON Response

```json
{
  "attachable_sgid": "BAh2CEkiCGdpZAY6BkVUSSIsZ2lkOi7vYmMzL0F0dGFjaG1lbnQvNzM4NDcyNj9leHBpcmVzX2luBjsAVEkiDHB1cnBvc2UGOwBUSSIPYXR0YWNoYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--13982201abe18044c897e32979c7dccfe8add9c1"
}
```

When you get this response you can use the sgid at other places like a comment like this:

```json
{
  "content": "<div>This could be a random comment.<br><br><bc-attachment sgid="BAh2CEkiCGdpZAY6BkVUSSIsZ2lkOi7vYmMzL0F0dGFjaG1lbnQvNzM4NDcyNj9leHBpcmVzX2luBjsAVEkiDHB1cnBvc2UGOwBUSSIPYXR0YWNoYWJsZQY7AFRJIg9leHBpcmVzX2F0BjsAVDA=--13982201abe18044c897e32979c7dccfe8add9c1"></bc-attachment></div>"
};
```

###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" \
  --data-binary @pizza.png \
  -H "Content-Type: image/png" -H "Content-Length: 123" \
  https://3.basecampapi.com/$ACCOUNT_ID/attachments.json?name=pizza.png  
```
