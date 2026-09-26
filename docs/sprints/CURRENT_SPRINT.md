# Current Sprint, S76

**Milestone**: M24 Modern DOCX authoring completeness.

**Goal**: establish rich header, footer, and note authoring on the existing
story model, while removing repeated canonical-prefix rebinding from retained
elements. Complete the footnote substrate before extending it to endnotes.

## Spec references

- `docs/hld/02-scope-and-non-goals.md`, for the DOCX-038 through DOCX-040
  capability boundaries and their public authoring obligations.
- `docs/hld/03-architecture.md`, for common story ownership, native facade
  operations, and separate footnote and endnote streams.
- `docs/hld/04-opc-and-packaging.md`, for part-scoped relationships, retained
  namespace declarations, and unchanged-part preservation.
- `docs/hld/08-rendering-spec.md`, for footnote continuation, endnote placement,
  and deterministic related-story layout.
- `docs/hld/10-bindings-spec.md`, for the common story API and header and footer
  variant operations exposed through bindings.
- `docs/hld/12-testing-strategy.md`, for source-built regressions, the hash
  harness, and pinned differential and round-trip checks.
- `docs/hld/14-development-backlog.md`, for F-X133 and F-271 through F-273
  acceptance contracts, dependencies, sizes, and named test gates.

## The wave

| F-ID | Title | Size | Status | Owner |
|------|-------|------|--------|-------|
| F-X133 | Stop rebinding a canonical prefix on every retained element | S | pending | - |
| F-271 | Uniform rich header and footer editing | L | pending | - |
| F-272 | Rich footnote authoring | L | pending | - |
| F-273 | Rich endnote authoring | L | pending | - |

## Sequencing note

F-X133 is independent and can proceed alongside F-271. F-271 extends every
header and footer variant through the common story API. F-272 establishes rich
footnote authoring before F-273 extends the same content and relationship
surface to endnotes with an independent identifier namespace. F-274 through
F-284 remain pending in S77 and are not part of this sprint's completion gate.

## Definition of done for this sprint

- F-X133 avoids redundant canonical namespace bindings on retained elements
  while preserving producer attributes and genuine new bindings on save.
- Every header and footer variant supports the same rich authored subtree and
  reopens with correct part-scoped relationships.
- Rich footnotes can be created, edited, reordered, and removed, with pinned
  differential evidence for numbering, placement, continuation, and structure.
- Rich endnotes provide the same content and relationship surface, remain
  independent from footnotes, and pass mixed-note differential placement gates.
- The integrated sprint passes full verification and sprint review without an
  unexplained hash or deterministic rendering delta.
