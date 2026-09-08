# Quality and verification

Use this module for documentation review, audits, freshness work, accessibility, linting, link checking, example testing, and completion claims.

## Two layers of quality

Technical documentation needs both:

- **Functional quality:** accurate, complete for its declared job, consistent, precise, findable, and usable.
- **Experiential quality:** legible flow, proportionate detail, humane cognitive load, accessible presentation, and fit with the reader's actual context.

Maximizing correctness while making the path hostile is a quality failure. Making prose effortless while hiding constraints or failure states is also a quality failure.

## Build a claim-evidence matrix

Before declaring completion, list the claims that matter and the independent evidence that can establish them.

| Claim class | Candidate authority | Independent verification |
|---|---|---|
| Command works | Actual executable and environment | Run from stated starting state and observe result |
| API coverage | Interface definition or exported symbols | Enumerate and diff documented entities |
| Configuration semantics | Schema, parser, runtime behavior | Validate examples and observe precedence or reload behavior |
| Architecture relationship | Code, deployment, accepted decision | Trace representative runtime and failure paths |
| Runbook safety | Operational controls and representative environment | Exercise precheck, abort, success, interruption, and rollback in a safe fixture |
| Knowledge article resolution | Reproduced symptom and authoritative remedy | Reuse on a matching case and verify outcome |
| Comment consistency | Exact symbol, invariant, or annotation semantics | Review changed path and run extractor, compiler, or analyzer |
| Migration completeness | Version diff and compatibility contract | Migrate representative old state, detect residue, and verify new behavior |
| Findability | Navigation, search index, reader vocabulary | Start from realistic entry points and queries |
| Accessibility | Content and rendered surface | Automated checks plus keyboard, structure, text alternative, contrast, and assistive review appropriate to the medium |

The authoring component must not be the sole validator of its own completion claim. Use a distinct tool, generated inventory, runtime observation, reviewer, or authoritative source.

## Verification sequence

1. **Scope:** Restate reader, job, environment, versions, exclusions, and risk.
2. **Authority:** Reconcile consequential claims with the authority map.
3. **Structure:** Confirm the information mode and entry path fit the reader's need.
4. **Mechanics:** Run applicable build, schema, extraction, lint, link, and example checks.
5. **Task walk-through:** Use the artifact from its declared starting state without silently supplying missing knowledge.
6. **Adversarial pass:** Introduce known false, missing, stale, or unsafe cases and confirm the checks detect them.
7. **Lifecycle:** Verify owner, update trigger, canonical relationships, and retirement handling.
8. **Residuals:** State what remains unproven and why.

Remediate findings and repeat the affected checks. Do not publish a closure status before the adversarial pass succeeds.

## Automated checks and their proof limits

### Documentation build

Can prove parseability, supported syntax, internal integration, and sometimes cross-reference validity. It cannot prove factual truth, task success, safety, or conceptual completeness.

### Link checker

Can prove that a target responds under check conditions. It cannot prove that the target still supports the linked claim, that anchors are semantically correct, or that authenticated and regional readers can reach it.

### Style and terminology lint

Can prove conformance to encoded rules such as vocabulary, capitalization, sentence patterns, or prohibited phrasing. It cannot prove clarity for this reader or correctness of meaning. Tools such as Vale are useful when the project owns a reviewed rule set.

### Spelling and grammar

Can catch surface errors. Technical identifiers, examples, domain terms, and intentional fragments require scoped configuration. A clean pass does not establish precision.

### Snippet, doctest, or procedure execution

Can prove that encoded examples execute in a named environment. It may not cover omitted prerequisites, production permissions, platform variants, nondeterminism, scale, external dependencies, or reader interpretation.

### Schema and contract validation

Can prove structural conformance to the chosen contract. It cannot prove that the contract captures all semantic rules or that the implementation honors it.

### Accessibility automation

Can detect some structural and contrast defects. It cannot replace keyboard use, assistive-technology checks, meaningful alternative text, comprehension, or cognitive accessibility review.

## Adversarial mutations

Every claimed automated guarantee needs at least one known-bad case. Select a mutation from the real failure surface:

- break a link or anchor;
- omit a public API entity;
- change a default or unit in a fixture;
- corrupt a code sample;
- add a malformed doc-comment tag;
- leave a deprecated identifier in a migration fixture;
- remove a runbook precondition;
- hide a current article behind a superseded duplicate; or
- remove a diagram's text equivalent.

Run the check and confirm it fails for the intended reason. Restore the valid fixture and confirm it passes. Keep the mutation as a regression test when its prevention is durable and proportionate.

Do not perform destructive, unsafe, or public mutations against live systems to prove documentation.

## Freshness

Freshness is a relationship between a claim and its authority, not a timestamp alone.

Inspect:

- code and schema changes without corresponding docs;
- documentation changes without source changes where a generated source should govern;
- examples pinned to unavailable versions;
- screenshots and UI paths after interface changes;
- owner changes and orphaned collections;
- recurring support or incident evidence contradicting the documented path;
- deprecated names still ranking in search; and
- duplicated claims with divergent edits.

Prefer event-coupled checks. Use review dates where the source does not emit a meaningful event, and record what authority the review must inspect.

## Accessibility and presentation

- Use a logical heading hierarchy and descriptive titles.
- Make link text meaningful outside its sentence.
- Give tables clear headers and avoid using layout tables for prose.
- Provide text equivalents for diagrams, screenshots, audio, and video that carry technical meaning.
- Do not encode status or distinction by color alone.
- Keep commands and identifiers distinguishable without relying only on typography.
- Explain abbreviations and domain terms at the level the reader needs.
- Ensure keyboard access and focus order when documentation includes interactive controls.
- Test narrow screens, zoom, contrast, and copy behavior when the rendered surface matters.

## Review by risk

Weight review depth by consequence and drift rate:

- High: destructive operations, security, money, privacy, data recovery, authentication, permissions, and breaking migration.
- Medium: common setup, public API semantics, configuration, deployment, and support resolution.
- Lower but nonzero: orientation, conceptual explanation, and low-impact examples.

Risk weighting changes evidence depth, not the obligation to be truthful.

## Review result

Report findings as:

```md
### <Finding>

**Failure mode:** What a reader would do, misunderstand, or fail to detect.

**Consequence:** The downstream technical or experiential effect.

**Scope:** Affected readers, versions, environments, and related artifacts.

**Evidence:** Authority and observation.

**Repair:** Canonical source and dependent projections to change.

**Regression proof:** Check that must reject recurrence.

**Residual uncertainty:** What remains unproven.
```

Avoid score-only audits. A weighted number hides whether one severe defect invalidates an otherwise polished collection.
