---
type: product-spec
status: draft
---

# Justin — Product Spec

What the preview site must do for a reader, and for Justin looking at it beside
v2. Behavior a person can see, not the implementation. The [brief](brief.md)
says why, including [how this differs from v2](brief.md#7-how-this-differs-from-v2).
The site's [design](site/design.md) says how the pages are put together, which
facts may appear, and the technical choices. Visual rules, when they are
applied, come from brand-system's personal sub-brand (BRAND-004), not from
this spec.

**Draft.** The first milestone delivers JUS-CAP-01 to 06 as a preview. JUS-CAP-07
waits until after Justin has seen it. Open questions are in §6.

Capability IDs are `JUS-CAP-<nn>`. They are not the `JYC-CAP` IDs, which belong
to [justinyurasits-com](../justinyurasits-com/product-spec.md) and are not reused.

## 1. Product scope

One preview site about Justin doing AI for construction. A reader learns who
he is in that work, sees the systems he has built, finds any writing he has
published on it, and can ask about consulting, speaking or advising. Construction
OS is a case study with links to the product. The site stops where the brief's
[out-of-scope list](brief.md#6-out-of-scope-on-purpose) starts.

The navigation is Story, Work and Writing. Work with me is the header's action.
Contact is a page, linked from Work with me and from the footer.

**The preview** includes:

- the homepage, with the construction-AI positioning and what he is working on
- the story of his construction path and why he builds AI for it
- work: Construction OS, the change order generator, and Fieldscope, each with
  a short case study that links out
- a writing library that can be empty, and says so
- work with me, for construction AI consulting, speaking and advising, with a
  link to Construction OS engagements for product offers
- contact
- a build Justin can open on the preview branch, beside v2, without the live
  domain changing

That is JUS-CAP-01 to JUS-CAP-06, plus the preview row in §5. Publishing
(JUS-CAP-07) is specified so the library can grow, and it is not required for
the preview.

No page shows a fee. No page uses the v2 headline "AI Product Leader. Systems
Designer. Hands-On Builder." No page has a Training section, a résumé, a C2C
offer, or an enterprise consulting track.

## 2. Users and their goals

Brief goals are cited by these short names, one per row of
[brief §4](brief.md#4-goals-and-how-well-know):

| Short name | Brief goal |
| --- | --- |
| **Compare** | Justin can look at this site beside v2 |
| **Recognize** | A construction reader can say what Justin does in construction AI, and what he is working on |
| **Evidence** | The work can be checked |
| **Inquire** | A reader can start a conversation about construction AI work with him |
| **Read** | Writing on AI in construction has a home |

| User | What they need to accomplish | Brief goals |
| --- | --- | --- |
| Owner or operations leader at a residential builder | See who Justin is in construction AI, check the work, and start a conversation or follow the product link | Recognize, Evidence, Inquire, Read |
| Justin, reviewing the pilot | Open a preview build and compare it with v2 without the live site changing | Compare |
| Justin, as author | Publish a piece on AI in construction after the preview, without editing layouts | Read |

## 3. Capabilities

### JUS-CAP-01: Homepage

The front page of a personal site about AI for construction. The reader sees
who Justin is and what he is working on, and Construction OS is one item in
the work, not the subject of the page.

In order:

1. **Positioning.** The working headline is "I build AI systems for construction,
   from inside a residential GC." The supporting line is the live About page's
   "I build the systems I needed when I was the one producing the paperwork."
   Both are register entries (design, content model). They are the words the
   preview shows.
2. **What I do.** Three paths: construction operations (the story), the systems
   (the work), and writing on AI in construction. Each links to its page.
3. **Now.** The three works, one line each, linking to their case studies.
4. **Work with me.** One path into consulting, speaking and advising, and no
   product offer.

**Acceptance criteria**

- Given a visitor at `/`, when the page loads, then the headline and what he
  is working on show without scrolling, at 375px and at 1280px.
- Given the homepage, then it links to Story, Work, Writing and Work with me.
- Given the homepage, then Construction OS appears as one work item and the
  page does not lead with Audit, Build, Monthly, or the four product modules.
- Given the homepage, then the headline is the working headline above, and the
  string "AI Product Leader. Systems Designer. Hands-On Builder." does not appear.
- Given any claim about Justin or his work, then it is rendered from the
  register (§5).

**Brief goals:** Recognize, Compare

**Delivered by:** [site](site/spec.md)

### JUS-CAP-02: Story

His path through construction operations, and why he started building AI for
that work. Prose is limited to sentences already public on justinyurasits.com
or already confirmed in this repo, rendered from the register. The portrait is
the live site's `images/about-portrait.jpg`.

The story the preview tells:

- He was working inside a residential GC, and Construction OS came out of that
  work rather than from taking a generic AI product and looking for a
  construction use case. Source: the live homepage.
- Massachusetts Construction Supervisor license. Three years in residential
  construction as project manager and site superintendent, running $1M–$4M
  renovations at a $50 million contractor. The contractor is not named.
  Source: the live About page and `content/facts.json` on `main`.
- He has written the scopes, produced the change orders, managed trades, and
  been responsible for work in the field. Source: the live About page.
- The premise he states: you can't automate what the business hasn't made
  legible. Source: the live About page.
- Construction OS attribution is the sentence confirmed in this repo on
  2026-11-22: he conceived and architected it and built its major components
  (the corpus, the Document Workbench and the intake router), drawing on his
  own construction document library, and Ava Yurasits contributed to the build.
  The page does not call him its sole designer and builder.

Enterprise employers, the twelve years of product leadership, and the
co-founder titles on the live About page are not on this page until he asks
for them (§6).

**Acceptance criteria**

- Given the story page, then a reader can see the construction path and the
  reason he builds AI for it, each sentence tracing to the register.
- Given a fact that is not in the register, then the page shows `[OPEN]` in
  its place and does not show a written sentence for it.
- Given the portrait file from the live site, then the story shows it. Given
  Justin has replaced the file, then the story shows the replacement. The page
  shows no other image of a person.
- Given the page, then it does not name an employer from the enterprise career,
  and it does not use a string on the register's banned list (§5).

**Brief goals:** Recognize

**Delivered by:** [site](site/spec.md)

### JUS-CAP-03: Work

The work index and one short case study per entry. The preview lists three, in
this order: Construction OS, the change order generator, Fieldscope. Each links
out. A case study is a checkable account, not a product pitch and not a gallery.

Every case study uses the same fields:

- the problem, in language already in that work's brief
- what it is
- Justin's role: **built**, **led** or **both**, and one line on what he
  personally did
- what a visitor can go and see, as working links
- results that have a source in the register, and no other results
- maturity, demo availability, and limitations

The allowed facts, the links, and the limitations are listed in the
[design content model](site/design.md#content-model). The build fails if a
case study adds a result, a client name, or a status that list does not have.

**Acceptance criteria**

- Given the work index, then it lists Construction OS, the change order
  generator and Fieldscope, in that order, and no other entry.
- Given any case study, then role, what he personally did, maturity, demo
  availability, what a visitor can view, and limitations are present. The
  build fails if any is missing.
- Given a number, a "used on", or a status on a case study, then it is rendered
  from the register and the register entry names its source.
- Given the change order generator, then the case study says that in the live
  version the model writes every price and total and nothing checks them, and
  it links to draftconstructionchangeorder.com and the public repository.
- Given Fieldscope, then the case study says it is a prototype, links to its
  demo and its repository, names no client, and states no pilot result.
- Given Construction OS, then the attribution is the register's `personallyDid`,
  the measured tasks and library counts are the register's, and the case study
  also states the validation limits from the Construction OS design record.
  Product offers and fees are absent. Each product module links to its page on
  the live site.
- Given a private repository, then the case study says "Private repository,
  walkthrough on request." and shows no URL.
- Given the job evaluator, then it does not appear.

**Brief goals:** Evidence, Recognize

**Delivered by:** [site](site/spec.md)

### JUS-CAP-04: Writing

A library of writing on AI in construction, and a page for each published
piece. The preview ships with no published piece. The empty library says that
nothing is published yet. It does not show drafts, and it does not show a
principle, a lesson or an old article as if it were a post.

Candidate seeds for later posts are listed in the design. They are not posts.

A published piece shows its title, description, date and body. Claims about
Justin or his work on the piece trace to the register. Other figures are
supported in the piece itself.

**Acceptance criteria**

- Given no published article, then `/writing/` says nothing is published yet
  and shows no draft and no seed.
- Given a published article, when the site builds, then it appears on its own
  URL, in the library, in the RSS feed and in the sitemap, with no listing
  edited by hand.
- Given an article marked draft, then it can be previewed locally and it
  appears nowhere in the built site: not in the library, the feed, the sitemap,
  or at its own URL.
- Given an article whose body uses a banned string, or a claim about Justin or
  his work that is not in the register, then the build fails and names it.

**Brief goals:** Read

**Delivered by:** [site](site/spec.md)

### JUS-CAP-05: Work with me

One page, `/work-with-me/`, for construction AI work with Justin: consulting,
speaking and advising. The three are equal sections. Each ends in a next step
that reaches contact (JUS-CAP-06). The page does not describe a package he has
not written. Where the words are not documented, the slot is `[OPEN]`.

Product work is a link, not a fourth section of offers. The link goes to the
live engagements page, `https://justinyurasits.com/services.html`, and the page
does not repeat Audit, Build or Monthly and does not show a fee.

**Acceptance criteria**

- Given the page, then it has a section for consulting, a section for speaking
  and a section for advising, and each reaches contact without a form.
- Given a description he has not supplied, then that slot reads `[OPEN]` and
  the page does not invent an engagement, a duration or an outcome.
- Given the page, then it links to the Construction OS engagements page for
  product offers, and it shows no fee and no résumé.
- Given the page, then it has no enterprise track and the word C2C does not appear.
- Given any claim about Justin or his work, then it traces to the register (§5).

**Brief goals:** Inquire, Recognize

**Delivered by:** [site](site/spec.md)

### JUS-CAP-06: Contact

A contact page for consulting, speaking and advising. No form and no form
backend.

- an email link for each of the three, `justin@justinyurasits.com`, with a
  prefilled subject naming the reason
- the booking link `https://cal.com/justinyurasits`
- LinkedIn `https://linkedin.com/in/justinjyurasits`, alongside the others

The footer on every page includes the email and LinkedIn. Work with me is in
the header of every page.

Privacy and terms in the footer link to the live site's `/privacy.html` and
`/terms.html`. This preview does not fork those pages.

**Acceptance criteria**

- Given any page, then Work with me is in the header, and the footer includes
  email and LinkedIn.
- Given the contact page, then each of consulting, speaking and advising has
  its own email link with a prefilled subject, and the booking link and
  LinkedIn are present.
- Given the contact page, then it contains no form.
- Given the footer, then Privacy and Terms link to the live site.

**Brief goals:** Inquire

**Delivered by:** [site](site/spec.md)

### JUS-CAP-07: Publishing

After the preview, Justin adds a piece on AI in construction by editing one
content file. The preview does not have to include this routine. The library's
empty state (JUS-CAP-04) does not depend on it.

1. Create a piece from a template.
2. Write it.
3. Set the title, description and date.
4. Preview it locally, including while it is a draft.
5. Mark it published and push it to the preview branch. It appears on the
   next build of that branch.

Code changes still go through an issue and a pull request. This routine is for
a content file and its images.

**Acceptance criteria**

- Given the routine is in place, when he publishes a text piece, then he edits
  one content file and changes no page layout.
- Given a draft, then the local preview shows it and the built site does not.
- Given a missing title, description or date, then the build fails and names
  the field.
- Given a failed build, then the branch's previous green build is unchanged,
  and `main` is unchanged because this branch does not deploy (§5).

**Brief goals:** Read

**Delivered by:** [site](site/spec.md)

## 4. User journeys

### Justin compares the preview with v2

1. Opens the preview build of branch `personal` (the command and the CI
   artifact are in the site repo README). The live site at justinyurasits.com
   is unchanged, and the `v2` branch is unchanged (JUS-CAP-01, §5).
2. Sees a homepage whose headline is construction AI, from inside a residential
   GC (JUS-CAP-01).
3. Opens the v2 site beside it and can tell the two apart: v2 leads with
   "AI Product Leader. Systems Designer. Hands-On Builder." and offers
   enterprise and construction; this preview does not.

**When it goes wrong:** the preview was deployed onto justinyurasits.com, or
the branch was cut from `v2` and still carries v2's pages. The preview row in
§5 fails. `main` and `v2` are the recovery: they were never the target.

### The construction owner

1. Opens the preview and reads the headline and the three works without
   scrolling (JUS-CAP-01).
2. Opens the story and reads the construction path (JUS-CAP-02).
3. Opens the Construction OS case study, sees sourced results and the
   limitations, and follows a link to a product page on the live site
   (JUS-CAP-03).
4. Comes back. Writing says nothing is published yet (JUS-CAP-04).
5. Opens Work with me. Product offers are a link to the engagements page, with
   no fee on this site (JUS-CAP-05).
6. Emails or books from the contact page (JUS-CAP-06).

**When it goes wrong:** he wants a price. The page has none. The engagements
link is where the live product site states its offers. He wants a published
essay. The library says nothing is published yet, and no draft is pretending
to be one.

### Justin publishes a piece, after the preview

1. Creates a piece from the template and writes it (JUS-CAP-07).
2. Previews it as a draft. The built site does not show it.
3. Marks it published. The next build of `personal` shows it in the library,
   the feed and the sitemap (JUS-CAP-04).

**When it goes wrong:** a required field is missing, or the piece uses a
banned string. The build fails, names the problem, and does not publish the
piece. The live domain is unaffected.

## 5. Cross-cutting requirements

| Requirement | What must hold | How it's checked |
| --- | --- | --- |
| **Preview, not the domain** | Branch `personal`, cut from `main`. Justin can open a build of it. Nothing deploys to justinyurasits.com. `main` and `v2` are not modified. | CI builds on pull requests to `personal` and uploads the site as an artifact. The workflow has no deploy job. The site repo README documents the local preview command. A check fails if the deploy workflow from `main` is changed. |
| **Facts register** | Claims about Justin and his work are rendered from the register: credentials, roles, results, product status, library counts. The register starts from `content/facts.json` on `main`. New keys are only the ones the [design content model](site/design.md#content-model) lists. The banned list in that file stays banned. The `pricing` block is not rendered. | The build fails when a rendered claim has no register key, when a banned string appears, or when a `pricing` value appears. |
| **No fees** | No page shows a fee, a rate or a résumé. | The register check, plus the absence of the résumé link. |
| **Sourced results** | A case study shows a result only when the register has it, and the entry names where it was documented. | The work schema rejects a result with no source. |
| **Built vs. led** | Every work entry has `role` (`built`, `led` or `both`) and `personallyDid`. | The build fails if either is missing. |
| **Maturity and demo** | Every work entry has `maturity` (`live`, `beta`, `prototype`, `experiment` or `in-development`) and `demo` (`public`, `on-request` or `none`), from the content model. | The build fails if either is missing or the value is off the list. |
| **Construction only** | The built pages do not contain the v2 headline, a Training nav item, an enterprise consulting track, or C2C. | A check fails the build if those strings appear. |
| **Placeholders** | `[OPEN]` is allowed in the preview where the content model says the words are unknown. It is visible. It is never filled with invented copy. | Review of the preview. A later pass removes them only when he supplies the words. |
| **Responsive** | Every page works on a phone and on a desktop. | Checked at 375px and 1280px. |
| **Accessible** | Navigation and reading are accessible. | WCAG 2.2 AA, checked when the visual design is applied. The preview meets it as far as neutral HTML can: headings, links, contrast of the neutral styles, a skip link. |

## 6. Open product questions

- **Services copy.** What consulting, speaking and advising actually consist of,
  in his words. The preview shows the three sections and `[OPEN]` for the
  descriptions. Blocks nothing in the preview. Blocks a later copy pass.
- **Enterprise backstory.** The live About page has twelve years of product
  leadership and names Optimizely, Fidelity Investments, Jabra and Citizens.
  This story leaves them off so the page stays construction. He decides whether
  a short "before that" belongs. Blocks nothing in the preview.
- **Attribution wording.** The live About page calls him and Ava Yurasits
  co-founders and says he designed, architected and built Construction OS. The
  sentence confirmed in this repo on 2026-11-22 is narrower, and it is the one
  this site uses. He decides whether the co-founder titles belong here.
- **The portrait.** The preview uses `images/about-portrait.jpg` from `main`,
  which is the portrait already on the live About page. The file's photo date
  is 2020. He says if he wants a different one.
- **Which seeds become posts,** and whether a later version needs one post
  before he would show it to anyone but himself. The preview needs none.
  Seeds are in the [design](site/design.md#content-model).
- **The job evaluator.** Documented, live, and not construction work. It stays
  off unless he wants it.
- **A skills list.** The preview shows skills by the story and the three works.
  He says if he wants a list of his own wording.
- **"What I'm working on" beyond the three works.** The preview uses the live
  About page's Today sentence and the three works. He says if the current focus
  is different.
- **Role on the two demos.** The change order generator and Fieldscope are
  marked `built`, because their READMEs present them as his published projects,
  and `personallyDid` is `[OPEN]`. He corrects the role if that overstates it.
