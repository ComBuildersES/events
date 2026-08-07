# Changelog

Notable changes to the OTE template — the files that live in *your* fork
(dashboard, thin workflows, issue templates, docs). Improvements to validation
and exports arrive automatically via `OpenTechEvents/ote-tools` and are **not**
tracked here.

This file, together with the [`VERSION`](VERSION) marker, is what the dashboard
reads to tell you a newer template is available and what it changed. To pull an
update in: `git pull upstream main` (see the README's *Updates* section).

The format follows [Keep a Changelog](https://keepachangelog.com/en/1.1.0/);
versions follow [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [0.3.0] - 2026-08-07

### Removed
- The bundled GDG Sample City example events. `events/` ships empty again,
  with an `events/README.md` explaining the format and pointing to the spec
  reference.

### Changed
- `README.md`: "Replace the sample events" → "Add your events"; the license
  section no longer claims sample event data.

### Fixed
- `events/README.md` keeps the directory tracked by Git even with zero real
  events. An `events/` directory with no files at all isn't tracked by Git,
  and `ote-build-feed` currently treats a missing directory as a fatal error
  rather than zero events — see
  [ote-tools#23](https://github.com/OpenTechEvents/ote-tools/issues/23) for
  the upstream fix. Keeping this file in place sidesteps it either way.

## [0.2.0] - 2026-08-07

Sample data upgraded to OTE schema [v0.3.0](https://github.com/OpenTechEvents/opentechevents-spec/blob/main/CHANGELOG.md).

### Changed
- Replaced the generic sample events with a complete example: a GDG chapter
  running a monthly meetup series plus its annual conference, DevFest —
  `events/2026-08-monthly-meetup.json` and `events/2026-09-monthly-meetup.json`
  (two editions of the same series, linked via `partOf`),
  `events/2026-10-online-workshop.json` (co-organized) and
  `events/2026-11-devfest.json` (call for papers, ticket tiers, waitlist).
  Together they exercise the fields schema v0.3 added: `organizers`, `image`,
  `location.address`, `offers`, `cfp`, `partOf` and `translations`.
- `ote.config.json`: `feed.organizers` and `feed.textLanguage` set for the
  sample community; `profile` defaults to `all` since the samples mix a
  meetup and a conference.
- Bumped every sample event and the README's minimal-event example to
  `specVersion: "0.3.0"`.

## [0.1.0] - 2026-07-17

Phase 1 (MVP): fork → configure three values → a validated OTE feed with ICS/RSS
exports published on GitHub Pages.

### Added
- Thin workflows calling `ote-tools` reusable workflows: validate, publish
  (build Pages), and issue-to-PR.
- Static dashboard (`docs/index.html`) linking to the central tools, with the
  adopter-registry banner.
- `propose-event` issue form and the `ote-event` label contract.
- `ote.config.json`, sample events, `CONTRIBUTING.md`, and the setup guide.
- `VERSION` + this changelog, so the dashboard can surface template updates
  client-side.
