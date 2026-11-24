---
type: spec
status: draft
---

# Justin — Site Spec

The site is the whole product, so the product spec is this component's spec:
[../product-spec.md](../product-spec.md). Requirements, issues and tests cite
its capability IDs (JUS-CAP-01 to 07) and the product-wide requirements in §5.
This file names the domain and points at those rules. It does not copy them.

## The domain

| Thing | What it is | Where its rules are |
| --- | --- | --- |
| Page | Home, Story, Work, a case study, Writing, an article, Work with me, Contact | [Product spec](../product-spec.md#3-capabilities), routes in the [design](design.md#information-architecture) |
| Work | A thing Justin has built that a reader can go and see. The preview has three: Construction OS, the change order generator, Fieldscope | [JUS-CAP-03](../product-spec.md#jus-cap-03-work), allowed facts in the [design](design.md#content-model) |
| Article | A published piece on AI in construction. A draft is not an article | [JUS-CAP-04](../product-spec.md#jus-cap-04-writing) and [JUS-CAP-07](../product-spec.md#jus-cap-07-publishing) |
| Claim | A statement about Justin or his work: a role, a credential, a metric, a status, a result | [Product spec §5](../product-spec.md#5-cross-cutting-requirements). Rendered from the facts register |
| Service | Consulting, speaking or advising on AI for construction. A Construction OS product offer is a link, not a service of this site | [JUS-CAP-05](../product-spec.md#jus-cap-05-work-with-me) |
| Preview | The build of branch `personal`, which Justin opens beside v2 | [Product spec §5](../product-spec.md#5-cross-cutting-requirements), [plan](plan.md) |

## Requirements

Behavior and acceptance criteria are the product spec's, one source. The site
delivers every capability:

| ID | Capability | Acceptance criteria |
| --- | --- | --- |
| [JUS-CAP-01](../product-spec.md#jus-cap-01-homepage) | Homepage | Product spec |
| [JUS-CAP-02](../product-spec.md#jus-cap-02-story) | Story | Product spec |
| [JUS-CAP-03](../product-spec.md#jus-cap-03-work) | Work | Product spec |
| [JUS-CAP-04](../product-spec.md#jus-cap-04-writing) | Writing | Product spec |
| [JUS-CAP-05](../product-spec.md#jus-cap-05-work-with-me) | Work with me | Product spec |
| [JUS-CAP-06](../product-spec.md#jus-cap-06-contact) | Contact | Product spec |
| [JUS-CAP-07](../product-spec.md#jus-cap-07-publishing) | Publishing | Product spec. After the preview, not part of the first milestone |

## Boundaries

- **In the domain:** pages about Justin's construction AI work, the register
  those claims render from, and the preview build.
- **Out of the domain:** the Construction OS product, its corpus and its
  workbench. This site links to them. Their rules stay in
  [construction-os/](../../construction-os/).
- **Out of the domain:** v2. Its capabilities stay JYC-CAP-01 to 10 in
  [justinyurasits-com/product-spec.md](../../justinyurasits-com/product-spec.md).
- **Out of the domain:** visual rules. They live in brand-system, BRAND-004.
- **Out of the domain:** the domain name, DNS and the live site on `main`.

## Known gaps

- Which `[OPEN]` slots he wants filled, and with which words. He decides,
  after he sees the preview. Listed in the product spec
  [§6](../product-spec.md#6-open-product-questions).
- The publishing routine (JUS-CAP-07) is specified and not part of the first
  preview.
