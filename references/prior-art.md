# Prior-art basis

## Search frame

Research date: 2026-09-08.

The target is a reusable agent skill for the full technical-documentation space: repository and product documentation, wikis and knowledge bases, learning and task guidance, API and reference material, architecture and decisions, operations, change communication, and source-local comments or annotations.

Included precedents had to contribute a distinct mechanism, quality model, lifecycle practice, or skill-routing boundary. Marketing-only writing advice and inaccessible search snippets were excluded from mechanistic conclusions.

## Closest precedent families

| Precedent | Mechanism contributed | What it optimizes | What it does not settle |
|---|---|---|---|
| [ISO/IEC/IEEE 26514:2022](https://www.iso.org/standard/77451.html) | Treats information development as a lifecycle: audience and task analysis, structure, content, review, release, updating, maintenance, and change control | Governed software information development | A lightweight agent workflow or artifact-specific templates |
| [Diátaxis](https://diataxis.fr/) | Separates tutorials, how-to guides, reference, and explanation by reader need | Functional fit between information form and user mode | Operational, institutional, change, and source-local documentation as full first-class domains |
| [OASIS DITA technical-content types](https://docs.oasis-open.org/dita/v1.2/os/spec/archSpec/dita_technicalContent_InformationTypes.html) | Topic-oriented concept, task, and reference structures designed for reuse | Modular structured authoring and reuse | Whether a project should adopt DITA or any particular publishing stack |
| [Write the Docs: Docs as Code](https://www.writethedocs.org/guide/docs-as-code/) | Version control, plain text, issue tracking, review, and automated checks integrated with product change | Change-coupled documentation workflow | Wiki-first knowledge or the semantic quality of any given artifact |
| [Google documentation best practices](https://google.github.io/styleguide/docguide/best_practices.html) | Update docs with code, use READMEs and docs directories deliberately, remove stale or redundant documentation | Repository-local freshness and discoverability | A complete documentation portfolio model |
| [Google Developer Documentation Style Guide](https://developers.google.com/style) | Gives local project style priority over general style while pursuing clarity and consistency | Consistent technical prose | Truth, lifecycle, architecture, or operational safety by itself |
| [KCS v6 Practices Guide](https://library.serviceinnovation.org/KCS/KCS_v6/KCS_v6_Practices_Guide) | Captures knowledge in the workflow, structures for reuse, treats reuse as review, measures content health, and archives obsolete knowledge | Living support and institutional knowledge bases | Version-coupled code reference and repository topology |
| [OpenAPI Specification](https://spec.openapis.org/oas/latest.html) | Provides a machine-readable, language-agnostic HTTP API description usable by people and tools | Contract-derived API reference and tooling | Narrative workflows, omitted semantics, or reader success |
| [C4 model diagrams](https://c4model.com/diagrams) | Uses audience-appropriate context, container, component, and code zoom levels | Legible software architecture communication | Decision authority or a mandate to draw every level |
| [ADR guidance](https://adr.github.io/) | Records one architecturally significant decision with rationale, tradeoffs, and consequences in a decision log | Durable decision memory | Making the decision or replacing system explanation |
| [Keep a Changelog](https://keepachangelog.com/en/1.1.0/) | Curates notable human-facing changes in stable categories rather than mirroring commits | User-readable change history | Release narrative, migration procedure, or universal versioning policy |
| [W3C accessibility introduction](https://www.w3.org/WAI/fundamentals/accessibility-intro/) | Treats accessible information and interaction as a requirement for people with varied auditory, cognitive, neurological, physical, speech, and visual conditions | Inclusive consumption | Artifact truth or domain completeness |

## Source-local conventions

The [Go doc-comment guide](https://go.dev/doc/comment), [Python PEP 257](https://peps.python.org/pep-0257/), [TSDoc approach](https://tsdoc.org/pages/intro/approach/), [Javadoc specification](https://docs.oracle.com/en/java/javase/24/docs/specs/man/javadoc.html), [Rust documentation guide](https://doc.rust-lang.org/rustdoc/how-to-write-documentation.html), and [Google C++ style guide](https://google.github.io/styleguide/cppguide) converge on a mechanism rather than one syntax: public interface documentation should follow the language and project's extractable convention, while ordinary comments should preserve contracts, reasons, invariants, constraints, or non-obvious behavior rather than narrating readable code.

This convergence supports a single source-documentation module with local-convention routing. It argues against imposing one comment grammar across languages.

## Verification precedents

| Tool or study | Evidence contributed | Limit |
|---|---|---|
| [Vale](https://docs.vale.sh/) | Automates configurable prose-style and terminology checks | Does not establish factual or task correctness |
| [Doc Detective](https://docs.doc-detective.com/docs/get-started/how-testing-works) | Models procedures as executable steps and assertions | Covers only executable environments and encoded assertions |
| [Lychee](https://github.com/lycheeverse/lychee) | Checks links across common documentation formats | Link reachability is not semantic validity |
| [The Good Docs Project templates](https://gitlab.com/tgdp/templates/-/tree/main) | Offers reusable templates for common documentation types | Templates require reader- and project-specific adaptation |
| [Customer-facing documentation debt study](https://arxiv.org/abs/2402.11048) | Finds missing content, erroneous code examples, and outdated content among prominent defect classes; recommends robust sources and automated testing | Empirical sample does not define a universal taxonomy |
| [How software engineers use documentation](https://ieeexplore.ieee.org/document/1241364/) | Reports timeliness and completeness problems in practice | Older study; used as persistent failure evidence, not current tooling guidance |
| [Google documentation-usage log study](https://research.google/pubs/understanding-documentation-usage-through-log-analysis-an-exploratory-case-study-of-four-cloud-services/) | Shows behavioral logs can reveal how documentation is actually consumed | Usage does not by itself prove successful outcomes |

## Public agent-skill precedents

| Skill or toolkit | Relevant boundary | Consequence for this skill |
|---|---|---|
| [Scribe](https://github.com/simota/agent-skills/blob/main/scribe/SKILL.md) | Broad requirements and specification authoring, with code comments, API design, and architecture decisions routed to sibling skills | Demonstrates the split-skill alternative but centers specification packages rather than the whole documentation lifecycle |
| [Keeping Docs Fresh](https://github.com/gg-mo/repo-hygiene/blob/main/skills/keeping-docs-fresh/SKILL.md) | Synchronizes README, docs, changelog, and comments after code changes | Supplies a maintenance pattern, not a full authoring and information-architecture method |
| [Agent Docs Writing](https://github.com/event4u-app/agent-config/blob/main/dist/agent-src/skills/agent-docs-writing/SKILL.md) | Project-local rule against creating documentation without a durable need; routes to sibling documentation forms | Supports need-first routing and avoiding document proliferation |
| [Architecture Knowledge Toolkit](https://github.com/docs-as-code-toolkit/architecture-knowledge-toolkit) | Separates semantic architecture contracts from publishing and emphasizes stable IDs and traceability | Supports canonical semantic sources plus derived views, within an architecture-specific scope |
| [Agent Skills specification](https://agentskills.io/specification) | Progressive disclosure through a compact SKILL.md and selectively loaded resources | Supports one shared router with substantial independent modules rather than one monolithic prompt |

## Search coverage and saturation

Query families covered documentation standards and lifecycles; information typing; docs-as-code and repository conventions; API contracts; architecture and decision records; runbooks and operational knowledge; wikis and KCS; code comments and language doc conventions; changelogs and migration communication; documentation testing, style linting, links, accessibility, and freshness; empirical documentation failures; and public agent skills.

The final query families added validation tools and empirical examples of known failure classes but no new top-level relationship class. Two successive families reinforced the same authority, mode, verification, and lifecycle structure, so the search was treated as saturated for skill architecture.

## Mechanism synthesis

The precedents converge on a shared documentation contract:

`reader and job -> authoritative source -> information mode -> durable surface -> independent proof -> lifecycle trigger`

The document forms differ in local ordering, risk, and proof:

- Learning material proves a progression from a named starting state.
- Task guidance proves an outcome under prerequisites.
- Reference proves coverage and fidelity to a contract.
- Explanation proves a coherent model against system evidence.
- Operations proves safe state transitions, failure recognition, and recovery.
- Knowledge bases prove retrieval, reuse, ownership, and content health.
- Source documentation proves proximity and consistency with the symbol or invariant.
- Change communication proves audience-visible consequence and required action across versions.

This is enough common mechanism for one skill and enough divergence for independently loadable modules.

## Extend, compose, or supersede

**Decision: compose.** The skill composes established information typing, docs-as-code, contract-derived reference, knowledge-centered service, architecture communication, decision records, source-language conventions, change communication, and artifact-specific verification. It does not supersede those practices or prescribe one publishing stack.

It composes with `repo-refiner` at a precise seam: `repo-refiner` owns repository topology and truthful navigational projection; this skill owns what technical documentation means and whether it enables its reader. Mixed artifacts use both contracts.

## Surviving distinct claims

The defensible contribution is not a new documentation theory. It is the packaging of prior art into one progressively disclosed agent method that:

- spans institutional wikis through code comments without loading every domain at once;
- treats authority and verification as first-class routing inputs, not post-writing polish;
- supports mixed artifacts without collapsing their reader modes;
- separates repository navigation from documentation semantics at an explicit composition seam; and
- requires failure-sensitive evidence before automated documentation guarantees count as complete.

## Split condition

Keep this as one skill while the modules share the same authority map, routing vocabulary, lifecycle contract, and completion report. Split a module into its own top-level skill only when it develops an independently recurring trigger set, owner, workflow, evaluation apparatus, or safety boundary that makes the shared router ambiguous or forces most invocations to load irrelevant policy.
