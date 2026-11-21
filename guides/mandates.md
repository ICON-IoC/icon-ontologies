# ICON Guidelines and mandates ontology

Laws, regulations, executive orders, agreements, certifications and guidelines that require, allow, fund or shape conservation work, and the ways organizations stand toward them: bound by, implementing, enforcing, issuing, certified by.

- Files: `icon-mandates.ttl` (Turtle) and `icon-mandates.owl` (RDF/XML), built from `src/mandates.terms`.
- Ontology IRI: `https://w3id.org/icon/mandates.owl`; this release `https://w3id.org/icon/releases/2026-11-21/mandates.owl`.
- Its own terms are numbered ICON:0006000 to ICON:0006999.

## Existing ontologies used

| Ontology | How | Terms |
|---|---|---|
| Information Artifact Ontology | built on | information content entity (`IAO:0000030`), directive information entity (`IAO:0000033`) |
| Ontology for Biomedical Investigations | built on | organization (`OBI:0000245`) |
| Ontology of Medically Related Social Entities | mapped to | contract (`OMRSE:00000089`) |
| European Legislation Identifier (ELI) | mapped to | Legal Resource (`eli:LegalResource`), passed by (`eli:passed_by`) |
| schema.org | mapped to | Legislation (`schema:Legislation`) |

*Reused* terms are used as they are, under their own IDs. *Built on* terms are parents, domains or ranges of this module's terms. *Mapped to* terms are recorded as SKOS matches for exchange with other systems.

## Links to other ICON modules

- **Core**: is involved with
- **Projects**: conservation project

## Classes

| Term | ID | Is a | Definition | Explorer |
|---|---|---|---|---|
| guideline or mandate | `ICON:0006000` | directive information entity (`IAO:0000033`) | A directive that requires, allows, funds or shapes conservation work: a law, regulation, executive order, agreement, certification standard or guideline. Some bind; others only advise. close match Legal Resource (`eli:LegalResource`); close match Legislation (`schema:Legislation`). | class GuidelineMandate; class Rule; vocab GMType |
| agreement | `ICON:0006001` | guideline or mandate | A guideline or mandate that two or more parties sign, such as a memorandum of understanding, a settlement or a habitat conservation plan's implementing agreement. close match contract (`OMRSE:00000089`). | term Agreement |
| certification standard | `ICON:0006002` | guideline or mandate | A guideline or mandate that sets the practices land, products or operations must meet to be certified, such as a sustainable farming or forestry standard. | term Certification |
| executive order | `ICON:0006003` | guideline or mandate | A guideline or mandate that a president or governor issues to direct government agencies. | term Executive Order |
| guideline | `ICON:0006004` | guideline or mandate | A guideline or mandate that recommends how something should be done without binding anyone. | term Guidelines |
| legislation | `ICON:0006005` | guideline or mandate | A guideline or mandate that a legislature or the voters enact: a statute, an act, a ballot measure. close match Legislation (`schema:Legislation`). | term Legislation |
| regulation | `ICON:0006006` | guideline or mandate | A guideline or mandate that an agency adopts under authority a statute gives it, with the force of law, as in the California Code of Regulations. | term Regulation |
| agency rule | `ICON:0006007` | guideline or mandate | A guideline or mandate that a body adopts to govern its own lands, programs or members, short of a codified regulation. | term Rule |
| court order | `ICON:0006008` | guideline or mandate | A guideline or mandate that a court issues in a case, such as a writ of mandate or an injunction, directing a party, often a government agency, to act or to stop acting. It binds the parties named in it. Example: the 2025 writ of mandate in California Chaparral Institute v. Board of Forestry and Fire Protection, which limits the California Vegetation Treatment Program in chaparral and coastal sage scrub. | term Court order |
| government level | `ICON:0006010` | information content entity (`IAO:0000030`) | The level of government a guideline or mandate comes from or applies at. | vocab GovLevel |

## Relations

| Relation | ID | Reverse | From → to | Definition | Explorer |
|---|---|---|---|---|---|
| has instrument type | `ICON:0006100` | is instrument type of | guideline or mandate → any | Links a guideline or mandate to one of the instrument type classes it belongs to. The explorer's way of stating its class. | phrase has instrument type |
| is instrument type of | `ICON:0006101` | has instrument type | any → any | The reverse of has instrument type. | phrase is instrument type of |
| at government level | `ICON:0006102` | is government level of | guideline or mandate → government level | The level of government a guideline or mandate comes from. | phrase at government level |
| is government level of | `ICON:0006103` | at government level | any → any | The reverse of at government level. | phrase is government level of |
| is required by | `ICON:0006104` | requires | any → guideline or mandate | A guideline or mandate requires this data, publication or plan to be produced, as the Endangered Species Act requires recovery plans. | phrase is required by |
| requires | `ICON:0006105` | is required by | any → any | The reverse of is required by. | phrase requires |
| is bound by | `ICON:0006106` | binds | any → guideline or mandate | A guideline or mandate binds the organization: it must comply with it. A project, program or other record is bound by a mandate only when a source says so for that record. | phrase is bound by |
| binds | `ICON:0006107` | is bound by | any → any | The reverse of is bound by. | phrase binds |
| implements | `ICON:0006108` | is implemented by | any → any | An organization, project, program or guideline or mandate carries out a guideline or mandate or a plan, as a program carries out the statute that authorizes it or the certification it runs, or a regulation carries out the statute that requires it. Kind of: is involved with (Core). | phrase implements |
| is implemented by | `ICON:0006109` | implements | any → any | The reverse of implements. Kind of: is involved with (Core). | phrase is implemented by |
| enforces | `ICON:0006110` | is enforced by | any → any | An organization holds the authority to enforce a guideline or mandate. | phrase enforces |
| is enforced by | `ICON:0006111` | enforces | any → any | The reverse of enforces. | phrase is enforced by |
| issued | `ICON:0006112` | was issued by | any → any | An organization issued a guideline, mandate or plan: adopted, signed or published it. | phrase issued |
| was issued by | `ICON:0006113` | issued | any → any | The reverse of issued. close match passed by (`eli:passed_by`). | phrase was issued by |
| is supported by | `ICON:0006114` | supports | any → any | An organization's work rests on a guideline or mandate, as a program on the statute that authorizes it. | phrase is supported by |
| supports | `ICON:0006115` | is supported by | any → any | The reverse of is supported by. | phrase supports |
| advises about | `ICON:0006116` | is advised about by | any → any | An organization gives advice on how to meet or apply a guideline or mandate. | phrase advises about |
| is advised about by | `ICON:0006117` | advises about | any → any | The reverse of advises about. | phrase is advised about by |
| is certified by | `ICON:0006118` | certifies | any → any | An organization, or a place such as a ranch or preserve, holds certification under a certification standard. | phrase is certified by |
| certifies | `ICON:0006119` | is certified by | any → any | The reverse of is certified by. | phrase certifies |
| funds established by | `ICON:0006120` |  | any → guideline or mandate | An organization pays out money a guideline or mandate set up, as a board awarding bond-measure grants. | phrase funds established by |
| sponsored | `ICON:0006121` | was sponsored by | organization (`OBI:0000245`) → guideline or mandate | An organization sponsored a bill or ballot measure: it brought the proposal to the legislator who carried it, or campaigned for the measure, and backed it to passage. | phrase sponsored |
| was sponsored by | `ICON:0006122` | sponsored | guideline or mandate → organization (`OBI:0000245`) | The reverse of sponsored. | phrase was sponsored by |
| is authorized under | `ICON:0006123` | authorizes | conservation project (Projects) → guideline or mandate | A project went ahead under a permit, order, biological opinion or exemption that approved its work, such as a restoration project covered by a programmatic biological opinion or a nationwide permit. | phrase is authorized under |
| authorizes | `ICON:0006124` | is authorized under | guideline or mandate → conservation project (Projects) | The reverse of is authorized under. | phrase authorizes |

## Controlled values

| Value | ID | Kind | Definition | Explorer |
|---|---|---|---|---|
| federal level | `ICON:0006011` | government level | The United States government. | term Federal |
| state level | `ICON:0006012` | government level | The State of California. | term State |
| local level | `ICON:0006013` | government level | Counties, cities and special districts. | term Local |
| private level | `ICON:0006014` | government level | No government: a standard or agreement set by private parties. | term Private |
| international level | `ICON:0006015` | government level | An agreement among national governments, such as a treaty or a decision of the parties to a convention. Example: the Kunming-Montreal Global Biodiversity Framework (2022), adopted under the Convention on Biological Diversity. | term International |
