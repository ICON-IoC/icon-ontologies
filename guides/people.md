# ICON People ontology

People named in the graph: whom they are affiliated with, whom they are the contact for, and the leadership roles they hold. Names are public; contact details are kept out of the graph's public face and out of this ontology.

- Files: `icon-people.ttl` (Turtle) and `icon-people.owl` (RDF/XML), built from `src/people.terms`.
- Ontology IRI: `https://w3id.org/icon-ioc/people.owl`; this release `https://w3id.org/icon-ioc/releases/2026-11-21/people.owl`.
- Its own terms are numbered ICON:0002000 to ICON:0002999.

## Existing ontologies used

| Ontology | How | Terms |
|---|---|---|
| Environment Ontology | built on | ecoregion (`ENVO:01000276`) |
| NCBI organismal classification | reused | Homo sapiens (`NCBITaxon:9606`) |
| Ontology for Biomedical Investigations | built on | organization (`OBI:0000245`) |
| Ontology of Medically Related Social Entities | built on | role in human social processes (`OMRSE:00002072`) |
| DCAT 3 (W3C Data Catalog Vocabulary) | mapped to | contact point (`dcat:contactPoint`) |
| FOAF | mapped to | Person (`foaf:Person`), account (`foaf:account`) |
| W3C Organization Ontology | mapped to | Role (`org:Role`), role (`org:role`) |
| schema.org | mapped to | Person (`schema:Person`), affiliation (`schema:affiliation`), identifier (`schema:identifier`), knowsAbout (`schema:knowsAbout`) |

*Reused* terms are used as they are, under their own IDs. *Built on* terms are parents, domains or ranges of this module's terms. *Mapped to* terms are recorded as SKOS matches for exchange with other systems.

## Links to other ICON modules

- **Taxa and habitats**: CWHR habitat type, coastal and marine habitat type, has broader habitat type, taxon, vegetation type
- **Core**: is involved with
- **Issues**: conservation issue, has broader issue
- **Places**: county, electoral district, geographic scope

## Classes

| Term | ID | Is a | Definition | Explorer |
|---|---|---|---|---|
| Homo sapiens | `NCBITaxon:9606` (reused) |  | Reused from the NCBI taxonomy, as OBO ontologies do for a person: the explorer's Person class. Only names are public; email and phone are never served. close match Person (`foaf:Person`); close match Person (`schema:Person`). | class Person |
| leadership role | `ICON:0002001` | role in human social processes (`OMRSE:00002072`) | A role in human social processes that a person holds when an organization, project or program puts them in charge of some part of it. close match Role (`org:Role`). |  |
| chief executive role | `ICON:0002002` | leadership role | Heads the record's staff or operations: executive director, CEO, staff president, general manager, agency director or secretary, city manager, and the manager of a field office, region, refuge or preserve that is itself the record. | roletype Chief executive |
| deputy executive role | `ICON:0002003` | leadership role | Second in the staff line: deputy, associate or assistant director, chief operating officer, undersecretary or deputy secretary, assistant or associate field manager. | roletype Deputy executive |
| board chair role | `ICON:0002004` | leadership role | Chairs the governing board, council or commission: chair, chairman, board president, tribal chair. | roletype Board chair |
| board officer role | `ICON:0002005` | leadership role | An officer of the governing board other than its chair: vice chair, vice president of the board, secretary, treasurer. | roletype Board officer |
| program leader role | `ICON:0002006` | leadership role | Leads a program, division or department within the record: program director, manager or coordinator, branch chief, program area chair. | roletype Program leader |
| project leader role | `ICON:0002007` | leadership role | Leads a particular project: project manager, project coordinator, project lead. | roletype Project leader |
| science leader role | `ICON:0002008` | leadership role | Leads the record's science: principal investigator, lead or chief scientist, science director. | roletype Science leader |
| elected official role | `ICON:0002009` | role in human social processes (`OMRSE:00002072`) | Holds an office the voters of a district or the state elect to: Assemblymember, State Senator, U.S. Representative, U.S. Senator, county supervisor. | roletype Elected official |

## Relations

| Relation | ID | Reverse | From → to | Definition | Explorer |
|---|---|---|---|---|---|
| is affiliated with | `ICON:0002100` | has affiliate | Homo sapiens (`NCBITaxon:9606`) → organization (`OBI:0000245`) | A person works for, serves on the board of, or is otherwise attached to an organization. The link may carry the person's title and its role type. close match affiliation (`schema:affiliation`). Kind of: is involved with (Core). | phrase is affiliated with |
| has affiliate | `ICON:0002101` | is affiliated with | any → any | The reverse of is affiliated with. Kind of: is involved with (Core). | phrase has affiliate |
| has contact | `ICON:0002102` | is contact for | any → Homo sapiens (`NCBITaxon:9606`) | The person to ask about an organization, project, place or data resource. The person's contact details are private. close match contact point (`dcat:contactPoint`). Kind of: is involved with (Core). | phrase has contact |
| is contact for | `ICON:0002103` | has contact | any → any | The reverse of has contact. Kind of: is involved with (Core). | phrase is contact for |
| has expertise in | `ICON:0002104` | is expertise of | Homo sapiens (`NCBITaxon:9606`) → conservation issue (Issues), county (Places), ecoregion (`ENVO:01000276`), taxon (Taxa and habitats), CWHR habitat type (Taxa and habitats), vegetation type (Taxa and habitats), coastal and marine habitat type (Taxa and habitats) | A person knows an issue, a place, a taxon or a habitat type through their work: the projects, programs and plans they lead and the papers and reports they wrote address it, or the source records say so. Expertise is never passed down from the organizations a person belongs to. close match knowsAbout (`schema:knowsAbout`). | phrase has expertise in |
| is expertise of | `ICON:0002105` | has expertise in | any → any | The reverse of has expertise in. | phrase is expertise of |
| represents | `ICON:0002106` | is represented by | Homo sapiens (`NCBITaxon:9606`) → electoral district (Places), geographic scope (Places) | An elected official holds the seat of the district: a member of the State Assembly or State Senate, a member of Congress, or a county supervisor. A U.S. senator represents the whole state (#1432). | phrase represents |
| is represented by | `ICON:0002107` | represents | any → any | The reverse of represents. | phrase is represented by |

## Attributes

| Attribute | ID | Definition | Explorer |
|---|---|---|---|
| role title | `ICON:0002200` | A person's title in the role a link records, as the organization or project writes it: Executive Director, Principal Investigator. close match role (`org:role`). | field relation.role |
| role type | `ICON:0002201` | The uniform kind of a role a link records, one of the leadership roles below, so titles that differ in wording can be compared. | field relation.role_type |
| LinkedIn profile | `ICON:0002300` | The address of the person's public LinkedIn profile: https://www.linkedin.com/in/name. close match account (`foaf:account`). | field person.linkedin |
| ORCID iD | `ICON:0002301` | The person's ORCID identifier, the persistent researcher id used by journals and funders: 0000-0002-1825-0097. close match identifier (`schema:identifier`). | field person.orcid |
