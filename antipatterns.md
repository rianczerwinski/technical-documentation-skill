# Antipatterns

Read these as failure tests, not as a substitute for the routed module.

## Filename-first documentation

❌ "The user asked for a README, so fill the standard README headings."

✅ Identify the README's actual readers and jobs, then combine only the navigation, orientation, installation, use, contribution, or reference sections they need.

**Why:** A filename is a container convention, not an information architecture. Template completion can produce a polished document that serves no real entry condition.

## One document type for every need

❌ Put conceptual teaching, urgent procedure, exhaustive lookup data, and decision history into one undifferentiated guide.

✅ Give distinct reader modes clear entry points, even when they coexist in one artifact.

**Why:** Learning, doing, looking up, and understanding impose different ordering and density. Blending them without signposting makes every mode harder to use.

## Existing prose as ground truth

❌ Copy old documentation forward because it is already documented.

✅ Trace consequential claims to code, schemas, runtime behavior, accepted decisions, policy, or accountable owners.

**Why:** Documentation is commonly the stale layer. Treating it as its own authority compounds drift and gives errors a cleaner presentation.

## Prose duplication without a source relationship

❌ Maintain the same commands, options, or policy independently in a README, wiki, generated site, and code comments.

✅ Choose one editable canonical source and derive, transclude, or point to it from the other surfaces.

**Why:** Unsynchronized copies turn every change into a hidden multi-write obligation and make readers arbitrate contradictions.

## Generation as a completeness claim

❌ Generate an API page from a schema and assume the API is documented.

✅ Generate structural facts, then add the semantics, constraints, examples, errors, workflows, and stability information the contract does not encode.

**Why:** Generators are excellent at fidelity to fields and signatures but cannot recover missing intent or user context.

## A successful build as reader proof

❌ "The docs build and all links resolve, so the documentation is correct."

✅ State that the build proves syntax and integration, then separately verify claims, procedures, findability, and reader outcomes.

**Why:** Tool success covers its encoded checks only. It cannot prove that the document answers the right question or that a safe-looking command is safe.

## Untested examples

❌ Publish plausible commands or snippets that were never executed in the named environment.

✅ Execute them from the stated prerequisites, or mark the exact unverified boundary and why it could not be tested.

**Why:** Examples are executable claims. Small omissions in environment, quoting, permissions, or ordering can invalidate the path readers are most likely to copy.

## Commenting the visible syntax

❌ `count += 1 // Increment count by one.`

✅ Comment the invariant, domain reason, surprising constraint, compatibility obligation, or failure mode that the code cannot express clearly.

**Why:** Restatement creates noise and drifts when code changes. Valuable comments preserve information that would otherwise be lost.

## Policy by comment

❌ Rely on a comment to prevent an invalid state that types, schemas, validators, or tests can reject deterministically.

✅ Encode the enforceable rule in machinery and use the comment to explain its domain reason or maintenance consequence.

**Why:** Readers can miss prose and code can violate it. Documentation should expose a control, not impersonate one.

## Proposal disguised as decision history

❌ Write an ADR in the accepted voice before the decision owner has chosen the architecture.

✅ Keep proposals in a design document with open questions; create or finalize the ADR only after the decision is made.

**Why:** Decision records are authoritative memory. Premature certainty corrupts later reasoning and makes an unresolved preference look governed.

## Happy-path operations

❌ Give production commands without preconditions, expected output, abort conditions, rollback, or escalation.

✅ Write the procedure around observable state transitions and include the unsafe branches an operator must distinguish.

**Why:** Operational documentation is used under pressure. Ambiguous state and irreversible steps create a larger failure than missing prose.

## Changelog as commit dump

❌ Paste commit subjects into a release log.

✅ Curate user-visible changes by consequence, compatibility, action required, and affected versions.

**Why:** Git history describes implementation activity. Change communication tells a reader what is different for them.

## Wiki accumulation without lifecycle

❌ Preserve every article indefinitely and add a newer near-duplicate when the old one is wrong.

✅ Consolidate reusable knowledge, mark ownership and state, redirect useful entry terms, and archive or retire obsolete copies.

**Why:** Search makes stale material look current. A knowledge base without gardening converts recall into misinformation.

## Universal house style over local convention

❌ Replace a project's established doc-comment format, terminology, or documentation toolchain with a preferred generic system.

✅ Follow the nearest authoritative conventions unless the task is to change them, and explain any migration boundary.

**Why:** Documentation participates in local tooling, review, and reader expectations. Unnecessary divergence increases maintenance cost and can break extraction.

## Freshness dates as maintenance theater

❌ Add a recurring review date to every document regardless of how its subject changes.

✅ Bind review to code, schema, product, incident, ownership, or reuse events, adding calendar review only where no stronger trigger exists.

**Why:** A date can be renewed without checking the right source. Event-coupled maintenance follows the actual drift mechanism.

## Deletion without value accounting

❌ Remove an old document because it is stale without checking whether it contains unique rationale, migration history, or search vocabulary.

✅ Preserve unique durable value in the canonical surface, verify replacement paths, then retire the redundant source.

**Why:** Staleness and redundancy are not the same. Cleanup is safe only after the information loss question is answered.
