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

Visual design, real copy and articles, launch checks, and the cutover to `main`.

- **Exit criterion:** visual design applied, no `[COPY]` left, launch articles in,
  launch checks pass, `v2` cut over to `main`, and all 16 old addresses verified
  live.
- **Covers:** product spec §1 (launch list) and every row of §5.
- **Depends on:** M1; the site's visual design from
  [`brand-system`](https://github.com/justinyurasits/brand-system); enterprise facts
  ([#4](https://github.com/justinyurasits/justinyurasits.github.io/issues/4)); starting copy ([#5](https://github.com/justinyurasits/justinyurasits.github.io/issues/5)); the résumé, articles and
  case-study material from Justin.
- **GitHub:** [M2 Launch](https://github.com/justinyurasits/justinyurasits.github.io/milestone/3), epic [#8](https://github.com/justinyurasits/justinyurasits.github.io/issues/8).

## Open questions blocking the plan

- Enterprise facts, from Career Facts v5 ([#4](https://github.com/justinyurasits/justinyurasits.github.io/issues/4)). Blocks M2. Justin.
- Reconcile workflow statuses with what currently works ([#28](https://github.com/justinyurasits/justinyurasits.github.io/issues/28)). Blocks
  M2. Justin.
