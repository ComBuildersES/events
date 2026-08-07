This folder holds your events — one JSON file per event, any file name.

```json
{
  "specVersion": "0.3.0",
  "id": "https://your-community.example/events/2026-09-meetup",
  "name": "September meetup",
  "startDate": "2026-09-24T19:00",
  "timezone": "Europe/Madrid",
  "license": "CC0-1.0"
}
```

Only `*.json` files are read — this `README.md` is ignored by the build. Full
field reference: [opentechevents.org/spec](https://opentechevents.org/spec/).

Keep at least one file here (this one is enough) even before you've added
your first event. Git doesn't track empty directories, and this folder
disappearing entirely used to break the build — fixed upstream in
[ote-tools#23](https://github.com/OpenTechEvents/ote-tools/issues/23), but
keeping a placeholder here is still good practice if your fork ever pins to
an older `ote-tools` ref.
