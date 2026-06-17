# Design — UK Grooming Gangs, Cross-Examined

**Date:** 2026-06-17
**Project:** not-all-not-none / nuance-2026
**New artifact:** `grooming-gangs.html` (standalone page) + nav-tab added to all existing pages

---

## 1. Purpose

Process *The Rape Gang Inquiry Report* (the privately crowdfunded, non-statutory
report chaired by Rupert Lowe MP, released June 2026) and add it to the site as a
standalone empirical case study. Quantify what can be quantified, attribute every
contested figure to its source, and apply the site's signature page-21 methodology:
**present each position uncensored, then cross-examine where it strains — both
directions.**

The case fits the site's themes of integration and the moderate-vs-extremist
distinction. The site is called *not all, not none*; that distinction is the
explicit analytical axis of the page.

### Critical disambiguation (load-bearing)

The downloaded PDF is **NOT** the official government inquiry referenced at
`gov.uk/government/speeches/independent-inquiry-into-grooming-gangs`.

| | Official inquiry | This document |
|---|---|---|
| Name | Independent Inquiry into Grooming Gangs | The Rape Gang Inquiry Report |
| Chair | Baroness Anne Longfield | Rupert Lowe MP |
| Status | **Statutory**, full powers | **Non-statutory**, "lacked statutory powers" |
| Funding | £65m government | Privately crowdfunded (~20,000 donors) |
| Announced | Dec 2025 | — |
| Reports | ~2029 (begins 2026) | Released June 2026 |

The page must state this plainly up front. Treating an advocacy report's
extrapolated figures as settled government findings would be a factual and
credibility error for this site.

---

## 2. Framing decisions (locked)

1. **Treatment:** Cross-examine the report itself — it is the named subject.
   Present its claims faithfully and in full, then separate what official sources
   (Casey 2025 audit, Jay/Rotherham, Telford, ONS) corroborate from what is
   extrapolation or contested sourcing. Honest about provenance throughout.
2. **Placement:** New standalone page + nav tab, modelled on `denmark-data.html`.
3. **Analytical center of gravity:** Two co-equal cross-examination spines —
   (a) data-integrity / provenance, and (b) religion-culture-integration /
   moderate-vs-extremist.

---

## 3. File, title, nav

- **Filename:** `grooming-gangs.html` (repo root, alongside `denmark-data.html`).
- **Bilingual title (house style):**
  `Grooming Gangs — the report, cross-examined / グルーミング・ギャング — 検証`
- **Status badge:** `empirical case · cross-examined · Phase 1` · date `2026-06-17`.
- **Nav tab label:** `UK Grooming Gangs · Cross-Examined`
  (middle-dot separator to match siblings, e.g. "Denmark · Honest Data").
- **Nav update:** The cross-section `<nav class="top-nav">` currently has 4 tabs
  (Nuance Hub, Unity & Diversity, Fault Lines, Denmark · Honest Data). Add a 5th
  tab pointing to `grooming-gangs.html` on **every page that carries the
  cross-section nav**. First step of implementation is to enumerate those pages
  via grep (`grep -l 'class="top-nav"' *.html fault-lines/*.html`) rather than
  assuming a count. Expected set:
  - Root-level pages (`nuance-2026.html`, `unity-and-diversity.html`,
    `denmark-data.html`): href `grooming-gangs.html` (no prefix).
  - `fault-lines/index.html` + `fault-lines/01..21-*.html`: href
    `../grooming-gangs.html`.
  - On `grooming-gangs.html` itself the new tab carries `class="nav-tab active"`
    and the previously-active tab (if any) is de-activated; on all other pages the
    new tab is inactive. Match each file's existing nav href convention exactly
    (root pages use bare filenames, fault-lines pages use the `../` prefix).

---

## 4. Page structure (sections)

Mirrors the `denmark-data.html` rhythm: why-this-exists → the material → the
numbers → cross-examination → caveats → sources.

1. **What this document actually is** — disambiguation table/prose (see §1).
   States provenance, the site's method, and the deliberate "rape gang" vs
   "grooming gang" terminology choice.

2. **The report's case, uncensored** *(steelman half)* — faithful presentation of
   its core thesis, headline figures, the religious-causation argument
   ("8 theological aspects of Islam"), and survivor testimony rendered as
   quote-cards. No softening. This is the "present the position fully" half.

3. **The figures, sorted by what they rest on** *(data-integrity spine)* — every
   headline number tagged by provenance tier:
   - **Statutory / official:** Rotherham/Jay 1,400 (1997–2013); Telford 1,000+;
     Casey 2025 national audit; ONS recorded-rape series.
   - **Extrapolation:** 250,000 (from Lord Pearson's 2019 Hansard remark).
   - **Name-analysis estimate:** 87% / 90% "distinctively Muslim names"
     (McLoughlin, *Easy Meat*); 95% (Dr Taj Hargey estimate).
   - **Single-source / contested:** per-survivor percentages, the theological
     causal model.
   A tiered visual (CSS, not fake-precision charts) — the tiering IS the honest
   visualization. No manufactured charts where data is weak.

4. **Cross-examination Ⅰ — the numbers** — where quantification strains (250k
   extrapolation logic; name-analysis ≠ religion; convictions ≠ offender
   population; selection/recording effects), named without softening — AND the
   opposite error: the "it's nothing / just as many white offenders" deflection.
   Both blades.

5. **Cross-examination Ⅱ — religion, culture, integration** *(moderate-vs-extremist
   spine, the heart)* — present the report's Islam-as-cause claim faithfully, then
   cross-examine with the report's OWN admissions: Hindus/Sikhs/Buddhists/most
   Muslims uninvolved (p.108); "filtered through culture" (p.117); imam Dr Taj
   Hargey as a *Muslim* critic; the Sikh community self-defence contrast (p.116).
   Then cross-examine the OPPOSITE error: the state's refusal to record ethnicity
   at all ("you can't say Asian, that's racist") was itself a catastrophic
   failure. This is *not all, not none* applied — both directions. Cross-links to
   the gender (04), family-law (14), and legal-pluralism (15) fault-lines.

6. **The institutional failure** — the well-corroborated core where the report and
   official sources agree: police, councils, NHS, CPS, the "fear of being called
   racist" dynamic, two-tier protection. The most verifiable part and the clearest
   integration story.

7. **Caveats & coverage** — denmark-style caveat-list: advocacy-report status,
   unverified individual testimony, redacted names in the report's appendices, the
   official statutory inquiry still pending (~2029).

8. **Sources** — every citation testable, in the fault-line `source-item`
   card style: the PDF itself (page-cited), Casey 2025 audit, Jay report (2014),
   Telford inquiry (2022), ONS recorded crime, the gov.uk official-inquiry page,
   Hansard (Pearson, 14 May 2019). No invented links.

---

## 5. Tone & integrity rules

- Every contested figure attributed to the report or its cited source — never
  stated as independently established fact.
- The report's own data caveats carried through, not stripped.
- Both failure modes named: inflation/monolith error AND denial/cover-up error.
- No invented citations; every source link must resolve.
- "Asian" vs "Pakistani" vs "Muslim" kept distinct throughout (the report itself
  flags the conflation, p.108) — this precision is the page's analytical value.

---

## 6. House-style / technical conventions (from existing pages)

- Single self-contained HTML file, inline `<style>`, no build step, no external JS.
- Palette: bg `#faf9f6`, ink `#17161a`, muted `#555047`/`#6d675c`, accent link
  `#4a7bb8`, warm card `#faf7ef`, caveat amber `#fef6e1`/`#d4a03a`.
- Reuse existing class vocabulary: `.top-nav`/`.nav-tab`, `.section-title`,
  `.section-sub`, `.caveat-list`/`.caveat-item`, `.cross-exam`, `.source-item`
  (`.src-type`/`.src-cite`/`.src-method`/`.src-link`/`.src-caveat`),
  `.open-questions`, `.status-badge`, quote-card pattern.
- Bilingual title; Japanese keyword in header (検証 = examination/verification).
- `max-width: 1120px` container; system font stack; responsive nav at 600px.

---

## 7. Out of scope (YAGNI)

- No interactive JS charts; tiered provenance shown with static CSS.
- No re-hosting or linking the PDF binary (it is a local download).
- No edits to the 21 fault-line pages beyond the single nav-tab addition.
- No new claims beyond what the report and named official sources support.

---

## 8. Verification

- Page renders standalone; every page in the grepped nav set shows the 5-tab nav;
  the active tab is correct on each; every nav href resolves with the right
  relative prefix.
- Every figure on the page traces to a page number (report) or named official
  source.
- Spot-check: no figure stated as fact without attribution; both cross-exam
  directions present.
