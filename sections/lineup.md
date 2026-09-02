Lineup
======

The Lineup plots every scheduled project on a single account-wide timeline, together with the [markers](lineup_markers.md#lineup-markers) that annotate it. These endpoints expose that read model and let you read and edit an individual project's start/end dates.

Endpoints:

- [Get the lineup](#get-the-lineup)
- [Get a project's schedule](#get-a-projects-schedule)
- [Update a project's schedule](#update-a-projects-schedule)


Get the lineup
--------------

* `GET /lineup.json` returns the projects scheduled within a timeframe, each with its schedule range, plus the account's markers in that timeframe.

Pass an optional `timeframe` parameter formatted as `START..END` (two ISO 8601 dates joined by `..`) to bound the window. When omitted, the timeframe is centered on the current week, spanning six weeks on either side — the same default the web Lineup uses.

Only projects the authenticated person can access are returned. Markers are omitted for client users.

###### Example JSON Response
<!-- START GET /lineup.json -->
```json
{
  "timeframe": {
    "start_date": "2026-07-20",
    "end_date": "2026-10-18"
  },
  "projects": [
    {
      "id": 2085958499,
      "name": "The Leto Laptop",
      "purpose": "topic",
      "schedule_start_date": "2026-08-03",
      "schedule_end_date": "2026-09-14",
      "schedule_status": "ongoing",
      "url": "https://3.basecampapi.com/195539477/projects/2085958499.json",
      "app_url": "https://3.basecamp.com/195539477/projects/2085958499",
      "schedule_url": "https://3.basecampapi.com/195539477/lineup/projects/2085958499/schedule.json"
    }
  ],
  "markers": [
    {
      "id": 6750828,
      "name": "Spring kickoff",
      "date": "2026-08-31",
      "title": "Aug 31: Spring kickoff"
    }
  ]
}
```
<!-- END GET /lineup.json -->

`schedule_status` is one of `ongoing`, `past`, or `future`, relative to today.

###### Copy as cURL

```shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" \
  "https://3.basecampapi.com/$ACCOUNT_ID/lineup.json?timeframe=2026-07-20..2026-10-18"
```


Get a project's schedule
------------------------

* `GET /lineup/projects/1/schedule.json` returns the start and end dates for the project with an ID of `1`.

Only available on regular (topic) projects. Client users are forbidden.

###### Example JSON Response
<!-- START GET /lineup/projects/1/schedule.json -->
```json
{
  "project_id": 2085958499,
  "start_date": "2026-08-03",
  "end_date": "2026-09-14",
  "status": "ongoing",
  "url": "https://3.basecampapi.com/195539477/lineup/projects/2085958499/schedule.json",
  "app_url": "https://3.basecamp.com/195539477/lineup/projects/2085958499/schedule"
}
```
<!-- END GET /lineup/projects/1/schedule.json -->

When the project has no dates set, `start_date`, `end_date`, and `status` are `null`.

###### Copy as cURL

```shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" \
  https://3.basecampapi.com/$ACCOUNT_ID/lineup/projects/1/schedule.json
```


Update a project's schedule
---------------------------

* `PUT /lineup/projects/1/schedule.json` sets the start and end dates for the project with an ID of `1`.

**Required parameters**, nested under `project` → `schedule_attributes`:

* `start_date` — the project's start date, ISO 8601 formatted without a time part.
* `end_date` — the project's end date, ISO 8601 formatted without a time part. Must not fall before `start_date`.

This endpoint returns `200 OK` with the same representation as [Get a project's schedule](#get-a-projects-schedule) on success, or `422 Unprocessable Entity` with an `errors` object when the dates are invalid.

Editing a project's dates is a project change, so it is forbidden for clients and for teammates who cannot edit the project.

###### Example JSON Request

```json
{
  "project": {
    "schedule_attributes": {
      "start_date": "2026-08-03",
      "end_date": "2026-09-14"
    }
  }
}
```

###### Copy as cURL

```shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -H "Content-Type: application/json" \
  -d '{"project":{"schedule_attributes":{"start_date":"2026-08-03","end_date":"2026-09-14"}}}' \
  -X PUT https://3.basecampapi.com/$ACCOUNT_ID/lineup/projects/1/schedule.json
```
