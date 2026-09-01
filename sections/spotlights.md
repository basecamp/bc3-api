Spotlights
==========

A spotlight puts a recording's card on the home page of the project or template
it belongs to, alongside the tools. A spotlight doesn't change who can see the
recording: clients see a spotlight only when the recording is shared with them.
A recording can be spotlighted once, and only in its own project or template.

A spotlight isn't a resource of its own: it's a mark on the recording, like a
pin. Spotlighting a recording returns that recording, and the project's `dock`
array is unaffected, since spotlights aren't tools. See
[recordings](recordings.md) for the shape of a recording and
[Get a project](projects.md#get-a-project) for the dock.

Endpoints:

- [Spotlight a recording](#spotlight-a-recording)
- [Remove a spotlight](#remove-a-spotlight)


Spotlight a recording
---------------------

* `POST /recordings/2/spotlight.json` will spotlight the recording with an ID of
  `2` on the home page of its project or template.

No parameters are required. This endpoint returns `201 Created` with the
recording that was spotlighted. Spotlighting a recording that's already
spotlighted also returns `201 Created`.

Not every recording can be spotlighted: containers such as message boards and
to-do sets can't, nor can recordings that are archived or trashed. Those
requests return `422 Unprocessable Entity`.
Spotlighting also requires permission to edit the project, so clients and people
without that permission get `403 Forbidden`.

###### Copy as cURL

```shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -X POST \
  https://3.basecampapi.com/$ACCOUNT_ID/recordings/2/spotlight.json
```


Remove a spotlight
------------------

* `DELETE /recordings/2/spotlight.json` will remove the spotlight on the
  recording with an ID of `2`.

This endpoint returns `204 No Content`. Removing a spotlight that doesn't exist
also returns `204 No Content`.

###### Copy as cURL

```shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -X DELETE \
  https://3.basecampapi.com/$ACCOUNT_ID/recordings/2/spotlight.json
```


Legacy project-scoped routes
-----------------------------

The following project-scoped routes are still supported and will remain
available, but flat routes above are the canonical form for new integrations.

* `POST /buckets/1/recordings/2/spotlight.json` → [Spotlight a recording](#spotlight-a-recording)
* `DELETE /buckets/1/recordings/2/spotlight.json` → [Remove a spotlight](#remove-a-spotlight)
