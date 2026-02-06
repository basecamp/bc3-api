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
<!-- START POST /attachments.json -->
```json
{
  "id": 1046628526,
  "attachable_sgid": "BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiL2dpZDovL2JjMy9BdHRhY2htZW50LzEwNDY2Mjg1MjY_ZXhwaXJlc19pbgY7AFRJIghwdXIGOwBUSSIPYXR0YWNoYWJsZQY7AFQ=--56e38ec83681abfe01b6203ad23176a5d9fad093",
  "sgid": "BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiL2dpZDovL2JjMy9BdHRhY2htZW50LzEwNDY2Mjg1MjY_ZXhwaXJlc19pbgY7AFRJIghwdXIGOwBUSSIPYXR0YWNoYWJsZQY7AFQ=--56e38ec83681abfe01b6203ad23176a5d9fad093",
  "status_url": "https://3.basecampapi.com/195539477/attachments/BAh7BkkiC19yYWlscwY6BkVUewdJIglkYXRhBjsAVEkiL2dpZDovL2JjMy9BdHRhY2htZW50LzEwNDY2Mjg1MjY_ZXhwaXJlc19pbgY7AFRJIghwdXIGOwBUSSIPYXR0YWNoYWJsZQY7AFQ=--56e38ec83681abfe01b6203ad23176a5d9fad093.json",
  "caption": null,
  "byte_size": 1281,
  "content_type": "image/png",
  "width": 164,
  "height": 39,
  "key": "490857bc2f3fa187475e9ca1b891918df6ec400c",
  "filename": "company-logo.png",
  "download_url": "https://3.basecamp-static.com/195539477/blobs/490857bc2f3fa187475e9ca1b891918df6ec400c/download/company-logo.png",
  "previewable": true,
  "preview_url": "https://3.basecamp-static.com/195539477/blobs/490857bc2f3fa187475e9ca1b891918df6ec400c/previews/full",
  "thumbnail_url": "https://3.basecamp-static.com/195539477/blobs/490857bc2f3fa187475e9ca1b891918df6ec400c/previews/card"
}
```
<!-- END POST /attachments.json -->

###### Copy as cURL

```shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" \
  --data-binary @pizza.png \
  -H "Content-Type: image/png" -H "Content-Length: 123" \
  https://3.basecampapi.com/$ACCOUNT_ID/attachments.json?name=pizza.png  
```

Including attachments in rich text in other recordings
------------------------------------------------------

Check [Inserting an image or file attachment](https://github.com/basecamp/bc3-api/blob/master/sections/rich_text.md#inserting-an-image-or-file-attachment) for details on how to do this.
