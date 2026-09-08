# Trigger tests

Use these as behavioral discovery tests for the skill description and boundary. Positive cases should select this skill; composition cases should select it with the named sibling; negative cases should route elsewhere.

## Positive

| User phrase | Expected route |
|---|---|
| "Write the API documentation for these endpoints and make sure the examples work." | Reference and API, then Quality and verification |
| "Turn this onboarding knowledge into a tutorial for a new contributor." | Learning and task guides |
| "Create a safe production runbook for rebuilding the search index." | Operations |
| "Our internal wiki is duplicative and stale; redesign its knowledge lifecycle." | Documentation system and Knowledge bases |
| "Document why this service boundary exists and capture the accepted decision." | Explanation and decisions |
| "Fix the docstrings and comments around this public parser API." | Source documentation |
| "Write release notes and a migration guide for the breaking configuration change." | Change communication, Reference and API, then Quality and verification |
| "Audit whether our technical docs are complete, current, accessible, and actually usable." | Documentation system and Quality and verification, then affected artifact modules |

## Composition

| User phrase | Expected route |
|---|---|
| "The repo moved packages; update the README tree and make the quickstart accurate." | `repo-refiner` for tree navigation, this skill for the quickstart |
| "Produce a polished PDF operator handbook from these verified runbooks." | This skill for operational content; PDF skill for layout and rendering |
| "Document the current OpenAI Responses API behavior in our integration guide." | OpenAI factual authority skill first; this skill for the guide |
| "Add executable documentation tests for these command examples." | This skill for documentation proof obligations; test-focused skill for test apparatus when applicable |

## Negative and boundary

| User phrase | Expected route |
|---|---|
| "Clean up the repository root and repair the README/MANIFEST navigation chain." | `repo-refiner`, not this skill |
| "Should we use events or polling? Make the architecture choice for me." | Decision framing or relevant engineering method; this skill only after or alongside an authorized decision record |
| "Answer this API question in chat; don't change any files." | Conversational answer using authoritative sources; do not create documentation merely because the topic is technical |
| "Format this already-final text as a Word document." | Document-format skill; this skill is unnecessary unless semantic technical-documentation work is requested |
| "Write marketing copy for the product launch." | Marketing or identity method, not technical documentation |

## Failure expectations

The description is defective if it:

- misses source-local comments, wikis, operations, change communication, or documentation audits;
- claims every README regardless of whether the concern is topology or semantic content;
- activates for generic technical conversation with no documentation job;
- implies authority to make unresolved product or architecture decisions; or
- forces every request to load the full reference set.
