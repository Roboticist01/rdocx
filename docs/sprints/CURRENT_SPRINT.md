# Current Sprint, S80

**Milestone**: X, contribution intake and issue repair.

**Goal**: complete the Word Python production checklist against the integrated
S79 prefix. Land the presentation text preservation and drawing contributions
in dependency order, with package validation and cross-viewer evidence.

## Spec references

- `docs/hld/03-architecture.md`, for source-preserving Word mutation and the
  ownership boundary behind the remaining Python operations.
- `docs/hld/05-drawingml-model.md`, for text body preservation, line feed
  serialization and schema-ordered drawing children.
- `docs/hld/06-presentationml-model.md`, for shape construction, click
  hyperlinks, effects and presentation facade ownership.
- `docs/hld/10-bindings-spec.md`, for Python lifetime, mutation and reopen
  behavior across Word and Presentation APIs.
- `docs/hld/12-testing-strategy.md`, for deterministic fonts, integration
  fixtures, package validation and pinned cross-viewer comparisons.
- `docs/hld/14-development-backlog.md`, for the F-X147, F-X154 and F-X155
  acceptance contracts, prerequisites and test gates.

## The wave

| F-ID | Title | Size | Status | Owner |
|------|-------|------|--------|-------|
| F-X147 | Complete rdocx Python production checklist | L | in-progress | codex |
| F-X154 | Presentation text and preservation repair | M | pending | - |
| F-X155 | Presentation drawing API contribution | L | pending | - |

## Sequencing note

Rows are listed in dependency order, not F-ID order. F-X147 can proceed on
its completed Word prerequisites while F-X154 reviews PRs 218 and 223.
F-X155 starts after F-X154 so its five drawing PRs are reconciled against the
reviewed presentation text and preservation prefix. PR 219 follows PR 189,
and PR 234 follows PR 207. Their overlapping shape, line, effect and binding
edits require manual reconciliation and a fresh integrated CI run.

## Definition of done for this sprint

- Every Issue 168 checklist example runs from Python, or has a reviewed scope
  decision and documented fallback accepted by the reporter's criteria.
- Issues 215 and 216 pass their preservation and line-feed regressions after
  PRs 218 and 223 are integrated.
- PRs 219, 221, 224, 230 and 234 are reconciled in schema order. Authored
  drawing effects and links reopen in python-pptx, validate and match the
  pinned cross-viewer renders.
- The integrated result passes the hash harness, `/verify --full` and
  `/sprint-review` before closure.
