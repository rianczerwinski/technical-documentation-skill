# Knowledge bases

Use this module for product wikis, internal wikis, support knowledge bases, reusable resolutions, institutional technical knowledge, and collaborative article collections.

## Knowledge is completed through reuse

A knowledge-base article is not finished when captured. It becomes trustworthy through retrieval, application, correction, consolidation, ownership, and retirement.

Design for a loop:

`demand -> search -> reuse or capture -> apply -> validate -> improve -> consolidate -> retire`

Capture in the workflow when the context is fresh, but do not publish raw notes as canonical guidance merely because they were captured quickly.

## Article contract

Each reusable article should expose:

- the question, symptom, task, or concept in reader language;
- scope, audience, product or system, and applicable versions;
- a concise answer or resolution near the top;
- evidence and authority for consequential claims;
- structured conditions, procedure, and verification where relevant;
- alternate vocabulary, error messages, and search phrases readers actually use;
- owner or owning domain;
- content state and confidence under the platform's governance;
- creation or validation event and update triggers; and
- supersession, merge, archive, or deletion relationships.

Use platform-native metadata when it supports these obligations. Do not reproduce metadata manually in prose if the platform can govern it.

## Article forms

### Known resolution

```md
# <Symptom or question in reader language>

## Applies to

Product, version, environment, permissions, and exclusions.

## Resolution

Shortest verified answer or procedure.

## Confirm the result

Observable success and meaningful failure states.

## Cause or explanation

Only the model needed to prevent recurrence or choose among variants.

## Search terms

Exact error strings, older names, abbreviations, and common reader phrasing.
```

### Concept or policy article

Lead with the question and consequence, state the authoritative rule or model, distinguish scope and exceptions, and link procedures rather than embedding several mutable copies.

### Draft capture

Preserve the request, environment, observed symptom, attempted actions, evidence, and provisional resolution. Label unverified claims and route the draft into validation; do not give it the same search prominence as verified guidance.

## Search and findability

- Title articles in the vocabulary of the person seeking them.
- Preserve exact error strings where safe.
- Add synonyms, previous product names, abbreviations, and domain terms.
- Link from common parent concepts and adjacent tasks.
- Prefer one strong article with multiple entry terms over several thin duplicates.
- Inspect zero-result searches, reformulated queries, pogoing between pages, and support escalations.

Search analytics reveal demand and friction, not correctness. A heavily visited article can be heavily wrong.

## Reuse as review

When an article is used:

1. Confirm that its applicability matches the case.
2. Apply the documented resolution without silently filling omitted steps.
3. Verify the outcome independently.
4. Correct missing context, ambiguity, stale facts, and weak search terms while the evidence is available.
5. Record or route novel residual knowledge rather than creating an immediate duplicate.

Readers should be able to signal "did not apply," "incomplete," "outdated," and "unsafe," not only generic approval.

## Duplication and consolidation

Compare candidate duplicates by durable constituents:

- reader question;
- applicability conditions;
- authoritative facts;
- procedure;
- exceptions;
- search vocabulary;
- rationale; and
- historical or compatibility value.

Merge when one article can serve the same job without obscuring materially different conditions. Keep separate articles when permissions, product versions, risk, or reader context produce genuinely different procedures.

Before retiring a duplicate, preserve unique search terms and inbound routes through aliases, redirects, or the surviving article's metadata. Do not leave two current-looking copies to avoid making the consolidation decision.

## State and authority

Use the platform's existing content states. If none exist, distinguish at least:

- **Provisional:** captured but not independently validated.
- **Current:** validated for named applicability.
- **Superseded:** replaced, with the current destination explicit.
- **Archived:** retained for bounded historical or compliance value and removed from ordinary current search.

State is not a decorative badge. It must affect search prominence, editing rights, review obligations, or reader interpretation.

## Product and internal boundaries

For public product knowledge:

- remove internal identifiers, security-sensitive detail, and unsupported commitments;
- make version and entitlement conditions visible;
- connect support resolution to product documentation when the issue is broadly reusable; and
- use customer language without erasing precise technical terms needed for diagnosis.

For internal knowledge:

- apply access controls based on the information, not the convenience of the workspace;
- distinguish authoritative policy from team habit;
- link code-coupled facts to repository authority; and
- preserve accountable ownership across team reorganizations.

## Verification and health

Sample articles using risk and demand, not only age. Verify:

- retrieval from realistic query terms;
- applicability and version scope;
- claims against authority;
- procedures from the stated environment;
- reuse outcomes and failure feedback;
- duplicate and contradiction clusters;
- ownership and escalation routes;
- state behavior in search and navigation; and
- archive and redirect behavior.

Challenge retrieval with a known synonym or exact error string absent from the title. Challenge lifecycle by marking a fixture as superseded and confirm it no longer outranks the current article. Challenge duplicate detection with two paraphrases of the same governed fact rather than identical text.
