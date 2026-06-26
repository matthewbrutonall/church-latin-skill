# Church Latin Translator — Claude Skill

A Claude skill for translating ecclesiastical Latin across all periods and genres, from the patristic period (c.200 AD) through the mid-twentieth century (reference files cover to c.1960).

---

## The Problem

Generic AI Latin translation defaults to classical (Ciceronian) meanings. Church Latin is not classical Latin, and translating it as if it were produces errors that range from awkward to seriously misleading.

*Religio* in a canonical document does not mean "religion" — it means a religious order. *Conversus* does not mean "convert" — it means a lay brother. *Virtutes* in a hagiographic text does not mean "virtues" — it means miracles. *Civitas* in an early Irish text does not mean "city" — it means a monastery.

These are not edge cases. They are the normal vocabulary of eighteen centuries of Church Latin, and any translation that misses them produces a document that is factually wrong.

---

## Before and After

We tested the same Latin passages across multiple leading AI models prompted as classical Latin scholars, without specialist ecclesiastical guidance. This is precisely the failure mode the skill is designed to correct — a classically trained translator applying the wrong lexical register to Church Latin. The failures below were consistent across models.

---

**Test 1 — Early Medieval Irish annals**

> *Mochtae, princeps civitatis Lughmadensis, obdormivit in Domino. Virtutes multae per eum operatae sunt etiam post obitum.*

| | Translation |
|---|---|
| **Without the skill** | "Mochtae, head of **the city of Lughmad**, fell asleep in the Lord. Many **virtues** were worked through him even after his death." |
| **With the skill** | "Mochtae, abbot of **the monastery of Louth**, fell asleep in the Lord. Many **miracles** were worked through him even after his death." |

*Civitas* in pre-Viking Irish Latin means a monastery, not a city (Ireland had no Roman-style urban centres before c.840). *Virtutes* in a hagiographic narrative means miracles, not moral virtues. Both errors are silent — the unguided translation reads fluently and is completely wrong.

---

**Test 2 — 19th-century canonical formula**

> *Frater Ioannes, sacerdos professus, qui per annos decem curam animarum in parochia vicina fideliter exercuerat, pie in Domino obdormivit.*

| | Translation |
|---|---|
| **Without the skill** | "Brother John, a professed priest, who for ten years had faithfully exercised **the care of souls** in the neighbouring parish, fell piously asleep in the Lord." |
| **With the skill** | "Brother John, a professed priest, who for ten years had faithfully exercised **the cure of souls** in the neighbouring parish, fell piously asleep in the Lord." |

*Cura animarum* is a canonical legal term meaning the cure of souls — the formal sacramental and legal charge of a parish priest, requiring canonical appointment and conferring specific obligations and authority. "Care of souls" sounds like general pastoral kindness. The difference is legally and historically significant.

---

**Test 3 — Dating formula**

> *Datum in domo nostra provinciali, die festo Sancti Andreae Apostoli, anno Domini MDCCCLXXXIII, indictione XI, pontificatus Leonis XIII anno sexto.*

| | Translation |
|---|---|
| **Without the skill** | "Given in our provincial house, on the feast day of Saint Andrew the Apostle, in the year of the Lord 1883, in the eleventh indiction, in the pontificate of Leo XIII." |
| **With the skill** | "Given in our provincial house, on the feast of Saint Andrew the Apostle [**30 November**], in the year of the Lord 1883, **indiction 11** (verified: (1883+3) mod 15 = 11 ✓), in the **sixth year of the pontificate of Leo XIII** (acc. 20 February 1878)." |

The unguided translation left the feast date unconverted, dropped *anno sexto* (the sixth year of the pontificate), and did not verify the indiction arithmetic. Dating formulas require active conversion to be useful — a transcribed date that is not converted is not yet translated.

---

## What This Skill Does

This skill trains Claude to identify what kind of Latin it is dealing with **before** it decides how to translate — then translate with correct ecclesiastical, canonical, liturgical, or monastic meanings — then audit its own output.

**Coverage:**

| Period | Dates |
|---|---|
| Late Antique / Patristic | c.200–600 |
| Early Medieval | c.600–1000 |
| High Medieval | c.1000–1350 |
| Late Medieval | c.1350–1500 |
| Renaissance / Neo-Latin | c.1450–1600 |
| Early Modern | c.1600–1800 |
| Modern | c.1800–1960 |

**Genres:** patristic · liturgical · scholastic · canonical · hagiographic · curial · monastic · devotional · epigraphic · administrative

**For:** historians · archivists · liturgists · theologians · canonists · seminarians · students

---

## Installation

```
claude skill install church-latin.skill
```

---

## Output Modes

Specify a mode at the start of your request. If you give no mode, the default is **Annotated**.

| Mode | Best for |
|---|---|
| `Mode: Literal` | Grammatical study, legal verification, close reading |
| `Mode: Flowing` | General history, publication, accessible rendering |
| `Mode: Annotated` | Archival research, general scholarly use *(default)* |
| `Mode: Scholarly` | Critical editions, canonists, advanced research |

---

## How It Works

Every translation runs two passes.

**Pass 1 — Triage and Translation**

Before any word is translated, the skill identifies:
- Genre, period, issuing authority, document function
- Diplomatic status and transcription quality
- Operative register

Triage controls lexical choice. A word is not translated the same way in a 7th-century Irish chronicle as in a 19th-century papal brief.

**Pass 2 — Audit**

A second pass reviews the translation for completeness, grammar, register fidelity, formulaic accuracy, theological and juridical force, ambiguity discipline, and missed Vulgate allusions — then issues a verdict and a corrected translation if needed.

---

## Examples

### Example 1 — 19th-Century Religious Order Chapter Act (Mode: Annotated)

**Input:**

> *Anno Domini MDCCCLXXXIII, die XXIII Aprilis, in festo Sancti Georgii Martyris, habita est congregatio capitularis in domo nostra provinciali. Praesidente A.R.P. Provinciali una cum definitoribus, statuta sunt sequentia.*
>
> *De receptione in religionem: decreverunt ut duo postulantes ad novitiatum admitterentur.*
>
> *Frater autem Ioannes Maguire, sacerdos professus huius domus, qui per duodecim annos curam animarum in parochia vicina fideliter exercuerat, pie in Domino obdormivit die XV Martii proxime praeteriti. Qui vere fuit in congregatione nostra, ut scriptum est, vas electionis. Cuius anima misericordissimo Deo commendatur.*

---

**[Triage]**
Genre: Mixed — administrative chapter act with embedded obituary notice
Period: Modern (1883)
Issuing Authority: Religious province chapter; Provincial Superior with council of definitors
Document Function: Administrative (admissions legislation) + commemorative (obituary)
Diplomatic Status: Register copy or clean transcript of chapter proceedings
Transcription Certainty: Clean — no damage, abbreviations, or orthographic instability
Register: Administrative/canonical (section I); devotional/commemorative (obituary)
Triage Confidence: high

**[Translation]**

In the year of the Lord 1883, on the 23rd day of April [feast of Saint George the Martyr], a capitular assembly was held in our provincial house. The Very Reverend Father Provincial presiding, together with the definitors, the following matters were resolved.

*On admission to the religious life:* It was decreed that two postulants be received into the novitiate.

Brother John Maguire, professed priest of this house, who for twelve years had faithfully exercised the cure of souls in the neighbouring parish, fell piously asleep in the Lord on the 15th day of last March. He was truly, in our congregation, as it is written, a "vessel of election."¹ May his soul be commended to the most merciful God.

**[Notes]**

- *in festo Sancti Georgii Martyris*: the feast of St. George falls on 23 April [Gregorian]; converted from the document's own dating formula.
- *congregatio capitularis*: a capitular assembly — the formal meeting of the chapter as a governing body; not a generic gathering.
- *definitores*: the definitors — the members of the Provincial's governing council; retained as a technical term.
- *in religionem*: rendered "to the religious life" — the fixed canonical formula for formal entry into a religious institute; not "to religion."
- *sacerdos professus*: professed priest — a fully professed member of the order in holy orders; the combination of priestly ordination and religious profession in one person.
- *cura animarum*: cure of souls — the official legal and sacramental pastoral charge of a parish priest, implying a canonical appointment with formal responsibility for a defined territory. Not "pastoral care" in a general sense. Requires priestly ordination; not possible for a lay brother.
- *parochia*: parish — post-medieval canonical sense (defined territorial unit with assigned pastor).
- *pie in Domino obdormivit*: the standard formula for Christian death in religious order records; rendered verbatim.

**[Footnote]**
¹ Acts 9:15. The author applies to the late priest the Vulgate description of St. Paul — *vas electionis est mihi iste* — signalled by the explicit citation formula *ut scriptum est* ("as it is written").

**[Confidence]**
Tier 1 — High. All terms securely identified; Vulgate allusion confirmed by citation marker; dating formula resolved.

---

**[Audit Verdict]:** Sound.

**[Audit Report]:**
Critical: none · Major: none
Minor: *Frater autem* — the *autem* is transitional/adversative, marking a shift from the administrative to the commemorative. The sentence-break rendering is acceptable in Annotated mode; note for Scholarly mode.

---

### Example 2 — 12th-Century Hagiographic Miracula (Mode: Scholarly)

**Input:**

> *Erat in vicinia monasterii vir quidam paralyticus nomine Patricius, qui ab annis multis in lectulo iacebat. Audita fama virtutum quas Deus per beatum N. in loco illo operatus erat, iussit se ad tumulum sancti patris deportari. Per totam noctem ibi in oratione pernoctavit. Mane autem facto, gressum recepit et sanus ad propria rediit, glorificans Deum qui talem famulum sibi elegerat.*

---

**[Triage]**
Genre: Hagiographic — specifically a Miracula (miracles collection); narrative account of a post-mortem healing at a saint's tomb
Period: High Medieval (c.12th century); formulaic style consistent with this period
Issuing Authority: Hagiographer or monastic compiler (unknown)
Document Function: Devotional and commemorative; intended to authenticate sanctity and promote the cult
Diplomatic Status: Edited edition or clean copy; no apparent textual damage
Transcription Certainty: Clean
Register: Narrative/hagiographic; elevated but not scholastic; biblical phraseology throughout
Triage Confidence: high

**[Translation]**

There was in the vicinity of the monastery a certain paralysed man named Patrick, who had lain in his bed for many years. Having heard of the fame of the miracles which God had wrought through the blessed N. in that place, he ordered himself to be carried to the tomb of the holy father. He spent the whole night there in prayer. When morning came, he recovered the use of his limbs and returned home whole, glorifying God who had chosen for himself so great a servant.

**[Notes]**

- *virtutum*: miracles — the central lexical danger of hagiographic Latin. In a Miracula text, *virtus*/*virtutes* denotes miraculous deeds or miraculous power, not virtues in the moral sense. In a Miracula text, this sentence reports that God worked miracles through the saint, not that God demonstrated virtues through him. A classical rendering would be factually incorrect.
- *loco illo*: that place — the holy site associated with the saint (here, the tomb); *locus* in hagiographic context often carries the specific sense of a saint's holy site.
- *tumulus*: tomb — the saint's burial place and the site of the cult; not a burial mound in the prehistoric sense.
- *famulum*: servant — the standard hagiographic designation (*famulus Dei* = servant of God); a technical term of praise in saints' literature, implying election to a special relationship with God.
- *propria*: his own home — *ad propria redire* is a fixed idiom for returning to one's place of origin or household.
- *Mane autem facto*: "when morning came" — a biblical-style temporal formula, echoing the Vulgate use of *mane facto* for dawn (cf. Genesis 44:3; Mark 15:1); contributes to the elevated register.

**[Key Terms]**

| Latin | Rendered as | Note |
|---|---|---|
| virtutes | miracles | hagiographic technical term; in Miracula and miracle narrative, always "miracles" — "virtues" is a material error |
| famulus (Dei) | servant (of God) | standard hagiographic honorific |
| locus | that place | holy site; saint's tomb or shrine |
| tumulus | tomb | saint's burial place and cult site |
| propria | home | *ad propria* = fixed idiom |

**[Confidence]**
Tier 1 — High. Genre, register, and key terms unambiguous.

---

**[Audit Verdict]:** Sound.

**[Audit Report]:**
Critical: none · Major: none
Minor: *glorificans Deum qui talem famulum sibi elegerat* — "who had chosen for himself so great a servant" is defensible; alternatively "who had chosen such a servant for himself" preserves the word-order emphasis on *sibi* (for himself). Either is acceptable; the present rendering is preferred.

---

### Example 3 — 8th-Century Irish Annals Entry (Mode: Flowing)

**Input:**

> *Anno Domini DCCXLVIII. Cellach, princeps civitatis Benchorensis, dormivit in pace, vir in scripturis doctissimus et a familia totius civitatis multum dilectus. Post eum electus est Colmanus ab omni familia et in sede principis confirmatus.*

---

**[Triage]**
Genre: Annalistic — a year-entry from an Irish chronicle recording the death of a monastic superior and the election of his successor
Period: Early Medieval / Insular (748 AD)
Issuing Authority: Monastic chronicler at Bangor or a scriptorium with access to Bangor annals
Document Function: Commemorative and administrative record; preserves succession data
Diplomatic Status: Annals entry — likely a copy transmitted through later manuscripts; standard Insular annals format
Transcription Certainty: Clean; no apparent damage
Register: Terse annalistic; Hiberno-Latin; characteristic Insular vocabulary
Triage Confidence: high — Insular provenance confirmed by vocabulary (*civitas* as monastery, *princeps* as abbot, *familia* as monastic community)

**[Translation]**

748 AD. Cellach, abbot of the monastery of Bangor, fell asleep in peace — a man most learned in the scriptures and greatly beloved by the entire monastic community. After him, Colmán was elected by the whole community and confirmed in the abbot's seat.

**[Notes — key decisions]**

Three terms require explanation because a reader unfamiliar with Insular Latin will find them surprising:

- *princeps*: rendered "abbot" — in early medieval Irish texts, *princeps* is the standard title for the head of a major monastery, functioning as the governing superior of the monastic community and its dependent houses. It does not denote a secular ruler. Translating it as "prince" or "head" would imply secular political authority where the text refers to a monastic office.

- *civitas Benchorensis*: rendered "monastery of Bangor" — in Insular Latin, *civitas* denotes a major monastery and the settlement that grew around it, not a city in the Roman or modern sense. Ireland had no Roman-style cities; the great ecclesiastical centres were monastic. Bangor (*Bennchor*, Co. Down) was one of the most important monasteries in 6th–8th century Ireland. Rendering *civitas* as "city" would be a geographical anachronism.

- *familia*: rendered "monastic community" — in an Insular context, *familia* means the monastic household or community, including dependent houses under the same abbot. It is not a biological family.

- *sede principis*: rendered "abbot's seat" — the *sedes* here is the formal seat of authority, the position of the abbot; *confirmatus in sede* is the standard formula for canonical confirmation in office.

- *dormivit in pace*: "fell asleep in peace" — the Insular formula for Christian death; parallel to *obdormivit in Domino* in Continental documents; retained verbatim.

**[Confidence]**
Tier 1 — High. All Insular vocabulary securely identified; year-date (748 AD) is straightforward.

---

**[Audit Verdict]:** Sound.

**[Audit Report]:**
Critical: none · Major: none
Minor: *multum dilectus* — "greatly beloved" is natural; "much loved" preserves the Latin's simplicity more closely in a Flowing rendering, but either is acceptable.

---

## What the Skill Catches

The three examples above show the skill catching:

| Error type | Example | Classical trap | Correct rendering |
|---|---|---|---|
| Canonical false friend | *conversus* | convert | lay brother |
| Canonical false friend | *cura animarum* | care of souls (literary) | cure of souls (legal office) |
| Canonical false friend | *in religionem* | into religion | into the religious life / religious order |
| Hagiographic false friend | *virtutes* | virtues | miracles |
| Insular false friend | *civitas* | city | monastery |
| Insular false friend | *princeps* | prince | abbot |
| Insular false friend | *familia* | family | monastic community |
| Vulgate allusion | *vas electionis* | chosen vessel | "vessel of election" (Acts 9:15) |
| Dating formula | *in festo Sancti Georgii* | — | 23 April [converted] |

---

## Scope and Limitations

This skill is designed for experienced users working with real documents. It will:
- Identify and flag uncertainty rather than produce a confident wrong translation
- Note when a text is too damaged or abbreviated for reliable translation
- Distinguish between what is securely established and what is provisional

It is not a replacement for a specialist Latinist on a critical edition, but it is substantially more reliable than generic AI translation for ecclesiastical documents.

The skill does not include access to the reference dictionaries it cites (Souter, DMLBS, Niermeyer, etc.) — it applies their conventions and decision rules. When a term requires specialist dictionary verification, the skill will flag it.

---

## Structure

```
church-latin/
├── SKILL.md                         # Core instructions (triage, modes, workflow)
└── references/
    ├── period-guide.md              # Patristic through Modern
    ├── genre-guide.md               # Hagiographic, scholastic, canonical, curial, etc.
    ├── dating-system.md             # Roman calendar, indiction, feast-days, pontifical year
    ├── reference-hierarchy.md       # Which dictionary to use, by period and genre
    └── false-friends.md             # Top 20 danger list + extended glossary (~80 terms)
```
