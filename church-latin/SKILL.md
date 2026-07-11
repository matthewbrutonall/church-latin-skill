---
name: church-latin
description: >
  Universal ecclesiastical Latin translator covering all Church Latin from the patristic
  period (c.200 AD) through the mid-twentieth century (reference files cover to c.1960);
  Vatican II-era and later documents can be handled but require noting the transitional
  vocabulary boundary. Apply this skill whenever a user presents
  Latin text from a Catholic, Christian, or ecclesiastical context — any genre (patristic,
  liturgical, scholastic, canonical, hagiographic, curial, monastic, devotional, epigraphic,
  administrative), any period (Late Antique through Early Modern), any issuing authority
  (papal, episcopal, conciliar, monastic, religious order). Use this skill in preference to
  generic Latin translation whenever the text is from a religious, Church, or medieval
  context — even if the user does not use the words "ecclesiastical" or "Church Latin."
  Serves historians, archivists, liturgists, theologians, canonists, seminarians, and students.
---

# Ecclesiastical Latin Translator

Church Latin is a family of registers spanning eighteen centuries, not a single language. A word that is unambiguous in Cicero may carry the opposite meaning in a canonical document. A phrase that parses as ordinary Latin prose may be a Vulgate allusion woven invisibly into the text. A document that looks like a letter may be a formal canonical instrument with specific legal effects. Translating correctly requires identifying what kind of Latin you are dealing with before choosing how to translate it.

This skill uses a mandatory two-pass workflow:

- **Pass 1 — Translation**: Triage the text, identify the output mode, then produce a disciplined translation.
- **Pass 2 — Audit**: Adopt the role of a severe textual auditor and review the Pass 1 output against the Latin source.

Complete both passes before presenting final output. Never collapse them.

---

## Step 1 — Mandatory Input Triage

Before translating, perform triage. Do this for every text, without exception.

Never begin translation before triage, even when the passage is short, formulaic, familiar, or apparently easy. Never assume genre, date, or register from one phrase alone. Never let fluency substitute for identification.

Establish, as far as the evidence permits:

1. **Genre** — biblical, patristic, conciliar, papal, episcopal, canonical, scholastic, liturgical, monastic, hagiographic, devotional, epigraphic, administrative, commemorative, or mixed

2. **Period** — patristic (c.200–600), early medieval (c.600–1000), high medieval (c.1000–1350), late medieval (c.1350–1500), Renaissance/Neo-Latin (c.1450–1600), early modern (c.1600–1800), modern (c.1800–1960), or uncertain

3. **Issuing Authority** — pope, Roman congregation, council, bishop, abbot, prior, monastic chapter, religious superior, theologian, hagiographer, liturgical compiler, or unknown

4. **Document Function** — doctrinal, juridical, administrative, sacramental, liturgical, devotional, commemorative, scholastic-argumentative, narrative, exhortatory, epistolary, or mixed

5. **Diplomatic Status** — original instrument, register copy, formulary, excerpt, abstract, inscription, edited edition, diplomatic transcription, OCR output, HTR output, or uncertain witness

6. **Transcription Certainty** — clean transcription, lightly normalized edition, OCR output, HTR output, heavily abbreviated manuscript, damaged text, or mixed

7. **Register** — curial/formal, scholastic, liturgical, biblical, narrative/hagiographic, epigraphic, devotional, legal-canonical, administrative, or hybrid

Use explicit caution when evidence is mixed. If any category cannot be securely identified, state the best-supported provisional judgment and mark it as provisional.

Let triage control lexical choice, formula recognition, structural handling, and confidence level. Do not translate as if all Church Latin were one register.

Output triage before the translation in this exact form:

```
[Triage]
Genre: ...
Period: ...
Issuing Authority: ...
Document Function: ...
Diplomatic Status: ...
Transcription Certainty: ...
Register: ...
Triage Confidence: high / medium / low
```

If the text is too short or too damaged for secure classification, still perform triage and note which fields remain uncertain.

---

## Step 2 — Output Mode

Support four output modes. If the user specifies a mode, use it. If not, default to **Annotated**.

**Literal** — Close, structure-preserving translation. Stay near Latin syntax where English remains intelligible. Preserve repetitions, distinctions, and formal structure. Notes only when confidence protocol requires them.

**Flowing** — Idiomatic, readable English while preserving meaning, doctrinal force, legal force, and register. Improve English style only after accuracy is secured. Do not paraphrase away technical distinctions, formulae, or ambiguities.

**Annotated** *(default)* — Faithful translation plus brief notes on technical terms, formulae, ambiguity, abbreviation expansion, textual instability, and significant contextual issues.

**Scholarly** — Research-facing output. Preserve structure carefully, flag technical terminology, report meaningful ambiguities, note translation decisions that affect interpretation. Use for scholastic, canonical, doctrinal, or diplomatically complex texts.

Output structure by mode:

```
Literal / Flowing:     [Triage]  [Translation]  [Confidence]
Annotated:             [Triage]  [Translation]  [Notes]  [Confidence]
Scholarly:             [Triage]  [Translation]  [Notes]  [Key Terms]  [Confidence]
```

Mode affects presentation, not standards. No mode permits doctrinal weakening, legal flattening, silent emendation, hidden ambiguity, or false confidence.

---

## Step 3 — Translation Pass

### Core Rules

1. Prefer canonical/ecclesiastical sense over classical sense when genre and context support it.
2. Preserve legal, theological, and liturgical force. Do not flatten titles, offices, ranks, or canonical statuses into vague English.
3. Render fixed ecclesiastical formulae in standard institutional English where such renderings exist.
4. Do not paraphrase away ambiguity. Do not insert commentary into the main translation.
5. Do not use distancing language (*reportedly*, *supposedly*) unless the Latin itself signals doubt.
6. Do not repair awkward syntax unless the mode explicitly asks for flowing English.
7. Keep translation and notes strictly separate.

For detailed lexical and stylistic guidance by period, read `references/period-guide.md`.
For detailed guidance by genre (scholastic, hagiographic, canonical, curial, epistolary, liturgical, epigraphic), read `references/genre-guide.md`.

### Three-Layer Normalization Pipeline

Apply in this order (silently in Literal and Flowing modes; report normalization decisions in notes when Scholarly mode or damaged/uncertain sources are involved):

1. **Orthographic normalization** — carry forward the normalized form for translation:
   - ae/oe for e: *celum* → *caelum*; *penitentia* → *paenitentia*; *cenobium* → *coenobium*
   - ti for ci before vowel: *gracia* → *gratia*; *spacium* → *spatium*
   - h insertion/omission: *michi* → *mihi*; *nichil* → *nihil*; *habundare* → *abundare*
   - j/v: treat j as consonantal i (*ejus* → *eius*); v as u where appropriate (*vt* → *ut*)

2. **Abbreviation expansion** — expand before translating; mark uncertain expansions in notes

3. **Input quality assessment** — if triage identifies OCR, HTR, or manuscript transcription, assess plausibility of each word before expanding; flag anomalous readings rather than silently accepting them

### English Register

Default to traditional formal Catholic English:
- Douay-Rheims/Challoner phrasing for Vulgate passages
- Traditional liturgical English where established equivalents exist (*thee/thou* register in prayer texts)
- "Holy Ghost" not "Holy Spirit"; standard pre-1970 Missal and Breviary renderings where relevant
- Avoid modern colloquial Catholic English that reduces the institutional weight of the Latin

This is a precision choice: the older forms preserve semantic exactness.

### Vulgate Allusion Detection

Clerical and monastic authors wrote with minds saturated in the Vulgate. Scriptural phrases appear without quotation marks in letters, chapter acts, hagiographies, and sermons. Translating these as ordinary prose violates the intertextual meaning.

**Detection triggers — scan every text for:**
- Any 3 or more consecutive words matching Clementine Vulgate text
- Formulaic biblical incipits: *factum est autem*, *et ecce*, *miserere mei*, *quid gloriaris*
- Specific biblical noun combinations: *vas electionis*, *in sinu Abrahae*, *lutum platearum*, *filii tenebrarum*, *odor suavitatis*
- Unusual case structures mirroring Greek-to-Latin Vulgate syntax (e.g., cognate accusatives: *flebant fletu magno*)

**When an allusion is detected:**
- Align with Douay-Rheims phrasing; adjust minimally for grammar
- Mark direct citations in quotation marks; paraphrased allusions in italics
- Report every allusion in a numbered footnote: `[N] Book Chapter:Verse. Note: why the author invoked this passage.`

**Limit:** Do not classify simple two-word theological pairings (*regnum Dei*, *gratia divina*, *pater noster*) as allusions unless embedded in a longer scriptural sentence structure.

For worked examples, see `references/genre-guide.md`.

### Top 20 Danger List

These terms produce material error when rendered by classical default. Check for any before translating.

| Latin | Classical trap | Correct ecclesiastical sense |
|---|---|---|
| religio | religion, piety | a religious order or congregation |
| conversatio morum | conversation of manners (verbal exchange) | the formal third Benedictine vow: ongoing transformation of one's whole manner of living toward God |
| capitulum | chapter of a book | the Chapter (governing body of a house or province) |
| princeps | prince, secular ruler | abbot or head of monastic federation (early medieval/Insular) |
| civitas | city, state | monastery or monastic town (early medieval and Insular contexts) |
| definitor | one who defines | provincial or general councilor |
| regularis | normal, standard | regular clergy (under a religious rule, as opposed to secular) |
| beneficium | benefit, favor | benefice (ecclesiastical office with endowed revenue) |
| oratio | speech, public oration | prayer or liturgical collect |
| vicarius | substitute, proxy | Vicar (holder of ordinary or delegated canonical power) |
| erectio | setting upright | canonical erection (formal decree establishing a community or altar) |
| parochia | diocese (late Latin) | parish (post-medieval); monastic federation (early medieval) |
| exhibitor | showman, presenter | petitioner or presenter of a canonical document |
| dimissoriales | dismissal letters | dimissorial letters (episcopal licence for ordination by another bishop) |
| conversus | turned, converted | lay brother (distinct monastic class) |
| postulatio | legal demand, claim | postulation (petition to appoint an impeded candidate to elected office) |
| cura animarum | care of souls (literary) | cure of souls (legal and sacramental pastoral responsibility) |
| saeculum | century, age | the world / secular life (life outside the cloister) |
| lector | reader | professor of theology or philosophy; or the minor order of Lector |
| rescriptum | imperial written reply | papal or curial rescript (written response granting a favor or decision) |

For full consequence-of-error notes and an extended glossary, see `references/false-friends.md`.

### Dating

For dating formulas (Roman calendar, indiction cycle, liturgical feast-day dating, pontifical year, Julian/Gregorian transitions), read `references/dating-system.md`.

### Imprints and Colophons

For printed material (breviaries, missals, conciliar decrees, patristic and theological editions), the publication statement uses a compact formulaic Latin with several dangerous false friends — `apud` = "at the shop of" (not "among/according to"), `cura` = "edited by", and the place of printing in the locative (`Venetiis`, `Lugduni`). For parsing imprints/colophons — verbs of printing, agent roles, financing formulas, shop-and-sign vocabulary, and worked examples — read `references/imprint-colophon-guide.md`.

### Source Criticism

Any characterization of papal, conciliar, or curial Latin as "obtuse," "dense," or stylistically deficient must be assessed relative to the norms of that genre and period — not against the personal register preferences or possible ideological biases of an external commentator. Note difficulty only when measured against comparable documents of the same type.

---

## Step 4 — Audit Pass

After completing the translation, adopt the role of a severe textual auditor. You are not the translator. Do not defend the draft. Audit it.

Check in this order:

1. **Completeness** — omissions, additions, merged clauses, invented connectives, dropped negatives, missing subordinate structures
2. **Grammar and syntax** — subject assignment, passive constructions, participles, gerundive force, relative clauses, ablative absolutes, scope of modifiers
3. **Lexical accuracy** — false friends, classical-over-ecclesiastical errors, canonical and liturgical terminology errors, unstable rendering of repeated terms
4. **Register fidelity** — does the translation preserve the genre? Flag smoothing that suppresses the real register.
5. **Formulae** — have diplomatic or ecclesiastical formulae been paraphrased when they should have standard renderings?
6. **Theological and juridical force** — does the draft weaken doctrinal claims, legal commands, vows, blessings, offices, or sacramental language?
7. **Ambiguity discipline** — does the draft present a doubtful reading as certain?
8. **Text-critical caution** — has the translator silently corrected odd wording, unstable orthography, abbreviatory residue, or possible corruption?
9. **Names, dates, numbers, scriptural references** — all proper nouns, titles, feast names, dates, numerals
10. **Vulgate alignment** — have any Vulgate allusions been missed or rendered from classical rather than Douay-Rheims?

Audit output:

```
[Verdict]
One line: sound / usable with corrections / unreliable

[Corrected Translation]
Full corrected translation — not just fragments.

[Audit Report]
Critical: [Latin phrase] → [what the draft did] → [correction] → [one-line justification]
Major:    ...
Minor:    ...

[Terminology Lock]
Key terms that must remain consistent if the text continues.

[Residual Uncertainties]
Unresolved ambiguities that cannot be settled from the text as provided.
```

Correct aggressively when needed. Do not rewrite for style alone. Do not replace one elegant error with another. If the draft is wrong in a meaning-bearing way, fix it. If acceptable but not ideal, keep corrections minimal. Never output only a critique without a corrected translation unless the source is too corrupt to support one.

---

## Confidence Protocol

**Tier 1 — High Confidence**: One translation only. In Literal or Flowing mode, notes minimal. In Annotated or Scholarly mode, brief notes only where genuinely useful.

**Tier 2 — Genuine Ambiguity**: One preferred translation and one alternate rendering with a brief rationale. In Flowing mode, do not hide ambiguity for style. In Annotated and Scholarly mode, show it explicitly.

**Tier 3 — Damaged, Unattested, or Anomalous**: Flag the problem explicitly in every mode. Do not produce a smooth full translation as if reliable. In Literal and Flowing mode, restrict to defensible partial rendering where possible. In Annotated and Scholarly mode, identify the exact source of instability.

No mode permits false confidence. If the text is too corrupt to translate responsibly, say so and identify the specific phrase preventing a reliable translation.

---

## Known Failure Modes

The following conditions require explicit declaration. Do not produce a confident full translation when they apply.

**1. Uncertain abbreviation expansion** — when a suspension mark or contraction could resolve in more than one way, give both expansions and flag the choice; do not silently commit to one reading.

**2. OCR or HTR damage** — when the source appears to be OCR or HTR output, assess each word's plausibility before translating; flag any word that may be a mistranscription or garbled reading.

**3. Hisperic Latin** — texts in the *Hisperica Famina* tradition use deliberate invented or obscure vocabulary that exceeds standard lexicons; flag entire sections as uncertain.

**4. Contested scholastic renderings** — where translators of Aquinas or Scotus genuinely disagree on a term (*esse*, *actus purus*, *suppositum*), present the competing renderings; do not impose one without noting the debate.

**5. Code-switching documents** — when a document mixes Latin with Italian, Spanish, French, English, or another vernacular, flag each switch with its language; do not translate vernacular passages under Latin rules.

**6. 1960s transitional vocabulary** — documents dated 1958–1965 may use vocabulary with pre-conciliar denotations and post-conciliar resonances (*aggiornamento*, *participatio actuosa*, *ecumenismus*, *collegialitas*); flag the temporal ambiguity and note what pre-conciliar meaning the term carried.

**7. Canonical beatification precision** — *servus Dei*, *venerabilis*, *beatus*, *sanctus* are formal canonical states with legally precise meanings; do not conflate them; note the applicable stage.

**8. Missing provenance context** — when genre, period, issuing authority, or geographic origin cannot be established from the text, state what is unknown and identify which translation decisions are affected.

**9. Uncertain proper names** — place names and personal names in Latin may have multiple vernacular equivalents; flag when identification is uncertain and affects interpretation.

**10. Catastrophically unstable sources** — when multiple consecutive words cannot be read confidently (corruption, lacunae, extreme damage), restrict to a partial rendering; never produce a smooth full translation of unreliable text.

---

## Vernacular Intrusions

Documents from c.1400 onward, especially religious order correspondence, curial notes, and chapter records, frequently mix Latin with the vernacular of the author's country. This is a documentary convention, not error.

**Detection signals:**
- Italian: inflected endings (-o, -a, -are, -ione); characteristic particles (*per*, *come*, *sopra*, *della*, *nel*)
- Spanish: inflected endings (-ó, -ar, -ción, -ado); characteristic particles (*para*, *como*, *del*, *también*)
- French: definite articles (*le*, *la*, *les*); characteristic particles (*pour*, *comme*, *dans*, *au*)
- English: articles (*the*, *a*, *an*); characteristic particles (*for*, *with*, *of*, *the which*)

**Rule:** Flag each vernacular intrusion with its language in square brackets — [Italian], [Spanish], [French], [English]. Translate it using the grammar and lexicon of the relevant vernacular language, not Latin rules. Integrate all elements into a single coherent final translation; keep them visually distinct in notes but do not produce two unrelated parallel texts.

**Exception — early medieval macaronic texts:** Old Irish, Old English, and Old High German glosses embedded in Latin manuscripts, and fully bilingual early medieval texts, are an integrated documentary form. Identify each element by language and translate the text as a whole rather than treating vernacular portions as anomalous intrusions.

---

## Reference Files

Read these when triage identifies the relevant period, genre, or document type:

- **`references/period-guide.md`** — lexical and stylistic guidance for each period from patristic through modern; key authors, characteristic features, and period-specific lexical warnings
- **`references/genre-guide.md`** — scholastic (quaestio structure, dangerous terminological pairs), hagiographic (six genre types, virtus warning), canonical/legal, curial/papal, epistolary, liturgical, epigraphic; worked Vulgate allusion examples
- **`references/dating-system.md`** — Roman calendar (Kalends/Nones/Ides), indiction cycle, liturgical feast-day table, pontifical year, secular regnal years, Julian/Gregorian transition rules, French Revolutionary calendar
- **`references/imprint-colophon-guide.md`** — reading the publication statement of printed books: verbs of printing/selling, agent roles, financing formulas (apud/sumptibus/impensis), shop-and-sign vocabulary, place-in-locative, worked examples
- **`references/reference-hierarchy.md`** — which lexicon to consult by period and genre; decision rules for Cappelli, Mohrmann, Blaise, Du Cange, DMLBS, DMLCS, Souter, TLL, Niermeyer, Forcellini, Stelten, Bacci, Stotz, and others
- **`references/false-friends.md`** — extended glossary of ecclesiastical Latin false friends and technical terms beyond the Top 20
