---
type: plan
status: current
---

# JustinYurasits.com — Site Plan

Work still ahead on v2, built on the `v2` branch of
[`justinyurasits.github.io`](https://github.com/justinyurasits/justinyurasits.github.io). `main` stays the live site until the M2 cutover.
Each milestone links to its GitHub milestone, which holds its epic and issues. Finished
milestones move to [build-log.md](build-log.md) at their roll-up; decisions go to
[design.md](design.md).

## Now

### M0 Foundation: one issue left

Done except M0.5 ([#13](https://github.com/justinyurasits/justinyurasits.github.io/issues/13)), the `basis` for the four existing metrics,
which is blocked on Justin. Until it's in, the facts check warns about the four. The rest
of M0 is in [build-log.md](build-log.md).

- **Exit criterion:** M0.5 closed, and the basis check reports no warnings.
- **GitHub:** [M0 Foundation](https://github.com/justinyurasits/justinyurasits.github.io/milestone/1), epic [#6](https://github.com/justinyurasits/justinyurasits.github.io/issues/6).

### M2 Launch

The approved visual design, real copy and articles, launch checks, and the cutover to
`main`. The design is the personal sub-brand in `brand-system` (BRAND-004); the pages
follow the revised product spec (JYC-CAP-01 to 10).

- **Exit criterion:** the approved design applied to every page; no `[COPY]` and no
  placeholder media left; launch articles in; launch checks pass; the M2 roll-up done;
  `v2` cut over to `main` with Justin's explicit approval; all 16 old addresses
  verified live.
- **Order** (new issues M2.10 to M2.18 are created with this plan's issue changes):
  1. M2.10 Navigation, routes and redirects.
  2. [#26](https://github.com/justinyurasits/justinyurasits.github.io/issues/26) M2.1, the shared visual system.
  3. Pages, each built in the approved design on #26:
     1. M2.15 Work with me and the contact panel
     2. M2.13 Demos & Builds and case studies
     3. M2.12 Solutions and Construction OS
     4. M2.14 Writing and article
     5. M2.16 About
     6. M2.17 Training
     7. M2.11 Homepage
  4. Content from Justin, alongside the pages:
     - [#13](https://github.com/justinyurasits/justinyurasits.github.io/issues/13) metric bases
     - [#4](https://github.com/justinyurasits/justinyurasits.github.io/issues/4) enterprise facts
     - [#28](https://github.com/justinyurasits/justinyurasits.github.io/issues/28) statuses
     - [#29](https://github.com/justinyurasits/justinyurasits.github.io/issues/29) the résumé
     - the Training details
     - M2.18 final imagery
     - [#30](https://github.com/justinyurasits/justinyurasits.github.io/issues/30) case studies
     - [#31](https://github.com/justinyurasits/justinyurasits.github.io/issues/31) articles
     - then [#27](https://github.com/justinyurasits/justinyurasits.github.io/issues/27), the copy
  5. [#33](https://github.com/justinyurasits/justinyurasits.github.io/issues/33) launch checks, then the M2 roll-up.
  6. [#34](https://github.com/justinyurasits/justinyurasits.github.io/issues/34) cutover, with Justin's explicit approval.
  7. [#32](https://github.com/justinyurasits/justinyurasits.github.io/issues/32), the live check of every old address.
- **Covers:** product spec §1 (launch list), JYC-CAP-01 to 10, and every row of §5.
- **Depends on:** the revised product spec and site design; BRAND-004 in
  `brand-system`; content from Justin. Final imagery doesn't block structural or visual
  work, but no placeholder ships.
- **GitHub:** [M2 Launch](https://github.com/justinyurasits/justinyurasits.github.io/milestone/3), epic [#8](https://github.com/justinyurasits/justinyurasits.github.io/issues/8).

## Open questions blocking the plan

- Enterprise facts, from Career Facts v5 ([#4](https://github.com/justinyurasits/justinyurasits.github.io/issues/4)). Blocks M2. Justin.
- Reconcile workflow statuses with what currently works ([#28](https://github.com/justinyurasits/justinyurasits.github.io/issues/28)). Blocks
  M2. Justin.
