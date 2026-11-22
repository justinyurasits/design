---
type: readme
status: draft
---

# JustinYurasits.com

Justin's personal website: the home for his writing, AI projects and consulting, for
enterprise AI buyers and construction leaders. Writing comes first; projects back it with
evidence, and consulting gives each audience a way to start a conversation.

This folder holds the product-level docs. Each component has its own folder.

## Where things stand

Brief and product spec in draft. The tech stack is decided, in the site's design doc.
Nothing is built or validated yet; v2 is being built on the `v2` branch of
[`justinyurasits.github.io`](https://github.com/justinyurasits/justinyurasits.github.io).

| | Designed | Built | Validated |
| --- | --- | --- | --- |
| — | — | — | — |

Nothing here is claimed as working until it is.

## Product-level docs

| File | What it is |
| --- | --- |
| [brief.md](brief.md) | Who the site is for, what it replaces, what's out of scope. Draft. |
| [product-spec.md](product-spec.md) | What the site must do: capabilities JYC-CAP-01 to 09 with acceptance criteria, journeys for each test persona, and product-wide requirements. Draft; two open questions. |

With one component there's no architecture doc; the site's design doc covers how it
works.

## Components

| Component | Folder | What it is |
| --- | --- | --- |
| Site | [site/](site/) | The website: pages, the writing library, project case studies and the publishing workflow. |

## Repositories

| Repository | What it holds |
| --- | --- |
| [`justinyurasits.github.io`](https://github.com/justinyurasits/justinyurasits.github.io) | The site's code and content. Public. `main` is the live Construction OS site until the v2 cutover; v2 is built on the `v2` branch. |

## How these docs work

All files here are written in this repo and edited by pull request; none is synced from
Claude Docs yet. `sync-manifest.yaml` will record the source and revision of any that
are.
