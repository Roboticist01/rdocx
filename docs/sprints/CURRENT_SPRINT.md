# Current Sprint, S82

**Milestone**: X, contribution intake and issue repair.

**Goal**: turn the reporter's Word and Presentation fixtures into repeatable
acceptance checks. Run the complete DOCX and deck workflows against pinned
references, then reconcile each open issue criterion against the integrated
result. Keep an issue open when any criterion lacks evidence.

## Spec references

- `docs/hld/04-opc-and-packaging.md`, for saved-package integrity and related
  parts in the reporter's Word and Presentation fixtures.
- `docs/hld/06-presentationml-model.md`, for slide, notes and relationship
  preservation in the deck workflow.
- `docs/hld/08-rendering-spec.md`, for deterministic output and pinned viewer
  comparison in both fixture gates.
- `docs/hld/10-bindings-spec.md`, for Python authoring and reopen behavior in
  the complete DOCX and deck workflows.
- `docs/hld/12-testing-strategy.md`, for source-built and reporter fixtures,
  matrix coverage, oracle tolerances and criterion-level evidence.
- `docs/hld/14-development-backlog.md`, for the F-X149, F-X158 and F-X150
  acceptance contracts and dependencies.

## The wave

| F-ID | Title | Size | Status | Owner |
|------|-------|------|--------|-------|
| F-X149 | Word fixture and workflow acceptance gate | L | in-progress | codex |
| F-X158 | Presentation fixture and workflow acceptance gate | L | pending | - |
| F-X150 | Reconcile issue closure evidence | M | pending | - |

## Sequencing note

F-X149 and F-X158 are independent fixture gates and may proceed in separate
worktrees. F-X150 follows both, audits every criterion in the original 22-issue
snapshot and closes Issue 158 last. New issues and contributions from 1 October
remain in their planned later sprints.

## Definition of done for this sprint

- F-X149 turns the reporter's DOCX fixture, 18 by 7 identity matrix, 11 by 8
  producer matrix and complete Word workflow into repeatable acceptance checks
  against pinned references with deterministic fonts.
- F-X158 turns the reporter's deck workflow into repeatable round-trip,
  validation and cross-viewer acceptance for Issues 169, 170, 215, 216 and 217.
- F-X150 records passing evidence or an explicit unresolved result for every
  criterion in its 22-issue snapshot. No issue closes solely because a PR
  merged, and Issue 158 closes only after both fixture gates pass.
- The integrated result passes the hash harness, `/verify --full` and
  `/sprint-review` before sprint closure.
