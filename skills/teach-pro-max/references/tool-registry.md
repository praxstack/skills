# Tool registry — teaching artifact production

A **catalogue**, not a router. `teacher` (or the host's resolved teaching
engine) chooses the medium; this file lists what exists, what it is good for,
and the operating cautions. It is not the embedded 38-tool registry: that one
applies only when the embedded fallback engine is active.

Verify current licences, versions and availability before adoption. The notes
below are cautions, not a licence grant. Pin versions in the project and record
engine eligibility and telemetry configuration.

## Decision order

1. Educational effectiveness.
2. Correctness and inspectability.
3. Meaningful interaction (model controls must recompute the model).
4. Accessibility and usability.
5. Visual quality.
6. Reliability, portability, maintainability, cost.

A video engine is not an interactive teaching engine. Use both only when each
does a different job.

## Browser, text and interaction

| Job | First choice | Also | Notes |
| --- | --- | --- | --- |
| Text + interaction | Single-file HTML/CSS/JS | React + Vite, Svelte, Astro | Single file is the default; inline CSS/JS |
| Typed interactive state | TypeScript | — | Worth it when state machines get complex |
| Motion / timelines | GSAP or Motion | Anime.js, Web Animations API, CSS | Deterministic, seekable timelines for step inspection |
| Vector motion | Lottie | SVG/CSS animation | Keep a reduced-motion path |

A stock Vite build is ESM and will not load from `file://`; use an inlining
step or document a local server path.

## Mathematics and science

| Job | First choice | Also | Notes |
| --- | --- | --- | --- |
| Typesetting | Hand-typeset HTML per the project notation rules | KaTeX, MathJax | Vendor locally; a vendored font/file still counts as a second file unless inlined |
| Symbolic checking | SymPy | hand derivation | Verify, do not decorate |
| Numeric checking | NumPy/SciPy | plain Python `fractions` | Label approximation vs exactness |
| Function plots | Custom SVG/canvas from verified formulas | D3, Observable Plot | Same formula must drive figure and verifier |
| Geometry/calculus labs | Custom canvas/SVG | JSXGraph, Desmos API, GeoGebra | External APIs need network and terms checks |
| Expression parsing | math.js | — | Validate inputs at the boundary |

## Data and diagrams

| Job | Use | Notes |
| --- | --- | --- |
| Statistical charts | D3, Observable Plot, Plotly, ECharts, Chart.js, Vega-Lite | Choose by data shape and interaction |
| Explanatory diagrams | SVG; Mermaid for relationship graphs | SVG gives exact control and accessibility |
| Node editors | React Flow | Only when editing the graph is the lesson |
| Hand-drawn diagrams | Excalidraw | Export SVG for the lesson |
| Graph layouts | Cytoscape.js, Graphviz | Verify labels and contrast |

## Spatial, simulation, coding

| Job | Use | Notes |
| --- | --- | --- |
| 3D | Three.js, React Three Fiber | Only when spatial understanding is the point |
| Creative coding | p5.js | Good for simulations and generative visuals |
| Physics | Matter.js, Rapier, custom JS | State assumptions and simplifications |
| Heavy computation | Web Workers, WebAssembly | Keep the UI responsive |
| Code playgrounds | Monaco, CodeMirror, Sandpack | Sandboxed execution only |
| Python in browser | Pyodide | Large download; label the cost |
| Full sandboxes | WebContainers | Check hosting and terms |

Never execute learner input with unrestricted OS access.

## Animation and video engines

| Engine | Licence / status | Use | Cautions |
| --- | --- | --- | --- |
| HyperFrames | npm package; **terms must be checked, not assumed** | HTML/GSAP compositions, deterministic seek | Do not classify as MIT/OSS without the current terms |
| Manim Community | MIT | Mathematical animation, proofs, transformations | Python + LaTeX; choose CE or GL, never mix APIs |
| ManimGL | MIT (3b1b) | 3Blue1Brown-style scenes | API differs from CE |
| Remotion | Proprietary/source-available; free eligibility is headcount- and organization-dependent (roughly up to three people, with conditions), then paid | React-driven video, player embeds | Record eligibility for the actual project; verify official pricing |
| Revideo | MIT | Generator-based TS scenes, parallel rendering | Repository moved to `midrender/revideo`; renders send PostHog telemetry unless `DISABLE_TELEMETRY=true` — set it |
| Motion Canvas | MIT | Narrated explainer animation, editor + player | Vite-based |
| Editly | MIT | Declarative assembly over ffmpeg | No browser needed |
| MoviePy | MIT | Python cuts/compositing | Slower than direct ffmpeg |
| FFmpeg | LGPL/GPL build-dependent | Encoding, compositing, concat, subtitles | Check the build's licence |
| Blender | GPL | Complex 3D scenes | Heavy; overkill for most lessons |
| Slidev | MIT | Interactive slide decks | CLI export is PDF/PPTX/PNG; video uses the separate recording workflow |

Generative video APIs change availability and pricing; verify before relying on
one. Do not use generative video to simulate a proof, equation or algorithm
where exactness matters.

## Narration and audio

| Job | Use | Notes |
| --- | --- | --- |
| Narration | Local TTS if available | Verify availability; captions + transcript required |
| Paid TTS API | Only with the learner's authorization | Never require a model-provider key for the lesson to work |

## Design and critique skills

Consult before a visual build and run at least one critique pass on a new
template; record the findings and the fixes. Install per the host's skill layout
(`npx skills add <owner/repo>` where supported).

| Skill | Source | Use |
| --- | --- | --- |
| frontend-design | `anthropics/skills` → `skills/frontend-design/SKILL.md` | Distinctive visual direction, type and palette |
| impeccable | `pbakaus/impeccable` (`npx impeccable install`) | `/polish`, `/audit`, `/typeset`, `/distill` critique |
| ui-ux-pro-max | `nextlevelbuilder/ui-ux-pro-max-skill` | Searchable styles, palettes, type pairings, UX patterns |
| emilkowalski/skills | `emilkowalski/skills` | Micro-interactions, motion timing, prototyping, DESIGN.md |
| web-design-guidelines | `vercel-labs/agent-skills` → `skills/web-design-guidelines/SKILL.md` | Interface audit and accessibility review |
| ux-ui-agent-skills | `plugin87/ux-ui-agent-skills` | Design systems, DTCG tokens, WCAG 2.2 gates |
| shadcn skill | `shadcn-ui/ui` → `skills/shadcn/SKILL.md` | Component and token conventions |
| wshobson/agents | `wshobson/agents` | Component and design catalog |

## Skills and upstream registries

Read the actual `SKILL.md` and its references before applying a skill; a name is
not evidence of use.

- `praxstack/skills` — `teacher` (pedagogy), `teach-pro-max`, `frontend-design`,
  `web-artifacts-builder`, `webapp-testing`, `algorithmic-art`,
  `canvas-design`, `theme-factory`
- `mattpocock/skills` — research, prototype, codebase-design, spec/implement,
  TDD, code review, diagnosing bugs, scaffolding exercises
- `adithya-s-k/manim_skill` — manim-composer, manimce-best-practices,
  manimgl-best-practices
- `heygen-com/hyperframes/tree/main/skills` — hyperframes, CLI, registry,
  media-use, slideshow
- `remotion-dev/skills` — create, docs, interactivity, render, multimedia,
  captions, studio, licence
- `ManimCommunity/manim`, `3b1b/manim`, `midrender/revideo`,
  `motion-canvas/motion-canvas`, `mifi/editly`, `Zulko/moviepy`

## Default delivery shape (recommendation; the gate owns the requirements)

1. Standalone HTML with inlined CSS/JS and no external resources — first choice.
2. Static build with bundled local assets (documented server if ESM).
3. Runnable application with pinned dependencies and documented commands.

Every substantial tutorial ships with a README, sources, licence notices for
redistributed dependencies, and the evidence for the checks that actually ran.
