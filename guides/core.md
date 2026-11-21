# ICON Core ontology

The shared top of the ICON ontologies: the broad kinds of record (agent, endeavor, place, information resource, planning element), the involvement and funding links every kind of record uses, and the annotation properties the other modules share. Every other module builds on it.

- Files: `icon-core.ttl` (Turtle) and `icon-core.owl` (RDF/XML), built from `src/core.terms`.
- Ontology IRI: `https://w3id.org/icon/core.owl`; this release `https://w3id.org/icon/releases/2026-11-21/core.owl`.
- Its own terms are numbered ICON:0000000 to ICON:0000999.

## Existing ontologies used

| Ontology | How | Terms |
|---|---|---|
| Basic Formal Ontology | reused | entity (`BFO:0000001`), part of (`BFO:0000050`), has part (`BFO:0000051`) |
| Basic Formal Ontology | built on | independent continuant (`BFO:0000004`), material entity (`BFO:0000040`) |
| Core Ontology for Biology and Biomedicine | built on | planned process (`COB:0000082`) |
| Information Artifact Ontology | built on | information content entity (`IAO:0000030`), directive information entity (`IAO:0000033`) |
| NCBI organismal classification | built on | Homo sapiens (`NCBITaxon:9606`) |
| Ontology for Biomedical Investigations | reused | has specified output (`OBI:0000299`), is specified output of (`OBI:0000312`) |
| Ontology for Biomedical Investigations | built on | organization (`OBI:0000245`) |
| Relation Ontology | reused | location of (`RO:0001015`), located in (`RO:0001025`), overlaps (`RO:0002131`) |
| DCAT 3 (W3C Data Catalog Vocabulary) | mapped to | Catalogued resource (`dcat:Resource`) |
| Dublin Core terms | reused | Access Rights (`dcterms:accessRights`), Description (`dcterms:description`), Date Issued (`dcterms:issued`), License (`dcterms:license`) |
| Dublin Core terms | mapped to | Creator (`dcterms:creator`), Relation (`dcterms:relation`) |
| FOAF | mapped to | Agent (`foaf:Agent`) |
| Funding, Research Administration and Projects Ontology (FRAPO) | mapped to | endeavour (`frapo:Endeavour`), funds (`frapo:funds`), is funded by (`frapo:isFundedBy`) |
| PROV-O (W3C provenance) | mapped to | Agent (`prov:Agent`) |
| schema.org | reused | endDate (`schema:endDate`), startDate (`schema:startDate`), url (`schema:url`) |
| schema.org | mapped to | CreativeWork (`schema:CreativeWork`), Place (`schema:Place`), creator (`schema:creator`), funder (`schema:funder`) |
| SKOS | reused | Concept (`skos:Concept`), alternative label (`skos:altLabel`), note (`skos:note`) |

*Reused* terms are used as they are, under their own IDs. *Built on* terms are parents, domains or ranges of this module's terms. *Mapped to* terms are recorded as SKOS matches for exchange with other systems.

## Links to other ICON modules

None: this module stands alone.

## Classes

| Term | ID | Is a | Definition | Explorer |
|---|---|---|---|---|
| agent | `ICON:0000010` | material entity (`BFO:0000040`) | An organization or a person: something that can lead, fund, own, manage or take part in conservation work. close match Agent (`prov:Agent`); close match Agent (`foaf:Agent`). | class Agent |
| endeavor | `ICON:0000011` | planned process (`COB:0000082`) | A planned process carried out to achieve conservation ends over a span of time: a project or a program. close match endeavour (`frapo:Endeavour`). | class Endeavor |
| place | `ICON:0000012` | independent continuant (`BFO:0000004`) | A part of the landscape or a structure in it that records can be located at, worked on or bounded by: a river, a reserve, a dam, a crossing structure. close match Place (`schema:Place`). | class Place |
| information resource | `ICON:0000013` | information content entity (`IAO:0000030`) | An information content entity that records or publishes information: a data resource, a paper or a report. close match Catalogued resource (`dcat:Resource`); close match CreativeWork (`schema:CreativeWork`). | class InformationResource |
| planning element | `ICON:0000014` | directive information entity (`IAO:0000033`) | A directive information entity that sets out what conservation work should achieve or do: a plan, one of its objectives, or one of its actions. | class Strategy |
| entity | `BFO:0000001` (reused) |  | The explorer's top class Resource, which every record belongs to. | class Resource |
| Concept | `skos:Concept` (reused) |  | A value of a controlled vocabulary in the explorer (a Term node): a county, an issue, a taxon, an organization type. Source: An idea or notion; a unit of thought. | class Term; class Concept |

## Relations

| Relation | ID | Reverse | From → to | Definition | Explorer |
|---|---|---|---|---|---|
| is involved with | `ICON:0000100` |  | any → any | A link between two records that work together or affect one another. Every more specific involvement link (leads, funds, manages, uses, is partner of and others) implies it. broad match Relation (`dcterms:relation`). (symmetric) | phrase is involved with |
| led by | `ICON:0000101` | leads | any → agent | An organization or person that directs the work and answers for it. Kind of: is involved with. | phrase led by |
| leads | `ICON:0000102` | led by | any → any | An organization or person directs this work: the reverse of led by. Kind of: is involved with. | phrase leads |
| used by | `ICON:0000103` | uses | any → any | An organization, project or program relies on this place, data or tool in its work. Kind of: is involved with. | phrase used by |
| uses | `ICON:0000104` | used by | any → any | The record relies on this place or data in its work: the reverse of used by. Kind of: is involved with. | phrase uses |
| funded by | `ICON:0000105` | funds | any → any | An organization or funding source that paid for the work, the data or the publication. close match is funded by (`frapo:isFundedBy`); close match funder (`schema:funder`). Kind of: is involved with. | phrase funded by |
| funds | `ICON:0000106` | funded by | any → any | The organization or funding source pays for this work, data or publication: the reverse of funded by and of funded through. close match funds (`frapo:funds`). Kind of: is involved with. | phrase funds |
| funded through | `ICON:0000107` |  | any → any | A program or a guideline or mandate whose money paid for the work, such as a grant program or a bond measure. A kind of funded by, naming the channel the money came through. Kind of: funded by. | phrase funded through |
| was created by | `ICON:0000108` | created | any → any | The organization or person that produced the record's subject, or the guideline or mandate that brought an organization into being. close match Creator (`dcterms:creator`); close match creator (`schema:creator`). Kind of: is involved with. | phrase was created by |
| created | `ICON:0000109` | was created by | any → any | The organization, person or mandate produced this: the reverse of was created by. Kind of: is involved with. | phrase created |
| informs | `ICON:0000110` | is informed by | any → any | The data or publication is drawn on by a plan, an objective, an action or a guideline or mandate, as survey counts inform a recovery objective. broad match Relation (`dcterms:relation`). | phrase informs |
| is informed by | `ICON:0000111` | informs | any → any | The plan, objective, action or mandate draws on this data or publication: the reverse of informs. | phrase is informed by |
| part of | `BFO:0000050` (reused) |  | any → any | A record belongs to a larger one of the same kind: an agency to its department, a dataset to its database, a sub-action to its action. Transitive. Source: a core relation that holds between a part and its whole | phrase is part of |
| has part | `BFO:0000051` (reused) |  | any → any | The reverse of part of. Source: a core relation that holds between a whole and its part | phrase has part |
| located in | `RO:0001025` (reused) |  | any → any | Spatial containment between places, as a HUC10 watershed within its HUC8 subbasin or a project area within a reserve. Transitive. Source: a relation between two independent continuants, the target and the location, in which the target is entirely within the location | phrase is contained within |
| location of | `RO:0001015` (reused) |  | any → any | The reverse of located in: a place contains another. Source: a relation between two independent continuants, the location and the target, in which the target is entirely within the location | phrase contains |
| overlaps | `RO:0002131` (reused) |  | any → any | Two places share some area without either containing the other, as a creek crossing a county line. Symmetric. Source: x overlaps y if and only if there exists some z such that x has part z and z part of y | phrase intersects |
| is specified output of | `OBI:0000312` (reused) |  | any → any | Data, a publication or a plan produced by a project's or program's work. Source: A relation between a completely executed planned process and a continuant participating in that process. The presence of the continuant at the end of the process is explicitly specified in the objective specification which the process realizes the concretization of. | phrase is output of |
| has specified output | `OBI:0000299` (reused) |  | any → any | The reverse of is specified output of: the project or program produced this. Source: The inverse property of is specified output of | phrase has output |

## Attributes

| Attribute | ID | Definition | Explorer |
|---|---|---|---|
| crosswalk | `ICON:0000001` | The matching field in a metadata standard that is not published as RDF, written as the standard's name, a colon and the field's path, such as "EML 2.2: dataset/title". |  |
| expected attribute | `ICON:0000002` | A property the records of this class are expected to carry, such as a title or a year. Records the attributes a class uses without adding domain axioms to terms borrowed from other vocabularies. |  |
| label | `rdfs:label` (reused) | Every record's name. | field node.name |
| alternative label | `skos:altLabel` (reused) | Other names a record goes by. Source: An alternative lexical label for a resource. | field node.alias |
| url | `schema:url` (reused) | The record's web page. | field node.url |
| startDate | `schema:startDate` (reused) | The year a record or link began (#98). The explorer keeps a year, not a full date. | field node.start_year; field relation.start_year |
| endDate | `schema:endDate` (reused) | The year a record or link ended (#98). | field node.end_year; field relation.end_year |
| note | `skos:note` (reused) | Free notes on an organization, a place or a taxon, and where an IUCN GET unit occurs. Source: A general note, for any purpose. | field organization.notes; field infrastructure.notes; field taxon.note; field get_unit.distribution |
| Date Issued | `dcterms:issued` (reused) | The year a mandate was enacted, data released, a paper published or a plan issued. | field guideline_mandate.year; field data.year; field publication.year; field plan.year |
| Access Rights | `dcterms:accessRights` (reused) | Who can get the data or read the publication; values from the Data and Papers and reports modules' access lists. | field data.availability; field publication.availability |
| License | `dcterms:license` (reused) | The license data or a publication is released under. | field data.license; field publication.license |
| Description | `dcterms:description` (reused) | What data contains, or what a tool does. | field data.description; field tool.description |
