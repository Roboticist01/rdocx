# F-X149, Word fixture and workflow acceptance gate

**Status**: approved
**Sprint**: S82
**Size**: L
**Depends on**: F-X144, F-X145, F-X146, F-X147, F-X152

## Problem

`crates/rdocx-py/tests/test_python_docx_parity.py:633` defines 17 identity attribute rows and omits the reporter's eighteenth control row with no attribute. Its producer matrix at line 652 has 11 rows, but the current cases do not establish every operation result from the reporter's script. `docs/hld/12-testing-strategy.md`, "The Word corpus", describes the matrices without a complete reporter workflow or the original attachment as a repeatable gate.

## Spec reference

- `docs/hld/04-opc-and-packaging.md`, "Package integrity".
- `docs/hld/08-rendering-spec.md`, "The renderer's input".
- `docs/hld/10-bindings-spec.md`, "Python API shape" and "CLIs".
- `docs/hld/12-testing-strategy.md`, "The Word corpus" and "Binding tests".
- `docs/hld/14-development-backlog.md`, "F-X149, Word fixture and workflow acceptance gate".

## Approach

Extend the existing Python parity entrypoint to enumerate the missing control row, exercise every identity and producer cell through its required operations, and assert observable saved structure and comparison results against pinned `python-docx==1.2.0` where that oracle can read them. Run the reporter's 12-step report workflow from DOCX through CLI and Python editing to deterministic PDF. Fetch the original attachment into ignored test storage with SHA-256 `d05f9c753c00eb804c6e345126ef7a1f7a4fc635d2c9b653b829922030cd875e`, or use a local file with that digest. The reporter's script archive has SHA-256 `e448d27c8ed4b060749b1b0cbd2c833cd2e4445d49cda9ad34069b8e80bb7f0c`. Do not check in binary fixtures.

## Rejected alternatives

- Repeating the S78 matrix tests without a complete workflow leaves the S82 acceptance gap.
- Treating a source-built approximation as the attached file would misstate reporter coverage.

## Test plan

| Category | Test | Asserts |
|---|---|---|
| differential | `test_issue_158_word_fixture_acceptance` in the existing Python parity entrypoint | All 18 identity rows and 11 producer rows run the declared operations and agree with pinned structural references. |
| integration | `test_issue_158_complete_word_workflow` in the existing Python entrypoint | The same report survives Python save, CLI actions, reopen, deterministic render and comparison. |
| gate | Backlog differential test gate | The report workflow and both matrices pass against pinned outputs, with attachment evidence explicitly distinguished from source-built coverage. |

## HLD impact

- `docs/hld/12-testing-strategy.md`

## Risk routing

- Layout and rendering: read `docs/hld/08-rendering-spec.md`. Use deterministic bundled fonts and verify any render baseline deliberately.
- External oracle: read `.claude/skills/differential-testing.md`. Pin and record python-docx, Word or LibreOffice versions actually used, compare parsed structure and state raster tolerance.
- PyO3 test changes: read `docs/hld/10-bindings-spec.md`. Run the isolated Python suite and the WASM check. Exclude Python binding crates from workspace tests.
- Any parser, serialiser or public API repair discovered during the gate earns its matching risk row before editing.

## Hash harness

Expected unchanged. An observed delta blocks completion until separately declared and reviewed.

## Implementation checklist

- [ ] Identify the eighteenth identity row and assert the 18 by 7 and 11 by 8 cell counts.
- [ ] Add mutation-sensitive assertions and pinned structural references for every operation.
- [ ] Exercise one complete Python, CLI and deterministic render report chain.
- [ ] Run the reporter's original attachment and record its digest and results.
- [ ] Run focused differential checks, scoped verification and microscope to zero findings.

## Open questions

None. Issue 158 supplies the fixture and acceptance scripts. The eighteenth identity row is the no-attribute control.
