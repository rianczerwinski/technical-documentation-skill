# Operations

Use this module for runbooks, playbooks, incident procedures, production troubleshooting, recovery, maintenance, and any procedure whose mistake can affect shared state, availability, security, money, privacy, or durable data.

## Operational documentation is a control surface

An operator must be able to identify the current state, decide whether the procedure applies, make one bounded transition, observe its result, stop before harm, recover when possible, and escalate with useful evidence.

The procedure must not collapse these states:

- healthy versus degraded;
- empty-success versus failed retrieval;
- symptom versus confirmed cause;
- safe-to-retry versus non-idempotent;
- reversible versus irreversible;
- mitigated versus resolved; and
- local impact versus wider blast radius.

## Choose the artifact

- **Runbook:** routine, bounded operation for a known system and starting state.
- **Playbook:** coordinated response pattern with branching judgment, often spanning systems or roles.
- **Troubleshooting guide:** symptom-led discrimination among plausible causes.
- **Incident procedure:** time-sensitive coordination, containment, communication, evidence preservation, and recovery.
- **Recovery guide:** restoration from a known failure or data-loss condition.
- **Maintenance procedure:** planned change with prechecks, execution, validation, and rollback.

Do not force an incident's decision tree into a linear runbook.

## Runbook contract

```md
# <Observable operation>

Use when <conditions>. Do not use when <exclusions>. Expected impact: <scope and duration>.

## Ownership and escalation

Owning service or role, approval requirements, escalation route, and communication channel.

## Preconditions

- Access, permissions, tools, versions, backups, capacity, maintenance window, and dependencies
- Commands or observations that prove the starting state
- Abort conditions before any mutation

## Procedure

### 1. <Single meaningful transition>

Action.

Expected observation, timeout, and interpretation.

If the observation differs: stop, recover or escalate; do not continue blindly.

## Verify

Independent health, data-integrity, user-path, and monitoring observations.

## Roll back or recover

Trigger, exact sequence, retained side effects, and verification.

## Evidence to retain

Commands, timestamps, identifiers, logs, snapshots, and communication record needed for diagnosis or audit.

## Known failure branches

Symptom -> discriminating check -> bounded response -> escalation.
```

## Procedure design

- Put warnings and irreversible consequences before the action.
- State the execution identity, host, region, cluster, tenant, working directory, and environment when ambiguity is dangerous.
- Use exact commands, but isolate values the operator must resolve and validate.
- Include expected output narrowly enough to recognize the state without depending on unstable noise.
- State safe retry semantics and timeouts.
- Use checkpoints for long or expensive work; expose complete, active, remaining, and failed units.
- Preserve evidence before a recovery action destroys diagnostic state.
- Prefer commands that inspect exact targets before mutating them.
- Separate containment from diagnosis and permanent repair.

Do not invent production commands from analogous development behavior. Verify against the actual operational authority or mark the runbook unusable for production until validated.

## Troubleshooting as discrimination

Start with the symptom as the operator sees it. Each branch should reduce uncertainty.

```md
## <Symptom>

### Confirm scope

Observations that distinguish one user, one tenant, one region, or the whole service.

### Check <candidate cause>

Read-only diagnostic and expected alternatives.

- If <observation A>: meaning and action.
- If <observation B>: meaning and action.
- Otherwise: stop and escalate with named evidence.
```

Avoid long lists of unrelated fixes. Mutation before diagnosis can hide the cause, widen the incident, or make rollback impossible.

## Incident and recovery additions

Include when relevant:

- severity or declaration criteria;
- incident roles and handoffs;
- containment order;
- status communication audience and cadence;
- evidence preservation and privacy handling;
- recovery point and recovery time constraints;
- data reconciliation and integrity checks;
- customer or downstream remediation;
- post-incident documentation updates; and
- explicit closure authority.

Never claim data is recovered merely because the service is responsive. Verify completeness, ordering, identity, and downstream consistency against an independent source.

## Security and privacy

- Do not place reusable secrets in documentation or examples.
- Identify commands that expose sensitive output and the approved handling path.
- Use least-privileged identities and scoped targets.
- Distinguish access failure from absence of data.
- Preserve audit evidence without copying personal or secret data into uncontrolled surfaces.
- Require human-owned confirmation for genuinely irreversible or high-blast-radius actions.

## Verification

Exercise the procedure in the closest safe representative environment. Record the environment boundary and what remains unproven.

Verify:

- applicability and exclusion checks;
- permission and dependency assumptions;
- each expected observation and timeout;
- stop and abort conditions;
- successful outcome and independent health signal;
- rollback or recovery from a deliberately interrupted step;
- idempotent retry claims;
- evidence retention; and
- escalation routing.

Use a deliberately false starting state or failed dependency to confirm the runbook stops before mutation. Use a disposable fixture to prove rollback detects and reverses the intended change. Never perform a destructive mutation against real shared state merely to test documentation.
