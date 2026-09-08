# Explanation and decisions

Use this module for conceptual documentation, system models, architecture views, design documents, and architecture decision records.

## Separate four authorities

These artifacts are related but not interchangeable:

- **Explanation** builds a reader's mental model of why a system behaves as it does.
- **Architecture description** identifies significant elements, boundaries, relationships, constraints, and runtime or deployment views.
- **Design document** evaluates a proposed change, including unresolved alternatives and validation strategy.
- **Decision record** preserves a decision that has actually been made, its context, rationale, tradeoffs, and consequences.

Do not turn current implementation into intended architecture without evidence. Do not turn a proposal into an accepted decision by writing it in authoritative prose.

## Explanation contract

Define:

- the question or confusion the explanation resolves;
- the reader's existing model and the correction or extension they need;
- the system evidence and accepted decisions that constrain the explanation;
- the principal causal mechanism;
- important boundaries, tradeoffs, and counterexamples; and
- links to task or reference material for action and lookup.

### Explanation shape

```md
# Why <system behavior or design> works this way

<Question and practical consequence.>

## The model

Name the participating concepts and the relationship that produces the behavior.

## What happens

Trace the causal sequence or state transition at the level the reader needs.

## Why this design exists

Constraints, accepted decisions, and tradeoffs with sources.

## Boundaries and exceptions

Conditions where the model changes, fails, or does not apply.

## Consequences

What the reader should now predict, diagnose, or decide differently.
```

Prefer one load-bearing model over a tour of components. Introduce terminology through the mechanism it names. Include technical internals when they change the reader's prediction or action.

## Architecture views

Choose views by reader question. The C4 vocabulary is useful where it fits:

- **System context:** people and external systems; use for scope and responsibility.
- **Container:** applications, services, data stores, and major runtime boundaries; use for deployment and major communication.
- **Component:** significant responsibilities within a container; use when maintainers need internal boundaries.
- **Code:** implementation structure; use only when a generated or focused code view materially helps.

Other necessary views may include:

- runtime sequence and state transitions;
- data ownership, lineage, and retention;
- deployment, trust, and failure boundaries;
- control plane versus data plane;
- tenancy, permissions, and identity flow;
- build and release flow; and
- degraded operation and recovery.

Do not draw every possible view. State the audience and question for each one.

### Diagram contract

Every consequential diagram should provide:

- a title that states the question or view;
- a legend or locally obvious notation;
- named boundaries and relationship direction;
- stable element names consistent with prose and code;
- version or revision context when the architecture changes over time;
- accompanying text that conveys the meaning without relying on color or image access; and
- a canonical editable source, not only an exported bitmap.

A diagram is not correct because it renders. Reconcile its nodes and relations against implementation, deployment, accepted decisions, and domain owners.

## Design documents

A design document is a decision surface while material choices remain open.

Include:

- problem and observable consequence;
- scope and non-goals;
- current system and evidence;
- constraints and invariants;
- candidate designs with real tradeoffs;
- preferred direction, clearly labeled as proposal when not decided;
- failure modes and operational consequences;
- data, security, privacy, accessibility, and compatibility effects where relevant;
- migration and rollback;
- independent validation and deliberately false cases; and
- open questions and decision owners.

Do not use consensus language unless a named authority or recorded process actually established it.

## Architecture decision records

An ADR records one architecturally significant decision. Use the repository's existing format and numbering. A minimal record includes:

```md
# <Decision title>

## Status

Accepted, superseded, or the repository's governed state.

## Context

The forces, constraints, evidence, and decision that had to be made.

## Decision

The chosen rule or architecture in unambiguous present tense.

## Alternatives considered

The tightest real competitors and why they were not chosen under these constraints.

## Consequences

Benefits, costs, risks, follow-up obligations, and observable effects.

## Validation

How implementation and later conformance can be checked independently.
```

Record supersession through the repository's established relationship rather than rewriting history. Update current architecture explanations when a decision changes the system, but preserve the decision log as the history of authority.

## Rationale discipline

Distinguish:

- facts observed in the system;
- constraints imposed by policy or environment;
- preferences chosen by an owner;
- hypotheses awaiting evidence; and
- interpretations synthesized by the author.

The rationale should explain why the decision followed under its actual constraints. Avoid retrospective stories that attribute motives not present in the decision evidence.

## Verification

- Trace architecture elements and boundaries to code, configuration, deployment, schemas, or accountable owners.
- Walk one representative runtime path and one failure path through the documented model.
- Compare accepted ADRs with current implementation and current explanatory docs.
- Confirm design-document open questions have not been written as settled facts.
- Review each diagram without color and with its text alternative.
- Ask a target reader to predict one non-obvious behavior from the explanation, then compare with actual behavior.

Challenge an architecture conformance check by introducing a forbidden dependency or missing required edge in a fixture. Confirm the check detects it before treating conformance as mechanically proven.
