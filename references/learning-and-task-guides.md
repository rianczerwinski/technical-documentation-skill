# Learning and task guides

Use this module for tutorials, onboarding, quickstarts, ordinary how-to guides, and task procedures that are not high-risk operational runbooks.

## Choose learning or task mode

### Tutorial

A tutorial serves a learner acquiring capability. It owns the learning path, controls the sequence, minimizes irrelevant choices, and produces visible progress. The immediate artifact is a means to understanding, not the sole objective.

Use a tutorial when the reader asks:

- "How do I begin?"
- "Can you teach me the basic workflow?"
- "What should I experience first to understand this system?"

### How-to guide

A how-to guide serves a reader who already has the relevant competence and wants a real-world outcome. It starts from a named situation, permits reasonable variation, and stops when the outcome is achieved.

Use a how-to guide when the reader asks:

- "How do I accomplish this specific task?"
- "How do I adapt the system to this condition?"
- "What sequence gets me from this known state to that result?"

Do not disguise reference as a how-to by listing every option, or explanation as a tutorial by lecturing before the reader can act.

## Tutorial contract

Define:

- learner identity and assumed knowledge;
- safe and reproducible starting environment;
- the capability the learner will acquire;
- a sequence of small, meaningful outcomes;
- expected observations after each critical step;
- controlled recovery from likely mistakes; and
- a closing model that names what the learner can do next.

### Tutorial shape

```md
# Build your first <meaningful result>

You will <observable capability>. This path assumes <knowledge and environment> and takes approximately <honest range, when useful>.

## Before you begin

- Required access, software, data, and safety constraints
- Starting state and how to confirm it

## 1. Produce the first visible result

Instruction.

Expected observation and its meaning.

## 2. Extend or inspect the result

Instruction.

Expected observation and its meaning.

## Recover from common mistakes

Symptom -> cause discrimination -> recovery.

## What you learned

Name the mental model and the next appropriate reader path.
```

Keep the path reliable. Defer optional branches until the learner has the main experience. Explain enough for orientation, but link deeper conceptual material rather than interrupting every action.

## How-to contract

Define:

- the desired outcome;
- prerequisites and starting state;
- supported variants and excluded conditions;
- ordered actions with exact inputs;
- observations that distinguish success from partial or failed states;
- cleanup or reversibility when the task changes durable state; and
- links to reference for exhaustive parameters and explanation for rationale.

### How-to shape

```md
# How to <achieve outcome>

Use this procedure when <situation>. It produces <observable result> and does not cover <important exclusion>.

## Prerequisites

- Required versions, permissions, data, and current state
- Check that confirms the starting state

## Procedure

1. Action with exact command or interface path.
2. Expected observation.
3. Next action, including meaningful variant when necessary.

## Verify the result

Independent observation and expected value.

## Undo or clean up

Reversal, retained side effects, or explicit irreversibility.

## If it does not work

Symptoms that discriminate likely causes and route to targeted recovery.
```

## Onboarding paths

Onboarding is a coordinated learning sequence, not a storage place for every fact a newcomer might need.

Order by capability:

1. Gain access and prove the environment works.
2. Build or run the smallest representative unit.
3. Observe the system's principal feedback loop.
4. Make one safe change and verify it.
5. Learn the architecture and contribution boundaries needed for the next task.

Route exhaustive setup matrices to reference. Route organizational policy to its canonical owner. Route repository navigation to `repo-refiner`.

## Instructions and examples

- Use imperative steps for actions and declarative sentences for observations.
- Put one state transition in a step when failure between transitions matters.
- Name the execution location, user, permissions, version, and environment when they affect the result.
- Show placeholders unmistakably; do not make fake values look copyable.
- Keep code samples complete enough to run at their declared scope.
- Show realistic output only where it helps recognize state; avoid brittle full-screen transcripts.
- Explain destructive or irreversible effects before the command that causes them.

## Troubleshooting boundary

Ordinary task troubleshooting can stay with a how-to when the failure set is small and bounded. Load [Operations](operations.md) when recovery affects production, shared state, security, data durability, availability, or incident response.

Troubleshooting should discriminate causes:

| Symptom | Check | Meaning | Action |
|---|---|---|---|
| Observable condition | Narrow diagnostic | What the result rules in or out | Targeted recovery or escalation |

Avoid undifferentiated lists of things to try. They teach readers to mutate state without learning which condition they are in.

## Verification

Run the path from the declared starting state with the documented permissions and versions. Capture:

- whether prerequisites were sufficient;
- whether every command or interaction was executable as written;
- whether expected observations appeared at the right point;
- whether the final outcome matched the claim;
- whether a likely wrong turn was diagnosable; and
- whether cleanup or reversal behaved as documented.

For a tutorial, add a reader check: after completing it, can the learner explain the core model or perform a small adjacent action without following the same script?

For a how-to, deliberately violate one prerequisite or expected state and confirm the guide detects or clearly excludes that condition instead of appearing to succeed.
