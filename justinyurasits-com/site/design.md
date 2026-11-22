---
type: design
status: draft
---

# JustinYurasits.com — Site Design

**Draft.** Only the decision log has entries, and all of them are proposals from the
website strategy brief (v0.2, §9). None is approved. Each moves to approved when Justin
approves it.

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
| 2026-11-22 | **Proposed.** No database, custom CMS or complicated hosting. | Open | Keeps the site static and cheap to maintain. | Publishing requirements that a static, file-based site can't meet. |
| 2026-11-22 | **Proposed.** Keep dependencies minimal and the repository easy to understand, so it stays maintainable with AI-assisted coding and design. | Open | Keeps ongoing maintenance low. | Open |
| 2026-11-22 | **Proposed.** Publish automatically with GitHub Actions, or an equivalent workflow, when approved changes reach the production branch. | Open | An article is published by editing one content file and pushing it. | Open |
| 2026-11-22 | **Proposed.** Host on GitHub Pages. | Open | Static hosting with no servers to run. | Open |
| 2026-11-22 | **Proposed.** Write articles and project case studies in Markdown/MDX, managed as Astro content collections with reusable components. | Open | Ordinary publishing needs no edits to page layouts or components. | Open |
| 2026-11-22 | **Proposed.** Build the site with Astro, generated statically. | Open | Static generation, few dependencies, little to maintain. | Open |
