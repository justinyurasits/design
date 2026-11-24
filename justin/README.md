---
type: readme
status: draft
---

# Justin

A pilot site about Justin doing AI for construction: his skills, his work, his
writing and his services in that field. It is the site he asked to see beside
the v2 site, so he can compare the two. The domain comes later.

This folder holds the product-level docs. The site is the only component.

Justin's words for this pilot (2026-11-24): "the new branch should be like 100%
focused on ai for construction as something i do. we can figure out the domain
later, i'm just going to want to see the demo."

## Where things stand

Design draft only. Nothing is built. The v2 site designed in
[justinyurasits-com/](../justinyurasits-com/) stays as it is, on the `v2` branch.
The live Construction OS site stays on `main`.

| | Designed | Built | Validated |
| --- | --- | --- | --- |
| Home, story, work, writing, services, contact (JUS-CAP-01 to 06) | Draft | — | — |
| A preview build Justin can open beside v2 | Draft | — | — |

Nothing here is claimed as working until it is.

## Product-level docs

| File | What it is |
| --- | --- |
| [brief.md](brief.md) | Who the pilot is for, how it differs from v2 and from the product site, and what's out of scope. Draft. |
| [product-spec.md](product-spec.md) | What the demo must do: capabilities JUS-CAP-01 to 07, journeys, acceptance criteria. Draft. |

With one component there is no architecture doc. The site's design doc covers
how it is put together. There is no principles doc yet: nothing has been built
here, so nothing has taught a lesson.

The visual design, when it is applied, is the personal sub-brand in
[`brand-system`](https://github.com/justinyurasits/brand-system/tree/main/brands/personal)
(BRAND-004). The first milestone is a readable preview, with neutral styling,
so Justin can judge the content. Colors, type and components stay in
brand-system.

Three decisions worth knowing, all proposed in the [site design log](site/design.md#4-decision-log)
until this pull request is merged:

- This is its own project. [justinyurasits-com/](../justinyurasits-com/) remains the design for v2.
- The pilot is only AI for construction. Construction OS is one piece of work, linked out.
- The first thing to build is a preview on a new branch. The domain is out of scope.

## Components

| Component | Folder | What it is |
| --- | --- | --- |
| Site | [site/](site/) | The preview site: pages, case studies, the writing library and the way Justin gets a build to look at. |

## Repositories

| Repository | What it holds |
| --- | --- |
| [`justinyurasits.github.io`](https://github.com/justinyurasits/justinyurasits.github.io) | The site's code, when the pilot is built, on a new branch `personal` taken from `main`. `main` is the live Construction OS site. `v2` is the other personal site. Neither branch is modified by this pilot. |

## How these docs work

All files here are written in this repo and edited by pull request. None is
synced from Claude Docs. `sync-manifest.yaml` records a source and revision
when one is. Repo-authored files carry `type` and `status` in front matter.
