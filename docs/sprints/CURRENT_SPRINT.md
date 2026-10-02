# Current Sprint, S83

**Milestone**: X, contribution intake and issue repair.

**Goal**: make newly authored Word documents open in Word and accept reported
style, drawing ID and measurement variants from existing producers. Review the
document-validity baseline change before the tolerance work so each output
delta has one owner.

## Spec references

- `docs/hld/04-opc-and-packaging.md`, for the fresh Word package graph,
  content types, relationships and saved-package integrity.
- `docs/hld/08-rendering-spec.md`, for deterministic Word output affected by
  the document-validity baseline.
- `docs/hld/10-bindings-spec.md`, for Python and CLI reads, style mutation and
  drawing identity behavior.
- `docs/hld/12-testing-strategy.md`, for source-built and reporter fixtures,
  Word opening, round trips and the reviewed hash delta.
- `docs/hld/14-development-backlog.md`, for the F-X159 and F-X160 contracts,
  dependencies and test gates.

## The wave

| F-ID | Title | Size | Status | Owner |
|------|-------|------|--------|-------|
| F-X159 | Word document validity baseline | M | in-progress | codex |
| F-X160 | Tolerant style, drawing and measurement reads | L | pending | - |

## Sequencing note

F-X159 reviews PR 240 first and owns the sprint's only hash baseline update.
F-X160 depends on that integrated result and reviews PRs 248, 249 and 250.
The two stories do not share a wave.

## Definition of done for this sprint

- F-X159 makes a source-built document and nested table open in Word, with
  only the declared deterministic hash changes.
- F-X160 accepts both Issue 243 reporter fixtures through every affected style
  mutator, and passes Issues 246 and 247 through read, edit, save and reopen
  with the specified rounding and drawing identity behavior.
- Word opening, exact XML, round-trip, CLI and Python checks accompany the
  source-built and reporter cases.
- The integrated result passes the hash harness, `/verify --full` and
  `/sprint-review` before any issue closure.
