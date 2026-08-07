# <Your community name>

<!--
Uncomment these once you've finished SETUP.md: replace your-user/your-repo
with your fork in the first two, and point the third one at your own
feed.json (it's a subscribe button, not a status indicator — it must lead
straight to something that resolves):

[![Validate](https://github.com/your-user/your-repo/actions/workflows/validate.yml/badge.svg)](https://github.com/your-user/your-repo/actions/workflows/validate.yml)
[![Publish](https://github.com/your-user/your-repo/actions/workflows/publish.yml/badge.svg)](https://github.com/your-user/your-repo/actions/workflows/publish.yml)
[![OTE feed](https://opentechevents.org/badge/ote-feed.svg)](https://your-user.github.io/your-repo/feed.json)
-->

<!-- New fork? The one-time setup guide is in SETUP.md. -->

Describe what type of events this feed includes — talks, meetups, workshops,
conferences…

**👉 [See what's coming up](https://your-user.github.io/your-repo/)**

## Subscribe

| Format | URL | For |
| --- | --- | --- |
| iCalendar | [`feed.ics`](https://your-user.github.io/your-repo/feed.ics) | Add it to Google Calendar, Apple Calendar or Outlook — new events show up on their own |
| RSS | [`feed.xml`](https://your-user.github.io/your-repo/feed.xml) | Follow it from any feed reader |
| JSON | [`feed.json`](https://your-user.github.io/your-repo/feed.json) | Build something with it — the machine-readable [OTE](https://opentechevents.org/spec/) feed |

For the calendar formats, look for "subscribe by **URL**" (not "import
file") and paste the `feed.ics` link — that way it stays in sync instead of
freezing at import time.

## Reuse the data

Event data in this repository is published under the license declared in
[`ote.config.json`](ote.config.json). Building a directory, a newsletter or
your own aggregator? Take what you need — republishing this feed is itself a
form of supporting this community.

## Contributing

Found a mistake, or want to add an event? See
[CONTRIBUTING.md](CONTRIBUTING.md).
