# Current Sprint, S84

**Milestone**: X, contribution intake and issue repair.

**Goal**: finish the live contributor queue and all eight open issue contracts
in one integrated repair sprint. Complete each F-ID's scoped checks and review,
then run one full verification and sprint review over the combined result.

## Spec references

- `docs/hld/03-architecture.md`, for accepted-view and comparison ownership.
- `docs/hld/04-opc-and-packaging.md`, for the remaining Word package and
  namespace acceptance criteria.
- `docs/hld/06-presentationml-model.md`, for new-shape style serialization.
- `docs/hld/07-inheritance-and-resolution.md`, for theme style resolution.
- `docs/hld/08-rendering-spec.md`, for the pending deterministic line-fit and
  tracked-view evidence.
- `docs/hld/10-bindings-spec.md`, for Python and CLI acceptance surfaces.
- `docs/hld/12-testing-strategy.md`, for the fixture matrices and combined
  verification gate.
- `docs/hld/14-development-backlog.md`, for all nine repair contracts and
  their formal dependencies.

## The wave

| F-ID | Title | Size | Status | Owner |
|------|-------|------|--------|-------|
| F-X169 | Reconcile live contributions and open issue contracts | L | done | - |
| F-X161 | Compact Word XML and namespace preservation | L | done | - |
| F-X162 | Per-paragraph section width and pagination | M | in-progress | codex |
| F-X163 | Plain-line trailing-space fit | M | pending | - |
| F-X164 | Added shape theme style | M | in-progress | codex |
| F-X165 | Python and CLI tracked revision view | M | done | - |
| F-X166 | Picture and final-block comparison revisions | L | in-progress | codex |
| F-X167 | Accepted-view exporters and readers | L | pending | - |
| F-X168 | Current issue and contribution closure evidence | M | pending | - |

## Sequencing note

F-X169 completes intake first. F-X161, F-X164 and F-X165 depend on it.
F-X162 follows F-X161, then F-X163 follows F-X162. F-X166 follows F-X165,
and F-X167 follows both F-X165 and F-X166. F-X168 checks all completed work
last. Use scoped dependency-prefix checkpoints so consumers start only after
their prerequisites complete. F-X161, F-X162 and F-X163 own three separate,
sequential hash baseline changes. The final full gate runs once.

## Definition of done for this sprint

- Every open PR has a reviewed incremental disposition against integrated
  main, including stacked commits and shared-file reconciliation.
- Issues 158, 160, 226, 244, 245 and 253 through 255 meet every acceptance
  criterion on the integrated result, with viewer evidence where required.
- The three hash changes and the golden pixel update are individually labelled
  and reviewed. The fixture workflows, producer and identity matrices, scoped
  checks, final hash harness, `/verify --full` and `/sprint-review` pass.
- After `/close-sprint` merges the reviewed result to main, all 31 open PRs
  and eight open issues in the 2 October intake are closed with evidence links.
