---
type: readme
status: current
---

# Design

The design docs for everything Justin builds: one folder per project, written while the
work is being built rather than reconstructed afterward. Code repositories don't keep
design docs; they read them from here.

## Projects

| Project | Folder | What it is |
| --- | --- | --- |
| Construction OS | [construction-os/](construction-os/) | A company-specific AI system for residential builders. Components: the [corpus](construction-os/corpus/) — the company's governed knowledge — the [document workbench](construction-os/document-workbench/) — retrieval, pricing and drafting — and the [intake router](construction-os/intake-router/), which classifies inbound messages and routes them to a workflow. |
| Agents | [agents/](agents/) | Small agents built to learn how agent loops work, starting with a job evaluator. Component: the job evaluator. Code in [`agents`](https://github.com/justinyurasits/agents). |
| Construction OS demos | [construction-os-demos/](construction-os-demos/) | Standalone tools in the same domain: Fieldscope (subcontractor safety compliance) and the PCO Generator (live at draftconstructionchangeorder.com). |
| JustinYurasits.com | [justinyurasits-com/](justinyurasits-com/) | Justin's personal website: writing, AI projects and consulting for enterprise AI and construction audiences. Brief in draft. |

Visual design (colors, type, marks, components) is the one exception. It lives in
[`brand-system`](https://github.com/justinyurasits/brand-system), and design docs that
need a visual rule point there.

## How it works

```mermaid
flowchart LR
    CD["Claude Docs<br/>Editable design sources"]

    subgraph DESIGN["Design repository"]
        P["Project<br/>Brief · Product spec · Architecture"]
        C["Component<br/>Spec · Design · Plan · Build log"]
        G["STANDARD.md<br/>Templates · Validator"]
        P --> C
        G -. governs .-> P
        G -. governs .-> C
    end

    subgraph CODE["Code repository"]
        I["Approved GitHub issue"]
        PR["Code · Tests · Pull request"]
        I --> PR
    end

    H["Human review<br/>Decisions · Merge"]

    CD -->|"Sync by PR"| P
    CD -->|"Sync by PR"| C
    C -->|"Requirements & constraints"| I
    PR --> H
    H -.->|"Roll-up: synced docs<br/>(+ drift check)"| CD
    H -.->|"Roll-up: repo-authored docs<br/>(design PR)"| C
    G -. starts new .-> CODE
```

**1. A project is a folder; a component is a subfolder.** Every component has the same
files from the day it's created: README, brief, spec, design, plan, build log, sync
manifest, images. A project adds a brief and, as it grows, principles, a product spec and
an architecture doc. Every file has one job.

**2. Docs are written in Claude Docs or here.** Most are drafted in a Claude Doc and
synced into this repo by pull request, so the history shows what changed and when. The
Claude Doc is the working copy; the file here is the reviewed record and is never edited
by hand. A few docs, like the agents docs, are written here directly, also by pull
request.

**3. Code repos read from here.** Each code repository's `CLAUDE.md` points Claude Code
at its project and component folder and says what to read first. Design leads, code
follows: a change to what the product does is made here (or in its Claude Doc) first,
and the code pull request cites it.

**4. Work runs through GitHub.** The issue is the plan. Each pull request records the
small decisions made while coding and what the work taught. Every so often, Claude Code
asks to roll those up into the component's design log and build log, and checks whether
any Claude Doc has moved ahead of its synced copy. Nothing enters the record without
Justin's approval.

**5. The structure is checked.** `python tools/validate.py` runs on every pull request
and fails if a project or component is missing a file or a sync record is wrong.

The rules behind all of this are in [STANDARD.md](STANDARD.md). Where this page and the standard differ, the standard is right.

## A change, start to finish

Here is one change all the way through: you decide the product should do something new.
Small work that fits the existing design (a bug, a refactor) starts at step 3.

```mermaid
sequenceDiagram
    actor J as Justin
    participant CD as Claude Doc
    participant D as design repo
    participant GH as GitHub issue
    participant CR as code repo (Claude Code)

    J->>CD: 1. Write the change (spec, design or product spec)
    CD->>D: 2. Sync PR: doc + manifest + DOCS.md
    J->>D: Review and merge
    J->>GH: 3. Open the issue, citing the design
    CR->>D: 4. Read CLAUDE.md, then the design docs
    CR->>GH: Read the issue
    CR->>CR: Branch, code, tests, checks
    Note over CR,D: Design gap? Stop, propose it, back to step 1
    CR->>GH: 5. Pull request: decisions + build notes
    J->>CR: Review and merge (closes the issue)
    CR->>CD: 6. Roll-up: decisions, findings, lessons (as suggestions)
    J->>CD: Accept what's right
    CD->>D: Sync PR, as in step 2
```

| Step | Who | Where | What changes |
| --- | --- | --- | --- |
| **1. Decide** | You, with Claude in chat | The Claude Doc | The component's `spec` (what it must do) or `design` (how), or the project's `product-spec`. Its revision goes up. Nothing in any repo changes yet. |
| **2. Sync** | Claude | A PR in `design` | The doc's file in its folder, the folder's `sync-manifest.yaml` (new revision), `DOCS.md` (rebuilt by `tools/build_docs.py`). The validator runs; you merge. If the change adds work, `plan.md` gets a milestone the same way. |
| **3. Plan the work** | You, or Claude from the plan | A GitHub issue in the code repo | Nothing in `design`. The issue says what to build, cites the design section it follows, and lists the acceptance criteria. The issue is the plan. |
| **4. Build** | Claude Code | A branch `issue-<N>-…` in the code repo | Code and tests. Claude Code reads its `CLAUDE.md`, then the design in order (brief, spec, design, plan), then the issue. If the design is silent or wrong, it stops and proposes the change: back to step 1. It never edits design docs in a code PR. |
| **5. Review** | Claude Code opens it, you merge | The PR | The PR records **Decisions (proposed)**, the implementation choices made while coding, and **Build notes**, what happened and what it taught. The checks run. Merging approves the decisions and closes the issue. |
| **6. Roll up** | Claude Code proposes, you approve | Back in the Claude Docs (or a `design` PR) | The component's `design.md` decision log gets the decisions; its `build-log.md` gets the findings; the project's `principles.md` gets any lesson that generalizes. A finished milestone leaves `plan.md`. For synced docs these arrive as suggestions in the Claude Doc, then sync as in step 2; for repo-authored docs, as a PR in `design`. The roll-up also flags any Claude Doc that has moved ahead of its synced copy. |

**When each design file changes**

| File | Changes when |
| --- | --- |
| `spec.md`, `product-spec.md` | You decide what the product must do differently (step 1) |
| `design.md` | You change how it works (step 1), or a roll-up adds decisions (step 6) |
| `plan.md` | Work is added (step 2) or a milestone finishes (step 6) |
| `build-log.md` | Every roll-up (step 6) |
| `principles.md` | A roll-up finds a lesson that generalizes (step 6) |
| `brief.md` | Rarely: who it's for or why changes |
| `sync-manifest.yaml`, `DOCS.md` | Every sync |

## The files at the top

| File | Its one job |
| --- | --- |
| `README.md` | This page: what the repo is and how it works. |
| [`STANDARD.md`](STANDARD.md) | The rulebook. Every file type and its job, naming, front matter, and the rules for how design and code work together. When this page and the standard differ, the standard is right. |
| [`CLAUDE.md`](CLAUDE.md) | Instructions for Claude Code working in this repository. |
| [`DOCS.md`](DOCS.md) | An index of every synced doc: its Claude Doc link, where it syncs to, revision and date. Rebuilt from the manifests by `python tools/build_docs.py`; never edited by hand. |
| `sync-manifest.yaml` | The sync record for the files at the top (today, `STANDARD.md`). Every folder with synced files has one. |
| [`_template/`](_template/) | The standard as files: `project/`, `component/`, and `repo/` (what every code repository starts with). |
| `tools/validate.py` | The structure check. |
| `tools/build_docs.py` | Rebuilds DOCS.md from the sync manifests. Run it after any sync. |

## Adding something

- **A project:** copy `_template/project/`, rename it, fill it in, and add a row to the
  table above.
- **A component:** copy `_template/component/` into the project and list it in the
  project README.
- **A code repository:** copy `_template/repo/` into it and fill in section 7 of its
  `CLAUDE.md`.

Every change is a branch and a pull request. Never commit to main.
