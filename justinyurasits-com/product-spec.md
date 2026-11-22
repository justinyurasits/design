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

**Draft.** Where the brief, the strategy brief (v0.2) or Justin's answers don't settle
something, it is marked **Open**, not decided here.

## 1. Product scope

One site that carries Justin's writing (primary), his project case studies, and two
consulting pathways: enterprise AI and construction AI. It replaces the current
Construction OS site at justinyurasits.com and keeps that site's links working. It stops
where the brief's [out-of-scope list](brief.md#6-out-of-scope-on-purpose) starts.

**The first release** includes:
- the homepage, with clear professional positioning
- the writing library and a working publishing workflow
- at least one substantive enterprise AI article, and at least one substantive
  construction AI article or evidence-rich resource
- the Construction OS case study, with existing links preserved
- Work With Me, for both audiences
- About and Contact
- mobile-responsive layouts and basic SEO
- automatic publishing

That is JYC-CAP-01 to JYC-CAP-09, with the product-wide requirements in §5.

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
| Recruiter or HR contact for a C2C placement | Confirm the fit and the engagement type, and reach Justin | Understand, Inquire |
| Owner of a mid-size construction firm, or an executive (COO, head of project management) at a larger one | See that Justin knows construction operations and has built working tools for them, and start a conversation | Understand, Evidence, Inquire |
| Justin, as author | Publish, correct and organize articles without touching page layouts or code | Publish |

## 3. Capabilities

### JYC-CAP-01: Homepage

The front page of a professional technology publication, not a consulting brochure.
A visitor learns who Justin is and gets a path for their audience without scrolling far.

In order:
1. **Introduction:** positioning, specific credentials, and immediate links to both
   consulting pathways. The working headline is *"AI Product Leader. Systems Designer.
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
  positioning and a link to each consulting pathway without scrolling, on desktop and
  on mobile.
- Given at least one published article in each category, when the homepage builds, then
  featured writing includes both categories.
- Given the featured article is unpublished or set back to draft, then the homepage
  doesn't link to it. *Open: what takes its place.*
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
  OS.
- Listings are built automatically: all articles, each category, each tag, plus
  featured and recent sections. Also an RSS feed and a sitemap.

**Acceptance criteria**
- Given a newly published article, when the site builds, then it appears in the full
  listing, its category's page, each of its tags' pages, the recent section, the RSS
  feed and the sitemap, with no listing edited by hand.
- Every article has exactly one primary category. *Open: what happens to an article
  with none, or more than one (see the author journey).*
- Given a tag with one article, then its tag page lists that article. *Open: whether
  tags have a minimum, or a fixed list beyond the starting set.*

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
- *Open: whether a corrected article shows that it was updated, with an updated date
  or a correction note, and when each applies.*

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
- Given an existing article, when Justin corrects it, then he edits that one file, and
  the URL stays the same.
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
- limitations and maturity status (§5)
- screenshots, demonstrations, repositories and related writing

**Acceptance criteria**
- Given any case study, then it shows built or led, and a maturity status.
- Given a case study with a demo or a public repository, then each link works, and
  each is counted for the Evidence goal.
- Given a project with no public repository, then the case study says so plainly and
  shows no dead or placeholder link. *Open: what evidence stands in (screenshots, a
  recorded demo, a write-up), and whether the reason is given.*
- Given an article cites the project, then the case study links back to it.
- Screenshots are of the real system, never generic AI imagery.

**Brief goals:** Evidence, Understand

**Delivered by:** [site](site/spec.md) (spec not written yet)

### JYC-CAP-06: Work With Me

Two commercial pathways. Each explains the business problems an engagement addresses, not
just a list of technical capabilities, and each ends in a clear next action.

- **Enterprise AI Consulting & Leadership:** contract or C2C, fractional AI product
  leadership, advisory, product strategy, solution design, modernization and
  implementation leadership.
  *Open: its opening.*
- **Construction AI Consulting:** education, opportunity assessment, business workflow
  design, advisory, custom implementation and Construction OS-related services.
  It opens with: *"Your 64-year-old COO is about to retire and half your business runs
  in his head."*

**Acceptance criteria**
- Given a visitor on either pathway, then they reach a contact action without leaving
  that pathway.
- Given the construction pathway, then its first line is the hook above, word for word.
- Given any price, duration or service status on either pathway, then it traces to the
  facts register (§5).
- *Open: whether prices are shown. The current site shows audit, build and monthly fees,
  and the register holds them.*
- *Open: whether each pathway is its own page or both share one.*

**Brief goals:** Inquire, Understand

**Delivered by:** [site](site/spec.md) (spec not written yet)

### JYC-CAP-07: About

Justin's professional history, enterprise leadership experience, construction operations
background, credentials, approach and selected achievements.

**Acceptance criteria**
- Given any experience entry or achievement, then it shows whether Justin built it
  himself or led the team that delivered it (§5).
- Given any credential, employer, figure or date, then it traces to the facts register
  (§5).
- *Open: whether a downloadable résumé is offered.*

**Brief goals:** Understand

**Delivered by:** [site](site/spec.md) (spec not written yet)

### JYC-CAP-08: Contact

Simple, professional contact options for consulting, contract engagements, partnerships,
speaking and education.

**Acceptance criteria**
- *Open: how far Contact is from any page.*
- Given a visitor contacting Justin, then they can say which of the five reasons it
  concerns. *Open: how, whether a form, a reason picker, or separate links.*
- *Open: which channels. The current site uses an email address and a booking link.*
- *Open: how an inquiry is counted as relevant, for the Inquire goal.*

**Brief goals:** Inquire

**Delivered by:** [site](site/spec.md) (spec not written yet)

### JYC-CAP-09: Construction OS section and preserved links

Construction OS is the flagship project, with a substantive landing page of its own. It
is a case study on Justin's site, not that product's marketing site
([brief §1](brief.md#1-customer)). Every link into the current Construction OS site keeps
working, and so do the existing product and demo links, until Construction OS moves to
its own domain.

The current site's addresses, which all have to keep working:
- `/`
- `/services.html`, `/engagements.html`, `/work.html`, `/insights.html`, `/about.html`,
  `/privacy.html`, `/terms.html`
- `/ai-projects-fail.html`, `/eighty-ninety-problem.html`, `/tribal-knowledge.html`
- `/products/document-workbench.html`, `/products/construction-intelligence.html`,
  `/products/operations-automation.html`, `/products/project-intelligence.html`,
  `/products/custom-solutions.html`

**Acceptance criteria**
- Given any address in the list above, when a visitor opens it, then they land on the
  page that now holds that content, never an error page.
- Given an old address with no matching content, then the visitor lands somewhere
  useful. *Open: where each old address goes.*
- Given the Construction OS landing page, then it links to each live product and demo.
  Each link works and shows its status from the facts register.
- *Open: whether Construction OS keeps its own visual identity here (the strategy brief
  allows it). That's for brand-system.*

**Brief goals:** Evidence, Understand

**Delivered by:** [site](site/spec.md) (spec not written yet)

## 4. User journeys

### The hiring manager for an agentic or AI product role

1. Clicks Justin's link on LinkedIn and lands on the homepage. The introduction says AI
   product leader and hands-on builder, not "Book a demo" (JYC-CAP-01).
2. Follows the enterprise pathway, or the featured enterprise article (JYC-CAP-03).
3. The article cites a project, and they open its case study. It shows built or led and
   a maturity status (JYC-CAP-05).
4. Opens About and reads which systems Justin built himself and which his teams
   delivered under his leadership (JYC-CAP-07).
5. Contacts Justin about a role (JYC-CAP-08).

**When it goes wrong:** the case study is for a project with no public repository. The
page says so plainly, with no dead link, and shows the evidence that does exist. The
hiring manager can still judge the work. *Open: what that evidence is.*

### The recruiter or HR contact for a C2C placement

1. Lands on the homepage from a link and takes the enterprise pathway (JYC-CAP-01,
   JYC-CAP-06).
2. Confirms contract and C2C engagements are offered, and what kind of work.
3. Checks the background on About (JYC-CAP-07).
4. Gets in touch, naming a contract engagement (JYC-CAP-08).

**When it goes wrong:** *Open: what a recruiter needs that the brief doesn't settle,
such as availability, location or rates, or a résumé to forward.* Until it's settled,
the site doesn't state any of these.

### The construction owner or COO

1. Met Justin in person and follows an old link, `/products/document-workbench.html`,
   from an email or a bookmark (JYC-CAP-09).
2. Lands on the page that now holds that content, then moves to the Construction OS
   landing page with its products and demos.
3. Takes the construction pathway. It opens with the COO hook (JYC-CAP-06).
4. Reads an AI for Construction article or case study (JYC-CAP-02, JYC-CAP-05).
5. Reads the construction background and credentials on About (JYC-CAP-07).
6. Contacts Justin about an assessment or education (JYC-CAP-08).

**When it goes wrong:** an old link has no matching page anymore. The visitor lands
somewhere useful, never on an error page. *Open: where each old address goes
(JYC-CAP-09).*

### Justin, as author, publishing an article

1. Creates a new article from the template and writes it (JYC-CAP-04).
2. Sets the title, description, date, one primary category and tags.
3. Adds a diagram, a code sample and a link to a related project.
4. Previews it locally, exactly as it will appear.
5. Marks it published and pushes. It appears on the article page, the listings, the RSS
   feed and the sitemap with no further step (JYC-CAP-02, JYC-CAP-03).
6. Later, finds a mistake, corrects the same file and pushes. The URL stays the same.

**When it goes wrong:**
- **Saved as draft.** Justin pushes the article still marked draft. It stays off the
  live site: no listing, no feed entry, nothing at its URL. He can still preview it
  locally. Nothing is lost; changing it to published and pushing again publishes it.
- **Missing a required field**, such as no primary category. *Open: whether the
  article is held back or published with a warning, and what Justin is told, and
  where.*
- **The publish fails partway.** *Open: what Justin sees, and whether the site stays on
  the previous version.*

## 5. Cross-cutting requirements

| Requirement | What must hold | How it's checked |
| --- | --- | --- |
| **Facts register** | Every factual claim on the site traces to one canonical facts register: every figure, credential, employer, status, price and duration. A page never states a fact differently from the register, and never uses a string the register bans. The current site's register (`content/facts.json` in the website repository) and its check (`tools/verify.js`) are carried forward, extended to articles and case studies. When a page and the register disagree, the page is fixed. The register changes only when the fact itself changes. | An automated check fails the build when a page drifts from the register or uses a banned string, as `verify.js` does today. |
| **Built vs. led** | Every project and every experience entry shows whether Justin built it himself or led the team that delivered it. Nothing implies he personally built something a team delivered. | *Open: a check that fails when a project or experience entry has no built/led value.* |
| **Maturity status** | Every project shows one status from a fixed list: live systems, beta capabilities, working prototypes, evaluated experiments, and work in development. Status values come from the facts register. | The register check, as `verify.js` checks status drift today. *Open: the final status vocabulary (see §6).* |
| **Preserved links** | Every address on the current site keeps resolving (JYC-CAP-09). | *Open: an automated check of the address list.* |
| **Responsive** | Every page works on desktop and mobile. | *Open: which devices or widths are checked.* |
| **Accessible** | Navigation and reading are accessible. | *Open: the standard (for example a WCAG level) and how it's checked.* |
| **Fast** | Pages load fast. | *Open: the target and how it's measured.* |
| **Discoverable** | Every published page has SEO metadata and a social preview, and is in the sitemap. Articles are in the RSS feed. | *Open.* |

Visual rules in today's `verify.js` (raw hex colors, type tokens, uppercase, arrows and
middle dots) belong to `brand-system`, not to this spec.

## 6. Open product questions

- **Which numbers are canonical.** Two files disagree. `content/metrics.json` gives
  estimates as "half a day → 1 hour", contract packages as "→ 30 min", and change
  orders as "10 days → 3 days". `content/facts.json` gives "~10 hrs → ~2 hrs", "~30 min"
  and "~10 days → ~3 days". The register needs one source. Justin decides.
- **Enterprise facts.** The register holds only Construction OS facts today. The
  enterprise employers, roles, achievements and the built/led value for each need to be
  added before About and the enterprise pathway can pass the facts check. Justin
  supplies them.
- **Status vocabulary.** The strategy brief's five maturity statuses don't match the
  register's current values ("Public demo", "Live, demo on request", "Beta, demonstrable",
  "Beta", "In development"). Justin decides which list wins.
- **First person.** Today's check forbids first person outside About and two
  exempted passages. The supporting positioning line, and a personal site generally,
  use "I". Justin decides whether the rule carries forward. It blocks the facts check
  for the homepage.
- **Where each old address goes** (JYC-CAP-09). This blocks the preserved-links check.
- **Prices on Work With Me** (JYC-CAP-06).
- **The enterprise pathway's opening** (JYC-CAP-06).
- **Contact channels and the reason picker** (JYC-CAP-08), and **what counts as a
  relevant inquiry**.
- **What a recruiter needs** beyond the brief: availability, location, rates, a résumé.
- **What stands in for a public repository** on a case study without one.
- **Corrections:** whether an updated date or a correction note is shown, and when.
- **Responsive, accessible and fast targets** (§5).
