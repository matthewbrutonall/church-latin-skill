# Abbreviations and Palaeography — Expanding Scribal Shorthand

Manuscript and early-printed ecclesiastical Latin is written in a dense system of **abbreviations**:
letters omitted and replaced by a mark, whole syllables replaced by a special sign, words contracted
to their first and last letters. A raw transcription — or OCR/HTR output — of such a text is a string
of half-words and sigla that **cannot be translated until it is expanded**. Expansion is a distinct
step that comes *before* translation, and it is not mechanical: the same siglum can expand several
ways depending on context (a bare `p`-with-a-stroke can be *per*, *par*, or *por*; `dns` is *dominus*
but a stroke over a vowel can stand for either *m* or *n*). **Expand first, flag every uncertain
expansion, and never auto-expand a siglum blindly.**

The indispensable reference for identifying any Latin abbreviation is **Adriano Cappelli, *Dizionario
di abbreviature latine ed italiane*** ("il Cappelli") — cite it as the standard authority.

---

## 1. The four mechanisms of abbreviation

Every abbreviation works by one of these mechanisms. Identify the mechanism to expand safely.

| Mechanism | What it does | Example |
|---|---|---|
| **Suspension** | Cuts off the **end** of a word, marking the cut | *ep̄s* → *episcopus*; *frāt* → *frater*; a final stroke on *domin̄* → *dominus* |
| **Contraction** | Omits letters from the **middle**, keeping first + last (with a mark over) | *dns̄* → *dominus*; *scōs* → *sanctos*; *nr̄i* → *nostri* |
| **Sign / brevigraph** | A special sign stands for a whole syllable or word | the *-us* hook, the *con-* sign, tironian ⁊ = *et* |
| **Superscript letter** | A small raised letter (usually a vowel) supplies the omitted letters around it | *qᵘ* → *qui*/*quo*; *gᵒ* → *gratia*/… (context); *ꝑ* with superscript = *pri*, etc. |

## 2. The general marks

| Mark | Meaning | Expansion |
|---|---|---|
| **Macron / tilde** (horizontal bar or wavy line over a letter) | omitted **m** or **n**, or a general contraction mark | *dñs* → *dominus*; *nõ* → *non*; *tāt* → *tantum*; *ōem* → *omnem*. Over a final vowel it is most often *m* or *n* — decide which by grammar |
| **Bar through an ascender** (crossed *l*, *b*, *d*, *h*) | suspension/contraction of that word | *ħ* → *hoc*/*habet* (context); crossed *ll* → *-lis* etc. |
| **General abbreviation stroke** | "something is omitted here" | forces you to supply letters from context; the least specific mark |

## 3. The syllabic signs (brevigraphs)

These stand for fixed letter-groups. High-frequency in ecclesiastical texts:

| Sign (described) | Stands for | Example |
|---|---|---|
| **-us hook** (a `9`-like or `ꝰ` hook, esp. word-final) | *-us* | *dñꝰ* → *dominus*; *eiꝰ* → *eius* |
| **`9`-shaped sign at word start** | *con-* / *com-* | *⁹fessio* → *confessio*; *⁹munis* → *communis* |
| **`-rum` sign** (a flourished `ꝛ`/looped tail) | *-rum* (genitive plural) | *oĩꝝ* → *omnium* type; *sctōꝛ* → *sanctorum* |
| **`-bus` sign** (a `;` or `b`-hook, word-final) | *-bus* | *oĩb;* → *omnibus*; *nobiſb;* → *nobilibus* |
| **`p` with a stroke through the descender** (ꝑ) | *per-* / *par-* | *ꝑ* → *per*; *ꝑte* → *parte* (context) |
| **`p` with a loop** (ꝓ) | *pro-* | *ꝓ* → *pro*; *ꝓpter* → *propter* |
| **`p` with a superscript stroke/hook** | *prae-* / *pri-* | *p̃* → *prae*; *ꝑ*+super = *pri* |
| **`q` with a stroke / `q;`** | *que* (enclitic) or *quae/qui/quod* forms | *q;* → *-que*; *q̄* → *quod*; *qᵐ* → *quoniam*; *qñ* → *quando* |
| **lunate/round `c`-based `con`/`cum` sign** | *con-* / *cum* | see the `9`-sign above; also *cū* → *cum* |
| **tironian *et* (⁊)** | *et* / *-et* | *⁊* → *et*; can also be the *-et* ending in context |

## 4. Nomina sacra and holy-name contractions

Sacred names are contracted by ancient convention (inherited from Greek), usually with an overline.
These are near-universal and must be recognised on sight:

| Siglum | Expansion | Meaning |
|---|---|---|
| *ihs* / *ihc* / *iħs* | *Iesus* | Jesus (from Greek ΙΗΣ) — **not** the false etymology "*Iesus Hominum Salvator*" |
| *xps* / *xpc* / *xр̄c* | *Christus* | Christ (from Greek ΧΡ, *chi-rho*) — the *xp* is chi-rho, not Latin "xp" |
| *ihu xpi* | *Iesu Christi* | of Jesus Christ (genitive) |
| *dns / dñs* | *dominus* | Lord |
| *ds / dñs* | *deus* | God (*ds̄* / *dī* genitive *dei*) |
| *spc / sps / spu* | *spiritus* | Spirit (*spu scō* → *spiritu sancto*) |
| *scs / scī / scōs* | *sanctus / sancti / sanctos* | holy / saint |
| *dnc / dñca* | *dominica* | Sunday / the Lord's day |
| *eccla / ecclia* | *ecclesia* | Church |
| *aplc / apls* | *apostolus / apostolicus* | apostle / apostolic |
| *epc / epūs / eps* | *episcopus* | bishop |
| *pbr / presb* | *presbyter* | priest |
| *oro / ōr* | *oratio* | prayer/collect |

**Caution:** *xps* / *xpi* begins with the Greek letters chi-rho (Χ, Ρ), not Latin x + p — do not read
or transcribe it as if Latin. And the sacred-name overline is a **contraction mark**, not a macron of
vowel quantity.

## 5. Domain-specific and liturgical sigla

Ecclesiastical texts add their own high-frequency contractions (see also the abbreviations table in
`false-friends.md` for honorifics like *R.P.*, *E.mo*):

| Siglum | Expansion | Meaning |
|---|---|---|
| *℣* | *Versiculus* | Versicle ("V.") |
| *℟* | *Responsorium* | Response ("R.") |
| *xᵽ* / *℈* | (various) | check Cappelli |
| *aīa / aīe* | *anima / animae* | soul(s) |
| *oĩa / oĩs* | *omnia / omnis* | all / every |
| *nr̄ / nr̄i / nr̄a* | *noster / nostri / nostra* | our |
| *ihrlm / ierlm* | *Ierusalem* | Jerusalem |
| *isrl / irł* | *Israel* | Israel |
| *psm / psalm* | *psalmus* | psalm |

## 6. The expansion discipline

1. **Identify the mechanism** (suspension / contraction / sign / superscript) before guessing letters.
2. **Expand in the transcription, then translate.** Never translate a still-abbreviated form.
3. **Mark the expansion when it matters.** Scholarly convention italicises supplied letters
   (*ep(iscopu)s*) or uses round brackets; in this skill, note any expansion that was not certain.
4. **Flag context-dependent sigla.** A single siglum with more than one possible expansion (the
   `p`-family, `q`-family, a bare overline as *m* vs *n*, `ħ` as *hoc* vs *habet*) must be resolved by
   grammar and sense — and if it cannot be, give both and flag it (SKILL.md failure mode 1).
5. **Do not "normalise away" a genuine ambiguity** to make the sentence flow. An uncertain expansion
   is a reported uncertainty, not a silent choice.
6. **Treat OCR/HTR sigla with extra suspicion** — automated transcription frequently mis-reads
   brevigraphs (a `-rum` sign as a `9`, a tironian *et* as a `7` or `&`); assess plausibility before
   expanding (SKILL.md failure mode 2).

---

## Worked example

A charter witness clause is transcribed from the manuscript as:

**Ego frᵃ Ioħes ep̄s ecclīe Lond̄ hͤ cōfirmaui ⁊ sigillũ meū appoſui in nōĩe dñi.**

Expand siglum by siglum:
- *frᵃ* — suspension with superscript *a* → *frater* (or *fra*; here the sense "brother" → *frater*)
- *Ioħes* — contraction with barred *h* → *Iohannes* ("John")
- *ep̄s* — suspension/contraction → *episcopus* ("bishop")
- *ecclīe* — contraction (nomen sacrum family) → *ecclesiae* ("of the church," genitive)
- *Lond̄* — suspension with final stroke → *Lond(oniensis)* ("of London"); flag the exact expanded
  form (*Londoniensis*) as supplied
- *hͤ* — barred/superscript *h* → context: here *hoc* ("this") — but *ħ* can also be *habet*; grammar
  (*hoc … confirmavi*) resolves it to *hoc*; **flag** the alternative
- *cōfirmaui* — overline for *n* → *confirmavi* ("I have confirmed"); *u* = consonantal/vowel per
  orthographic normalisation → *confirmavi*
- *⁊* — tironian *et* → *et* ("and")
- *sigillũ meū* — overlines for *m* → *sigillum meum* ("my seal")
- *appoſui* — long-*s* → *apposui* ("I have affixed")
- *in nōĩe dñi* — *nōĩe* contraction → *nomine*; *dñi* nomen sacrum → *domini* → "in the name of the
  Lord"

Expanded Latin: **Ego frater Iohannes episcopus ecclesiae Lond(oniensis) hoc confirmavi et sigillum
meum apposui in nomine Domini.**

→ **"I, Brother John, bishop of the church of London, have confirmed this and have affixed my seal, in
the name of the Lord."**

*Note:* two sigla required a judgement call — *Lond̄* (supplied as *Londoniensis*) and *ħ* (*hoc* vs
*habet*, resolved by grammar). Both are flagged as expansions rather than silently committed. Verify
any unfamiliar siglum against Cappelli before expanding.

---

*The standard authority is A. Cappelli, *Dizionario di abbreviature latine ed italiane* (the
*Lexicon Abbreviaturarum*); consult it — or the searchable "Ábbreviationes" / Cappelli-online
databases — for any siglum. For the general system, see B. Bischoff, *Latin Palaeography*, and for
English records C. T. Martin, *The Record Interpreter*. Expansion precedes the orthographic
normalisation pipeline in SKILL.md (Step 3), which then regularises the expanded forms.*
