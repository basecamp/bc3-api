Notification settings
=====================

Endpoints for reading and updating the current user's notification preferences, including delivery platform, granularity, schedule, reminders, and snoozing.

Endpoints:

- [Get notification settings](#get-notification-settings)
- [Update notification settings](#update-notification-settings)
- [Snooze notifications](#snooze-notifications)


Get notification settings
-------------------------

* `GET /my/notifications/settings.json` will return the current user's notification settings.

###### Example JSON Response
<!-- START GET /my/notifications/settings.json -->
```json
{
  "platform": "web_and_email",
  "granularity": "everything",
  "show_badge_counts": true,
  "schedule_enabled": false,
  "schedule": null,
  "bundle_enabled": true,
  "schedule_entries_reminders": true,
  "due_assignments_reminders": true,
  "state": "on"
}
```
<!-- END GET /my/notifications/settings.json -->

When `schedule_enabled` is `true`, the `schedule` object is included:

```json
{
  "schedule_enabled": true,
  "schedule": {
    "start_hour": 9,
    "end_hour": 17,
    "work_days": [1, 2, 3, 4, 5]
  }
}
```

###### Copy as cURL

```shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecampapi.com/$ACCOUNT_ID/my/notifications/settings.json
```


Update notification settings
----------------------------

* `PUT /my/notifications/settings.json` will update the current user's notification settings. Only the provided parameters are changed; omitted parameters remain unchanged. Returns `204 No Content` on success.

_Optional parameters_:

* `platform` - delivery platform. Valid options: `web`, `email`, `web_and_email`.
* `granularity` - notification granularity. Valid options: `everything`, `pings_and_mentions`.
* `show_badge_counts` - whether to show badge counts. JSON `true` or `false` (not strings).
* `schedule_enabled` - whether the notification schedule is active. JSON `true` or `false` (not strings). When `true`, also provide `schedule`.
* `schedule` - an object with `start_hour` (integer 0–23), `end_hour` (integer 0–23, must be greater than `start_hour`), and `work_days` (non-empty array of integers, 0=Sunday through 6=Saturday).
* `bundle_enabled` - whether notification bundling is enabled. JSON `true` or `false` (not strings).
* `reminders` - an array of reminder types to enable. Valid values: `schedule_entries`, `due_assignments`. Pass an empty array to disable all reminders. These correspond to the `schedule_entries_reminders` and `due_assignments_reminders` boolean fields in the GET response.

Providing an invalid `platform` or `granularity` returns `422 Unprocessable Entity` with an error listing the valid options:

```json
{
  "errors": ["Invalid platform 'carrier_pigeon'. Valid options: web, email, web_and_email"]
}
```

###### Example JSON Request
<!-- START PUT PAYLOAD /my/notifications/settings.json -->
```json
{
  "platform": "email",
  "granularity": "pings_and_mentions",
  "schedule_enabled": true,
  "schedule": {
    "start_hour": 9,
    "end_hour": 17,
    "work_days": [1, 2, 3, 4, 5]
  },
  "bundle_enabled": true,
  "reminders": ["schedule_entries", "due_assignments"]
}
```
<!-- END PUT PAYLOAD /my/notifications/settings.json -->

###### Copy as cURL

```shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -H "Content-Type: application/json" \
  -d '{"platform":"email","granularity":"pings_and_mentions"}' -X PUT \
  https://3.basecampapi.com/$ACCOUNT_ID/my/notifications/settings.json
```


Snooze notifications
--------------------

* `PUT /my/notifications/snooze.json` will snooze the current user's notifications for the given duration. Returns `200 OK` with the snooze state.

**Required parameters**:

* `duration` - a positive integer representing the number of seconds to snooze notifications.

###### Example JSON Response
<!-- START PUT /my/notifications/snooze.json -->
```json
{
  "state": "snoozed",
  "off_until": "2024-12-05T15:00:00Z"
}
```
<!-- END PUT /my/notifications/snooze.json -->

###### Example JSON Request
<!-- START PUT PAYLOAD /my/notifications/snooze.json -->
```json
{
  "duration": 10800
}
```
<!-- END PUT PAYLOAD /my/notifications/snooze.json -->

###### Copy as cURL

```shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" -H "Content-Type: application/json" \
  -d '{"duration":10800}' -X PUT \
  https://3.basecampapi.com/$ACCOUNT_ID/my/notifications/snooze.json
```
