---
type: product-spec
status: draft
---

# JustinYurasits.com — Product Spec

What the site must do for its visitors and its author, capability by capability, and how
anyone can check that it does. Behavior a visitor or the author can observe, not
implementation. The [brief](brief.md) says why. The site's [design doc](site/design.md)
says how; its tech stack is proposed there, not approved. Visual rules come from
[`brand-system`](https://github.com/justinyurasits/brand-system).

**Draft.** One question is open, in §6. The old-address mapping in JYC-CAP-09 is a
proposal, approved when this spec is approved.

## 1. Product scope

One site that carries Justin's writing (primary), his project case studies, and two
consulting pathways: enterprise AI and construction AI. It replaces the current
Construction OS site at justinyurasits.com and keeps that site's links working. It stops
where the brief's [out-of-scope list](brief.md#6-out-of-scope-on-purpose) starts. No page
shows a price.

**The first release** includes:
- the homepage, with clear professional positioning
- the writing library and a working publishing workflow
- at least one substantive enterprise AI article, and at least one substantive
  construction AI article or evidence-rich resource
- the Construction OS case study, with existing links preserved
- one Work With Me page per audience
- About and Contact
- mobile-responsive layouts and basic SEO
- automatic publishing

That is JYC-CAP-01 to JYC-CAP-09, with the product-wide requirements in §5.

**Existing articles.** Three articles from the current site are migrated as articles.
They were published there, then withdrawn on 2026-09-19 and replaced with redirects to
`/`. Their text is still in the website repository's history (commit `416e8ba`).

| Old address | Title | Category | Counts toward launch? |
| --- | --- | --- | --- |
| `/tribal-knowledge.html` | What Walks Out the Door When Your Best Person Leaves | AI for Construction | Could meet the construction article requirement. It's the closest to the construction pathway's COO hook. |
| `/eighty-ninety-problem.html` | The Work Around the Work: Why Construction Operations Stay So Manual | AI for Construction | Could meet the construction article requirement. |
| `/ai-projects-fail.html` | AI Can't Automate a Business It Doesn't Understand | AI for Construction | Could meet the construction article requirement. Its argument applies to enterprise readers too, but it's written for construction businesses. |

None of the three meets the enterprise article requirement, so that article is new
writing. Each migrated article passes the facts check before it is published again. None
contains a banned string today. Two state figures ("20 years", "10 days") that the check
will trace to the register.

## 2. Users and their goals

Brief goals are cited by these short names, one per row of
[brief §4](brief.md#4-goals-and-how-well-know):

| Short name | Brief goal |
| --- | --- |
| **Understand** | Enterprise AI buyers and construction leaders quickly understand Justin's expertise and how to engage him |
| **Inquire** | Relevant visitors start consulting conversations |
| **Read** | Original writing is easy to discover, read and share |
| **Evidence** | Technical projects give credible evidence of real capability |
| **Publish** | New articles are published quickly and reliably, and publishing gets easier |

| User | What they need to accomplish | Brief goals |
| --- | --- | --- |
| Hiring manager for an agentic or AI product role | Judge whether Justin is an AI product leader who builds, from his writing, his experience and his working systems, in one visit | Understand, Evidence, Read |
| Recruiter or HR contact for a C2C placement | Confirm the engagement type and location, get a résumé to forward, and reach Justin | Understand, Inquire |
| Owner of a mid-size construction firm, or an executive (COO, head of project management) at a larger one | See that Justin knows construction operations and has built working tools for them, and start a conversation | Understand, Evidence, Inquire |
| Justin, as author | Publish, correct and organize articles without touching page layouts or code | Publish |

## 3. Capabilities

### JYC-CAP-01: Homepage

The front page of a professional technology publication, not a consulting brochure.
A visitor learns who Justin is and gets a path for their audience without scrolling far.

In order:
1. **Introduction:** positioning, specific credentials, and immediate links to both
   pathway pages. The working headline is *"AI Product Leader. Systems Designer.
   Hands-On Builder."* The supporting line is *"I combine enterprise AI product
   leadership, firsthand business operations experience, and hands-on AI software
   development to help organizations turn complex problems into practical AI systems."*
2. **Featured writing:** one prominent featured article, plus curated articles for both
   audiences.
3. **Selected work:** Construction OS, other AI systems, demonstrations and case studies.
4. **Work With Me:** both pathways, each with a clear next action.
5. **Background and contact:** professional credibility, and a straightforward way to
   connect.

**Acceptance criteria**
- Given a visitor arriving at `/`, when the page loads, then the introduction shows the
  positioning and a link to each pathway page without scrolling, at 375px and at
  1280px.
- Given at least one published article in each category, when the homepage builds, then
  featured writing includes both categories.
- Given the featured article is unpublished or set back to draft, then the homepage
  features the most recent published article in the same category instead.
- Every credential and claim in the introduction traces to the facts register (§5).

**Brief goals:** Understand, Read, Inquire

**Delivered by:** [site](site/spec.md) (spec not written yet)

### JYC-CAP-02: Writing library and categories

A publication-style library of long-form articles, technical explanations, AI strategy,
research and implementation lessons. It is browsable by category and by tag.

- Two primary categories: **Enterprise AI & Product Leadership** and **AI for
  Construction**. Every article has exactly one primary category.
- Topic tags, any number per article. The starting set is Agentic AI, Conversational
  AI, Evaluation, Product Strategy, Intent Design, Document Intelligence and Construction
  OS. New tags are added as articles need them.
- Listings are built automatically: all articles, each category, each tag, plus
  featured and recent sections. Also an RSS feed and a sitemap.

**Acceptance criteria**
- Given a newly published article, when the site builds, then it appears in the full
  listing, its category's page, each of its tags' pages, the recent section, the RSS
  feed and the sitemap, with no listing edited by hand.
- Given an article with no primary category, or more than one, then the build fails and
  names the field. Nothing publishes.

**Brief goals:** Read

**Delivered by:** [site](site/spec.md) (spec not written yet)

### JYC-CAP-03: Article page

A clean, readable long-form page that carries technical content well.

- Title, description, publication date, primary category and tags
- Images, diagrams and code with syntax highlighting, as each article needs them
- References
- Links to related projects and related expertise
- A stable, readable URL
- SEO metadata, and a social sharing preview

**Acceptance criteria**
- Given a published article, then its URL is readable and stays the same when the
  article is corrected or updated.
- Given an article that cites a project, then the page links to that project's case
  study.
- Given the article's URL shared on a social platform, then the preview shows its
  title and description.
- Given a substantive change after publication, then the article shows "Updated
  <date>". A typo fix shows nothing.

**Brief goals:** Read, Evidence

**Delivered by:** [site](site/spec.md) (spec not written yet)

### JYC-CAP-04: Author publishing workflow

Justin creates, previews, publishes, corrects and organizes articles without editing page
layouts or writing boilerplate. Publishing usability is a core requirement, not a
technical afterthought.

1. Create a new article from a simple template.
2. Write or paste the article.
3. Set the title, description, publication date, primary category and tags.
4. Optionally add images, diagrams, code, references and related projects.
5. Preview it locally, exactly as it will appear.
6. Mark it draft or published, and push it. The site publishes it with no further step.

The source format and push-to-publish mechanism are proposed in
[site/design.md](site/design.md#4-decision-log), not settled here.

**Acceptance criteria**
- Given the site is configured, when Justin publishes a standard text article, then he
  edits one content file and pushes it, and changes no site component.
- Given an article marked draft, then it can be previewed locally and appears nowhere on
  the live site: not in listings, the feed or the sitemap, and not at its own URL.
- Given an article missing a required field, then the build fails and names the field.
  Nothing publishes.
- Given a publish that fails for any reason, then the previous version of the site stays
  live.
- Given an existing article, when Justin corrects it, then he edits that one file, and
  the URL stays the same. He marks whether the change is substantive (JYC-CAP-03).
- Given an advanced layout or an interactive demonstration, then it may need
  development work. A standard article never does.

**Brief goals:** Publish

**Delivered by:** [site](site/spec.md) (spec not written yet)

### JYC-CAP-05: Projects and case studies

Evidence-backed case studies, not a visual gallery. They cover Construction OS, AI
applications, agents, test harnesses, technical experiments and other significant work.
Every case study uses the same format and can include:

- the business or technical problem
- Justin's role and ownership: **built** or **led** (§5)
- the solution architecture and approach
- important design decisions and tradeoffs
- implemented functionality
- testing and evaluation evidence
- limitations, maturity and demo availability (§5)
- screenshots, demonstrations, repositories and related writing

**Acceptance criteria**
- Given any case study, then it shows built or led, its maturity, and its demo
  availability. The build fails if any of the three is missing.
- Given a case study with a public demo or a public repository, then each link works.
- Given a project with no public repository, then the case study shows screenshots and
  a short walkthrough, labeled "Private repository, walkthrough on request." It shows
  no dead or placeholder link.
- Given an article cites the project, then the case study links back to it.
- Screenshots are of the real system, never generic AI imagery.

**Brief goals:** Evidence, Understand

**Delivered by:** [site](site/spec.md) (spec not written yet)

### JYC-CAP-06: Work With Me

One pathway page per audience. Each explains the business problems an engagement
addresses, not just a list of technical capabilities, and each ends in a clear next
action. No page shows a price.

- **Enterprise AI Consulting & Leadership:** contract or C2C, fractional AI product
  leadership, advisory, product strategy, solution design, modernization and
  implementation leadership.
  - It opens with: *"You have an AI strategy and no one who can both run the product
    and build the system."*
  - It states the engagement types and *"remote, based in Boston"*, and links to a
    downloadable résumé PDF.
  - It shows no rates or availability dates.
- **Construction AI Consulting:** education, opportunity assessment, business workflow
  design, advisory, custom implementation and Construction OS-related services.
  - It opens with: *"Your 64-year-old COO is about to retire and half your business
    runs in his head."*

**Acceptance criteria**
- Given either pathway page, then its first line is its opening above, word for word.
- Given a visitor on either pathway page, then they reach the contact options without
  leaving it.
- Given the enterprise pathway page, then the résumé PDF downloads from it, and the page
  shows no rates or availability dates.
- Given any duration, figure or service status on either page, then it traces to the
  facts register (§5).
- Given any page, then it shows no price or fee (§5).

**Brief goals:** Inquire, Understand

**Delivered by:** [site](site/spec.md) (spec not written yet)

### JYC-CAP-07: About

Justin's professional history, enterprise leadership experience, construction operations
background, credentials, approach and selected achievements.

**Acceptance criteria**
- Given any experience entry or achievement, then it shows whether Justin built it
  himself or led the team that delivered it. The build fails if it's missing (§5).
- Given any credential, employer, figure or date, then it traces to the facts register
  (§5).

**Brief goals:** Understand

**Delivered by:** [site](site/spec.md) (spec not written yet)

### JYC-CAP-08: Contact

Simple, professional contact for consulting, contract engagements, partnerships, speaking
and education. There are two channels: email, and a booking link
(`cal.com/justinyurasits`). There's no form and no form backend.

**Acceptance criteria**
- Given any page, then Contact is in the header navigation and in the footer.
- Given a visitor choosing a reason, then each of the five reasons has its own email
  link with a prefilled subject naming that reason.
- Given a visitor who wants to talk, then the booking link opens Justin's booking page.
- Given an inquiry arrives, then Justin tags it relevant or not by hand. Tagged
  inquiries are the Inquire goal's measure.

**Brief goals:** Inquire

**Delivered by:** [site](site/spec.md) (spec not written yet)

### JYC-CAP-09: Construction OS section and preserved links

Construction OS is the flagship project, with a substantive landing page of its own. It
is a case study on Justin's site, not that product's marketing site
([brief §1](brief.md#1-customer)). Every link into the current Construction OS site keeps
working, and so do the existing product and demo links, until Construction OS moves to
its own domain. Whether Construction OS keeps its own visual identity here is for
`brand-system`.

**Proposed old-address mapping.** Approved with this spec.

| Current address | What it holds today | Goes to |
| --- | --- | --- |
| `/` | Construction OS home | The new homepage (JYC-CAP-01), which links to the Construction OS landing page |
| `/services.html` | Construction services | The construction pathway page (JYC-CAP-06) |
| `/engagements.html` | Redirect to `/services.html` | The construction pathway page |
| `/work.html` | Redirect to `/` | The projects index (JYC-CAP-05) |
| `/insights.html` | Redirect to `/` (was the article listing) | The writing library (JYC-CAP-02) |
| `/about.html` | About | About (JYC-CAP-07) |
| `/privacy.html` | Privacy policy | Kept at the same address |
| `/terms.html` | Terms | Kept at the same address |
| `/tribal-knowledge.html` | Redirect to `/` (was an article) | The migrated article (§1) |
| `/eighty-ninety-problem.html` | Redirect to `/` (was an article) | The migrated article |
| `/ai-projects-fail.html` | Redirect to `/` (was an article) | The migrated article |
| `/products/document-workbench.html` | Product page | The Construction OS landing page, at Document Workbench |
| `/products/construction-intelligence.html` | Product page | The Construction OS landing page, at Construction Intelligence |
| `/products/operations-automation.html` | Product page | The Construction OS landing page, at Operations Automation |
| `/products/project-intelligence.html` | Product page | The Construction OS landing page, at Project Intelligence |
| `/products/custom-solutions.html` | Product page | The construction pathway page |

**Acceptance criteria**
- Given any address in the table, when a visitor opens it, then they land on the page in
  its "Goes to" column, never an error page. An automated check fails the build if any
  address doesn't resolve.
- Given the Construction OS landing page, then it links to each live product and demo.
  Each link works and shows its maturity and demo availability (§5).

**Brief goals:** Evidence, Understand

**Delivered by:** [site](site/spec.md) (spec not written yet)

## 4. User journeys

### The hiring manager for an agentic or AI product role

1. Clicks Justin's link on LinkedIn and lands on the homepage. The introduction says AI
   product leader and hands-on builder, not "Book a demo" (JYC-CAP-01).
2. Follows the enterprise pathway page, or the featured enterprise article
   (JYC-CAP-06, JYC-CAP-03).
3. The article cites a project, and they open its case study. It shows built or led,
   maturity and demo availability (JYC-CAP-05).
4. Opens About and reads which systems Justin built himself and which his teams
   delivered under his leadership (JYC-CAP-07).
5. Uses the contact link for a contract engagement from the header (JYC-CAP-08).

**When it goes wrong:** the case study is for a project with no public repository. It
shows screenshots and a short walkthrough, labeled "Private repository, walkthrough on
request." It has no dead link. The hiring manager can still judge the work, and can ask
for the walkthrough through Contact.

### The recruiter or HR contact for a C2C placement

1. Lands on the homepage from a link and opens the enterprise pathway page
   (JYC-CAP-01, JYC-CAP-06).
2. Sees the engagement types, contract and C2C among them, and "remote, based in
   Boston".
3. Downloads the résumé PDF to forward.
4. Emails Justin through the contract-engagement link, with its subject prefilled
   (JYC-CAP-08).

**When it goes wrong:** the recruiter wants a rate or a start date. The site gives
neither. They ask through Contact, and the prefilled subject tells Justin what it's
about.

### The construction owner or COO

1. Met Justin in person and follows an old link, `/products/document-workbench.html`,
   from an email or a bookmark (JYC-CAP-09).
2. Lands on the Construction OS landing page at Document Workbench, with its products
   and demos.
3. Opens the construction pathway page. It opens with the COO hook (JYC-CAP-06).
4. Reads an AI for Construction article or case study (JYC-CAP-02, JYC-CAP-05).
5. Reads the construction background and credentials on About (JYC-CAP-07).
6. Books a call through the booking link, or emails through the education link
   (JYC-CAP-08).

**When it goes wrong:** the old link was `/insights.html`, a page that's now only a
redirect. It takes them to the writing library, never an error page. Every old address
is in the JYC-CAP-09 table, and the build fails if one stops resolving.

### Justin, as author, publishing an article

1. Creates a new article from the template and writes it (JYC-CAP-04).
2. Sets the title, description, date, one primary category and tags.
3. Adds a diagram, a code sample and a link to a related project.
4. Previews it locally, exactly as it will appear.
5. Marks it published and pushes. It appears on the article page, the listings, the RSS
   feed and the sitemap with no further step (JYC-CAP-02, JYC-CAP-03).
6. Later, finds a mistake, corrects the same file and pushes. The URL stays the same. A
   substantive change shows "Updated <date>", and a typo fix shows nothing.

**When it goes wrong:**
- **Saved as draft.** Justin pushes the article still marked draft. It stays off the
  live site: no listing, no feed entry, nothing at its URL. He can still preview it
  locally. Nothing is lost; changing it to published and pushing again publishes it.
- **Missing a required field**, such as no primary category. The build fails and names
  the field. Nothing publishes, and the previous version stays live.
- **The publish fails partway.** The previous version stays live. Justin fixes the
  cause and pushes again.

## 5. Cross-cutting requirements

| Requirement | What must hold | How it's checked |
| --- | --- | --- |
| **Facts register** | Every factual claim on the site traces to one canonical facts register: every figure, credential, employer, status and duration. A page never states a fact differently from the register, and never uses a string the register bans. The current site's register (`content/facts.json` in the website repository) and its check (`tools/verify.js`) are carried forward and extended to articles and case studies. Two changes:<br>• The first-person rule is dropped. First person is allowed site-wide.<br>• Price facts are no longer used on any page.<br>When a page and the register disagree, the page is fixed. The register changes only when the fact itself changes. | An automated check fails the build when a page drifts from the register or uses a banned string, as `verify.js` does today. |
| **Canonical figures** | `content/facts.json` is the one register, and `content/metrics.json` is folded into it. The values:<br>• **Preliminary estimating:** 10 hours → 2 hours<br>• **Project manager knowledge:** months → day one (new in the register, from `metrics.json`)<br>• **Contract package:** keeps the register's current "up to 8 hrs → ~30 min"<br>• **Change order:** keeps the register's current "~10 days → ~3 days" | The register check. |
| **No prices** | No page shows a price or fee. The register's pricing values are kept out of page-facing use. | The check fails the build if a fee from the register, or a price in a fee pattern such as "from $" or a "$N–M" range, appears on a page. |
| **Built vs. led** | Every project and every experience entry shows whether Justin built it himself or led the team that delivered it. Nothing implies he personally built something a team delivered. | A required field in the content schema. The build fails without it. |
| **Maturity and demo** | Every project shows two fields:<br>• **maturity:** `live`, `beta`, `prototype`, `experiment` or `in-development`<br>• **demo:** `public`, `on-request` or `none`<br>Values come from the register, mapped as in the table below. | Required fields in the content schema; the build fails without them. The register check catches drift, as `verify.js` checks status drift today. |
| **Preserved links** | Every address in the JYC-CAP-09 table resolves. | An automated check fails the build if any doesn't. |
| **Responsive** | Every page works on mobile and desktop. | Checked at 375px and 1280px wide. |
| **Accessible** | Navigation and reading are accessible. | WCAG 2.2 AA. |
| **Fast** | Pages load fast. | Lighthouse scores of 90 or more for performance and for accessibility. |
| **Discoverable** | Every published page has SEO metadata and a social preview, and is in the sitemap. Articles are in the RSS feed. | Checked by the build. |

**Mapping the register's current status values**

| Register value | Used by | maturity | demo |
| --- | --- | --- | --- |
| "Public demo" | Change Order Drafting | `live` | `public` |
| "Live, demo on request" | Invoice Intake, Site Safety, Field Reports | `live` | `on-request` |
| "Beta, demonstrable" | Document Workbench, Construction Intelligence | `beta` | `on-request` |
| "Beta" | Bid Comparison, Pay App Preparation, Subcontractor Compliance, Client Selections | `beta` | `none` |
| "In development" | Project Intelligence | `in-development` | `none` |
| "One public demo, three live, four beta" | Operations Automation | No single value. The product shows each of its workflows' values, above. | — |

Change Order Drafting is live at draftconstructionchangeorder.com, so its "Public demo"
maps to `live`. A plain "Beta" says nothing about a demo, so it maps to `none` until the
register says otherwise.

Visual rules in today's `verify.js` (raw hex colors, type tokens, uppercase, arrows and
middle dots) belong to `brand-system`, not to this spec.

## 6. Open product questions

- **Enterprise facts.** The register holds only Construction OS facts today. Justin will
  supply the enterprise employers, roles, achievements and credentials, and the built/led
  value for each, from Career Facts v5. Until they're in, About, the homepage
  introduction and the enterprise pathway page can't pass the facts check. Tracked in
  [justinyurasits.github.io#4](https://github.com/justinyurasits/justinyurasits.github.io/issues/4).
