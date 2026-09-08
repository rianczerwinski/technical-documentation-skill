---
name: technical-documentation
description: Designs, writes, revises, and verifies technical documentation across repositories, products, wikis, APIs, architecture, operations, change communication, and source-local comments or annotations. Use when the user asks to document a system or feature; create or improve tutorials, how-to guides, reference, explanations, ADRs, runbooks, troubleshooting, knowledge-base articles, changelogs, migration guides, docstrings, or code comments; establish a documentation system; audit documentation quality or freshness; or decide what kind of documentation belongs where. Routes repository topology and purely navigational README/MANIFEST/AGENTS work to repo-refiner.
---

# Technical Documentation

Create documentation that lets a particular reader do, understand, operate, or change something correctly. Treat prose as an interface to an underlying source of truth, not as an independent story about the system.

## Boundary

This skill owns the semantic and operational quality of technical documentation from product wikis through source-local comments.

It does not own:

- Repository shape, canonical folder homes, root clutter, STRUCTURE.json, or the navigational README/MANIFEST/AGENTS chain. Route those concerns to `repo-refiner`.
- Product, policy, or architecture decisions that have not been made. Surface the decision rather than laundering a proposal into documentation. Once decided, this skill can record it.
- Factual authority for a specialized platform. Use the authoritative source or relevant domain skill, then document the verified result.
- Binary-document layout. Compose with the relevant document, PDF, spreadsheet, presentation, or site skill when the delivery format requires it.

A mixed artifact can invoke both sides of a boundary. A README may need `repo-refiner` for truthful navigation and this skill for its quickstart, explanation, or usage contract. Keep one reader-coherent artifact; do not split it merely to preserve skill boundaries.

## Core contract

Before writing, establish five things:

1. **Reader:** Who will use this, and what can they already be expected to know?
2. **Job:** What must the reader be able to do, decide, understand, verify, or recover afterward?
3. **Authority:** Which artifact or owner can prove each consequential claim?
4. **Mode:** Is the reader learning, completing a task, looking something up, understanding a system, operating it, tracking a change, or maintaining source code?
5. **Proof:** What independent observation would show that the documentation works and is current?

Do not start from a requested filename or template alone. Infer its reader and job, inspect local conventions, and report any material mismatch before authoring.

## Workflow

### 1. Inspect the local documentation system

Read the applicable repository or workspace instructions, the nearest README, existing sibling documents, source artifacts, generators, documentation configuration, and contribution rules. Prefer the project's established terminology, information architecture, style, and tooling unless those are the defect being repaired.

Treat existing documentation as evidence, not automatic authority. Code, schemas, runtime behavior, accepted decisions, tests, product policy, and domain owners may outrank it depending on the claim.

### 2. Frame the documentation unit

State the reader, job, scope, authority, update trigger, and proof in working notes. For a portfolio or wiki, do this at the collection level and for each materially different article class.

If one artifact is trying to serve incompatible jobs, separate the modes or create clear sections with independent entry points. Do not force every document into a single pure type when a coherent mixed artifact better serves the reader.

### 3. Route and load only the needed module

| Need | Load |
|---|---|
| Documentation portfolio, ownership, repo/wiki placement, canonical and derived surfaces | [Documentation system](references/documentation-system.md) |
| Tutorial, onboarding path, ordinary how-to, procedural guide | [Learning and task guides](references/learning-and-task-guides.md) |
| API, CLI, configuration, schema, command, or other lookup reference | [Reference and API](references/reference-and-api.md) |
| Conceptual explanation, system model, architecture view, design document, or ADR | [Explanation and decisions](references/explanation-and-decisions.md) |
| Runbook, playbook, incident procedure, recovery guide, or operational troubleshooting | [Operations](references/operations.md) |
| Product wiki, internal wiki, support knowledge base, or reusable solution article | [Knowledge bases](references/knowledge-bases.md) |
| Comment, docstring, doc comment, annotation, directive, TODO, or generated source reference | [Source documentation](references/source-documentation.md) |
| Changelog, release note, migration guide, compatibility note, or deprecation notice | [Change communication](references/change-communication.md) |
| Documentation review, freshness audit, accessibility, linting, link checking, example testing, or completion claim | [Quality and verification](references/quality-and-verification.md) |

Use [Worked routing](examples/worked-routing.md) when the artifact spans several modes. The research basis and limits of this architecture are in [Prior art](references/prior-art.md). Read [Antipatterns](antipatterns.md) before finalizing a new documentation system or a large cross-surface revision. Use [Trigger tests](examples/trigger-tests.md) when changing this skill's description or boundary.

### 4. Build an authority map

For each consequential claim, record the best available source and its relation to the document:

- **Normative:** an accepted policy, specification, schema, contract, or decision defines what must be true.
- **Descriptive:** inspected behavior, code, configuration, or telemetry shows what is true now.
- **Procedural:** a command or sequence has been executed successfully under named conditions.
- **Interpretive:** the document explains implications or rationale; distinguish sourced fact from synthesis.

When authorities conflict, do not silently choose the convenient one. Resolve the defect at the canonical source when authorized, or disclose the conflict and stop any affected completion claim.

### 5. Author at the durable source

Put change-coupled information as close as practical to the thing that changes. Generate repeated reference from machine-readable contracts when the generator preserves the needed semantics. Maintain one editable canonical source for duplicated content and mark other copies as generated or projected.

Write final-form documentation:

- Lead with the reader's task or conceptual anchor.
- Use exact names, states, prerequisites, and failure conditions.
- Keep examples realistic, minimal, and runnable.
- Separate success, empty, degraded, and failure states where the distinction affects action.
- Explain why only when the reason changes correct use, maintenance, or judgment.
- Prefer deletion or consolidation over preserving stale, redundant prose.
- Preserve accessibility in headings, link text, tables, diagrams, examples, and media alternatives.

### 6. Verify independently

Choose proof from the artifact's failure surface, not from a generic checklist. At minimum:

- Reconcile claims against their authority map.
- Walk the document as its intended reader from the stated starting condition.
- Run commands, snippets, generators, schema validators, documentation builds, link checks, or linting where they can establish relevant truth.
- Confirm navigation and search terms expose the artifact from the reader's likely entry point.
- Have an oracle independent of the authoring step assess consequential completion claims.

For any claimed automated guarantee, introduce one deliberately invalid fixture or mutation and confirm the check rejects it. A passing checker that has not demonstrated failure sensitivity is candidate evidence, not closure.

Automated style checks prove only what their rules encode. A clean build, valid link set, or style-lint pass does not prove conceptual completeness, safe procedure, or reader success.

### 7. Bind lifecycle

Name the owner or owning subsystem, update trigger, currentness signal, and retirement path. Update documentation in the same change as the behavior when possible. Archive or remove obsolete material once its durable value has been preserved and its discoverability no longer serves a current reader.

For a collection, use actual reuse, support demand, incidents, search behavior, change history, and reader feedback as review signals. Do not substitute arbitrary review dates for event-driven maintenance when the system exposes a better trigger.

## Completion report

Report:

- What reader job the resulting documentation now supports.
- Which canonical sources and conventions governed it.
- What was created, changed, consolidated, or retired.
- Which validations ran and what each one actually proves.
- Any unresolved conflict, unverified environment, inaccessible source, or lifecycle risk.

Do not call the work complete because prose exists. Completion means the intended reader can use it under the stated conditions and the important claims remain traceable to authority.
