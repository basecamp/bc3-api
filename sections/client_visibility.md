Client visibility
=================

The client visibility refers to [the newer way to work with clients in Basecamp 3][1], and not to the _Clientside_, which is covered in its own sections: [approvals][2], [correspondences][3] and [replies][4].

Endpoints:

- [Toggle client visibility](#toggle-client-visibility)

Toggle client visibility
------------------------

* `PUT /buckets/1/recordings/2/client_visibility.json` allows changing the client visibility for the recording with an ID of `2` in the project with ID `1`.

**Required parameter**: `visible_to_clients` with value `true` or `false`.

This endpoint will return `200 OK` with the current JSON representation of the recording if the update was a success. Notice that not all recordings allow toggling client visibility, some inherit the visibility of their parent. For example, individual to-dos inherit the visibility of the to-do list they belong to. This endpoint will return `403 Forbidden` if the recording provided doesn't control its client visibility.

###### Example JSON Request

``` json
{
  "visible_to_clients": true
}
```

###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -H "Content-Type: application/json" \
  -d '{"visible_to_clients":true}' -X PUT \
  https://3.basecampapi.com/$ACCOUNT_ID/buckets/1/recordings/2/client_visibility.json
```

[1]: https://m.signalvnoise.com/launch-a-brand-new-way-to-work-with-clients-in-basecamp-3-6a78b1175c5d
[2]: https://github.com/basecamp/bc3-api/blob/master/sections/client_approvals.md
[3]: https://github.com/basecamp/bc3-api/blob/master/sections/client_correspondences.md
[4]: https://github.com/basecamp/bc3-api/blob/master/sections/client_replies.md
