# CLAUDE.md — a module of the Interactive Teaching Platform

This repository is one module (a single `index.html`): **Autonomic Nervous System** (module key `autonomic`, storage prefix
`an_`, build `1.0`). Medical Physiology for dental students (Faculty of Dentistry). Built 2026-11-11 from
the course lecture "Autonomic N.S. Physiology" (Concise medical physiology, pp. 15–31) as a VERY condensed, high-yield module,
with the app code of `third-year-med/Granulomatous-and-parasitic-diseases`. Served at
`https://third-year-med.github.io/third-year-med-autonomic-nervous-system/` (GitHub kept the owner prefix in the name).

The platform's decisions, the checklist for modules, the deployment steps, the testing workflow and the lessons learned are
in the platform repository: `third-year-med/Interactive-pathology-platform` → `CLAUDE.md` and `docs/HANDBOOK.md` (§4.2.5;
rebuilds: `docs/REBUILD.md`).

- The course data in `index.html` is encrypted with this module's OWN content key, which lives only in the user's Code.gs
  (`CONTENT_KEYS.autonomic`; env `AN_CONTENT_KEY` in a session). Never commit a key or an unencrypted copy of the course.
- The `<script id="platform-nav">` block is maintained in the platform repo (`modules/platform-nav.js`) and written here
  with `tools/module-release.js refresh` — do not edit it by hand.
- Stable IDs: topics t01–t10 (organisation; ganglia and outflows; sympathetic; parasympathetic; salivary glands;
  acetylcholine; noradrenaline and adrenal medulla; receptors; drugs; integration) — NO practical topic; sections sNNMM
  (24); questions q001–q133 (5-option single-best-answer); cases c01–c08; lecture figures `fig_*` (22, credit "Course
  lecture … p. N") + the original diagram `fig_saliv`; flowcharts `dx_alarm`, `dx_na`.
- Delivered to the user directly, never committed: `autonomic-pictures-elsevier2.json` (21 textbook figures from the user's .ppt, keys
  `an-elsevier2-sNN` = slide NN, © Elsevier, imported in ✏️ Edit master draft; where one duplicates a lecture figure BOTH are kept — the
  user chooses later).
- Module-local changes (in this page only, not shared patches): Revision → 🖨 Print asks "Questions only" (compact, two columns, no
  answers) or "With answers"; the print header says "Interactive Physiology Teaching Platform". Question difficulty is 1–3 (cases 1–5).
- Test changes on the real page with the platform repo's e2e test "Autonomic Nervous System module (autonomic)"
  (`AN_CONTENT_KEY` in the environment) and `node test/module-smoke/smoke.js` before pushing.
