---
type: readme
status: draft
---

# Site

The website itself: pages, the writing library, project case studies and the publishing
workflow. Today it is the whole product.

Product-level docs are one folder up, in [../](../).

## Where things stand

M0 and M1 are built on the `v2` branch ([roll-up #35–#50](build-log.md)):
- Every capability, JYC-CAP-01 to 09, has neutral styling and `[COPY]` slots.
- The site checks and CI are in, and all 16 old addresses are preserved.
- On `v2`: `npm run check` passes on 25 pages, and 85 tests pass.

Not live yet: `main` is still the old site until the M2 cutover. Not built: the visual
design, copy and launch articles (M2). One M0 item is open: the metric bases ([#13](https://github.com/justinyurasits/justinyurasits.github.io/issues/13)).

**Code:** [`justinyurasits.github.io`](https://github.com/justinyurasits/justinyurasits.github.io),
`v2` branch until cutover. Its CLAUDE.md points back to this folder.

## The docs

| File | What it is |
| --- | --- |
| [brief.md](brief.md) | A pointer to the product brief, which covers the site. |
| [spec.md](spec.md) | A pointer to the product spec, which covers the site. |
| [design.md](design.md) | How it works, its boundaries, and the decision log. Holds the tech stack and the repository overrides. Draft. |
| [plan.md](plan.md) | What's left: M0.5 and M2, each with its exit criterion and GitHub milestone. |
| [build-log.md](build-log.md) | What happened, in order, and what each finding changed. M0 and M1 so far. |

All of these are written in this repo; none is synced from Claude Docs yet.
