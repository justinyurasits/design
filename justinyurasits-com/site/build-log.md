---
type: build-log
status: current
---

# JustinYurasits.com — Site Build Log

What happened, in order, and what each finding changed. Decisions are in
[design.md](design.md#4-decision-log); this log points to them.

## 2026-11-22 — M0 Foundation, except M0.5 ([#35](https://github.com/justinyurasits/justinyurasits.github.io/pull/35)–[#40](https://github.com/justinyurasits/justinyurasits.github.io/pull/40))

Standard repo files, Astro 7 on Node 22, content schemas, the facts register, the site
checks, CI and the deploy workflow, all on `v2`. The live site on `main` is untouched.
M0.5, the `basis` for the four metrics, is open and blocked on Justin
([#13](https://github.com/justinyurasits/justinyurasits.github.io/issues/13)). Until then the check warns about the four.

- **No CI existed before v2.** So the first PR ([#35](https://github.com/justinyurasits/justinyurasits.github.io/pull/35)) couldn't meet the "CI passes"
  half of the self-merge override, and merged on local checks. Every PR after it had CI.
- **Astro 7 needs Node 22.23.4 or later,** and the machine defaulted to Node 20, which is
  past end-of-life. Node 22 was installed through nvm and pinned in `.nvmrc`
  ([#36](https://github.com/justinyurasits/justinyurasits.github.io/pull/36)).
- **Astro 7 uses Zod 4.** Field messages go in `{ error: '…' }`, and Astro adds the file
  name, which gives the plain-language errors JYC-CAP-04 asks for. `node --test tests/`
  fails on Node 22 and needs a quoted glob ([#37](https://github.com/justinyurasits/justinyurasits.github.io/pull/37)).
- **The old register undercounted live workflows.** "One public demo, three live, four
  beta" missed that Change Order Drafting is both the public demo and live: it's 4 live.
  This feeds M2.3, reconciling statuses ([#28](https://github.com/justinyurasits/justinyurasits.github.io/issues/28)) ([#38](https://github.com/justinyurasits/justinyurasits.github.io/pull/38)).
- **Checking the built HTML, not the source,** catches a fact however a page produces it.
  The schema catches missing fields earlier ([#39](https://github.com/justinyurasits/justinyurasits.github.io/pull/39)).
- **A workflow file on `v2` can't fire on a `main` push** until the cutover puts it on
  `main`, so the cutover merge is the main deploy safety. The repository variable is the
  second ([#40](https://github.com/justinyurasits/justinyurasits.github.io/pull/40)).

## 2026-11-22 — M1 Pages ([#41](https://github.com/justinyurasits/justinyurasits.github.io/pull/41)–[#50](https://github.com/justinyurasits/justinyurasits.github.io/pull/50))

Every capability, JYC-CAP-01 to 09, built with neutral styling and `[COPY]` slots.
- **Pages:** the homepage, the writing library with categories, tags, RSS and sitemap,
  the article page, projects and case studies, both pathway pages, About, Contact, and
  the Construction OS landing page.
- **Publishing:** the routine `new-article`, `preview` and `check`.
- **Old addresses:** all 16 preserved.

At the end: `npm run check` passes on 25 pages, and 85 tests pass.

- **The link check caught a link to a page a later issue builds.** The RSS `<link>` was
  added before the feed existed, and moved to the feed's PR ([#41](https://github.com/justinyurasits/justinyurasits.github.io/pull/41)).
- **Parallel tests shared state, three ways:**
  - **The content cache:** Astro keeps it in `node_modules/.astro`, and the throwaway
    test sites share a symlinked `node_modules`, so CI failed a test that passed locally.
    Fixed with `cacheDir: './.astro/cache'` ([#41](https://github.com/justinyurasits/justinyurasits.github.io/pull/41)).
  - **A hung server:** killing `npm` left the Astro dev server running, and its open
    output pipe hung CI for 10 minutes. Fixed by stopping the whole process group, with
    test and job timeouts ([#43](https://github.com/justinyurasits/justinyurasits.github.io/pull/43)).
  - **Ports:** random ports occasionally collided under four parallel builds. Fixed with
    OS-assigned free ports ([#49](https://github.com/justinyurasits/justinyurasits.github.io/pull/49)).

  These became candidate principle 3.
- **Astro processes drafts too.** The first article template's example image broke the
  build for a fresh draft, so the example now sits in a comment ([#43](https://github.com/justinyurasits/justinyurasits.github.io/pull/43)).
- **A status drift is reported once per page that shows it,** for example the case study
  and the index. Noisy, but accurate ([#44](https://github.com/justinyurasits/justinyurasits.github.io/pull/44)).
- **"Every claim traces to the register" is only checkable if the claim is rendered from
  it.** Free-text experience titles were replaced with register keys ([#45](https://github.com/justinyurasits/justinyurasits.github.io/pull/45)). This
  became candidate principle 1.
- **At 375px the seven-link navigation wraps over three lines** and still leaves the
  introduction above the fold. Brand-system's header in M2.1 has to keep that, and the
  browser test will catch it ([#49](https://github.com/justinyurasits/justinyurasits.github.io/pull/49)).
- **The preserved-links check failed every M0.6 unit test,** because their fixture
  sites have no old addresses. The address list is now an option of the check
  ([#50](https://github.com/justinyurasits/justinyurasits.github.io/pull/50)).
- **Checking that redirect files exist would miss a renamed product,** whose anchor moves
  and quietly breaks an old link. Following each redirect to its final anchor catches it
  ([#50](https://github.com/justinyurasits/justinyurasits.github.io/pull/50)). This became candidate principle 2.

Roll-up: justinyurasits.github.io #35–#50
