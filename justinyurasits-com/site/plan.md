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

### M0 Foundation

The repository, the build and the checks are in place on `v2`, so every page after it
is built against the content model and checked from the first commit. Serves the
brief's Publish goal.

- **Exit criterion:** on `v2`, CI builds the site and runs the schema, register and
  discoverability checks on every PR, and they pass. Repo files follow template v1.7.
  No visual design needed.
- **Covers:** JYC-CAP-04 (overrides, drafts, missing fields, failed publish),
  JYC-CAP-08 (Contact in the header and footer), and the facts register, fee, schema and
  discoverability checks (product spec §5).
- **Depends on:** the decided stack and repository overrides in
  [design.md](design.md#4-decision-log).
- **GitHub:** [M0 Foundation](https://github.com/justinyurasits/justinyurasits.github.io/milestone/1), epic [#6](https://github.com/justinyurasits/justinyurasits.github.io/issues/6).

## Next

### M1 Pages

Every capability built with neutral styling and `[COPY]` placeholders. Serves every
brief goal.

- **Exit criterion:** every capability JYC-CAP-01 to 09 is built with neutral styling
  and `[COPY]` placeholders, and passes its acceptance criteria. The preserved-links
  check passes. No visual design needed.
- **Covers:** JYC-CAP-01 to JYC-CAP-09.
- **Depends on:** M0.
- **GitHub:** [M1 Pages](https://github.com/justinyurasits/justinyurasits.github.io/milestone/2), epic [#7](https://github.com/justinyurasits/justinyurasits.github.io/issues/7). Stops for a roll-up
  when done.

## Later

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
