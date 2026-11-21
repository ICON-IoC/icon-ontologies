# ICON Programs ontology

Conservation programs: ongoing arrangements, usually run by an agency, that fund, regulate, certify, plan or carry out work through many projects. Covers program types and administration.

- Files: `icon-programs.ttl` (Turtle) and `icon-programs.owl` (RDF/XML), built from `src/programs.terms`.
- Ontology IRI: `https://w3id.org/icon-ioc/programs.owl`; this release `https://w3id.org/icon-ioc/releases/2026-11-21/programs.owl`.
- Its own terms are numbered ICON:0004000 to ICON:0004999.

## Existing ontologies used

| Ontology | How | Terms |
|---|---|---|
| Ontology for Biomedical Investigations | built on | organization (`OBI:0000245`) |
| Ontology for Biomedical Investigations | mapped to | investigation (`OBI:0000066`) |
| Funding, Research Administration and Projects Ontology (FRAPO) | mapped to | funding programme (`frapo:FundingProgramme`) |

*Reused* terms are used as they are, under their own IDs. *Built on* terms are parents, domains or ranges of this module's terms. *Mapped to* terms are recorded as SKOS matches for exchange with other systems.

## Links to other ICON modules

- **Core**: endeavor, is involved with
- **Infrastructure**: infrastructure

## Classes

| Term | ID | Is a | Definition | Explorer |
|---|---|---|---|---|
| conservation program | `ICON:0004000` | endeavor (Core) | An ongoing arrangement, usually run by an agency, that funds, regulates, certifies, plans or carries out conservation work through many projects or participants, with no set end. | class Program; vocab ProgType |
| acquisition program | `ICON:0004001` | conservation program | A program that buys land, water or easements, or pays others to. | term Acquisition |
| certification program | `ICON:0004002` | conservation program | A program that certifies land, products or practices against a standard. | term Certification |
| education program | `ICON:0004003` | conservation program | A program that teaches the public, students or practitioners. | term Education |
| funding program | `ICON:0004004` | conservation program | A program that pays for others' conservation work, as a grant or cost-share program. close match funding programme (`frapo:FundingProgramme`). | term Funding |
| habitat enhancement program | `ICON:0004005` | conservation program | A program that restores or improves habitat. | term Habitat Enhancement |
| management program | `ICON:0004006` | conservation program | A program that manages land, water or wildlife over time. | term Management |
| planning program | `ICON:0004007` | conservation program | A program that prepares plans, such as regional conservation planning. | term Planning |
| regulatory program | `ICON:0004008` | conservation program | A program that issues permits or enforces rules. | term Regulatory |
| research program | `ICON:0004009` | conservation program | A program that studies or monitors nature or conservation. close match investigation (`OBI:0000066`). | term Research |
| technical assistance program | `ICON:0004010` | conservation program | A program that gives free expert help rather than money, so that communities, Tribes, and organizations can plan projects, build capacity, and apply for and manage funding. Example: the U.S. Environmental Protection Agency's Water Technical Assistance (WaterTA). | term Technical Assistance |

## Relations

| Relation | ID | Reverse | From → to | Definition | Explorer |
|---|---|---|---|---|---|
| has program type | `ICON:0004100` | is program type of | conservation program → any | Links a program to one of the program type classes it belongs to. The explorer's way of stating the program's class. | phrase has program type |
| is program type of | `ICON:0004101` | has program type | any → any | The reverse of has program type. | phrase is program type of |
| administered by | `ICON:0004102` | administers | conservation program → organization (`OBI:0000245`) | The organization that runs the program. Kind of: is involved with (Core). | phrase administered by |
| administers | `ICON:0004103` | administered by | any → any | The reverse of administered by. Kind of: is involved with (Core). | phrase administers |
| operates at | `ICON:0004104` | hosts program | conservation program → infrastructure (Infrastructure) | A place where the program does its work, such as a river a restoration program works along, a groundwater basin a banking program recharges, or a camera array a research program runs. | phrase operates at |
| hosts program | `ICON:0004105` | operates at | infrastructure (Infrastructure) → conservation program | The reverse of operates at. | phrase hosts program |
