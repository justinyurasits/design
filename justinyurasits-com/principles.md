---
type: principles
status: draft
---

# JustinYurasits.com — Principles

What building the site has taught, each principle anchored to the incident behind it and
to where it's enforced. **All three are candidates** from the roll-up of
`justinyurasits.github.io` #35–#50. Justin approves them by merging the PR that adds them.

## 1. A claim is checkable only if it's rendered from its source

A rule like "every claim traces to the register" holds only for claims the page renders
from the register. A free-text field next to it is unchecked, however careful the
author is.

- **Learned from:** About (JYC-CAP-07, [#45](https://github.com/justinyurasits/justinyurasits.github.io/pull/45), 2026-11-22). Experience entries had a free-text
  `title`, so an employer or role title could be typed in with no check against the
  register. The fix makes entries name register keys, and the page renders them.
- **Rules that follow:**
  - Claims about Justin or his products are rendered through `<Fact>` or `<Status>` and
    marked `data-fact` or `data-status`.
  - Schemas don't offer a free-text field where a register fact belongs.
- **Enforced in:** `scripts/check.mjs` (fact and status drift, unknown keys) and the
  experience schema in `src/content.config.ts`.

## 2. Check what the visitor gets, all the way to the end

Check the built site, and follow every link to its final destination and anchor.
Checking that a file exists, or that a source field is set, misses what breaks in
between.

- **Learned from:**
  - The preserved-links check ([#50](https://github.com/justinyurasits/justinyurasits.github.io/pull/50), 2026-11-22). Renaming a product moves
    its anchor on the Construction OS page. Every redirect file still exists, but the old
    `/products/…` address no longer lands anywhere. Only following the redirect to its
    anchor catches it.
  - The link check ([#41](https://github.com/justinyurasits/justinyurasits.github.io/pull/41)) caught a link to a feed that didn't exist yet.
- **Rules that follow:**
  - Checks run on `dist/`, after the build.
  - Redirects are followed hop by hop to a real page, and anchors are confirmed on it.
  - A browser test proves a redirect actually lands.
- **Enforced in:** `scripts/check.mjs` (links, anchors, preserved links) and
  `tests/redirects.test.mjs`.

## 3. Tests that run in parallel share nothing

Each test gets its own copy of every cache, port and process it uses, and cleans up
everything it starts.

- **Learned from:** three incidents in one milestone, all 2026-11-22.
  - A content cache shared through a symlinked `node_modules` failed a test in CI that
    passed locally ([#41](https://github.com/justinyurasits/justinyurasits.github.io/pull/41)).
  - Killing `npm` left a dev server running that hung CI for 10 minutes
    ([#43](https://github.com/justinyurasits/justinyurasits.github.io/pull/43)).
  - Random ports collided under four parallel builds ([#49](https://github.com/justinyurasits/justinyurasits.github.io/pull/49)).
- **Rules that follow:**
  - Caches live in the project (`cacheDir: './.astro/cache'`).
  - Ports come from the OS (`freePort()`).
  - A spawned server runs in its own process group, and the whole group is stopped.
  - Every long test, and the CI job, has a timeout.
- **Enforced in:** `astro.config.mjs`, `tests/harness.mjs`, `tests/browser.mjs`, and the
  `timeout-minutes` in `.github/workflows/ci.yml`.
