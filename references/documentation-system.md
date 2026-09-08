# Documentation system

Use this module when the task concerns a documentation portfolio, docs strategy, repository-versus-wiki placement, ownership, canonical sources, or cross-surface lifecycle.

## Model the system before adding artifacts

Inventory documentation by reader job, not merely by filename or platform. A useful census records:

| Field | Question |
|---|---|
| Reader | Who reaches this surface, with what prior knowledge and access? |
| Job | What are they trying to do, decide, understand, verify, or recover? |
| Entry point | Where do they naturally look or search first? |
| Authority | What source can prove the consequential claims? |
| Surface | Repository file, generated site, product help, internal wiki, ticketing knowledge base, or source code? |
| Owner | Which role or subsystem notices when it becomes wrong? |
| Trigger | What code, schema, product, policy, incident, or support event should cause review? |
| Proof | How can a reviewer establish that this unit still works? |
| State | Current, provisional, superseded, archived, or another locally governed state? |

Do not mistake an inventory of files for an inventory of obligations. Several files can duplicate one obligation, and one file can hide several incompatible reader jobs.

## Establish the authority graph

Documentation should project from the closest durable source that can legitimately govern the claim.

Common authority relationships include:

- API shapes from interface definitions or schemas.
- CLI flags from command metadata.
- Configuration keys from validated configuration schemas.
- Runtime procedure from exercised behavior in a named environment.
- Architecture rationale from accepted decisions and implementation evidence.
- Product policy from the accountable product or policy owner.
- Support resolution from a reproduced symptom and verified remedy.
- Public interface behavior from code and compatibility commitments.

When several surfaces repeat a claim, mark one relationship explicitly:

- **Canonical:** the editable source of the claim.
- **Generated:** reproducibly emitted from a canonical source.
- **Projected:** selected or reformatted from a canonical source for another audience.
- **Supplemental:** adds reader-specific context without restating the governed fact.
- **Historical:** retained to explain a past state and clearly bounded to that state.

Avoid two editable canonical sources for the same claim. If a platform cannot transclude or generate, prefer a concise pointer plus audience-specific context over a pasted duplicate.

## Choose the surface by change coupling and reader access

### Repository documentation

Prefer repository-local documentation when the content:

- must change in the same review as code, schemas, configuration, or deployment machinery;
- benefits from versioning with a release or branch;
- contains executable examples or source-linked reference;
- is primarily consumed by contributors and maintainers; or
- can be checked by the repository's build and test workflow.

Repository placement does not automatically make documentation discoverable to product users or operators outside the codebase.

### Product documentation or generated documentation site

Prefer a product-facing documentation surface when the content:

- serves customers across several releases or repositories;
- needs search, navigation, localization, analytics, or public version switching;
- forms part of the product experience; or
- must be accessible without repository access.

Keep version-coupled facts derived from or linked to their technical authority rather than rewriting them manually in the publishing layer.

### Wiki or knowledge platform

Prefer a wiki or knowledge platform when the content:

- spans several systems or teams;
- evolves through collaborative operational or institutional use;
- needs permissions, discussion, or workflow states not available in the repository; or
- is primarily retrieved through workplace search or support tooling.

Wiki placement is not permission to detach the article from owners, evidence, or change triggers. Load [Knowledge bases](knowledge-bases.md) for the article contract.

## Respect repository navigation as a separate concern

Use `repo-refiner` for the physical tree and its navigational projection:

- canonical folder homes;
- root cleanliness and development quarantine;
- STRUCTURE.json;
- README and MANIFEST index chains;
- AGENTS navigation and scope boundaries.

Use this skill for semantic content inside those surfaces:

- orientation and conceptual models;
- installation and task paths;
- API or configuration meaning;
- operational procedures;
- contribution rationale and behavioral contracts.

For a mixed README, first let `repo-refiner` establish what the file must point to and how it participates in the tree. Then apply the routed technical-documentation modules to the sections that teach, instruct, explain, or specify.

## Design the portfolio

A complete portfolio is not one document of every type. It is the smallest set that covers real reader jobs without orphaned obligations or unmanaged duplication.

Use demand signals:

- onboarding failures;
- repeated support questions;
- incidents and near misses;
- search queries that land on poor results or no result;
- API or schema changes;
- recurring review comments;
- misunderstood architecture boundaries;
- common copy-paste errors;
- migration and deprecation events; and
- source comments carrying knowledge that belongs at a wider interface.

Classify every proposed addition as one of:

- a missing reader job;
- a replacement for a defective artifact;
- a projection from an existing canonical source;
- reader-specific supplementation; or
- unjustified proliferation.

## Minimal collection contract

For a durable documentation collection, define:

```yaml
readers:
  - identity and assumed context
jobs:
  - observable outcome
canonical_sources:
  - claim class: authority
surfaces:
  - surface: audience and role
owners:
  - area: accountable role or subsystem
update_triggers:
  - event: affected documentation class
verification:
  - documentation class: independent oracle
retirement:
  - supersession and archive or deletion rule
```

Use the project's existing metadata system when one exists. The fields above are obligations, not a demand to introduce YAML.

## Lifecycle

Prefer event-driven lifecycle hooks:

- Interface changes trigger reference and examples.
- User-flow changes trigger tutorials and how-to guides.
- Operational changes trigger runbooks and troubleshooting.
- Accepted decisions trigger ADRs and architecture explanation.
- Releases trigger changelog, release notes, and migration communication.
- Recurring support resolutions trigger knowledge capture or consolidation.
- Code changes trigger nearby doc comments and generated reference.

Calendar review is appropriate when drift has no reliable event source, but it should identify the authority to recheck rather than merely renew a date.

Retire material when its reader job no longer exists, its authoritative content has moved, or its historical value is better represented elsewhere. Preserve unique rationale, compatibility history, and search vocabulary before removal. Use redirects or replacement pointers only where readers may still arrive through an external or durable link.

## System-level verification

Verify the portfolio with independent evidence:

- Sample real reader jobs and trace each from its likely entry point to a usable answer.
- Select consequential claims and follow them back to authority.
- Search for duplicated distinctive phrases, commands, option tables, and policy language.
- Compare recent code, schema, product, and incident changes with documentation updates.
- Inspect dead ends, orphaned pages, broken incoming links, and unowned collections.
- Confirm retired material does not remain more discoverable than its replacement.

A coverage table proves only enumerated obligations. Challenge it with a deliberately missing known reader job or stale duplicated claim and confirm the audit detects the defect.
