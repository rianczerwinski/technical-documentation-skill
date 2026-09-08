# Reference and API documentation

Use this module for APIs, CLIs, configuration, schemas, protocols, commands, data formats, public interfaces, and other lookup-oriented documentation.

## Reference contract

Reference documentation describes the machinery accurately and systematically. A reader should be able to locate an entity, determine its contract, distinguish valid from invalid use, and predict relevant outcomes without reading a narrative end to end.

For every documented entity, establish:

- canonical name and stable identifier;
- purpose in one precise sentence;
- availability by version, environment, feature state, or permission;
- inputs, types, units, ranges, defaults, and required relationships;
- outputs, side effects, ordering, idempotency, and durability where relevant;
- error or failure conditions and how they are surfaced;
- compatibility, stability, and deprecation state;
- at least one representative valid example; and
- cross-links to task guidance and explanation without embedding those modes wholesale.

Not every entity needs every field. Omit inapplicable fields deliberately; do not omit consequential unknowns silently.

## Derive structure from contracts

Prefer machine-readable authorities for structural facts:

- OpenAPI or equivalent interface descriptions for HTTP APIs;
- language signatures and doc-comment extraction for libraries;
- parser or command metadata for CLIs;
- schema definitions for configuration and data formats;
- protocol definitions for messages and state transitions; and
- type systems or validation rules for public objects.

Generated reference is a projection, not a separate authority. Make generation reproducible, identify the source revision, and prevent manual edits to generated output from becoming the only copy.

Contracts rarely encode the whole documentation obligation. Add human-authored semantics for:

- why and when to use the entity;
- cross-field constraints;
- permission and security consequences;
- rate, quota, timing, and consistency behavior;
- retry and idempotency expectations;
- lifecycle and compatibility policy;
- meaningful errors and recovery;
- realistic examples; and
- distinctions between similar entities.

## HTTP API entry

```md
## <Operation name>

`<METHOD> <path>`

<Purpose and appropriate use.>

### Availability

Authentication, authorization, version, feature state, quota, and relevant environment.

### Request

Path, query, header, and body fields with type, requiredness, default, constraints, and interaction rules.

### Response

Status, schema, side effects, consistency, pagination or streaming behavior, and stable identifiers.

### Errors

| Condition | Signal | Meaning | Caller action |
|---|---|---|---|

### Example

Minimal realistic request and response with secrets and unstable values removed.

### Compatibility

Introduction, change, deprecation, and replacement information.
```

Do not document only the `200` path. Distinguish authentication failure, authorization failure, invalid input, missing state, conflict, rate limitation, dependency failure, and server failure when callers must respond differently.

## CLI entry

Document:

- exact invocation and subcommand hierarchy;
- arguments and options, including precedence and repeatability;
- defaults and environment-variable or configuration interactions;
- stdin, stdout, stderr, exit status, and machine-readable modes;
- filesystem, network, credential, or durable-state effects;
- examples for common use and a consequential edge case; and
- version and platform differences.

Generate syntax and option tables from command definitions when possible. Verify prose examples against the actual executable, not just the parser schema.

## Configuration entry

Document:

- key path and scope;
- value type, unit, range, allowed values, and default;
- whether absence differs from an explicit null, empty, false, or zero;
- precedence among file, environment, flag, remote policy, and runtime override;
- dynamic reload versus restart requirements;
- security or privacy implications;
- interaction with other keys;
- version availability and migration; and
- one valid and one invalid or dangerous example where useful.

Never publish credential-like sample values that resemble usable secrets. Mark placeholders and storage requirements clearly.

## Data and schema entry

For a field or object, specify semantic meaning in addition to shape. Include units, timezone, encoding, normalization, identity, cardinality, ordering, uniqueness, optionality, nullability, unknown-field behavior, forward compatibility, and validation boundaries where relevant.

Use examples to expose interaction rules, not to replace the schema.

## Organization and retrieval

- Mirror the stable domain taxonomy or public interface, not the incidental source-file layout, unless source navigation is the reader's job.
- Give entities predictable headings and anchors.
- Include aliases and older names when readers genuinely search for them.
- Put comparisons close to commonly confused entities.
- Keep exhaustive lookup material out of task sequences; link to it at the decision point.

## Verification

Use independent structural and behavioral evidence:

- Validate the machine-readable contract with its official validator.
- Compare generated output with a clean regeneration from the canonical source.
- Execute examples against the declared version and environment.
- Enumerate public entities from the implementation or schema and diff them against documented coverage.
- Confirm defaults, constraints, errors, exit statuses, and side effects with tests or direct observation.
- Check anchors, cross-links, search labels, and version selection.

Challenge coverage by adding or selecting one known public entity absent from the documentation fixture and confirm the comparison fails. Challenge example validation with one invalid field, flag, or response and confirm the checker rejects it.

A complete entity count does not prove semantic completeness. Review a risk-weighted sample for constraints the source contract cannot express.
