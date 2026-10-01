# Current Sprint, S79

**Milestone**: X, contribution intake and issue repair.

**Goal**: finish the Word layout and CLI diff defects on the verified S78
prefix, then close the remaining Word Python binding gaps before the production
fixture gate. Reconcile the assigned contributions with the integrated result
and prove the focused layout, story and binding cases before the full sprint gate.

## Spec references

- `docs/hld/03-architecture.md`, for the Word layout conversion boundary,
  full-story comparison model and native comment and run ownership.
- `docs/hld/08-rendering-spec.md`, for text line geometry and inline picture
  placement in Word layout.
- `docs/hld/10-bindings-spec.md`, for Python paragraph, comment and run mutation
  behavior after save and reopen.
- `docs/hld/12-testing-strategy.md`, for deterministic bundled-font fixtures,
  full-story regressions and the integrated verification gate.
- `docs/hld/14-development-backlog.md`, for the F-X146, F-X152 and F-X153
  contracts, dependencies and test gates.

## The wave

| F-ID | Title | Size | Status | Owner |
|------|-------|------|--------|-------|
| F-X146 | Word line height and inline picture spacing | L | in-progress | codex |
| F-X152 | Full-story CLI diff and count repair | M | in-progress | codex |
| F-X153 | Word Python supplemental contribution | M | in-progress | codex |

## Sequencing note

Rows are listed in dependency order, not F-ID order. All three stories have
their prerequisite F-IDs on the completed prefix, so none blocks another.
Review PRs 222, 225 and 237 for F-X146, PR 236 for F-X152 and PR 220 for
F-X153 against that prefix. F-X146 covers Issue 162 and only the rich-line
symptom of Issue 226. F-X163 follows later for its plain-line symptom. F-X152
covers Issue 227. F-X153 reconciles PR 220 with F-X141 and contributes comment,
numbering and run operations toward the remaining Issue 168 checklist.
Run the Word fixture and focused layout oracles on the integrated result before
`/verify --full` and `/sprint-review`.

## Definition of done for this sprint

- PRs 222, 225, 237, 236 and 220 have reviewed incremental diffs against the
  integrated prefix, with overlap reconciled and focused checks passing.
- The four-family, two-size, two-spacing pitch matrix and the Word-exported
  inline picture fixture meet pinned geometry for Issue 162 and Issue 226's
  rich-line symptom.
- The Issue 227 reproducer locates every changed story paragraph and counts
  each once in the CLI diff report.
- Python and CLI comment coordinates, numbering and run removal pass after
  save and reopen, with the Issue 168 checklist recording the remaining work.
- The combined result passes the hash harness, `/verify --full` and
  `/sprint-review` before closure.
