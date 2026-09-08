# Change communication

Use this module for changelogs, release notes, migration guides, compatibility notes, upgrade instructions, and deprecation or removal notices.

## Choose the artifact by reader consequence

- **Changelog:** durable chronological index of notable changes across versions.
- **Release notes:** curated narrative for a particular release and audience.
- **Migration guide:** ordered work required to preserve or restore behavior across a change.
- **Compatibility note:** precise statement of supported versions, environments, protocols, or combinations.
- **Deprecation notice:** lifecycle contract from discouraged use through replacement and possible removal.

One release can require several. Do not make a changelog entry carry a complex migration, or make a migration guide serve as the only durable record that a change occurred.

## Authority map

Derive change communication from:

- actual diff and released artifact;
- version and release metadata;
- accepted compatibility policy;
- public interface and schema changes;
- migration implementation and tests;
- security advisories and disclosure authority;
- product behavior and entitlement changes; and
- decision records where rationale matters.

Issue titles and commit messages are discovery inputs, not final user-facing authority. Verify the shipped consequence.

## Changelog

Curate changes that matter to users, operators, integrators, or contributors. Organize with the project's established categories; common human-readable classes include Added, Changed, Deprecated, Removed, Fixed, and Security.

Each entry should answer:

- What observable behavior or interface changed?
- Who is affected?
- In which version or date boundary?
- Is action required?
- Where are migration, security, or deeper technical details?

```md
## <Version or release> — <date>

### Changed

- <Reader-visible consequence>. <Required action or link when applicable>.
```

Do not paste the commit log. Several commits may implement one reader-visible change, and one small commit may create a major compatibility consequence.

## Release notes

Order release notes by reader importance, not implementation chronology.

Include:

- concise release significance;
- important new capability and who can use it;
- behavior changes and compatibility effects;
- fixes whose symptoms readers recognize;
- known limitations and rollout conditions;
- required action, migration, or rollback route; and
- links to reference, guides, changelog, and advisories.

Avoid promotional claims the shipped behavior cannot substantiate. Avoid burying breaking changes below feature narrative.

## Migration guide

Define the exact from-state and to-state. A robust guide includes:

```md
# Migrate from <old state> to <new state>

## Who must migrate

Affected versions, configurations, interfaces, and exclusions.

## Before migrating

Compatibility matrix, backups, capacity, access, deprecation deadline, and preflight checks.

## Changes you must make

Old behavior -> new behavior -> concrete action, grouped by dependency order.

## Perform the migration

Bounded steps with expected observations and stop conditions.

## Verify

Independent behavior, data, compatibility, and performance checks.

## Roll back or coexist

Supported reversal, dual-read or dual-write period, irreversible boundary, and retained effects.

## Remove compatibility scaffolding

Exit conditions and cleanup after the migration is proven.
```

Use before-and-after examples when they expose the semantic difference. Do not rely on search-and-replace instructions for changes whose meaning depends on context.

## Deprecation lifecycle

A deprecation notice should state:

- the deprecated interface or behavior;
- the first affected version or date;
- why continued use is risky or unsupported;
- the supported replacement and meaningful differences;
- detection method for remaining use;
- migration path and verification;
- planned removal condition or explicit absence of a committed date;
- compatibility behavior during the transition; and
- communication channels for material changes.

Do not invent a removal date. Do not call something deprecated if users have no viable replacement unless the consequence is explicit and owned.

Keep notices synchronized across compiler or runtime warnings, reference docs, changelog, release notes, and migration material. Prefer generating repeated lifecycle facts from one governed source.

## Security changes

Follow the project's disclosure and advisory process. Communicate affected versions, impact, fixed versions, mitigation, detection, and upgrade action without exposing details that the authority has not approved for release.

Do not infer exploitability or severity from a code diff alone.

## Verification

- Diff the public interface, schema, configuration, behavior, and released artifacts across the named versions.
- Confirm every breaking or action-requiring change has a migration or explicit disposition.
- Execute migration and rollback or coexistence in a representative fixture.
- Verify changelog and release-note version links, dates, and availability.
- Search documentation and examples for deprecated names and old behavior.
- Confirm runtime, compiler, or product warnings match the documented lifecycle.
- Test compatibility matrices against supported combinations where feasible.

Challenge the change detector with a known breaking fixture, such as a removed field or changed default, and confirm it is surfaced. Challenge migration verification by leaving one old-form artifact behind and confirm the check fails.

State exactly what was not testable. A migration validated only on synthetic data does not prove production volume, permissions, or integration behavior.
