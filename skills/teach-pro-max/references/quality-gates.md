# Quality gates — interactive tutorial delivery

**This is the canonical checklist.** Agent files and workspace gates may add
stricter checks, but they reference this file instead of restating it. Where two
gates differ, the stricter applies.

Two states only:

- **draft** — at least one required check is unrun or failed. It may be shared
  only as a draft, with the unrun/failed list. Never call it finished or delivered.
- **ready** — every applicable required check **passed** with evidence. Only
  ready may be described as delivered. An unrun or failed gate is a blocker,
  not a disclosure.

## 1. Correctness and sources

- Every numeric or computational claim is recomputed by a script; use exact
  arithmetic where applicable, and state tolerances, assumptions and
  approximation error where exactness does not apply.
- Non-numeric claims are verified by a source or a derivation, not by a script.
  Mathematical claims are proved for every `n`, not inferred from three terms.
- No invented source, quotation, benchmark or API behaviour. Version-specific
  claims checked against the installed version.
- Figures derive their geometry from the same formula the verifier tests, or
  the verifier parses the figure back. A screenshot is not a numeric check.

## 2. Functional

- Every control exercised: model controls at minimum, maximum and an interior
  value; navigation, theme, playback, reveal and accessibility controls judged
  by their stated purpose (a theme switch need not recompute a model, but it
  must switch the theme).
- Resets restore state; empty, boundary, invalid and extreme inputs do not
  break the page.
- Controls change what they claim to change; a **model** control that only
  restyles itself is a defect.
- Zero uncaught console errors on load and after every interaction; no failed
  asset loads.

## 3. Self-contained delivery

- Default single-file lesson: **byte check first** — every essential resource
  is embedded. Search every loading mechanism: `<link rel="stylesheet">`,
  `@import`, `<script src>`, `<img src>`, `srcset`, CSS `url(…)`, iframes,
  `fetch`/XHR and runtime-asset code. Navigational `<a href>` is allowed (it
  loads nothing until clicked). Then open the file with only the delivered HTML
  available and the network blocked, and confirm it renders styled.
- A richer stack is allowed only when the learner asked for it or a written
  justification names a learning gain the single-file version cannot deliver.
  The exception carries every no-CDN/no-telemetry/no-provider-key/licence rule;
  dependencies are pinned; the primary path **and** the offline/simplified path
  are both verified, and the fallback must cover the essential objective.
- Record the justification and both results. Inject themes before verification
  and record the hash of the delivered bytes; verified bytes equal delivered
  bytes.
- Format-specific: for narrated video, verify playback, captions and a complete
  transcript. HTML lint and viewport checks do not establish video quality.
- Redistributed dependencies and assets keep their required licence notices.

## 4. Visual

- Screenshots inspected at 1440, 1024 and 390 px wide, in every reachable theme
  state; `scrollWidth == clientWidth` measured at 390 and 320 px.
- Use device emulation or an iframe: `--window-size` alone can crop a wider
  layout and hide overflow.
- No clipped or overlapping text, invisible labels, broken formulas, layout
  shifts, unreadable controls or excessive density.
- Colour carries one meaning per hue; a variable's identity is consistent
  across representations.
- Typography has a deliberate hierarchy; the reading measure is comfortable.

## 5. Accessibility

- Measured contrast at least 4.5:1 for body text in every reachable theme state,
  including highlighted cells and controls.
- Keyboard-reachable controls with visible focus; labelled inputs; logical focus
  order.
- Reduced motion honoured; no required drag-only interaction.
- Every essential visual has a textual equivalent; narrated media has captions
  and a transcript.
- Semantic landmarks and headings; tables have captions and scopes; figures
  have captions; SVGs have names.

## 6. Pedagogy

- The objective is stated and the progression serves it.
- Missing-rung check at every transition: a learner without the concept can
  justify why the next step follows.
- Symbols, indices, units and conventions defined before use. A concrete
  example is required; it is numeric when the subject is quantitative.
- Misconceptions named and countered; simplifications labelled.
- Leakage is defined by visibility before interaction, not byte presence: the
  protected answer may exist in the file, but not in headings, captions, alt
  text, `aria-label`, `title`, default-open `<details>`, initial DOM text, hints
  or previews before the learner commits.
- Practice keeps the spoiler guard; a transfer check is offered, not required.
  Reading the page is not evidence of learning; say what remains untested.

## 7. Release blockers

Any one of these blocks delivery regardless of the rest:

- wrong core explanation or result;
- misleading visualization;
- missing reasoning step that makes the result unjustified;
- non-functional essential control;
- unrequested solution spoiler;
- unusable layout or unreadable text;
- missing essential asset;
- serious accessibility failure in a core interaction;
- fabricated source, benchmark or verification claim;
- a required check left unrun or failed while the artifact is called ready.

## 8. Evidence record

Write down, in the deliverable's README or report:

- `State: draft | ready` and `Unrun or failed required checks: none | <list>`;
- each required check with pass / fail / not-run and the command or observation;
- for a richer stack: the justification, primary-path evidence, fallback-path
  evidence and the delivered-bytes hash;
- screenshots viewed and the defects fixed (file paths);
- contrast measurements and viewport results;
- the licence/telemetry configuration for any adopted engine;
- what could not be executed or verified in this environment;
- learner evidence that does not exist yet (e.g. transfer untested).

A project may specialize this checklist. The project gate wins where it is
stricter; never weaken it to make a delivery pass.
