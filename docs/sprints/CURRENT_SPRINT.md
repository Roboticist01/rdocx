# Current Sprint, S77

**Milestone**: X, contribution intake and issue repair.

**Goal**: integrate the remaining reviewed rendering, layout, Python,
presentation and CLI contributions on the completed S76 prefix. Reconcile
stacked and overlapping PRs before one combined verification and review
boundary. Issue acceptance continues through S82 before the deferred feature work at S83.

## Spec references

- `docs/hld/03-architecture.md`, for crate and facade ownership across the
  Word, presentation and CLI contributions.
- `docs/hld/05-drawingml-model.md`, for shared DrawingML geometry, tables and
  preservation rules touched by rendering and presentation work.
- `docs/hld/06-presentationml-model.md`, for presentation shapes, tables,
  layouts, relationships and validation.
- `docs/hld/08-rendering-spec.md`, for Word and slide layout, PDF and raster
  rendering behavior.
- `docs/hld/10-bindings-spec.md`, for native and Python API agreement, handle
  behavior and both CLI contracts.
- `docs/hld/12-testing-strategy.md`, for deterministic rendering, the hash
  harness, fidelity corpora, binding smoke and integration evidence.
- `docs/hld/14-development-backlog.md`, for F-X140 through F-X158
  dependencies, PR sets and named test gates.

## The wave

| F-ID | Title | Size | Status | Owner |
|------|-------|------|--------|-------|
| F-X140 | Rendering and layout contribution wave | L | in-progress | codex |
| F-X141 | Word Python contribution wave | L | pending | - |
| F-X142 | Presentation Python contribution wave | L | pending | - |
| F-X143 | Revision listing and CLI story contribution wave | M | pending | - |

## Sequencing note

F-X140 follows S76's package prefix and owns the first reviewed hash baseline
update. F-X141 follows F-X140 and owns a separate baseline update for native
common styles and any reviewed TOC output delta. Each behavior change has its
own labelled commit and expected delta.
PR 196's Presentation fidelity gate and PR 206's MSRV and Test gates must pass
before integration. F-X141 and F-X142 both follow F-X140. Their shared
presentation tests and documentation make them separate waves, with F-X141
first. In F-X141, PR 203
follows 201. In F-X142, PRs 208 and 209 follow 189. F-X143 follows F-X141
and S76's PR 198, with PR 204 replayed after that parent. Reapply only the
incremental diff of each stacked PR, then rebase and rerun CI.

## Definition of done for this sprint

- Every S77 PR has a reviewed incremental diff, reconciled overlap and
  passing relevant focused checks after rebasing. The later 30 September PR
  intake is assigned to S78 through S81.
- F-X140's intentional rendering delta has its own labelled commit and
  reviewed expected hash change. The deterministic Word and presentation
  fidelity gates pass.
- F-X141 completes the named section-default, native common-style and
  refreshable TOC behavior gaps, with a separately reviewed baseline delta.
- Word and presentation Python workflows, typing smoke, native parity,
  round-trip, validation and rendering checks pass on the integrated result.
- F-X142 covers every Issue 169 checklist item through a working API or a
  reviewed scope decision and documented fallback, including shape hyperlinks,
  anchored comments and built-in table styles.
- Revision listing covers all stories. The CLI detects malformed related
  parts and undefined styles in its stated scope.
- The combined S77 result passes binding smoke, package, rendering,
  documentation and release regression checks, then `/verify --full` and
  `/sprint-review`. Broader issue acceptance remains scheduled for S78 and
  S79.
