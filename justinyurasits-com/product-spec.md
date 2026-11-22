---
type: product-spec
status: draft
---

# JustinYurasits.com — Product Spec

What the site must do for its visitors and its author, capability by capability, and how
anyone can check that it does. Behavior a visitor or the author can observe, not
implementation. The [brief](brief.md) says why. The site's [design doc](site/design.md)
says how, including its tech stack. Visual rules come from the personal sub-brand in
[`brand-system`](https://github.com/justinyurasits/brand-system), `brands/personal/`
(BRAND-004).

**Draft.** Three questions are open, in §6. The old-address mapping in JYC-CAP-09 is
approved with this spec.

## 1. Product scope

One site that carries Justin's writing (primary), his solutions and demos with their case
studies, training, and two consulting tracks: enterprise AI and construction AI. It
replaces the current Construction OS site at justinyurasits.com and keeps that site's
links working. It stops where the brief's
[out-of-scope list](brief.md#6-out-of-scope-on-purpose) starts. No page shows Justin's fees
or service pricing.

The navigation is Solutions, Demos, Writing, Training and About, with Work with me as the
header's action. Writing stays the site's primary strategic purpose wherever it sits in
the navigation.

**The first release** includes:
- the homepage, with clear professional positioning
- the writing library and a working publishing workflow
- at least one substantive enterprise AI article, and at least one substantive
  construction AI article or evidence-rich resource
- Solutions and the Construction OS page, with existing links preserved
- Demos & Builds, with a case study for each entry
- Training, informational only
- Work with me: one page with two tracks and the contact panel
- About
- mobile-responsive layouts and basic SEO
- automatic publishing
- **a publishing demonstration:** one real article with images, code, references and a
  related project, published using the documented routine (JYC-CAP-04)

That is JYC-CAP-01 to JYC-CAP-10, with the product-wide requirements in §5.

**Existing articles.** Three articles from the current site are migrated as articles.
They were published there, then withdrawn on 2026-09-19 and replaced with redirects to
`/`. Their text is still in the website repository's history (commit `416e8ba`).

They migrate as **drafts to re-edit, not launch-ready**. None counts toward the launch
requirements as it stands. Once re-edited and published, any of them could meet the
construction article requirement. None would meet the enterprise one, so that article is
new writing either way.

| Old address | Title | Category | After re-editing |
| --- | --- | --- | --- |
| `/tribal-knowledge.html` | What Walks Out the Door When Your Best Person Leaves | AI for Construction | Could meet the construction article requirement. It's the closest to the construction track's starting copy, the retiring-COO opening. |
| `/eighty-ninety-problem.html` | The Work Around the Work: Why Construction Operations Stay So Manual | AI for Construction | Could meet the construction article requirement. |
| `/ai-projects-fail.html` | AI Can't Automate a Business It Doesn't Understand | AI for Construction | Could meet the construction article requirement. Its argument applies to enterprise readers too, but it's written for construction businesses. |

Each passes the facts check before it is published. None contains a banned string
today. Two state figures ("20 years", "10 days"). Each is either a claim about Justin or
his products, traced to the register, or supported in the article itself (§5).

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
| Owner or leader of a construction firm looking for AI education | Find a class that fits, see what participants leave with, and register interest or ask about private training | Inquire, Understand |
| Justin, as author | Publish, correct and organize articles without touching page layouts or code | Publish |

## 3. Capabilities

### JYC-CAP-01: Homepage

The front page of a professional technology site: not a consulting brochure, and not a
product site. A visitor learns who Justin is and how to engage him without scrolling far.

In order:
1. **Hero:** positioning, the Work with me and Explore my work actions, and a portrait.
   The working headline is *"AI Product Leader. Systems Designer. Hands-On Builder."* The
   supporting line is *"I combine enterprise AI product leadership, firsthand business
   operations experience, and hands-on AI software development to help organizations
   turn complex problems into practical AI systems."* The final hero copy is chosen in
   the copy pass; the approved design's prototype text is illustrative.
2. **Capabilities:** three short statements of what Justin does.
3. **Solutions:** applied work, with Construction OS as its flagship (JYC-CAP-09).
4. **Demos:** working systems and experiments (JYC-CAP-05).
5. **Writing:** articles for both audiences (JYC-CAP-02).
6. **Work with me:** both consulting tracks, each with a clear next action (JYC-CAP-06).

Writing remains the site's primary strategic purpose, wherever it sits on the page
([brief](brief.md)).

**Acceptance criteria**
- Given a visitor arriving at `/`, when the page loads, then the headline and the Work
  with me and Explore my work actions show without scrolling, at 375px and at 1280px.
- Given the homepage, then its Work with me section links to both consulting tracks, and
  so does the footer on every page (JYC-CAP-06, JYC-CAP-08).
- Given at least one published article in each category, when the homepage builds, then
  its Writing section includes both categories.
- Every credential and claim on the homepage traces to the facts register (§5).

**Brief goals:** Understand, Read, Inquire

**Delivered by:** [site](site/spec.md)

### JYC-CAP-02: Writing library and categories

A publication-style library of long-form articles, technical explanations, AI strategy,
research and implementation lessons. It is browsable by category and by tag.

- A featured article leads the library.
- Two primary categories: **Enterprise AI & Product Leadership** and **AI for
  Construction**. Every article has exactly one primary category.
- Topic tags, any number per article. The starting set is Agentic AI, AI Systems,
  Conversational AI, Evaluation, Product Strategy, Intent Design, Document Intelligence
  and Construction OS. New tags are added as articles need them. AI Systems is a tag, not
  a category.
- Category filters narrow the full listing in place. Without JavaScript, every article
  shows.
- Listings are built automatically: all articles, each category, each tag, plus
  featured and recent sections. Also an RSS feed and a sitemap.

**Acceptance criteria**
- Given a newly published article, when the site builds, then it appears in the full
  listing, its category's page, each of its tags' pages, the recent section, the RSS
  feed and the sitemap, with no listing edited by hand.
- Given an article with no primary category, or more than one, then the build fails and
  names the field. Nothing publishes.
- Given the featured article is unpublished or set back to draft, then the writing
  library features the most recent published article in the same category instead.
- Given the category filters, when a visitor picks a category, then the listing shows
  only that category's articles and says how many it shows. Without JavaScript, every
  article shows.

**Brief goals:** Read

**Delivered by:** [site](site/spec.md)

### JYC-CAP-03: Article page

A clean, readable long-form page that carries technical content well.

- Title, description, publication date, primary category and tags
- Images, diagrams and code with syntax highlighting, as each article needs them
- A deck under the title, and a byline
- A table of contents for longer articles
- References and notes
- Links to related projects and related expertise
- Two related articles
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
- Given an article with two or more sections, then a table of contents links to each
  section heading.
- Given an article, then it shows two related articles: the ones Justin picks,
  otherwise the two newest in the same category. A draft is never shown.

**Brief goals:** Read, Evidence

**Delivered by:** [site](site/spec.md)

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

The source format and push-to-publish mechanism are decided in
[site/design.md](site/design.md#4-decision-log), not here.

After cutover, article-only changes (an article's content file and its images) may be
pushed by Justin directly to `main`. Code changes follow issues and pull requests. This is recorded in
[site/design.md](site/design.md#4-decision-log) as an override for section 7 of the
site repository's `CLAUDE.md`.

**Acceptance criteria**
- Given the site is configured, when Justin publishes a standard text article, then he
  edits one content file and pushes it, and changes no site component.
- Given Justin publishing any article, then he follows a documented short routine. There
  is one command to create a new article, one command to preview it, and a validation
  result in plain language. No Astro knowledge is needed at any step.
- Given an article-only change, then Justin can push it directly to `main`. Given any
  change to code, then it goes through an issue and a pull request.
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

**Delivered by:** [site](site/spec.md)

### JYC-CAP-05: Demos & Builds and case studies

The Demos & Builds page (`/demos/`, "Demos" in the navigation) lists working
demonstrations, prototypes and experiments, with a featured build first and filters by
topic. Every entry shows what a visitor can view, Justin's role, its maturity, its demo
availability and its limitations. Actual demonstrations are clearly told apart from
experiments and from work with no public demo.

Each entry has a substantive case study at `/demos/<entry>/`: evidence-backed, not a
visual gallery, with relevant demos, repositories and architecture details where they
exist. Case studies cover Construction OS, AI applications, agents, test harnesses,
technical experiments and other significant work. Every case study uses the same format
and can include:

- the business or technical problem
- Justin's role and ownership: **built**, **led** or **both**, and what he personally
  did (§5)
- the solution architecture and approach
- important design decisions and tradeoffs
- implemented functionality
- testing and evaluation evidence
- limitations, maturity and demo availability (§5)
- screenshots, demonstrations, repositories and related writing

**Acceptance criteria**
- Given any case study, then it shows built, led or both, what Justin personally did,
  its maturity, and its demo availability. The build fails if any of them is missing.
- Given a case study with a public demo or a public repository, then each link works.
- Given a project with no public repository, then the case study shows at least one of:
  screenshots, a walkthrough, or a sanitized architecture explanation. It shows no dead
  or placeholder link.
- Given one of Justin's own projects in a private repository, then it's labeled
  "Private repository, walkthrough on request." The label is used only for Justin's own
  repositories.
- Given confidential work for an employer or client, then the case study shows no
  client-identifying detail: no names, documents, data or screenshots that identify the
  client.
- Given an article cites the project, then the case study links back to it.
- Screenshots are of the real system, never generic AI imagery.
- Given any entry, then it shows what a visitor can view and its limitations. The build
  fails if either is missing.
- Given an entry with demo `none`, then nothing on its card or its case study says or
  implies a demo exists. Its demo availability reads "No demo".
- Given the topic filters, when a visitor picks a topic, then only matching entries
  show. Without JavaScript, every entry shows.

**Brief goals:** Evidence, Understand

**Delivered by:** [site](site/spec.md)

### JYC-CAP-06: Work With Me

One page, `/work-with-me/`, with two consulting tracks of equal weight: **Enterprise AI
Consulting & Leadership** (`#enterprise`) and **Construction AI Consulting**
(`#construction`). Each track opens with a named business problem, states the outcomes
an engagement delivers rather than just a list of technical capabilities, and ends with
a next step that reaches the contact panel (JYC-CAP-08) on the same page. The page never
shows Justin's fees or service pricing. This replaces one pathway page per audience,
decided in #70; Justin changed it on 2026-11-22 to adopt the approved design.

Starting copy for both openings is held in the site's code repository, not here
([justinyurasits.github.io#5](https://github.com/justinyurasits/justinyurasits.github.io/issues/5)).

- **Enterprise AI Consulting & Leadership:** contract or C2C, fractional AI product
  leadership, advisory, product strategy, solution design, modernization and
  implementation leadership.
  - It states the engagement types and *"remote, based in Boston"*, and links to a
    downloadable résumé PDF.
  - It shows no rates or availability dates.
- **Construction AI Consulting:** education, opportunity assessment, business workflow
  design, advisory, custom implementation and Construction OS-related services.

**Acceptance criteria**
- Given either track, then it opens with a named business problem its audience has.
- Given either track, then it states the outcomes of an engagement.
- Given either track, then it ends with a next step that reaches the contact panel
  without leaving the page.
- Given the two tracks, then they have the same structure: the problem, the outcomes,
  what working together looks like, and the next step.
- Given the enterprise track, then the résumé PDF downloads from it, and the page shows
  no rates or availability dates.
- Given any claim about Justin or his products on the page, then it traces to the facts
  register (§5).
- Given the page, then it shows none of Justin's fees or service pricing (§5).

**Brief goals:** Inquire, Understand

**Delivered by:** [site](site/spec.md)

### JYC-CAP-07: About

Justin's professional history, enterprise leadership experience, construction operations
background, credentials, approach and selected achievements. Prose sections on
enterprise leadership, hands-on building, construction background and approach, plus
professional history, credentials and selected achievements, each with built-versus-led
attribution where it applies.

**Acceptance criteria**
- Given any experience entry or achievement, then it shows whether Justin built it, led
  the team that delivered it, or both, with one line on what he personally did. The
  build fails if either is missing (§5).
- Given any credential, employer, figure or date, then it traces to the facts register
  (§5).

**Brief goals:** Understand

**Delivered by:** [site](site/spec.md)

### JYC-CAP-08: Contact

Simple, professional contact for consulting, contract engagements, partnerships, speaking
and education. Work with me is in the header of every page. Its contact panel
(`/work-with-me/#contact`) holds the contact options:
- an email link for each of the five reasons
- the booking link (`cal.com/justinyurasits`)
- LinkedIn, as a supplement

The footer's Contact group, on every page, links email and LinkedIn. There's no form and
no form backend. `/contact/` redirects to the panel.

**Acceptance criteria**
- Given any page, then Work with me is in the header, and the footer has a Contact
  group.
- Given a visitor choosing a reason, then each of the five reasons has its own email
  link with a prefilled subject naming that reason.
- Given a visitor who wants to talk, then the booking link opens Justin's booking page.
- Given the contact panel, then LinkedIn is offered alongside email and booking, never
  instead of them.
- Given an inquiry arrives, then Justin tags it relevant or not by hand. Tagged
  inquiries are the Inquire goal's measure.

**Brief goals:** Inquire

**Delivered by:** [site](site/spec.md)

### JYC-CAP-09: Solutions, Construction OS and preserved links

**Solutions** (`/solutions/`) explains how Justin applies AI to business problems: the
Construction OS flagship, the applied solution areas, and a note on scope. It's part of
Justin's professional site, not Construction OS's marketing site
([brief §1](brief.md#1-customer)), and enterprise AI and construction AI carry equal
weight on it.

**Construction OS** (`/solutions/construction-os/`) has a section for each of its four
products, each with an anchor. Each section shows the maturity and demo availability of
the product or its workflows, from the register. Construction OS has no status of its
own: it shows its products' and workflows' (§5).

Every link into the old Construction OS site keeps working, and so do existing product
and demo links, until Construction OS moves to its own domain. These pages use the site's
own visual design. Construction OS's separate properties keep their own brand.

**Old-address mapping.**

| Current address | What it holds today | Goes to |
| --- | --- | --- |
| `/` | Construction OS home | The new homepage (JYC-CAP-01) |
| `/services.html` | Construction services | The construction track (`/work-with-me/#construction`, JYC-CAP-06) |
| `/engagements.html` | Redirect to `/services.html` | The construction track |
| `/work.html` | Redirect to `/` | Demos & Builds (`/demos/`, JYC-CAP-05) |
| `/insights.html` | Redirect to `/` (was the article listing) | The writing library (JYC-CAP-02) |
| `/about.html` | About | About (JYC-CAP-07) |
| `/privacy.html` | Privacy policy | Kept at the same address |
| `/terms.html` | Terms | Kept at the same address |
| `/tribal-knowledge.html` | Redirect to `/` (was an article) | The migrated article once it's re-edited and published (§1); the writing library until then |
| `/eighty-ninety-problem.html` | Redirect to `/` (was an article) | The same |
| `/ai-projects-fail.html` | Redirect to `/` (was an article) | The same |
| `/products/document-workbench.html` | Product page | The Construction OS page, at Document Workbench |
| `/products/construction-intelligence.html` | Product page | The Construction OS page, at Construction Intelligence |
| `/products/operations-automation.html` | Product page | The Construction OS page, at Operations Automation |
| `/products/project-intelligence.html` | Product page | The Construction OS page, at Project Intelligence |
| `/products/custom-solutions.html` | Product page | The construction track |

**Acceptance criteria**
- Given any address in the table that moves, then it serves a redirect page (a meta
  refresh plus a canonical link) to its "Goes to" destination, never an error page.
  GitHub Pages can't issue 301 redirects. The limitation is logged in
  [site/design.md](site/design.md#4-decision-log).
- Given the preserved-links check, then it follows each address to its final
  destination. It fails the build if the destination doesn't resolve, or if the anchor
  target the address points at (such as the Document Workbench section of the
  Construction OS page) doesn't exist there.
- Given the Construction OS page, then it links to each live product and demo. Each link
  works and shows its maturity and demo availability (§5).
- Given each solution area, then it says whether it's an existing build, a consulting
  service or a possible custom engagement.
- Given the Construction OS flagship on Solutions, then it links to the Construction OS
  page.

**Brief goals:** Evidence, Understand, Inquire

**Delivered by:** [site](site/spec.md)

### JYC-CAP-10: Training

Informational pages for AI education, starting with the construction audience
([brief §1](brief.md#1-customer)). `/training/` lists the classes, each with its audience,
level, format, prerequisites, schedule, description and what a participant leaves with.
Then a way to stay informed, private company training, and workshops being planned.
There's no registration, form, payment or course management in the first release;
interest arrives by email. Enterprise training can be added later as content.

**Acceptance criteria**
- Given any class, then it shows its audience, level, format, prerequisites, schedule,
  description and what a participant leaves with. The build fails if any is missing.
- Given a visitor interested in a class, then its email link opens an email with a
  prefilled subject naming the class.
- Given the training page, then it has no registration, form or payment, and shows no
  tuition or fees (§5).
- Given a third-party price on the page, such as a required subscription, then it has
  been checked against its source before publishing.
- Given private company training, then it links to the construction consulting track
  (JYC-CAP-06).
- Given a class for another audience, then it's added as content, with no change to the
  page.

**Brief goals:** Inquire, Understand

**Delivered by:** [site](site/spec.md)

## 4. User journeys

### The hiring manager for an agentic or AI product role

1. Clicks Justin's link on LinkedIn and lands on the homepage. The introduction says AI
   product leader and hands-on builder, not "Book a demo" (JYC-CAP-01).
2. Opens Work with me from the header and reads the enterprise track, or opens the
   featured enterprise article (JYC-CAP-06, JYC-CAP-03).
3. The article cites a project, and they open its case study from Demos & Builds. It shows built, led or
   both, what Justin personally did, maturity and demo availability (JYC-CAP-05).
4. Opens About and reads which systems Justin built himself and which his teams
   delivered under his leadership (JYC-CAP-07).
5. Uses the contract-engagement email link in the Work with me contact panel
   (JYC-CAP-08).

**When it goes wrong:** the case study is for a project with no public repository. If
it's Justin's own project, it shows screenshots, a walkthrough or a sanitized
architecture explanation, labeled "Private repository, walkthrough on request." If it's
confidential work for an employer, it shows the same kinds of evidence with no
client-identifying detail. Neither has a dead link. The hiring manager can still judge
the work, and can ask for more through the contact panel.

### The recruiter or HR contact for a C2C placement

1. Lands on the homepage from a link and opens Work with me, at the enterprise track
   (JYC-CAP-01, JYC-CAP-06).
2. Sees the engagement types, contract and C2C among them, and "remote, based in
   Boston".
3. Downloads the résumé PDF to forward.
4. Emails Justin through the contract-engagement link, with its subject prefilled
   (JYC-CAP-08).

**When it goes wrong:** the recruiter wants a rate or a start date. The site gives
neither. They ask through the contact panel, and the prefilled subject tells Justin
what it's about.

### The construction owner or COO

1. Met Justin in person and follows an old link, `/products/document-workbench.html`,
   from an email or a bookmark (JYC-CAP-09).
2. Lands on the Construction OS page under Solutions, at Document Workbench, with its
   products and their statuses.
3. Opens Work with me. The construction track opens with a business problem they
   recognize (JYC-CAP-06).
4. Reads an AI for Construction article or case study (JYC-CAP-02, JYC-CAP-05).
5. Looks at Training for a class for their leadership team, and emails about it
   (JYC-CAP-10).
6. Reads the construction background and credentials on About (JYC-CAP-07).
7. Books a call through the booking link, or emails through the education link
   (JYC-CAP-08).

**When it goes wrong:** the old link was `/insights.html`, a page that's now only a
redirect. Its redirect page takes them to the writing library, never an error page. Every old address
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
| **Facts register** | The register governs claims about Justin and his products only: credentials, employers, roles, product status and product metrics. Wherever such a claim appears, it never differs from the register, and no page uses a string the register bans.<br>Other figures inside an article are supported in the article itself, with a citation, the method, or a label saying they're illustrative. They don't go in the register.<br>Every metric entry has a required `basis`: how and where it was measured, for example "measured across ~20 real jobs and bids".<br>The current site's register (`content/facts.json` in the website repository) and its check (`tools/verify.js`) are carried forward. Two changes:<br>• The first-person rule is dropped. First person is allowed site-wide.<br>• Justin's fee and service-pricing facts are kept out of page-facing use.<br>When a page and the register disagree, the page is fixed. The register changes only when the fact itself changes. | An automated check fails the build when a claim about Justin or his products drifts from the register, when a page uses a banned string, or when a metric entry has no `basis`. Figures in articles that aren't about Justin or his products aren't checked against the register. |
| **Canonical figures** | `content/facts.json` is the one register, and `content/metrics.json` is folded into it. The values:<br>• **Preliminary estimating:** "~10 hrs → ~2 hrs", as the register has it<br>• **Project manager knowledge:** months → day one (new in the register, from `metrics.json`)<br>• **Contract package:** keeps the register's current "up to 8 hrs → ~30 min"<br>• **Change order:** keeps the register's current "~10 days → ~3 days"<br>Each gets its `basis` when the register is updated. | The register check. |
| **No fees** | No page shows Justin's fees or service pricing. Tuition for Justin's training counts as his fees. Other monetary figures in articles and case studies are allowed, and a third-party price on Training is checked against its source before it's published. | The check fails the build if one of the register's fee values appears on any page. |
| **Built vs. led** | Every project and every experience entry has two fields:<br>• **role:** `built`, `led` or `both`<br>• **what I personally did:** one line<br>Nothing implies Justin personally built something a team delivered. | Both are required fields in the content schema. The build fails without either. |
| **Maturity and demo** | Every project and product shows two fields:<br>• **maturity:** `live`, `beta`, `prototype`, `experiment` or `in-development`<br>• **demo:** `public`, `on-request` or `none`<br>Values come from the register, mapped as in the table below. There's no "Active Build" value. Construction OS has no status of its own: it shows its products' and workflows' values. | Required fields in the content schema; the build fails without them. The register check catches drift, as `verify.js` checks status drift today. |
| **Preserved links** | Every address in the JYC-CAP-09 table reaches its destination, through a redirect page where it moves. Every anchor target it points at exists. | An automated check follows each address to its final destination, and fails the build if the destination or the anchor target is missing. |
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
| (none) | Construction OS | No single value. It shows its four products' values, and Operations Automation's workflows'. | — |

Change Order Drafting is live at draftconstructionchangeorder.com, so its "Public demo"
maps to `live`. A plain "Beta" says nothing about a demo, so it maps to `none` until the
register says otherwise.

Visual rules come from brand-system's personal sub-brand (BRAND-004), not from this spec.
The old `verify.js` visual rules (raw hex colors, type tokens, uppercase, arrows and
middle dots) belong to the Construction OS brand and don't apply to this site.

## 6. Open product questions

- **Enterprise facts.** The register holds only Construction OS facts today. Justin will
  supply the enterprise employers, roles, achievements and credentials, and the built/led
  value for each, from Career Facts v5. Until they're in, About, the homepage and the
  enterprise track can't pass the facts check. Tracked in
  [justinyurasits.github.io#4](https://github.com/justinyurasits/justinyurasits.github.io/issues/4).
- **Reconcile workflow statuses with what currently works.** The register's workflow
  statuses, and the maturity and demo values mapped from them in §5, need checking
  against what runs today. Justin decides. This includes the verified statuses of
  Construction OS's four products (JYC-CAP-09).
- **Construction OS role.** What Justin personally did on Construction OS (its `role` and
  `personallyDid`) is pending his confirmation. Its case study can't publish until then,
  and no page describes the role, such as "sole designer and builder", before it's
  confirmed.
