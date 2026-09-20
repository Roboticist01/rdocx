# Current Sprint, S75

**Milestone**: M24 Modern DOCX authoring completeness.

**Goal**: make every non-main Word story a first-class authoring location
through the same rich, relationship-safe public surface as the main story.
The sprint completes notes, cross-story ranges, transactional fragments, and
glossary building blocks with deterministic package ownership and rendering.

## Spec references

- `docs/hld/02-scope-and-non-goals.md`, for DOCX-036 and DOCX-038 through
  DOCX-044, whose remaining story, note, range, fragment, and glossary
  capability boundaries this sprint closes.
- `docs/hld/03-architecture.md`, for container-neutral story addressing,
  staged rich-content mutation, physical header and footer ownership,
  independent note streams, and package-authoritative fragment import.
- `docs/hld/04-opc-and-packaging.md`, for part-scoped relationships,
  deterministic identities, schema-ordered note and story serialization,
  glossary ownership, and atomic dependency remapping.
- `docs/hld/08-rendering-spec.md`, for inherited header and footer projection,
  footnote page placement, endnote document-end flow, and story-aware field
  and annotation behavior.
- `docs/hld/12-testing-strategy.md`, for public integration, round-trip, and
  pinned differential gates in deterministic font mode.
- `docs/hld/14-development-backlog.md`, for the F-271 through F-277 and F-X133
  through F-X134 acceptance contracts, dependencies, sizes, and named test
  gates.

## The wave

| F-ID | Title | Size | Status | Owner |
|------|-------|------|--------|-------|
| F-X134 | Keep Python story hyperlink snapshots linear | S | done | - |
| F-X133 | Stop rebinding a canonical prefix on every retained element | S | pending | - |
| F-271 | Uniform rich header and footer editing | L | pending | - |
| F-272 | Rich footnote authoring | L | pending | - |
| F-275 | Cross-story bookmarks, ranges, and annotations | L | pending | - |
| F-273 | Rich endnote authoring | L | pending | - |
| F-274 | Note separators, markers, and restart policy | L | pending | - |
| F-276 | Complete fragment conflict and dependency policy | L | pending | - |
| F-277 | Glossary and building-block creation | L | pending | - |

## Sequencing note

Rows are listed in dependency order, not F-ID order.

F-X134 runs first because it repairs the hosted Python binding gate inherited
from the completed story inventory work. F-X133 is independent and follows the
completed F-X131 and F-X132 namespace-retention corrections.

F-271, F-272, and F-275 can begin from the completed common story,
relationship, and annotation foundations. F-273 follows F-272 so endnotes
reuse the complete rich-note content surface while retaining an independent
identifier namespace. F-274 then composes both note families with the section
policy completed by F-269.

F-276 follows F-271 through F-275 because full-story import must account for
every newly modeled related-story dependency and conflict. F-277 follows
F-276 so public-created glossary entries and building blocks use the completed
transactional import and remapping policy.

## Definition of done for this sprint

- The same rich subtree can be authored in every header and footer variant and
  reopens with the correct part-scoped relationships.
- Rich footnotes and endnotes support public creation, editing, ordering, and
  removal, retain independent identities, and match the pinned placement and
  round-trip evidence.
- Note separators, continuation stories, custom markers, number formats,
  starts, placement, and section restart policy produce the pinned result
  without disturbing unrelated numbering.
- Bookmarks and supported paired ranges work in every valid story and nested
  container, retain exact endpoints, and reject invalid crossings atomically.
- Full-story fragment import deterministically remaps every supported package
  dependency under conflict and leaves no dangling identity or relationship.
- Public-created glossary entries and building blocks retain classification,
  behavior, rich content, relationships, and unsupported siblings after
  insertion and reopen.
- Story hyperlink snapshots inventory namespace scopes once per physical
  source and pass the hosted Python linear-scaling gate without weakening its
  bound.
- The full workspace, deterministic hash harness, pinned differential oracles,
  package gates, bindings, and documentation checks pass without unexplained
  output changes.
