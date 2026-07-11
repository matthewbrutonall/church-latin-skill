# Imprints and Colophons — Reading the Publication Statement

From the mid-fifteenth century onward, a large part of the ecclesiastical-Latin corpus is *printed*:
breviaries, missals, pontificals, conciliar decrees, patristic editions, theological *summae*, and
polemical tracts. Each carries an **imprint** (on the title page) and/or a **colophon** (at the end)
stating where, by whom, at whose expense, and when it was produced. These statements use a compact,
formulaic Latin that is easy to mis-handle: `apud` here does **not** mean "among" or "according to",
`cura` means "edited by", and the place of printing is almost always in the **locative** case
(`Venetiis`, `Lugduni`, `Coloniae`) rather than the nominative.

Parse an imprint as four slots, in any order:

> **[verb of printing] · [agent(s), with role and financing] · [place, in the locative] · [date]**

*Example.* **Excusum Moguntiae, typis Ioannis Schoeffer, anno 1541.**
→ "Printed at Mainz, with the type of Johann Schöffer, in the year 1541."
(`Excusum` = printed; `Moguntiae` = locative of Mainz; `typis` = with the type of; `anno 1541` = the date.)

Resolve the place with the toponym gazetteer (the locative imprint forms are covered) and the date
with `dating-system.md`.

---

## 1. Verbs of printing, publishing, and selling

Often in the perfect/imperfect or as a perfect participle. The *printing* verbs and the *selling*
verbs are distinct — do not collapse "printed" and "for sale".

| Latin | Meaning |
|---|---|
| *imprimebat, impressum est, imprimebatur* | printed / was printed |
| *excudebat, excudebant, excusum, excusa(e)* | printed / struck off (of type) |
| *exarare, exarata, exaratum* | printed (lit. "ploughed up"; older/rhetorical) |
| *typis (mandavit), e typis, per typos* | (put) into type; printed with the type of |
| *recusa* | (re)printed |
| *reimpressa* | reprinted |
| *emissum, emissio* | published; an edition/issue |
| *prostat (venalis), prostant (venales)* | is/are for sale |
| *venundatur, venundantur, veneunt* | is/are sold |

**False-friend caution:** *exarare* literally means "to plough"; in imprints it means "to print/write out".
*Emissio* is an "edition/issue", not an "emission".

## 2. Agents and their roles

| Latin | Role |
|---|---|
| *typographus* | printer |
| *impressor* | printer |
| *excusor* | printer |
| *typographia, typographeum* | printing office / press ("E typographeo Clarendoniano" = at the Clarendon Press) |
| *architypographia* | chief/main printing office ("Ex architypographia Plantiniana") |
| *officina* | shop / printing establishment ("Ex officina …") |
| *aedes* (in aedibus) | shop / house ("In aedibus Aldi" = in the shop of Aldus) |
| *bibliopola* | bookseller |
| *praelum / prelum* (praelo) | the press itself ("praelo Sheldoniano" = at the Sheldonian press) |
| *castigator; castigatus* | proofreader; corrected/proofread |
| *cura* (cura et studio) | "by the care of" — i.e. **edited by** |
| *collegit / conlegit* (collegit et edidit) | compiled (and edited) |

**False-friend caution:** *cura* in an imprint means "edited by", not "cure/care" in the medical sense.

## 3. Financing and partnership formulas

The name after these tells you who *paid* or whose *shop* it was, not necessarily who printed it.

| Latin | Meaning |
|---|---|
| *apud* | **at the shop of** (NOT "among"/"according to") |
| *per* | by / through (the person who did the printing) |
| *sumptibus, sumptu* | at the expense of |
| *impensis, impensa* | at the expense of |
| *socii, sociorum* (& socios) | and partners / associates |
| *filius, filii* (& filios) | son(s) |
| *frater, fratres* | brother(s) |
| *vidua* | widow (e.g. "apud viduam & filios …") |
| *haeredes / heredes* | heirs |
| *successores* | successors |

**False-friend caution:** *apud* is the single most mis-read imprint word. In classical prose it means
"among / in the works of / according to"; on a title page it means "at the shop/press of". "Apud Aldum"
= "at Aldus's press", not "according to Aldus".

## 4. Locating the shop (place, street, and sign)

Early shops were identified by street and by a hanging sign, not a number.

| Latin | Meaning |
|---|---|
| *via, vico* | street ("via Iacobaea" = Rue St-Jacques) |
| *platea* | street / square |
| *angulus* (angulo) | corner |
| *ad insigne, sub insigni* | at / under the sign of |
| *sub signo, ad signum* | under / at the sign of |
| *sub scuto* | under the shield (i.e. sign) of |

The **place of printing itself** is given in the **locative**: `Romae` (Rome), `Venetiis` (Venice),
`Lugduni` (Lyon), `Coloniae` (Cologne), `Moguntiae` (Mainz), `Parisiis` (Paris), `Basileae` (Basel),
`Antuerpiae` (Antwerp), `Augustae Vindelicorum` (Augsburg), `Argentorati` (Strasbourg). Treat the
locative as a lookup key, not the nominative.

## 5. Dates

Imprint dates may be Arabic, Roman (`M.DCC.XCIII` = 1793), or expressed with `anno`, `anno Domini`,
`mense … anno …`. Beware chronograms (a motto whose capital letters, read as Roman numerals, sum to the
year) and *stylus* differences (e.g. Easter/Annunciation year-start) — see `dating-system.md`.

---

## Worked example

**Excudebat Salmanticae in officina Andreae à Portonariis, expensis viduae Iacobi Cardon, anno M.D.LX.**

- *Excudebat* — "printed" (3rd-person imperfect)
- *Salmanticae* — locative → **Salamanca**
- *in officina Andreae à Portonariis* — "in the shop of Andrés de Portonariis" (the printer)
- *expensis viduae Iacobi Cardon* — "at the expense of the widow of Jacques Cardon" (the financier)
- *anno M.D.LX* — 1560

→ **"Printed at Salamanca in the shop of Andrés de Portonariis, at the expense of the widow of Jacques
Cardon, in the year 1560."**

---

*Terminology in this guide follows the RBMS "Glossary of Common Latin Terms Found in Imprints of Early
Printed Books" and its "Latin Place Names" list. For the place-name forms, use the toponym gazetteer;
for the dates, `dating-system.md`.*
