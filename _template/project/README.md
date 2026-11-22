---
type: readme
status: draft
---

# Project name

*One or two sentences: what this is, who it's for, and the first thing it does.*

This folder holds the product-level docs. Each component has its own folder.

## Where things stand

| | Designed | Built | Validated |
| --- | --- | --- | --- |
| *<capability>* | *✓ / —* | *✓ / —* | *✓ / Partial — what was checked / —* |

Nothing here is claimed as working until it is. An evaluation set written is not
an evaluation run.

## Product-level docs

| File | What it is |
| --- | --- |
| [brief.md](brief.md) | Who it's for, the painful moment, what it replaces, what's out of scope. Every decision is checked against it. Required. |
| [principles.md](principles.md) | *Optional.* What building this taught, each principle tied to the incident behind it and where it's enforced. |
| [product-spec.md](product-spec.md) | *Optional, needed once a project's components make up one product. A project that groups independent builds has none.* What the product must do for its users: capabilities with stable IDs (`PRJ-CAP-01`), journeys, acceptance criteria. |
| [architecture.md](architecture.md) | *Optional, needed once a product has more than one component. A single-component product, or a group of independent builds, has none.* How the components fit together and how a request moves through them. |

## Components

| Component | Folder | What it is |
| --- | --- | --- |
| *<Component name>* | [component/](component/) | *One sentence: its job, and the first slice it builds.* |

## Repositories

| Repository | What it holds |
| --- | --- |
| *[`<product>-<part>`](https://github.com/justinyurasits/<product>-<part>)* | *Code, content or data, and whether it's public. Its README links back here.* |

## How these docs work

Synced files are written in Claude Docs and synced here by pull request; each starts
with a link to its source and is never edited by hand. `sync-manifest.yaml` records
the source and revision of each. Files without a sync header, like this README, are
written in the repo.
