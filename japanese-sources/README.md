# Japanese-language sources catalog

This directory is the Japanese-language sources catalog for the **nuance-2026** fault-lines project (`../nuance-2026.html` and `../fault-lines/`).

## Project context

The hub essay treats "The West" as **EU + US + Japan**. The fault-line pages, as currently written, lean heavily on anglophone and francophone sources. Japan has a different debate: roughly 230,000 Muslims (Tanada Hirofumi's most-cited estimate, 2020), no live headscarf-ban controversy, but real disputes around cemetery space (Beppu, Hokuto), school-canteen halal accommodation, mosque siting, the post-Paris-attacks counter-terror legislation (2017 共謀罪), and the trauma of the January–February 2015 ISIS hostage murders of Yukawa Haruna and Goto Kenji.

This catalog is **Phase 1**: cataloguing real Japanese-language sources per fault line. **Phase 2** (separate pass) will integrate the strongest entries into the actual HTML pages.

## How to read the catalog

Each per-fault-line file has the following structure:

- **Header**: fault-line title + one-paragraph framing of why the fault line lands differently (or doesn't) in Japan.
- **Sources**: 3–8 entries in a fixed format.
- **Japan-specific cases**: documented incidents bearing on the fault line.
- **Gaps**: where Japanese-language sources are sparse and the catalog should be revisited.

### Source-entry format

```
### [Title in Japanese (transliteration in modified Hepburn)]
- Author/Publisher: ...
- Date: ...
- URL: ... (or `<!-- TODO Phase 2: locate URL -->`)
- Summary: one or two sentences in English on the source's argument or data.
- Relevance: how it bears on this fault line.
```

### Conventions

- **Romanization**: modified Hepburn (e.g., 中東 → *Chūtō*, not *Chuutou*).
- **Author order**: surname first, matching Japanese convention (Tanada Hirofumi, not Hirofumi Tanada).
- **Honesty flags**: where I'm uncertain about a specific bibliographic detail, the entry carries `<!-- TODO Phase 2: verify -->`. Where the URL is plausibly locatable but I haven't pinned it, the entry carries `<!-- TODO Phase 2: locate URL -->`. Where the entire source is provisional pending verification, that's flagged at the entry head.
- **No invented sources.** If I can't recall a real publication, I leave the section thin and flag the gap.

## The 21 fault lines

| # | File | Fault line |
|---|---|---|
| 01 | [01-political-authority.md](01-political-authority.md) | Political authority: caliphate vs. constitutional rule |
| 02 | [02-religion-and-state.md](02-religion-and-state.md) | Religion and state: separation vs. integration |
| 03 | [03-individual-vs-duties.md](03-individual-vs-duties.md) | Individual rights vs. religious duties |
| 04 | [04-gender-equality.md](04-gender-equality.md) | Gender equality |
| 05 | [05-religious-pluralism.md](05-religious-pluralism.md) | Religious pluralism / apostasy |
| 06 | [06-blasphemy-expression.md](06-blasphemy-expression.md) | Blasphemy and free expression |
| 07 | [07-violence-political-change.md](07-violence-political-change.md) | Violence as instrument of political change |
| 08 | [08-universalism-particularism.md](08-universalism-particularism.md) | Universalism vs. particularism |
| 09 | [09-education.md](09-education.md) | Education |
| 10 | [10-nation-vs-ummah.md](10-nation-vs-ummah.md) | Nation-state vs. ummah |
| 11 | [11-eschatology.md](11-eschatology.md) | Eschatology in public life |
| 12 | [12-burial-body.md](12-burial-body.md) | Burial and the body |
| 13 | [13-dietary-shared-life.md](13-dietary-shared-life.md) | Dietary law and shared life (halal) |
| 14 | [14-family-law.md](14-family-law.md) | Family law |
| 15 | [15-legal-pluralism.md](15-legal-pluralism.md) | Legal pluralism / sharia |
| 16 | [16-banking-finance.md](16-banking-finance.md) | Banking and finance (Islamic finance) |
| 17 | [17-dress-bodily-display.md](17-dress-bodily-display.md) | Dress and bodily display (hijab) |
| 18 | [18-calendar-time.md](18-calendar-time.md) | Calendar and time |
| 19 | [19-hygiene-purity.md](19-hygiene-purity.md) | Hygiene and ritual purity |
| 20 | [20-music-image-depiction.md](20-music-image-depiction.md) | Music, image, depiction |
| 21 | [21-homosexuality.md](21-homosexuality.md) | Same-sex conduct |

## General references

Sources that span multiple fault lines (Tanada's demographics, Kosugi's overview lectures, JIME periodicals, the 2015 ISIS-hostage corpus) live in [general-references.md](general-references.md). Per-fault-line files cite these by short form.

## Known sparse pages

Phase-1 honesty: Japanese-language scholarship is sparse on several fault lines because the issue has not become a Japanese domestic flashpoint or because the relevant primary debate is internal to the Muslim world. Pages flagged sparse:

- **16 (banking and finance)** — Islamic-finance literature in Japanese exists (mostly post-2007 Kyoto/Waseda working papers around the Bank of Japan / FSA opening Islamic-finance windows) but does not engage the *fault line* (the riba debate) as a values question.
- **18 (calendar and time)** — almost no Japanese-language treatment of calendrical politics as a fault line; Japan keeps Gregorian + nengō and treats the Hijri calendar as anthropological curiosity.
- **19 (hygiene and ritual purity)** — almost no Japanese-language scholarly treatment of Islamic *tahāra* as a public-policy question; the closest domestic reference is wudū-compatible washroom design in mosques and at airports, which is a halal-tourism subgenre.
- **11 (eschatology in public life)** — Japanese Islam-studies treats eschatology theologically (Kosugi, Tonaga) but rarely as a *public-life* fault line.
- **20 (music, image, depiction)** — discussed inside aesthetics/architecture scholarship (Tonaga Yasushi), not as a values-politics fault line.

These gaps are real, not fillable by harder searching, and the catalog flags them rather than padding.

## Pages with high source density

Pages where Japanese-language scholarship and journalism are abundant:

- **07 (violence and political change)** — the 2015 ISIS hostage murders generated sustained reporting and analysis (Asahi, Mainichi, Nikkei, *Foresight*, *Chūōkōron*, *Bungei shunjū*, JIME).
- **12 (burial and the body)** — the Beppu and Hokuto cemetery disputes generated NHK, Asahi, Mainichi reporting plus academic treatment (Sakurai Keiko, Tanada).
- **13 (dietary law and shared life)** — halal-tourism and school-canteen accommodation generated METI white papers, JNTO reports, and a substantial trade press.
- **02, 10 (religion-state, nation-vs-ummah)** — Kosugi Yasushi's mainstream output addresses these directly.

## Phase 2

When this catalog moves into the HTML pages: prioritize Tanada's demographic figures (every page citing "230k Muslims in Japan"), the 2015 ISIS-hostage primary record (page 07), the Beppu/Hokuto cemetery dispute (page 12), and the halal-canteen METI/JNTO reports (page 13). These are the four anchors where Japanese sources change the page rather than decorate it.
