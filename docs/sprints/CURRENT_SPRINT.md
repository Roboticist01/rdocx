# Current Sprint, S81

**Milestone**: X, contribution intake and issue repair.

**Goal**: finish the presentation authoring surface after the S80 drawing work.
Prove the complete Issue 169 and Issue 217 deck checklists with saved-package
validation, python-pptx reopening and pinned cross-viewer rendering. Record an
explicit scope decision and fallback for any unsupported operation.

## Spec references

- `docs/hld/04-opc-and-packaging.md`, for slide import, media deduplication
  and relationship ownership without losing package parts.
- `docs/hld/05-drawingml-model.md`, for line, shadow, geometry and table style
  preservation in the completed deck chain.
- `docs/hld/06-presentationml-model.md`, for slide collection, notes, scoped
  mutation, schema order and validation.
- `docs/hld/07-inheritance-and-resolution.md`, for built-in table styles and
  theme effects when imported or authored slides render.
- `docs/hld/08-rendering-spec.md`, for deterministic slide rendering and the
  stated cross-viewer comparison boundary.
- `docs/hld/10-bindings-spec.md`, for Python handle lifetime, API parity and
  save-reopen behavior.
- `docs/hld/12-testing-strategy.md`, for source-built fixtures, package
  validation and pinned python-pptx and LibreOffice oracles.
- `docs/hld/14-development-backlog.md`, for the F-X156, F-X148 and F-X157
  acceptance contracts and dependencies.

## The wave

| F-ID | Title | Size | Status | Owner |
|------|-------|------|--------|-------|
| F-X156 | Presentation slide and table contribution | L | done | - |
| F-X148 | Complete rpptx Python production checklist | L | done | - |
| F-X157 | Complete deck-chain authoring checklist | L | in-progress | codex |

## Sequencing note

Rows are listed in dependency order, not F-ID order. F-X156 follows the
completed F-X155 drawing prefix and reconciles PRs 231, 235 and 238, with PR
231 following PR 181. F-X148 then checks the complete Issue 169 Python chain
on that slide and table surface. F-X157 follows both and checks all six Issue
217 operations in one authored deck.

## Definition of done for this sprint

- F-X156 imports and edits slides without losing media, notes or
  relationships, and its scoped replacement and table behavior validate and
  render after save and reopen.
- Every Issue 169 checklist item passes from Python in the production deck
  chain or has a reviewed scope decision and documented fallback.
- Every Issue 217 checklist item passes python-pptx reopening,
  `rpptx validate` and pinned LibreOffice versus deterministic rpptx rendering,
  or has a reviewed scope boundary and fallback.
- The integrated result passes the hash harness, `/verify --full` and
  `/sprint-review` before closure.
