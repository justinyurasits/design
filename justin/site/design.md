---
type: design
status: draft
---

# Justin — Site Design

**Draft.** How the preview is put together, which facts it may show, and the
decisions proposed with it. The [product spec](../product-spec.md) says what a
reader can do. The [brief](../brief.md) says who it is for and
[how it differs from v2](../brief.md#7-how-this-differs-from-v2).

## 1. Scope and boundaries

| In scope now | Later |
| --- | --- |
| A preview on branch `personal`: Home, Story, Work and three case studies, an empty writing library, Work with me, Contact. Neutral styling. Register-backed claims. | JUS-CAP-07 publishing, after he has seen the preview |
| Links out to the live product site, the change order generator, and Fieldscope | BRAND-004, after the preview, if he wants the visual comparison too |
| | The domain, old addresses, and anything on `main` or `v2` |
| | Posts, the job evaluator, enterprise biography, services prose he has not written |

The preview is the whole of the first milestone. A page that is not in the
table is not in the preview.

## 2. How it works

A static site. Content files in, HTML out. Claims about Justin and his work
are rendered from one register, seeded from `content/facts.json` on `main`
plus the keys in the content model below. The branch builds in CI and uploads
the site as an artifact. It does not deploy.

### Information architecture

| Path | Page |
| --- | --- |
| `/` | Home |
| `/story/` | Story |
| `/work/` | Work index |
| `/work/construction-os/` | Construction OS case study |
| `/work/change-order-generator/` | Change order generator case study |
| `/work/fieldscope/` | Fieldscope case study |
| `/writing/` | Writing library |
| `/writing/<file-name>/` | A published piece, when one exists |
| `/work-with-me/` | Consulting, speaking, advising |
| `/contact/` | Contact |

The header is the wordmark "Justin Yurasits" (home), then Story, Work, Writing,
and Work with me as the action. Contact is not in the header. It is in the
footer and at the end of Work with me. v2's build log found that seven header
links wrap onto three lines at 375px. This header stays at four plus the action.

The footer on every page: Work with me, Contact, the email, LinkedIn, and
Privacy and Terms as absolute links to `https://justinyurasits.com/privacy.html`
and `https://justinyurasits.com/terms.html`.

There is no Solutions item, no Demos item, no Training item, and no About item.
The story is the about.

### Page structure

**Home.** Positioning, then What I do (story, work, writing), then Now (the
three works, one line each), then a Work with me line. No module grid and no
offer table.

**Story.** The residential-GC sentence. The license, the three years, the role,
the project scale, the contractor unnamed. The field-work sentence. The
legibility sentence. One attribution sentence for Construction OS, then a link
to the case study. The portrait.

**Work index.** Three cards, in the spec's order. Each card: name, one line,
maturity, demo, link to the case study.

**Case study.** Problem. What it is. Role and what he personally did. What a
visitor can open. Results from the register. Limitations and maturity. Links.

**Writing.** The empty state, in one sentence: "Writing on AI in construction.
Nothing is published yet." A published piece later: title, date, description,
body.

**Work with me.** Three sections, consulting, speaking, advising. Each has an
`[OPEN]` body until he writes it, and a contact link. Under them, one line and
a link: product offers live on the Construction OS engagements page.

**Contact.** Three email links, the booking link, LinkedIn. No form.

### Content model

The register starts as a copy of `content/facts.json` on `main`
(`justinyurasits.github.io`). The preview adds only the keys in the tables
below. It does not add enterprise employers. It does not render `pricing`.

`[OPEN]` is a visible placeholder. It is the words he has not supplied. It is
not filled in by the implementer.

**Positioning and story.** These sentences are already public. The preview
registers them with the source, and the page renders the key.

| Key | Text the page renders | Source |
| --- | --- | --- |
| `positioning.headline` | I build AI systems for construction, from inside a residential GC. | His pilot direction, plus the live homepage: "working inside a residential GC— not from taking a generic AI product and looking for a construction use case." |
| `positioning.support` | I build the systems I needed when I was the one producing the paperwork. | Live About page |
| `positioning.now` | I build operating systems for construction companies— configuring Construction OS around how a company actually works, or building something purpose-made when nothing off-the-shelf fits. | Live About page, "Today" |
| `positioning.fromTheWork` | Construction OS grew out of solving these problems while I was working inside a residential GC— not from taking a generic AI product and looking for a construction use case. | Live homepage |
| `story.fieldWork` | I've written the scopes, produced the change orders, managed trades, and been responsible for work in the field. | Live About page |
| `story.constructionRole` | Three years in residential construction as project manager and site superintendent. | Live About page |
| `story.legibility` | You can't automate what the business hasn't made legible. | Live About page |
| `credential` | licensed Massachusetts Construction Supervisor | `facts.json` on `main`. The live About page says "Massachusetts Construction Supervisor License" |
| `operatorScale` | $1M–$4M renovations at a $50 million contractor | `facts.json` on `main`, and the live About page. The contractor is not named |

The banned list in `facts.json` stays in force. The ones easiest to trip over
while writing this site: "AI-powered", "General Contractor license",
"Beacon Hill", "Wellen", "$30 million", "industry best practices",
"grounded in best practices", "first built and applied", "Custom Solutions",
"field photos", "Operational Architecture", "150+", "4–8 hrs", "CASE-001".
"General Contractor license" is banned. The license the page may state is the
Construction Supervisor license. "Inside a residential GC" is the homepage's
phrase and is allowed.

**Construction OS** (`/work/construction-os/`).

| Field | Value | Source |
| --- | --- | --- |
| What it is | A company-specific AI system for residential builders that understands how a company operates and produces the documents its PMs and superintendents need. It drafts and advises. People review, sign, send and decide. | [construction-os/README.md](../../construction-os/README.md), [brief](../../construction-os/brief.md) |
| Problem | A PM's documentation takes longer than the day has. The potential change order is the wedge. | [construction-os/brief.md](../../construction-os/brief.md) §2 and §4 |
| Role | `built` | [justinyurasits-com product spec](../../justinyurasits-com/product-spec.md), confirmed 2026-11-22 |
| `personallyDid` | Conceived and architected Construction OS and built its major components (the corpus, the Document Workbench and the intake router), drawing on my own construction document library. Ava Yurasits contributed to the build. | The same confirmation. The page does not say he built it alone |
| Library | `documentTypes` 110, `categories` 38, `lifecyclePhases` 5, `constructionSOPs` 160+, `pricingItems` 1258 | `facts.json` on `main` |
| Measured | Contract package, up to 8 hrs → ~30 min. Change order, ~10 days → ~3 days. Preliminary estimating, ~10 hrs → ~2 hrs. | `facts.json` `measured` |
| Usage | roughly twenty real jobs and bids | `facts.json` `usage`. This is the basis the register states. There is no separate per-metric basis |
| Product status | Document Workbench: Beta, demonstrable. Construction Intelligence: Beta, demonstrable. Operations Automation: One public demo, three live, four beta. Project Intelligence: In development | `facts.json` `products` |
| Validation limits, required on the page | Corpus and governance: built, policy verified against procedures only in part. PCO generation: built, not validated. Retrieval: in scope, lookup and search not yet designed, not built. Intake router: spec and classifier prompt written; the rest of its docs still in the build guide | [construction-os/README.md](../../construction-os/README.md) |
| Links | Live product home and the four product pages on justinyurasits.com. Public repo: [construction-os-workbench](https://github.com/justinyurasits/construction-os-workbench). Corpus repo: private, so "Private repository, walkthrough on request." and no URL | The repos' READMEs in this design repo |
| Maturity / demo | No single status for Construction OS. The page shows the four products' register statuses. Demo: the public change-order demo is the separate generator, linked from its own case study | `facts.json`, and the product spec note in justinyurasits-com §5 |
| Left off the page | Audit, Build, Monthly, and every fee. The six pain-point essays. Co-founder titles. The name of the contractor | This site's brief |

**Change order generator** (`/work/change-order-generator/`).

| Field | Value | Source |
| --- | --- | --- |
| What it is | Turns a description of a change into a formatted potential change order, as Word and PDF | [pco-generator README](../../construction-os-demos/pco-generator/README.md) |
| Problem | The decision is quick. Producing the document is what takes the time, and change work is where margin gets lost when nothing is authorized in writing | [pco-generator brief](../../construction-os-demos/pco-generator/brief.md) |
| Role | `built` | The README describes the system as his published work. `personallyDid` is `[OPEN]` until he writes the line. The confirmed Construction OS sentence is not reused here |
| Maturity | `live` at the public URL. The design record says built (v3), not validated | The README |
| Demo | `public` | https://draftconstructionchangeorder.com/ |
| Repository | Public, https://github.com/justinyurasits/pco-generator | The README |
| Limitation, required | In the live version the model writes every price and total, and nothing checks them. Moving the arithmetic into code is decided and not built | The README and its design log |
| Left off | Any claim that the prices are checked, any user count, any client name | Not documented |

**Fieldscope** (`/work/fieldscope/`).

| Field | Value | Source |
| --- | --- | --- |
| What it is | Subcontractor safety compliance for general contractors: task-scoped protocols, training and review tracking, and PPE checks from daily site photos. An AI-generated protocol stays a draft until a named person approves it | [fieldscope README](../../construction-os-demos/fieldscope/README.md) and [brief](../../construction-os-demos/fieldscope/brief.md) |
| Problem | Protocols, training records and daily PPE checks degrade into paperwork nobody trusts | The brief's positioning |
| Role | `built` | The README describes the prototype as his published work. `personallyDid` is `[OPEN]` until he writes the line |
| Maturity | `prototype` | The README: "Prototype, pilot scope" |
| Demo | `public` | https://fieldscope-vm64.onrender.com/ |
| Repository | Public, https://github.com/justinyurasits/fieldscope | The README |
| Limitation, required | No measured pilot result is documented. The brief's success criteria are drafts. The page states no result | The README and the brief |
| Left off | Any company named in the brief's working assumptions. The string "field photos" is banned; the page says "daily site photos" only if that phrase is kept out, and otherwise says "PPE checks against photos of the work." The Construction OS workflow status "Site Safety: Live, demo on request" is not applied to Fieldscope. Whether they are the same work is open | The brief; `facts.json` banned list |

**Writing seeds, not posts.** A later piece can start from one of these. None
is published by the preview.

- [Construction OS principles](../../construction-os/principles.md). Ten
  principles, each tied to an incident. The doc's own "For the article" section
  already says a post can be one principle or one incident, opened with the
  incident. The incidents include: version stamps in 139 document bodies
  contradicted their front matter, and 2,526 old references pointed at nothing;
  a carpenter rate recorded as $89 in one source and $90 in another, so two
  systems priced the same change $7.26 apart; four days of governance work
  before anyone had named a customer; a test contract's markup that the system
  had to apply once and not learn as the company's markup.
- Three articles that were on the live site, withdrawn on 2026-09-19, text
  still in `justinyurasits.github.io` history at commit `416e8ba`. Titles:
  "What Walks Out the Door When Your Best Person Leaves", "The Work Around the
  Work: Why Construction Operations Stay So Manual", "AI Can't Automate a
  Business It Doesn't Understand." The v2 spec says they are drafts to re-edit,
  not launch-ready. Same here.
- [Agents principles](../../agents/principles.md) and the three candidate
  principles in [justinyurasits-com](../../justinyurasits-com/principles.md) are
  about building agents and about building the v2 site. They are a poor fit
  for a construction-AI library. They are not seeds for this preview.

**Work with me and contact** have no register facts beyond the contact
addresses, which are not claims. Email `justin@justinyurasits.com`, booking
`https://cal.com/justinyurasits`, LinkedIn
`https://linkedin.com/in/justinjyurasits`. All three are on the live site.
The three section bodies are `[OPEN]`.

**Portrait.** `images/about-portrait.jpg` on `main`, already used by the live
About page. Story shows it. Home does not, so the first screen stays text.

### Relationship to v2, the product site, and brand-system

**v2** is a different product, designed in
[justinyurasits-com/](../../justinyurasits-com/) and built on branch `v2`.
This pilot does not edit those docs, does not branch from `v2`, and does not
import its routes, its headline, or its capabilities. The comparison is the
point: two branches, two sites, same repository, neither merged into the other.

**The product site** is `main`, live at justinyurasits.com. It stays the
Construction OS pitch: pain points, four modules, Audit / Build / Monthly.
This preview links to it with absolute URLs, which keep working while `main`
is that site. Those links are:

- https://justinyurasits.com/
- https://justinyurasits.com/services.html
- https://justinyurasits.com/products/document-workbench.html
- https://justinyurasits.com/products/construction-intelligence.html
- https://justinyurasits.com/products/project-intelligence.html
- https://justinyurasits.com/products/operations-automation.html
- https://justinyurasits.com/privacy.html
- https://justinyurasits.com/terms.html

**brand-system** is the visual authority when a later milestone applies it:
`brands/personal/` (BRAND-004), the same sub-brand v2 uses, because this is
also his site and not the Construction OS brand. The preview milestone does
not apply it. Neutral styling: system fonts, no brand colors, no Construction
OS mark. If a later page needs a treatment BRAND-004 does not document, the
work stops for a brand-system change. This repo does not invent the treatment.
The site keeps its own copy of any tokens it adopts, with the brand-system
commit recorded in the file, and the build does not read a neighboring
repository. That is the same rule v2 recorded, proposed again here because
this is a separate product.

## 3. Constraints

- Branch `personal` is cut from `main`. Every pull request targets `personal`.
  Nothing targets `main` or `v2`. Justin merges.
- No deploy workflow for `personal`. `justinyurasits.github.io` publishes
  `main` to the domain. A second branch cannot have a public Pages URL on that
  repository without replacing the live site, so the preview is a CI artifact
  and a local preview command.
- The implementer does not file the GitHub issues in the plan, and does not
  start the code, until Justin has merged this design and asked for the issues.
- No new facts. If a sentence is not in the content model, it is `[OPEN]` or
  it is absent.
- First person is allowed. The page is his.
- Dependencies stay minimal. The preview is a static site.
- Node and Astro versions, if Astro is the build (decision log), are pinned.
  The v2 branch's versions are a reference, not a dependency: this branch does
  not import v2's tree.

## 4. Decision log

One entry per decision, newest at the top. These are proposed with this pull
request. Merging it approves them. A plan or a build log may point here;
neither records a decision.

| Date | Decision | Options considered | Why | What would change it |
| --- | --- | --- | --- | --- |
| 2026-11-24 | **Proposed.** The preview uses neutral styling. BRAND-004 is a later milestone, after he has seen the content beside v2. | Apply BRAND-004 in the first build; invent a temporary look | He asked to see the demo, and the comparison he named is with v2's content and positioning. Visual rules stay in brand-system. A neutral preview does not pretend to be a brand. | He wants the first look to wear the personal sub-brand. |
| 2026-11-24 | **Proposed.** The story and the work page use the public construction facts in the content model, including the working headline "I build AI systems for construction, from inside a residential GC." Enterprise employers and co-founder titles stay off. Construction OS attribution is the 2026-11-22 sentence. | Leave every sentence as `[OPEN]` until a separate copy pass; lead with the enterprise career the way the live About page does | A preview of placeholders is not a demo he can compare. The construction sentences are already public. The enterprise career would make this the v2 site again. | He edits the headline, or asks for the enterprise paragraph. |
| 2026-11-24 | **Proposed.** Work is three case studies: Construction OS, the change order generator, Fieldscope. The job evaluator stays off. | Include the job evaluator as a fourth card, as the first sketch of this pilot did | The later direction is that the branch is entirely AI for construction. The job evaluator's subject is job postings. | He asks for it on the site. |
| 2026-11-24 | **Proposed.** Product, privacy and terms links are absolute URLs to the live site. This preview does not copy the offer tables or the legal pages. | Reproduce Audit / Build / Monthly; host a second copy of the legal pages | The product site remains the product site. Duplicating fees would put prices on his personal preview, which the v2 spec already keeps off a personal site. Absolute links work while the domain is undecided. | The product site moves, or he takes a domain. |
| 2026-11-24 | **Proposed.** Routes and header as in §2. Contact is a page and is not a header item. | v2's navigation; Contact in the header | The pages are the ones he named, narrowed to construction. The header stays short enough for a phone. | He wants Contact in the header. |
| 2026-11-24 | **Proposed.** The preview is Astro, generated statically, with Markdown content collections, on Node pinned in `.nvmrc`. No database and no CMS. Articles and case studies are content files. | A one-off HTML file; reuse the `v2` branch's app | A static build is what he can open, and it can grow a writing file without a redesign. Reusing the v2 tree would bring v2's pages along. The stack matches the one already chosen for his other site, recorded again because this product is separate. | A preview that is not a website. |
| 2026-11-24 | **Proposed.** Branch `personal`, cut from `main`. Pull requests target `personal` only. CI builds and uploads `dist`. There is no deploy. Justin merges. There is no self-merge override. | Branch from `v2`; deploy the branch to the domain; let the implementer merge | `main` is the live product site and `v2` is the other personal site. He asked to see a demo and to decide the domain later. A user-site repository publishes `main` only, so a deploy from `personal` would replace the live site. | He asks for a domain, or for the implementer to merge. |
| 2026-11-24 | **Proposed.** This pilot is a new project, `justin/`, with one component, `site/`. [justinyurasits-com/](../../justinyurasits-com/) stays the design for v2 and is not edited. | A second component under justinyurasits-com | A project holds one product. justinyurasits-com is already one product: the v2 site, capabilities JYC-CAP-01 to 10, and its one component is that whole product. This pilot does not narrow that spec. It is a different audience, a different headline, and a different ending (a preview, not a cutover). Two components that do not hand work to each other would need an architecture doc with nothing to describe, and a second decision log next to v2's. Separate folders keep one decision source for each site. | He decides this pilot should replace the v2 design. That would be a revision of justinyurasits-com, in its own pull request, after he has seen the demo. |
