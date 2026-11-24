---
type: plan
status: draft
---

# Justin — Site Plan

Work still ahead. The first milestone is a preview Justin can open beside v2.
The domain is not in this plan. Finished work moves to [build-log.md](build-log.md).
Decisions live in [design.md](design.md#4-decision-log).

Nothing below is filed on GitHub. The issues are proposals for
[`justinyurasits.github.io`](https://github.com/justinyurasits/justinyurasits.github.io),
written so they can be created when Justin asks. Creating them is not part of
this design pull request, and building is not authorized until he has merged
the design and asked for the issues. Until then this plan and the
[product spec](../product-spec.md) are the record.

Branch `personal` does not exist yet. It is cut from `main` when M0.1 is done.
`main` and `v2` are never the target.

## Now

### M0 Viewable demo

A build of branch `personal` that Justin can open beside v2. The pages are
Home, Story, Work and three case studies, an empty writing library, Work with
me, and Contact. Neutral styling. Construction AI only. The live site is
unchanged.

- **Exit criterion:** CI on a pull request to `personal` builds the site and
  uploads `dist`. The site repo README documents the local preview command.
  He can open that build and see JUS-CAP-01 to 06. `main` and `v2` have no
  new commits from this work. No deploy ran.
- **Covers:** [JUS-CAP-01](../product-spec.md#jus-cap-01-homepage) through
  [JUS-CAP-06](../product-spec.md#jus-cap-06-contact), and the preview row of
  [§5](../product-spec.md#5-cross-cutting-requirements).
- **Depends on:** this design merged, and Justin asking for the issues to be
  filed. Does not depend on a domain, on BRAND-004, or on new copy from him.
  `[OPEN]` slots ship as `[OPEN]`.
- **GitHub:** proposed milestone **M0 Viewable demo**, not created. Description:
  "On `personal`, CI builds a site Justin can open beside v2. The pages are
  AI for construction. `main` and `v2` are untouched. No deploy." Epic and
  child issues are below.

## Next

### M1 After he has seen it

Changes he asks for once the preview exists: confirmed copy in place of
`[OPEN]`, the personal sub-brand if he wants the visual comparison, and the
publishing routine. Still no domain.

- **Exit criterion:** he has said what to change, those changes are on
  `personal`, and the preview still does not deploy.
- **Covers:** the open questions he chooses to close, BRAND-004 if he asks,
  [JUS-CAP-07](../product-spec.md#jus-cap-07-publishing).
- **Depends on:** M0, and his notes on the preview.
- **GitHub:** proposed milestone **M1 After the demo**, not created. File it
  after he has looked, not before. Draft issues are below so the shape is
  visible.

## Later

- Posts, only for seeds he approves. The empty library is a valid preview.
- The job evaluator, only if he wants it on this site.
- A domain, old addresses, and any cutover. He said that comes later. Do not
  file those issues from this plan.

## Open questions blocking the plan

None block M0. The preview is buildable from the content model. These block
parts of M1, and he is the one who decides. The full list is the product
spec's [§6](../product-spec.md#6-open-product-questions).

- Services prose, the enterprise "before that", attribution titles, a newer
  portrait, which seeds become posts, a skills list, and whether the current
  focus is something other than the three works.

## Proposed GitHub milestone and issues

Not created. Titles are the identifiers until GitHub assigns numbers. When
they are filed, the epic carries the `epic` label, the same way
[justinyurasits.github.io#6](https://github.com/justinyurasits/justinyurasits.github.io/issues/6)
does. Child issues use the sections the existing issues use: Scope, Acceptance
criteria, Depends on, Design.

### Milestone: M0 Viewable demo

On `personal`, CI builds a site Justin can open beside v2. The pages are AI
for construction. `main` and `v2` are untouched. No deploy.

#### Epic: M0 Viewable demo

**Exit criterion:** CI on a pull request to `personal` builds the site and
uploads `dist`. The README documents the local preview command. The build
shows JUS-CAP-01 to 06. `main` and `v2` have no commits from this work. No
deploy ran.

## Issues

- [ ] M0.1 Branch `personal` from `main`, with the standard repo files
- [ ] M0.2 Neutral shell, routes and navigation
- [ ] M0.3 Content schemas, the facts register and the checks
- [ ] M0.4 Home and Story
- [ ] M0.5 Work and the three case studies
- [ ] M0.6 Writing, Work with me, and Contact
- [ ] M0.7 Preview path: local command and CI artifact

File these only after the design pull request is merged and Justin asks.
Through M0, Justin merges every pull request. There is no self-merge override.
Nothing merges to `main` or `v2`.

#### M0.1 Branch `personal` from `main`, with the standard repo files

**Milestone:** M0 Viewable demo · **Epic:** M0 Viewable demo
**Delivers:** the preview row of [§5](../product-spec.md#5-cross-cutting-requirements)

## Scope

- Create branch `personal` from `main` of `justinyurasits.github.io`. Do not
  branch from `v2`. Do not commit to `main` or `v2`.
- Add the standard repo files from `_template/repo/` in this design repo:
  `CLAUDE.md`, the pull request template, `README.md`, `.gitignore`. Section 7
  of `CLAUDE.md` points at `../design/justin/site/` and records the override:
  until Justin says otherwise, every pull request is branched from `personal`
  and targets `personal`. `main` and `v2` are not targets.
- The README says what the branch is (a construction-AI preview), its status
  (`prototype`), how to build and preview it, and links here.
- Remove the live site's pages from this branch only, the way v2 removed them
  from its own branch. They stay on `main` and in history. Keep
  `content/facts.json` for M0.3 and `images/about-portrait.jpg` for M0.4.

## Acceptance criteria

- [ ] Branch `personal` exists and its base is `main`. `main` and `v2` have no
  new commits from this work.
- [ ] `CLAUDE.md` points at `justin/site` in the design repo, and section 7
  says pull requests target `personal`.
- [ ] The README links to this design folder and documents the preview command
  M0.7 will make true.

## Depends on

- The design pull request for `justin/` merged, and Justin's ask to file these
  issues.

## Design

- [Product spec §5](../product-spec.md#5-cross-cutting-requirements)
- [Site design, decision log](design.md#4-decision-log)
- [Brief, how this differs from v2](../brief.md#7-how-this-differs-from-v2)

#### M0.2 Neutral shell, routes and navigation

**Milestone:** M0 Viewable demo · **Epic:** M0 Viewable demo
**Delivers:** [JUS-CAP-01](../product-spec.md#jus-cap-01-homepage),
[JUS-CAP-06](../product-spec.md#jus-cap-06-contact)

## Scope

- Astro, statically generated, at the repo root on `personal`. Node pinned in
  `.nvmrc`. Versions may follow the v2 branch's pins as a reference. The v2
  tree is not copied.
- Routes from the [information architecture](design.md#information-architecture):
  `/`, `/story/`, `/work/`, `/work/construction-os/`,
  `/work/change-order-generator/`, `/work/fieldscope/`, `/writing/`,
  `/work-with-me/`, `/contact/`.
- Header: wordmark "Justin Yurasits" to home; Story, Work, Writing; Work with
  me as the action. Footer: Work with me, Contact, email, LinkedIn, Privacy
  and Terms as absolute links to the live site.
- Neutral styling only: system fonts, no colors, type or components from
  brand-system or from the Construction OS brand. No Construction OS mark.

## Acceptance criteria

- [ ] `npm run build` writes a static site to `dist/`.
- [ ] Every route above returns a page.
- [ ] Given any page, then Work with me is in the header, and the footer
  includes email and LinkedIn.
- [ ] No brand colors, fonts or components are used.
- [ ] The string "AI Product Leader. Systems Designer. Hands-On Builder." does
  not appear, and there is no Training, Solutions or Demos nav item.

## Depends on

- M0.1

## Design

- [Product spec, JUS-CAP-01](../product-spec.md#jus-cap-01-homepage)
- [Product spec, JUS-CAP-06](../product-spec.md#jus-cap-06-contact)
- [Site design, information architecture](design.md#information-architecture)

#### M0.3 Content schemas, the facts register and the checks

**Milestone:** M0 Viewable demo · **Epic:** M0 Viewable demo
**Delivers:** [§5](../product-spec.md#5-cross-cutting-requirements)

## Scope

- Content collections for work entries and articles. Required fields fail the
  build in plain language: on a work entry, `role`, `personallyDid`,
  `maturity`, `demo`, what a visitor can view, and limitations. `personallyDid`
  may be the token `[OPEN]`.
- Seed the register from `content/facts.json` on `main`. Add only the keys in
  the [content model](design.md#content-model). Do not add enterprise
  employers. Do not render `pricing`.
- Checks, run on the built HTML: a claim about Justin or his work has a
  register key, no banned string, no `pricing` value, and the v2 strings from
  §5 are absent ("AI Product Leader. Systems Designer. Hands-On Builder.",
  an enterprise track, C2C).
- Draft articles are visible to the local preview and absent from `dist/`.

## Acceptance criteria

- [ ] A work entry missing `role`, `personallyDid`, `maturity`, `demo`, what a
  visitor can view, or limitations fails the build and names the field.
- [ ] A page that shows a banned string fails the build and names the string.
- [ ] A rendered fee from the register's `pricing` block fails the build.
- [ ] The v2 headline, "C2C", and a Training nav item fail the build if present.
- [ ] An article marked draft is absent from `dist/`.

## Depends on

- M0.2

## Design

- [Product spec §5](../product-spec.md#5-cross-cutting-requirements)
- [Site design, content model](design.md#content-model)

#### M0.4 Home and Story

**Milestone:** M0 Viewable demo · **Epic:** M0 Viewable demo
**Delivers:** [JUS-CAP-01](../product-spec.md#jus-cap-01-homepage),
[JUS-CAP-02](../product-spec.md#jus-cap-02-story)

## Scope

- Home, in the order in the [page structure](design.md#page-structure):
  positioning, What I do, Now, Work with me. The headline and supporting line
  are the register keys `positioning.headline` and `positioning.support`.
- Story, from the story keys in the content model, plus the Construction OS
  `personallyDid` and a link to the case study. Portrait from
  `images/about-portrait.jpg`. No enterprise employers. No second portrait.
- Every claim is rendered from the register.

## Acceptance criteria

From the product spec, checked on the built pages:

- [ ] Given a visitor at `/`, when the page loads, then the headline and what
  he is working on show without scrolling, at 375px and at 1280px.
- [ ] Given the homepage, then it links to Story, Work, Writing and Work with me.
- [ ] Given the homepage, then Construction OS appears as one work item and the
  page does not lead with Audit, Build, Monthly, or the four product modules.
- [ ] Given the homepage, then the headline is "I build AI systems for
  construction, from inside a residential GC."
- [ ] Given the story page, then each sentence traces to the register, the
  portrait is the live site's file, and no enterprise employer is named.

## Depends on

- M0.3

## Design

- [Product spec, JUS-CAP-01](../product-spec.md#jus-cap-01-homepage)
- [Product spec, JUS-CAP-02](../product-spec.md#jus-cap-02-story)
- [Site design, content model](design.md#content-model)

#### M0.5 Work and the three case studies

**Milestone:** M0 Viewable demo · **Epic:** M0 Viewable demo
**Delivers:** [JUS-CAP-03](../product-spec.md#jus-cap-03-work)

## Scope

- `/work/` lists Construction OS, the change order generator and Fieldscope,
  in that order.
- One case study each, fields and allowed facts from the
  [content model](design.md#content-model). `personallyDid` is the confirmed
  sentence for Construction OS and `[OPEN]` for the other two.
- Outbound links are the absolute URLs in the design. The corpus repository
  is labeled "Private repository, walkthrough on request." with no URL.
- The change-order page states that the model writes every price and total
  and nothing checks them. The Fieldscope page states that no pilot result is
  documented and names no client. The Construction OS page states both the
  register statuses and the validation limits.

## Acceptance criteria

From the product spec:

- [ ] Given the work index, then it lists the three entries in order and no
  other entry.
- [ ] Given any case study, then role, what he personally did, maturity, demo
  availability, what a visitor can view, and limitations are present.
- [ ] Given a number, a "used on", or a status, then it is rendered from the
  register.
- [ ] Given the change order generator, then the unchecked-prices limitation
  is on the page, and both public links work.
- [ ] Given Fieldscope, then it says prototype, names no client, and states no
  pilot result.
- [ ] Given Construction OS, then the attribution is the confirmed
  `personallyDid`, the measured tasks and library counts are the register's,
  the validation limits are on the page, and no fee is shown.
- [ ] The job evaluator does not appear.

## Depends on

- M0.3

## Design

- [Product spec, JUS-CAP-03](../product-spec.md#jus-cap-03-work)
- [Site design, content model](design.md#content-model)

#### M0.6 Writing, Work with me, and Contact

**Milestone:** M0 Viewable demo · **Epic:** M0 Viewable demo
**Delivers:** [JUS-CAP-04](../product-spec.md#jus-cap-04-writing),
[JUS-CAP-05](../product-spec.md#jus-cap-05-work-with-me),
[JUS-CAP-06](../product-spec.md#jus-cap-06-contact)

## Scope

- `/writing/` empty state: "Writing on AI in construction. Nothing is published
  yet." No seeds and no withdrawn articles rendered as posts. RSS and sitemap
  exist and list no articles.
- `/work-with-me/` with three sections, consulting, speaking and advising.
  Bodies are `[OPEN]`. Each links to contact. Product offers are one link to
  `https://justinyurasits.com/services.html`, with no fee and no offer table.
- `/contact/` with three mailto links (`justin@justinyurasits.com`, subjects
  Consulting, Speaking, Advising), `https://cal.com/justinyurasits`, and
  `https://linkedin.com/in/justinjyurasits`. No form.
- Footer Privacy and Terms link to the live pages.

## Acceptance criteria

- [ ] Given no published article, then `/writing/` says nothing is published
  yet and shows no draft and no seed.
- [ ] Given the work-with-me page, then the three sections each reach contact,
  the engagements link is present, and no fee, résumé or C2C appears.
- [ ] Given an `[OPEN]` slot, then it is visible and has not been filled with
  invented copy.
- [ ] Given the contact page, then the three email links, the booking link and
  LinkedIn are present, and there is no form.
- [ ] Given the footer, then Privacy and Terms link to the live site.

## Depends on

- M0.2

## Design

- [Product spec, JUS-CAP-04](../product-spec.md#jus-cap-04-writing)
- [Product spec, JUS-CAP-05](../product-spec.md#jus-cap-05-work-with-me)
- [Product spec, JUS-CAP-06](../product-spec.md#jus-cap-06-contact)
- [Site design, page structure](design.md#page-structure)

#### M0.7 Preview path: local command and CI artifact

**Milestone:** M0 Viewable demo · **Epic:** M0 Viewable demo
**Delivers:** the preview row of [§5](../product-spec.md#5-cross-cutting-requirements)

## Scope

- `npm run preview` serves the local build, documented in the README from a
  fresh checkout of `personal`.
- CI runs on pull requests to `personal`: install, build, checks. The job
  uploads `dist` as an artifact. There is no deploy job, and the workflow that
  deploys `main` is not edited.
- The README tells Justin both ways to open the demo: the local command, and
  the artifact on the GitHub Actions run.

## Acceptance criteria

- [ ] Following the README on a fresh checkout of `personal` produces a site
  he can open in a browser.
- [ ] CI on a pull request to `personal` builds and uploads `dist`.
- [ ] No workflow deploys `personal`, and the `main` deploy workflow is
  unchanged.
- [ ] `git log main` and `git log v2` show no commits from this work.

## Depends on

- M0.4, M0.5, M0.6

## Design

- [Product spec §5](../product-spec.md#5-cross-cutting-requirements)
- [Site design, constraints](design.md#3-constraints)

### Milestone: M1 After the demo

File this milestone after Justin has opened the M0 preview. Not before. Still
no domain work.

#### Epic: M1 After the demo

**Exit criterion:** the changes he asked for after seeing the preview are on
`personal`, and the branch still does not deploy.

## Issues

- [ ] M1.1 Notes from the preview, turned into issues
- [ ] M1.2 Confirmed copy in place of `[OPEN]`
- [ ] M1.3 Personal sub-brand, if he asks
- [ ] M1.4 Publishing routine

#### M1.1 Notes from the preview, turned into issues

**Milestone:** M1 After the demo · **Epic:** M1 After the demo
**Delivers:** whichever of [§6](../product-spec.md#6-open-product-questions) he
closes

## Scope

- Read his notes on the preview. For each change, either it fits an open
  question already in the product spec, or it is a design change: stop and
  propose it in this design repo before building it.
- Do not widen the site into v2, and do not start a domain cutover.

## Acceptance criteria

- [ ] Each note is either a child issue under this milestone or a design change
  proposed in `justin/`.
- [ ] No note is implemented by editing `main`, `v2`, or justinyurasits-com.

## Depends on

- M0.7, and Justin's notes

## Design

- [Product spec §6](../product-spec.md#6-open-product-questions)
- [Brief §6](../brief.md#6-out-of-scope-on-purpose)

#### M1.2 Confirmed copy in place of `[OPEN]`

**Milestone:** M1 After the demo · **Epic:** M1 After the demo
**Delivers:** [JUS-CAP-02](../product-spec.md#jus-cap-02-story),
[JUS-CAP-03](../product-spec.md#jus-cap-03-work),
[JUS-CAP-05](../product-spec.md#jus-cap-05-work-with-me)

## Scope

- Replace each `[OPEN]` he has answered, by adding his words to the register
  or the content file. Leave any he has not answered as `[OPEN]`.
- `personallyDid` for the change order generator and for Fieldscope, the three
  service descriptions, and any headline edit.

## Acceptance criteria

- [ ] Every replaced slot matches his words and traces to the register when it
  is a claim.
- [ ] An unanswered slot is still `[OPEN]`.
- [ ] No new employer, metric, client or quote appears that he did not supply
  and that the content model did not already allow.

## Depends on

- M1.1

## Design

- [Site design, content model](design.md#content-model)

#### M1.3 Personal sub-brand, if he asks

**Milestone:** M1 After the demo · **Epic:** M1 After the demo
**Delivers:** the visual half of the comparison with v2

## Scope

- Apply BRAND-004 from `brand-system` `brands/personal/`. Tokens are copied
  into the site, with the brand-system commit recorded in the file. The build
  does not read a neighboring repository.
- Pages the handoff does not cover are composed from its documented components.
  If a page needs a treatment the handoff does not have, stop and ask for a
  brand-system change. Do not invent one here.
- Skip this issue if he does not ask for it.

## Acceptance criteria

- [ ] Given he asked for the sub-brand, then `tokens.css` names the brand-system
  commit it came from, and no hex value appears outside it.
- [ ] Given a missing treatment, then the pull request says so and does not
  add a new one.
- [ ] Given he did not ask, then this issue is closed unbuilt.

## Depends on

- M0.7, and his ask

## Design

- [Site design, relationship to brand-system](design.md#relationship-to-v2-the-product-site-and-brand-system)
- [BRAND-004](https://github.com/justinyurasits/brand-system/blob/main/brands/personal/BRAND.md)

#### M1.4 Publishing routine

**Milestone:** M1 After the demo · **Epic:** M1 After the demo
**Delivers:** [JUS-CAP-07](../product-spec.md#jus-cap-07-publishing)

## Scope

- One command to create a piece, one command to preview it, including drafts.
  Publishing is marking it published and pushing the content file to
  `personal`.
- A missing title, description or date fails the build and names the field.
- This does not deploy, and it does not publish a piece he has not written.
  The empty library remains valid.

## Acceptance criteria

- [ ] Given a new piece, then one content file is the only edit, and a draft
  is absent from `dist/`.
- [ ] Given a missing required field, then the build fails and names it.
- [ ] Given the empty library, then `/writing/` still says nothing is published
  yet.

## Depends on

- M0.6

## Design

- [Product spec, JUS-CAP-07](../product-spec.md#jus-cap-07-publishing)
