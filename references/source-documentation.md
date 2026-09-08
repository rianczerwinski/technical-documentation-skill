# Source documentation

Use this module for comments, docstrings, extractable doc comments, annotations, directives, TODOs, generated source reference, and documentation that must stay adjacent to code.

## Start with the local language and project contract

Inspect:

- repository instructions and style guides;
- language-native documentation conventions;
- formatter, linter, compiler, or extractor behavior;
- generated API-documentation configuration;
- public compatibility commitments; and
- nearby high-quality examples.

Follow the local convention unless changing it is part of the task. Syntax is tooling: an otherwise elegant comment in the wrong form may not be extracted, checked, localized, or shown where readers expect it.

## Decide whether prose belongs in source

Put information in source when it is tightly coupled to a symbol, invariant, non-obvious algorithm, compatibility constraint, unsafe edge, or maintenance obligation.

Put it elsewhere when it primarily serves:

- a multi-component architecture model;
- an end-user task spanning several interfaces;
- an operational procedure with roles and recovery;
- a long design argument or decision history;
- a product policy governed outside the code; or
- a repository navigation need.

Link outward from source only when the external artifact has a stable canonical location. Preserve the minimum local warning or invariant needed to prevent misuse if the link is unavailable.

## Comments

Valuable comments preserve information the code cannot state economically:

- why an apparently simpler implementation is wrong;
- domain invariants and units;
- ordering, concurrency, timing, or lifecycle constraints;
- compatibility and protocol obligations;
- security and privacy boundaries;
- surprising side effects or failure behavior;
- provenance for a non-obvious algorithm or constant;
- intentional deviation from an established convention; and
- the relationship between generated code and its source.

Avoid comments that:

- paraphrase syntax or names;
- narrate control flow already obvious from the code;
- preserve deleted implementation history that version control already owns;
- excuse confusing structure that should be refactored;
- state an enforceable rule that machinery could reject; or
- speculate about intent without evidence.

### Comment shape

Prefer:

```text
Constraint or surprising behavior.
Reason or source of the constraint.
Maintenance consequence when it is violated.
```

Not every comment needs all three sentences. The shape identifies the information worth preserving.

## Public doc comments and docstrings

Document a public interface as a contract. Depending on language and project convention, include:

- concise purpose in the declaration's terms;
- parameters by semantic meaning, not only type;
- units, ranges, formats, nullability, and cross-parameter constraints;
- return meaning and stable identity;
- mutations, I/O, allocation, persistence, and other side effects;
- errors, exceptions, panics, exit behavior, or undefined conditions;
- concurrency, thread-safety, reentrancy, cancellation, and ordering;
- security or permission requirements;
- lifecycle, ownership, and resource cleanup;
- representative use when it resolves ambiguity; and
- version, stability, compatibility, or deprecation state.

Do not repeat facts the signature or generated type display already communicates unless the language convention requires the repetition for extraction. Add the semantics the type does not carry.

For private interfaces, document only what reduces real maintenance risk. Visibility alone does not justify boilerplate.

## Modules, packages, and files

A module-level document should explain the module's responsibility, public boundary, important invariants, and relationship to adjacent modules. It should not enumerate the file's contents line by line.

Use a file header for legal requirements, generated-source notices, critical build instructions, or a genuinely file-wide model. Avoid author/date banners and manual change histories that version control already provides.

## Annotations and directives

Annotations may be documentation, executable metadata, or both. Determine which authority governs them:

- compiler or runtime semantics;
- documentation generator;
- static analyzer;
- framework reflection;
- code-review interface; or
- local human convention.

When an annotation changes runtime, build, security, serialization, or compatibility behavior, treat it as code: validate it mechanically and document the consequence at the affected interface.

Do not invent an informal annotation syntax when a language, type, schema, test, linter, or issue tracker can carry the rule more reliably.

## TODO, FIXME, and debt markers

A durable source marker should identify:

- the concrete unmet condition;
- why it cannot be resolved in the current change;
- a stable issue or owner when the project requires one; and
- the removal condition.

Avoid vague markers such as "clean this up" or "temporary." If the work is important enough to survive the change but too large for a local marker, record it in the project's canonical work tracker and keep only the local pointer needed for discoverability.

Security, data-loss, or correctness defects should not be normalized as unattended TODOs.

## Keep code and documentation synchronized

Change source documentation in the same change as the interface, invariant, or behavior. Review comments as part of the code's correctness:

- Does the documented condition still exist?
- Has an exception become the normal path?
- Does the name or type now express what the comment repeats?
- Did a refactor move the invariant to another owner?
- Does generated reference reflect the updated source comment?
- Are examples compiled or exercised?

When the comment is the only surviving explanation for a constraint, preserve it through refactoring even if its exact location changes.

## Language-specific routing

Use the current official guidance and repository configuration for the language in scope. Representative conventions include:

- Go doc comments associated with declared names and package documentation;
- Python docstring conventions established by PEP 257 and the project's chosen field syntax;
- TSDoc or JSDoc-compatible structured comments where TypeScript or JavaScript tooling expects them;
- Javadoc tags and visibility configured by the Java documentation build;
- Rust documentation comments, examples, links, and doctests; and
- C++ project's chosen extraction and style conventions.

These examples do not authorize changing the repository's toolchain. Detect the actual convention first.

## Verification

- Run the language formatter, linter, compiler, and documentation extractor relevant to the changed comments.
- Compile or execute documentation examples where the ecosystem supports it.
- Compare public symbols with generated reference coverage.
- Inspect warnings for broken intra-doc links, missing parameters, invalid tags, and stale references.
- Review comment claims against the exact code path, including failure and concurrency behavior.
- Search for old symbol names and duplicated explanations after a rename or refactor.
- Confirm a source annotation changes or constrains behavior exactly as documented.

Challenge doc-comment coverage with a fixture containing one undocumented public symbol. Challenge an extractor with one malformed tag or broken symbol link. A tool that accepts both does not prove the promised contract.
