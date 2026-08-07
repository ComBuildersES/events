# Contributing

Thanks for helping keep this event feed accurate! A few ways to help, from
easiest to most technical.

## 1. Add a missing event

Fill in the form — no git, no JSON, no write access needed:

**👉 [Open the OTE editor](https://tools.opentechevents.org/editor?repo=your-user/your-repo)**

It generates the event data for you and opens a prefilled issue in this
repository. A workflow validates it and turns it into a pull request; a
maintainer reviews and merges it. Minutes later, it's published.

## 2. Report a mistake

Wrong date, broken link, venue changed, event cancelled? [Open an
issue](../../issues/new/choose) describing what's wrong. Small fixes are
welcome — don't sit on one because it seems minor.

## 3. Fix it yourself with a pull request

Events are one JSON file per event in [events/](events/) — see
[events/README.md](events/README.md) for the format and a minimal example.

Every pull request is validated automatically against the OTE spec, so you
can't break the published feed: if validation fails, the PR tells you
exactly what's wrong, and nothing publishes until it passes and someone
merges it.

## 4. Spread the word

A real contribution, and it needs no GitHub account at all: share the
events, add the feed to your own community's calendar, or republish the
data on your site. See [Reuse the data](README.md#reuse-the-data) in the
README for the license and the feed URLs.

## License of what you contribute

Event data in this repository is published under the license declared in
[ote.config.json](ote.config.json). By contributing an event, you agree it's
published under that license: reusable, republishable and buildable-upon by
anyone, without asking permission.

So only submit event information you can publish on those terms — public
facts (title, date, venue, public links), not material someone shared with
you privately, and not text copied from a page under a more restrictive
license.
