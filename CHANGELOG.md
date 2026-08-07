# Changelog

Notable changes to the OTE template — the files that live in *your* fork
(dashboard, thin workflows, issue templates, docs). Improvements to validation
and exports arrive automatically via `OpenTechEvents/ote-tools` and are **not**
tracked here.

This file, together with the [`VERSION`](VERSION) marker, is what the dashboard
reads to tell you a newer template is available and what it changed. To pull an
update in: `git pull upstream main` (see *Staying up to date* in `SETUP.md`,
or below if you've already deleted it).

The format follows [Keep a Changelog](https://keepachangelog.com/en/1.1.0/);
versions follow [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

**This version number is unrelated to the OTE spec's own `specVersion`**
(currently `0.3.0`, tracked in
[opentechevents-spec](https://github.com/OpenTechEvents/opentechevents-spec)).
They're two independent axes that happen to share small numbers right now —
this file versions the template repo (dashboard, workflows, docs), the spec
versions the data format. A template release never implies a schema bump, or
the other way around.

## [0.6.0] - 2026-08-07

Restructured around one principle: **every file has exactly one owner,
upstream or the fork, never both.** Prompted by a real fork
(`ComBuildersES/events`) that had to fully rewrite `README.md` and
`CONTRIBUTING.md` to be usable, and shipped with a `textLanguage: "en"`
default that didn't match its own content.

### Added
- `SETUP.md`: the one-time onboarding manual (enable Actions/Pages/Issues,
  create the `ote-event` label, register as an adopter, turn on badges…),
  upstream-owned. Read once, safe to delete. Absorbs the "Using an AI coding
  assistant" block and the update-from-upstream recipe that used to live in
  `README.md`.
- `i18n/README.es.md` and `i18n/CONTRIBUTING.es.md`: optional Spanish
  starting points for the two fork-owned files below, referenced from
  `SETUP.md`.

### Changed
- `README.md` and `CONTRIBUTING.md` are now minimal, fork-owned skeletons
  from the moment you fork — modeled on what `ComBuildersES/events`
  independently rewrote them into. **Upstream commits to never editing
  either file again in a future template release**, so `git pull upstream
  main` has nothing left to conflict with on them.
- `ote.config.json`: dropped the hardcoded `textLanguage: "en"` default —
  the field is optional and "absent = unknown, never English" was already
  the documented rule; shipping `"en"` anyway contradicted it. Also fixed
  two comments that referenced the sample events removed in 0.3.0.
- `events/README.md`: the `ote-tools#23` reference now reflects that it's
  fixed upstream, not still open.

### Evaluated, not done (tracked as `ote-tools` follow-ups)
- Warning (not failing) validation when `feed.url`/`organizers[].url` still
  ends in `.example`.
- A `dashboard-checks.js` banner for disabled Issues or a missing
  `ote-event` label.
- A "configure your feed" mode in the `ote-tools` editor, writing
  `ote.config.json` through the same propose-change/edit-directly pipeline
  events already use — preferred over a self-committing `workflow_dispatch`
  bootstrap in this repo, since the steps causing the most friction (enabling
  Issues/Pages, allowing Actions to open PRs) are repo *Settings* that the
  default `GITHUB_TOKEN` can't change regardless of mechanism.
- A `.gitattributes` `merge=ours` driver: skipped as the primary fix, since
  it requires `git config merge.ours.driver` set locally per clone and
  doesn't travel with the repository — the file-ownership split above makes
  it unnecessary rather than papering over it.

## [0.5.0] - 2026-08-07

### Removed
- `DESIGN.md`: a pre-implementation proposal doc (Spanish, "nothing
  implemented yet") that added nothing for an organizer and was already
  stale even in its canonical home, `OpenTechEvents/ote-tools` — phase 2
  (the central editor) is substantially built there already.
- `CLAUDE.md` as a shipped file. The guardrails it held (don't add
  validation/export/UI logic here, keep the repo simple, English is the
  official language) now live as a copy-paste block under a new README
  section, "Using an AI coding assistant on your fork" — tool-agnostic
  (`CLAUDE.md`, `AGENTS.md`, Copilot instructions…) instead of committing
  every fork to one assistant's file format.

## [0.4.1] - 2026-08-07

### Fixed
- The three README badges added in 0.4.0 now ship commented out instead of
  rendering broken by default: a broken badge is a fine nudge in your own
  fork, but it also made both the template's own README and every freshly
  forked one look broken before anyone had a chance to configure anything.
  Setup step 9 tells you where to uncomment and edit them.

## [0.4.0] - 2026-08-07

### Added
- README badges: `Validate` and `Publish` workflow status, and a dynamic
  `OTE spec` badge that reads the `specVersion` straight from your published
  `feed.json` (via shields.io) instead of a hardcoded number that could drift
  from what the workflows actually validate against. All three need
  `your-user/your-repo` replaced with your fork.

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
