# Setup

One-time steps to get from "I forked this" to "my feed is live." Follow them
in order, then delete this file (or keep it around for future co-organizers
— it costs nothing to leave in place).

## 1. Fork

Click **Fork** on this repository. Fork — not "Use this template" — so you
can pull upstream improvements later:

```
git remote add upstream https://github.com/OpenTechEvents/ote-template
git pull upstream main
```

## 2. Enable workflows

GitHub disables Actions on forks by default. In your fork, open the
**Actions** tab and click **"I understand my workflows, go ahead and enable
them"**. Without this, nothing gets validated or published.

## 3. Enable GitHub Pages

In your fork: **Settings → Pages → Source: GitHub Actions**.

Once the first deploy finishes, link the site from your repo so visitors
find it: repo home → **About** (gear icon) → check **"Use your GitHub Pages
website"**.

**Custom domain?** If your Pages are served from your own domain instead of
`*.github.io`, the dashboard can't detect the repository from the URL.
Create a `docs/config.js` with one line:

```js
window.OTE_REPO = "your-user/your-repo";
```

## 4. Enable issues (optional, recommended)

GitHub disables Issues on forks by default. If you want the community to be
able to report mistakes or propose events — and to use the OTE editor's
"propose change" flow, which delivers changes as prefilled issues — enable
them: **Settings → General → Features → Issues**.

Then create the label the flow depends on — forks don't inherit labels, and
GitHub silently ignores missing labels declared in issue forms, so without
it proposed events never become pull requests. In your fork: **Issues →
Labels → New label**, name it exactly `ote-event`.

Finally, let Actions open the pull request: **Settings → Actions → General
→ Workflow permissions → check "Allow GitHub Actions to create and approve
pull requests"**. Without this, a proposed event validates and its branch is
pushed, but the workflow can't open the PR.

## 5. Make `README.md` and `CONTRIBUTING.md` your own

Both files ship as short skeletons meant to be replaced — say who you are,
what this calendar covers, where it's published, how to subscribe. There's
no fixed shape to follow; write what your community actually needs to read.

**This is the only step where you're expected to fully rewrite a file, and
it's a one-time thing**: from this commit on, upstream will never edit
`README.md` or `CONTRIBUTING.md` again in a future template release —
they're yours. `git pull upstream main` will keep working without ever
touching them, so there's nothing to reconcile later. Everything else in this
repo (workflows, `docs/index.html`, this file) stays upstream-owned and
updates safely the same way.

Community writes in Spanish? Start from [`i18n/README.es.md`](i18n/README.es.md)
and [`i18n/CONTRIBUTING.es.md`](i18n/CONTRIBUTING.es.md) instead of the
English default.

## 6. Configure `ote.config.json`

Open it — every field has an inline `_comment_*` explaining what it's for
and what to put there. Same principle as above: those are placeholders to
replace, not real defaults to leave in place.

## 7. Add your first event

See [`events/README.md`](events/README.md) for the format and a minimal
example. Every push validates your events and, if valid, rebuilds and
redeploys your site: dashboard + `feed.json` + `feed.ics` + `feed.xml` at
`https://<user>.github.io/<repo>/`. Deploys take a couple of minutes.

## 8. Make your feed discoverable

Add this to the `<head>` of your community's website (if you have one):

```html
<link rel="alternate" type="application/ote+json"
      href="https://<user>.github.io/<repo>/feed.json">
```

## 9. Register as an adopter

Add your community to the adopters list in
[opentechevents-spec](https://github.com/OpenTechEvents/opentechevents-spec)
so directories and users can find your feed.

## 10. Turn on the README badges (optional)

Near the top of your new `README.md`, uncomment the `Validate`/`Publish`/
`OTE feed` badges: replace `your-user/your-repo` with your fork in the
first two, and point the third at your own `feed.json` — it's a subscribe
button, so it has to lead straight to your feed, not to a page about OTE.

## Using an AI coding assistant on your fork

If you use Claude Code, Codex, Copilot or similar to help manage your fork,
paste this into whichever instructions file it reads (`CLAUDE.md`,
`AGENTS.md`, `.github/copilot-instructions.md`…) — it keeps the assistant
from "helpfully" adding logic that belongs in `ote-tools` instead of here:

```
This is a fork of a template that community organizers use. It should
contain ONLY: events/*.json (your data), ote.config.json (your
configuration), docs/ (a minimal static dashboard), and thin workflows that
call reusable workflows in OpenTechEvents/ote-tools.

It must NOT contain validation/export/UI logic — that lives in
OpenTechEvents/ote-tools. If a task asks you to add logic here, that's a
sign something is wrong: stop and ask before proceeding.

The workflows reference OpenTechEvents/ote-tools/.github/workflows/*.yml@main
(will pin to @v1 once stable).

Keep this repo simple enough that a co-organizer can understand it in five
minutes.
```

## Staying up to date

The thin workflows track `OpenTechEvents/ote-tools@main` (pinned to `@v1`
once stable), so validation and export improvements arrive automatically —
no action needed. For the few files upstream keeps maintaining directly
(workflows, `docs/index.html`, this file), pull from upstream whenever you
like:

```
git pull upstream main
```

Since `README.md` and `CONTRIBUTING.md` are yours from step 5 onward and
upstream never touches them again, this should never conflict. If it ever
does, keep your version of those two files (and of `ote.config.json`) and
take upstream's version of everything else.

## Done?

Delete this file — nothing else in the repo depends on it. Or keep it, for
the next person who helps run this feed.
