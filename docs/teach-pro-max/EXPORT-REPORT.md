# Public source export

Source repository: `praxstack/skills-and-personas`.
Source commit: `4753585b0eb9a2da915f9f450c54f8b02724ae5e`.
Export branch: `publish/teach-pro-max-20261024` in `praxstack/skills`.

The export reads only committed Git blobs under `skills/teacher` and
`skills/teach-pro-max`. It copies 1,566 files totaling 16,745,318 bytes: 762 teacher
files and 804 wrapper/compatibility files. No runtime or source edits were made
inside either copied tree. The file set, each SHA256 and every executable/symlink
Git mode were checked against the source export manifest after running tests.

[SOURCE-MANIFEST.json](SOURCE-MANIFEST.json) lists the source commit, Git blobs,
Git modes, byte counts and SHA256 for every member. Its SHA256 is
`c9eba845213d5793b377f92f2795d95ed95580bd9b0ef138dd4a2af59301138a`.
The manifest and this report are outside the copied skill trees.

## Portable checks

All six commands exited 0. Local execution used Python 3.13.17 and v26.12.1,
with PyYAML 6.0.3 and `Python 3.13.17DONTWRITEBYTECODE=1`.
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
- Node publish/template/report regressions: 18 tests passed, 0 skips.

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
