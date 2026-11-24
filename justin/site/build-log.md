---
type: build-log
status: draft
---

# Justin — Site Build Log

What happened, in order, and what each finding changed. Decisions are in
[design.md](design.md#4-decision-log). This log points to them.

## 2026-11-24 — Design draft for the preview

No code. The pilot is a set of docs in `justin/`, for a site Justin can open
beside v2. The domain is deferred, at his request.

- **justinyurasits-com is already a personal site.** Its product spec is the
  v2 site: two audiences, the headline "AI Product Leader. Systems Designer.
  Hands-On Builder.", Training, and a cutover onto the domain. The live site
  on `main` is still the Construction OS pitch. This pilot is a third thing,
  so it has its own folder. See the placement row in the decision log.
- **The portrait exists.** `images/about-portrait.jpg` on `main` is the photo
  the live About page already uses. The story can use that file. The photo
  date in the file is 2020, which is an open question, not a fact the page
  states.
- **Construction facts and enterprise facts are in different places.** The
  license, the project scale, the library counts and the three measured tasks
  are in `content/facts.json` on `main`. The construction sentences and the
  enterprise employers are on the live About page and are not keys in that
  file. The preview registers the construction sentences and leaves the
  enterprise employers off.
- **Fieldscope has no measured result.** The brief's pilot criteria are drafts,
  and its company names are assumptions to go validate. The case study states
  no result and names no company.
- **The change order generator's prices are unchecked.** Its own README says
  the model writes every price and total. The case study has to say so.
- **Construction OS's public statuses and its design record don't match in
  strength.** The register says "Beta, demonstrable" for two products. The
  Construction OS README says PCO generation is built and not validated, and
  retrieval is not built. The case study carries both.
- **A branch of `justinyurasits.github.io` cannot have its own public Pages
  URL.** That repository publishes `main` to the domain. The preview is a CI
  artifact and a local command, which is what "see the demo" can mean while
  the domain is out of scope.

Nothing has been rolled up from a code repository. There is no code yet.
