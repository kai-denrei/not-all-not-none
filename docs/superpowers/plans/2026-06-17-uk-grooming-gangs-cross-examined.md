# UK Grooming Gangs, Cross-Examined — Implementation Plan

> **For agentic workers:** This plan is executed via a Workflow orchestration
> (draft → adversarial-verify → assemble → review). Steps use checkbox syntax.

**Goal:** Ship `grooming-gangs.html` — a standalone, page-21-methodology case
study cross-examining *The Rape Gang Inquiry Report* — and add a "UK Grooming
Gangs · Cross-Examined" tab to the cross-section nav on all 25 existing pages.

**Architecture:** One self-contained HTML file (inline `<style>`, no JS/build),
reusing the `denmark-data.html` class vocabulary plus three new local classes
(`.quote-card`, `.tier-grid/.tier-card`, `.disambig`). Content drafted by
parallel section-agents from the verified extraction
(`docs/research/rape-gang-report-extraction.md`), each fragment adversarially
fact-checked against the PDF before assembly. Nav propagated by a single uniform
string insertion (every page ends its nav with `Denmark · Honest Data</a></nav>`).

**Tech Stack:** Static HTML5 + CSS. No dependencies. Sources of truth:
`docs/research/rape-gang-report-extraction.md`, the PDF (page-cited), and the
spec `docs/superpowers/specs/2026-06-17-uk-grooming-gangs-cross-examined-design.md`.

---

## File structure

- **Create:** `grooming-gangs.html` (repo root).
- **Modify (nav only, 1 line each):** all 25 pages carrying `class="top-nav"` —
  `nuance-2026.html`, `unity-and-diversity.html`, `denmark-data.html`,
  `fault-lines/index.html`, `fault-lines/01..21-*.html`.
- **Reference (read-only):** `docs/research/rape-gang-report-extraction.md`,
  `denmark-data.html` (style donor), the PDF.

## Class vocabulary contract (agents use ONLY these)

Existing (copied verbatim from denmark-data.html `<style>`): `.container`,
`.breadcrumb`, `.eyebrow`, `h1/.subtitle`, `.status-row/.status-badge`,
`.section-title`, `.section-sub`, `.one-sentence` (em=accent), `.headline-row/
.headline-cell/.headline-num/.headline-label` (dark stat band), `.friction-grid/
.friction-card` (+ `.uk` flag variant), `.tbl-inventory` (th/td/code/a),
`.cross-exam` (`.ce-lead`, `.ce-side`, `.strain-list/.strain/.strain-claim/
.strain-expose`), `.caveat-list/.caveat-item`, `.sources-list/.source-item`
(`.src-type/.src-cite/.src-method/.src-link` + new `.src-caveat`), `.method-box`,
`footer`.

New (defined in this page's shell, documented for agents):
- `.quote-card` — survivor testimony. White bg, left border `#5e2a3b`, large
  italic quote, `.qc-attrib` line with page cite. `.qc-warn` optional amber tag
  for unverified testimony.
- `.tier-grid` / `.tier-card` — provenance ladder. Four colored cards:
  `.t-statutory` (green), `.t-extrapolation` (red), `.t-name` (amber),
  `.t-contested` (grey). Each lists figures + page cites.
- `.disambig` — two-column "official vs this document" comparison (reuse
  `.tbl-inventory` styling; `.disambig` just adds a header treatment).

## Tone & integrity rules (every agent, every section)

1. Every figure/quote carries a page cite (report) or named official source.
2. Contested figures attributed ("the report claims…", "Lord Pearson's
   extrapolation…") — never stated as established fact.
3. Carry the report's own caveats through; never strip them.
4. Keep "Asian" / "Pakistani" / "Muslim" distinct (the report flags the
   conflation, p.108).
5. Both failure modes named: inflation/monolith error AND denial/cover-up error.
6. No invented citations; every `<a href>` resolves to a real URL.

---

## Task 1: Build the page shell

**Files:** Create `grooming-gangs.html`.

- [ ] **Step 1:** Copy the full `<style>` block from `denmark-data.html` (lines
  7–138) verbatim into the new file's head. Set `<title>Grooming Gangs — the
  report, cross-examined / グルーミング・ギャング — 検証</title>`.
- [ ] **Step 2:** Append the three new CSS classes (`.quote-card`/`.qc-attrib`/
  `.qc-warn`, `.tier-grid`/`.tier-card`/`.t-*`, `.disambig`) to the style block,
  matching the existing palette (bg `#faf9f6`, ink `#17161a`, accent `#4a7bb8`,
  warm `#faf7ef`, amber `#fef6e1`/`#d4a03a`, UK maroon `#5e2a3b`).
- [ ] **Step 3:** Add `<body><div class="container">` then the 5-tab nav with the
  new tab active:
  `…<a href="denmark-data.html" class="nav-tab">Denmark · Honest Data</a><a href="grooming-gangs.html" class="nav-tab active">UK Grooming Gangs · Cross-Examined</a></nav>`
- [ ] **Step 4:** Add breadcrumb, `<header>` (eyebrow "Empirical case ·
  Cross-examination", h1 bilingual title, subtitle, status-row badge
  `empirical case · cross-examined · Phase 1` + date `2026-06-17`), and a
  `.one-sentence` thesis line.
- [ ] **Step 5:** Add 8 empty section stubs (each `<h2 class="section-title"
  id="…">` + `<p class="section-sub">`) as drop targets, then `<footer>` (links
  back to Nuance Hub + Unity & Diversity + the official-inquiry gov.uk page) and
  close tags.
- [ ] **Verify:** `python3 -c "import html.parser…"` structural balance check (or
  tidy); open in browser; confirm nav renders 5 tabs, new one active.

## Task 2: Draft the 8 content sections (parallel agents → fragments)

Each agent reads `docs/research/rape-gang-report-extraction.md` + the class
contract + integrity rules, reopens the cited PDF pages to confirm its
figures/quotes, and returns a ready-to-drop HTML fragment (inner content of one
section, no `<html>/<head>`). Sections:

- [ ] **2.1 What this document actually is** — `.disambig` table (official
  Longfield inquiry vs Lowe report), provenance prose, the "rape gang" vs
  "grooming gang" terminology note, the site's method statement.
- [ ] **2.2 The report's case, uncensored** — faithful steelman: thesis, the
  headline figures as the report presents them, the "8 theological aspects"
  argument, 4–6 survivor `.quote-card`s. No softening, no rebuttal yet.
- [ ] **2.3 The figures, sorted by what they rest on** — `.tier-grid` (statutory /
  extrapolation / name-analysis / contested) + a `.tbl-inventory` figure ledger
  (figure · what it measures · provenance · page).
- [ ] **2.4 Cross-examination Ⅰ — the numbers** — `.cross-exam` with `.ce-side`
  "Where the report's quantification strains" (250k extrapolation, name-analysis
  ≠ religion, convictions ≠ offender pop) AND `.ce-side` "Where the denial
  position strains" (the deflection that it's negligible / equally distributed).
- [ ] **2.5 Cross-examination Ⅱ — religion, culture, integration** — `.cross-exam`
  two-sided: cross-examine the Islam-as-cause monolith using the report's own
  p.108/p.117 caveats, Taj Hargey, Sikh self-defence; THEN cross-examine the
  refusal-to-look error (p.30 "that's racist"). Cross-links to fault-lines
  04/14/15. This is the not-all-not-none core.
- [ ] **2.6 The institutional failure** — the corroborated core (police, councils,
  NHS, CPS, "fear of being called racist", two-tier protection); note where
  official sources (Casey, Jay, Telford) agree.
- [ ] **2.7 Caveats & coverage** — `.caveat-list`: advocacy-report status,
  unverified testimony, redacted names, official inquiry pending (~2029).
- [ ] **2.8 Sources** — `.sources-list` of `.source-item` cards: the PDF
  (page-cited), Casey 2025 audit, Jay 2014, Telford 2022, ONS recorded crime,
  gov.uk official inquiry, Hansard 14 May 2019. Real URLs only.

## Task 3: Adversarial verification (per fragment, pipelined)

- [ ] For each drafted fragment, a skeptic agent reopens the specific PDF pages
  and checks: (a) every figure/quote matches the report exactly; (b) every claim
  is attributed; (c) no invented citation; (d) both-directions present where
  required (2.4, 2.5). Returns `{ok, fixes[]}`. Apply fixes; re-draft if a
  fragment fails hard.

## Task 4: Assemble + propagate nav

- [ ] **Step 1:** Drop each verified fragment into its section stub in
  `grooming-gangs.html`.
- [ ] **Step 2:** Propagate nav. For the 3 root pages, replace
  `Denmark · Honest Data</a></nav>` with
  `Denmark · Honest Data</a><a href="grooming-gangs.html" class="nav-tab">UK Grooming Gangs · Cross-Examined</a></nav>`.
  For the 22 fault-lines pages, same but href `../grooming-gangs.html`.
- [ ] **Verify:** `grep -c 'nav-tab' <file>` returns 5 anchors on every page;
  `grep -L 'grooming-gangs' …` returns nothing; each fault-lines tab uses `../`.

## Task 5: Whole-page review + fix

- [ ] Review agent(s): coherence/voice across sections; both-blades balance;
  unattributed-claim sweep; "Asian/Pakistani/Muslim" precision; HTML validity;
  every nav correct. Apply fixes. Loop until clean.
- [ ] **Final verify:** open `grooming-gangs.html` in a browser; confirm all 8
  sections render, tiers/quote-cards/cross-exam styled, nav 5-tab active-correct,
  footer links resolve. Report evidence (not assertions).

---

## Self-review (against spec)
- Spec §4 sections 1–8 → Tasks 2.1–2.8 ✓
- Spec §1 disambiguation → Task 2.1 ✓
- Spec §3 nav propagation → Task 4 Step 2 + verify ✓
- Spec §5 integrity rules → "Tone & integrity rules" block, enforced per-agent ✓
- Spec §6 house style → Task 1 (copied CSS) + class contract ✓
- Spec §8 verification → Tasks 1,4,5 verify steps ✓
- No placeholders; new classes defined before use; nav string exact-matched.
