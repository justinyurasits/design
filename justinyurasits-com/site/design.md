---
type: design
status: draft
---

# JustinYurasits.com — Site Design

**Draft.** Only the decision log has entries, and every one is decided:
- the stack: Astro, Markdown/MDX, GitHub Pages and GitHub Actions
- redirect pages for old addresses
- no database or CMS, and minimal dependencies
- three overrides for the site repository's `CLAUDE.md`

## 1. Scope and boundaries

**Open.** What the first release builds and what it defers follows from the product
spec, which isn't written yet. Visual rules (type, color, spacing, components) come from
[`brand-system`](https://github.com/justinyurasits/brand-system), not from this doc.

## 2. How it works

**Open.**

## 3. Constraints

**Open.**

## 4. Decision log

One entry per decision, newest at the top. A plan or build log may point to a decision
here; neither records one.

| Date | Decision | Options considered | Why | What would change it |
| --- | --- | --- | --- | --- |
| 2026-11-22 | **Decided.** Through M0 and M1, Claude Code may merge its own pull requests into `v2` once CI passes and every acceptance criterion is checked in the pull request body. Justin reviews the work at each milestone's roll-up. Merging to `main` (the M2 cutover) still requires Justin's approval. The site repository's `CLAUDE.md` records this under section 7, Overrides: *"Section 3's 'Never merge' doesn't apply to Claude Code's own pull requests into `v2` during M0 and M1, once CI passes and every acceptance criterion is checked in the pull request body. Justin reviews at each milestone's roll-up. Merging to `main` always needs Justin's approval."* | Justin merges every pull request | Keeps M0 and M1 moving without a review per pull request; the roll-up at each milestone is the review. | A merged pull request that fails an acceptance criterion found at roll-up, or the start of M2. |
| 2026-11-22 | **Decided.** Until cutover, every pull request targets `v2`, not `main`. `main` stays the live site until the M2 cutover merges `v2` into it. The site repository's `CLAUDE.md` records this under section 7, Overrides: *"Until cutover, branch from `v2` and target `v2` with every pull request. `main` is the live site and changes only at cutover."* | Building v2 on `main` behind a flag; a separate repository | The live site keeps running unchanged while v2 is built in the same repository. | Cutover. |
| 2026-11-22 | **Decided.** Old addresses that move are served as redirect pages: a meta refresh plus a canonical link to the destination. GitHub Pages can't issue 301 redirects, so search engines and browsers see a redirect page, not a permanent redirect. The preserved-links check follows each one to its final destination ([JYC-CAP-09](../product-spec.md#jyc-cap-09-construction-os-section-and-preserved-links)). | Server-side 301 redirects, which GitHub Pages doesn't offer | Keeps every old address working on GitHub Pages. | Moving to a host that supports server-side redirects. |
| 2026-11-22 | **Decided.** After cutover, Justin may push article-only changes directly to `main`: an article's content file and its images. Code changes follow issues and pull requests. The site repository's `CLAUDE.md` records this under section 7, Overrides: *"After cutover, section 3's 'Work only from a GitHub issue' and 'Never commit to `main`' don't apply to article-only changes Justin pushes himself. Code changes, and all work by Claude Code, follow section 3."* | Every change through an issue and a pull request | Publishing an article is one file and a push ([JYC-CAP-04](../product-spec.md#jyc-cap-04-author-publishing-workflow)); a pull request for each article would make publishing harder, against the brief's Publish goal. | Article pushes that break the build or the live site. |
| 2026-11-22 | **Decided.** No database, custom CMS or complicated hosting. | Open | Keeps the site static and cheap to maintain. | Publishing requirements that a static, file-based site can't meet. |
| 2026-11-22 | **Decided.** Keep dependencies minimal and the repository easy to understand, so it stays maintainable with AI-assisted coding and design. | Open | Keeps ongoing maintenance low. | Open |
| 2026-11-22 | **Decided.** Publish automatically with GitHub Actions, or an equivalent workflow, when approved changes reach the production branch. | Open | An article is published by editing one content file and pushing it. | Open |
| 2026-11-22 | **Decided.** Host on GitHub Pages. | Open | Static hosting with no servers to run. | Open |
| 2026-11-22 | **Decided.** Write articles and project case studies in Markdown/MDX, managed as Astro content collections with reusable components. | Open | Ordinary publishing needs no edits to page layouts or components. | Open |
| 2026-11-22 | **Decided.** Build the site with Astro, generated statically. | Open | Static generation, few dependencies, little to maintain. | Open |
