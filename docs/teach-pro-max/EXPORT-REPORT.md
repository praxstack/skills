# Public source export

Source repository: `praxstack/skills-and-personas`.
Source commit: `51e1031918a5d9d4441b9b5265a8a9ef1746500e`.
Export branch: `publish/teach-pro-max-20261024` in `praxstack/skills`.

The export reads only committed Git blobs under `skills/teacher` and
`skills/teach-pro-max`. It copies 1,566 files totaling 16,747,355 bytes: 762 teacher
files and 804 wrapper/compatibility files. No runtime or source edits were made
inside either copied tree. The file set, each SHA256 and every executable/symlink
Git mode were checked against the source export manifest after running tests.

[SOURCE-MANIFEST.json](SOURCE-MANIFEST.json) lists the source commit, Git blobs,
Git modes, byte counts and SHA256 for every member. Its SHA256 is
`de73e8fc8d31a182447f9fd1479fddb3238ea6d4aeddcfa47645ae4fb2571bdd`.
The manifest and this report are outside the copied skill trees.

## Portable checks

All six commands exited 0. Local execution used Python 3.13.17 and Node v26.12.1,
with PyYAML 6.0.3 and `PYTHONDONTWRITEBYTECODE=1`.
Full command arguments and output are in
[PORTABLE-TEST-RESULTS.json](PORTABLE-TEST-RESULTS.json).

- Teacher vendor verification: 16 vendored skills, 6 copied files, 6 native
  skills and 0 problems. The verifier discloses 12 vendored skills with recorded
  local changes; this export preserves those source bytes.
- Wrapper distribution verification: 759 embedded engine files match the
  embedded source manifest. The verifier checks the wrapper name, not its full
  content; the external export manifest hashes the whole wrapper tree.
- Teacher core: 71 tests, 3 expected standalone-copy skips. The skips are repo
  lint and 2 site-course fixtures absent from this repository.
- Discovery: 8 tests passed.
- Manim resolution: 9 tests passed using trusted import-only controls; no authored
  scene was rendered.
- Node publish/template/report regressions: 20 tests passed, 0 skips.

The CI workflow pins the same checkout action as the primary repository and
installs PyYAML 6.0.3 in an isolated environment before these portable checks.
Full container and sandbox qualification remains in the primary repository.
These portable results establish no new browser playback, media isolation,
subjective listening or learning claim.

## Publication glue

The README documents `$teach-pro-max`, visual explanation before optional
practice, consent for durable learner state, and installation of both skills.
The added marketplace plugin references both exact folders. A wrapper-only
install retains the embedded compatibility fallback. Existing Anthropic skills,
plugin entries, marketplace ownership and licenses remain in place.

This preparation report records local verification. Remote CI, PR review,
merge, skills.sh discovery and post-merge installation are separate release steps.

The broad `git diff --check` reports pre-existing whitespace in the exact exported
source and vendored licenses. Those bytes remain unchanged. Publication glue passes
a scoped whitespace check; workflow YAML parses with PyYAML 6.0.3. Committed Git
blob IDs, modes and membership also match all 1,566 source manifest entries.

## Review round 1

The exact source export includes all four PR1 fixes, with primary RED/GREEN
controls and the separate Python 3.11 import repair documented in
[REVIEW-ROUND-1.md](REVIEW-ROUND-1.md). The transcript repair belongs only to the
primary repository. The secondary portable suites were rerun after resynchronizing
the teacher and wrapper trees. Full bounded narrated regressions remain a primary
release check, separate from this portable export.

The initial round-1 portable rerun exposed a Node-only formula-control regression.
[The failing command output](PORTABLE-ROUND-1-INITIAL-FAILURE.json) is preserved.
The corrected source skips entity decoding for entity-free text; the same formula
assertion and all six portable commands pass after correction.
