# Worked routing

These examples show how to compose modules around one reader job without turning the router into a rigid taxonomy.

## Repository README after a restructure

**Request:** "Update the README now that packages moved, and make setup clearer."

**Route:** Use `repo-refiner` for the repository tree, canonical homes, and README navigation chain. Use Learning and task guides for setup. Use Explanation and decisions only if the README needs a concise system model.

**Authority:** Actual materialized tree and structure contract for navigation; package manager, build configuration, and exercised commands for setup; accepted architecture and implementation for the system model.

**Proof:** Navigate every linked path; run setup from the declared starting state; introduce a stale path in a fixture and confirm the structural check rejects it.

**Resulting shape:** One reader-coherent README. The skill seam does not require separate files.

## HTTP endpoint change

**Request:** "Document the new batch endpoint, including upgrade impact."

**Route:** Reference and API for endpoint contract; Learning and task guides for the batch workflow if callers need a procedure; Change communication for release, compatibility, and migration effects.

**Authority:** OpenAPI or interface schema, handler behavior, authentication and quota policy, compatibility decision, and released version metadata.

**Proof:** Validate the contract, execute representative request and error cases, diff public interface coverage, migrate a caller fixture, and confirm an omitted required field is rejected.

**Avoid:** Copying the same field table independently into API reference, release notes, and migration guide. Generate or link the governed facts, then add audience-specific consequence.

## Production recovery procedure

**Request:** "Write a runbook for recovering the index after a worker crash."

**Route:** Operations. Add Explanation and decisions only if operators need a causal model to discriminate corruption from delayed processing. Add Change communication if the recovery mechanism changes an existing operator contract.

**Authority:** Worker checkpoint semantics, persisted job state, actual health and integrity probes, storage guarantees, escalation ownership, and tested recovery behavior.

**Proof:** In a disposable representative environment, interrupt a bounded unit, observe the documented failed state, resume from the durable checkpoint, verify no completed unit repeats, test the abort condition, and exercise rollback or reconciliation.

**Avoid:** Treating service responsiveness as proof of index completeness.

## Product-support wiki article

**Request:** "Turn this recurring authentication ticket into a reusable knowledge article."

**Route:** Knowledge bases for capture, search terms, reuse, ownership, and lifecycle. Use Learning and task guides for a bounded customer procedure. Use Reference and API for authoritative error meanings when relevant.

**Authority:** Reproduced symptom, authentication contract, product entitlement policy, observed remedy, and support owner.

**Proof:** Retrieve the article using the customer's phrasing and exact safe error text, apply it to a matching case, distinguish invalid credentials from missing entitlement, and confirm a superseded article cannot outrank it.

**Avoid:** Publishing ticket chronology or customer-specific data as the reusable article.

## Misleading source comment

**Request:** "Fix comments around this retry loop."

**Route:** Source documentation. Use Explanation and decisions only if the retry policy belongs to a system-wide resilience model. Use Operations if operators rely on the timing during incidents.

**Authority:** Actual retry implementation, timeout and backoff tests, upstream idempotency contract, and accepted reliability constraints.

**Proof:** Trace success, retryable, terminal, cancellation, and exhaustion paths; run relevant tests; confirm the comment states why retry is safe and does not restate the loop; mutate an error classification fixture and confirm tests reject the mismatch.

**Avoid:** Leaving a comment as the only enforcement of retry-safe operations when a type, policy table, or test can encode the boundary.

## Architecture proposal becoming a decision

**Request:** "Document why we are moving from polling to events."

**Route:** First determine authority. If the move is still open, use a design document under Explanation and decisions. If accepted, record the ADR and update the current architecture explanation. Use Change communication for integrator-visible migration.

**Authority:** Current behavior and load evidence, accepted decision owner or record, event-delivery guarantees, implementation, and compatibility plan.

**Proof:** Ensure alternatives remain visible in the design phase; after acceptance, trace the selected event path and a failure path through implementation; verify the ADR status; migrate a polling consumer fixture; detect one leftover polling dependency.

**Avoid:** Writing an accepted-sounding ADR to force an unresolved choice.

## Documentation quality audit

**Request:** "Tell me whether the docs are complete and current."

**Route:** Documentation system for the reader-job census and authority graph; Quality and verification for evidence and adversarial checks; then load only the artifact modules implicated by findings.

**Authority:** Actual repository and product surfaces, public interfaces, runtime behavior, change history, support and incident signals, search behavior, and named owners.

**Proof:** Sample every high-consequence reader job, diff governed entities, execute risk-weighted procedures and examples, detect duplicate claims, trace recent changes, and introduce known stale or missing fixtures to prove the audit checks are failure-sensitive.

**Avoid:** Counting pages or reporting a weighted score as completeness.
