# F-X150, Reconcile issue closure evidence

**Status**: approved
**Sprint**: S82
**Size**: M
**Depends on**: F-X149, F-X158

## Problem

`docs/sprints/SPRINT_PLAN.md:1885` lists closure criteria from the original 22-issue snapshot. Prior sprint records contain focused evidence and some closed issues, but no single criterion-level reconciliation against the integrated S76 to S82 result. Issue 158 requires both attachment gates before closure.

## Spec reference

- `docs/hld/12-testing-strategy.md`, "The Word corpus", "The deck corpus" and "Binding tests".
- `docs/hld/14-development-backlog.md`, "F-X150, Reconcile issue closure evidence".
- `docs/sprints/SPRINT_PLAN.md`, "S82, Production acceptance and issue closure evidence" and the original issue closure table.

## Approach

Build a criterion ledger inside the F-X150 design plan or its HLD impact section, with one row per criterion in the 22-issue snapshot. Each row names a passing test or observation at the integrated SHA, or says unresolved and identifies the gap. Check live issue state when GitHub access returns. Close only issues whose complete criterion set is evidenced, with Issue 158 last after both fixture gates and final full verification and sprint review. Leave incomplete issues open with an evidence comment if the external service is available.

## Rejected alternatives

- A PR merge or previous issue closure alone does not prove the original acceptance criteria.
- A summary count without per-criterion links hides unsupported claims.

## Test plan

| Category | Test | Asserts |
|---|---|---|
| integration | Criterion ledger audit | Every criterion from the 22-issue snapshot has a passing artifact or explicit unresolved result. |
| regression | Evidence locator check in existing sprint workflow tests | Every passing row resolves to a real test or immutable observation. |
| gate | Backlog integration test gate | Criterion ledger is complete, and final sprint verify and review pass before closure actions. |

## HLD impact

- `docs/hld/12-testing-strategy.md`

## Risk routing

none. This story records evidence and issue state without changing product behavior. Any implementation needed to make a criterion pass requires a separately reviewed feature scope.

## Hash harness

Expected unchanged.

## Implementation checklist

- [ ] Enumerate every criterion in the original 22-issue snapshot.
- [ ] Bind each to a current passing artifact or an explicit unresolved result.
- [ ] Confirm both fixture gates and final integrated verification and review before any issue closure.
- [ ] Reconcile live issue state, close fully evidenced issues with Issue 158 last, and leave incomplete issues open.
- [ ] Run scoped verification and microscope to zero findings.

## Open questions

None. GitHub issue access is available through the approved remote read path. Both reporter attachments are identified and SHA-bound. An incomplete criterion keeps its issue open.
