# ICON Papers and reports ontology

Peer-reviewed papers and technical reports: authors, publishers and sponsors, what a work describes, which data it uses, which works it cites, and where its study was done.

- Files: `icon-publications.ttl` (Turtle) and `icon-publications.owl` (RDF/XML), built from `src/publications.terms`.
- Ontology IRI: `https://w3id.org/icon-ioc/publications.owl`; this release `https://w3id.org/icon-ioc/releases/2026-11-21/publications.owl`.
- Its own terms are numbered ICON:0009000 to ICON:0009999.

## Existing ontologies used

| Ontology | How | Terms |
|---|---|---|
| Information Artifact Ontology | built on | journal article (`IAO:0000013`), information content entity (`IAO:0000030`), report (`IAO:0000088`), is about (`IAO:0000136`), document (`IAO:0000310`) |
| Ontology for Biomedical Investigations | built on | organization (`OBI:0000245`) |
| Bibliographic Ontology (BIBO) | reused | doi (`bibo:doi`), issue (`bibo:issue`), pages (`bibo:pages`), volume (`bibo:volume`) |
| Bibliographic Ontology (BIBO) | mapped to | Academic Article (`bibo:AcademicArticle`), Document (`bibo:Document`), Report (`bibo:Report`), list of authors (`bibo:authorList`), number (`bibo:number`) |
| Citation Typing Ontology (CiTO) | mapped to | cites (`cito:cites`), describes (`cito:describes`), is cited by (`cito:isCitedBy`), provides data for (`cito:providesDataFor`), uses data from (`cito:usesDataFrom`) |
| Dublin Core terms | reused | Abstract (`dcterms:abstract`) |
| Dublin Core terms | built on | Access Rights (`dcterms:accessRights`), Date Issued (`dcterms:issued`), License (`dcterms:license`) |
| Dublin Core terms | mapped to | Creator (`dcterms:creator`) |
| FRBR-aligned Bibliographic Ontology (FaBiO) | mapped to | journal article (`fabio:JournalArticle`), technical report (`fabio:TechnicalReport`), work (`fabio:Work`) |
| schema.org | reused | keywords (`schema:keywords`) |
| schema.org | mapped to | CreativeWork (`schema:CreativeWork`), Report (`schema:Report`), ScholarlyArticle (`schema:ScholarlyArticle`), about (`schema:about`), author (`schema:author`), citation (`schema:citation`), isBasedOn (`schema:isBasedOn`), isPartOf (`schema:isPartOf`), spatialCoverage (`schema:spatialCoverage`), sponsor (`schema:sponsor`) |

*Reused* terms are used as they are, under their own IDs. *Built on* terms are parents, domains or ranges of this module's terms. *Mapped to* terms are recorded as SKOS matches for exchange with other systems.

## Links to other ICON modules

- **Core**: agent, information resource, is involved with
- **Data**: data resource
- **Infrastructure**: infrastructure
- **Tools**: tool

## Classes

| Term | ID | Is a | Definition | Explorer |
|---|---|---|---|---|
| paper or report | `ICON:0009000` | information resource (Core), document (`IAO:0000310`) | A written work that reports research, monitoring or assessment: a peer-reviewed paper or a technical report. Shown in the explorer as Papers & reports. close match Document (`bibo:Document`); close match work (`fabio:Work`); close match CreativeWork (`schema:CreativeWork`). | class Publication; vocab PublicationType |
| peer-reviewed paper | `ICON:0009001` | paper or report, journal article (`IAO:0000013`) | An article that independent experts reviewed before a journal or conference published it. A work counts as one only if its journal certainly peer-reviewed it. close match Academic Article (`bibo:AcademicArticle`); close match journal article (`fabio:JournalArticle`); close match ScholarlyArticle (`schema:ScholarlyArticle`). | term Peer-reviewed paper |
| technical report | `ICON:0009002` | paper or report, report (`IAO:0000088`) | A report an agency, organization or research group issues itself on a study, a monitoring program, an assessment or a project's results, usually in a numbered series. It may or may not have been reviewed. close match Report (`bibo:Report`); close match technical report (`fabio:TechnicalReport`); close match Report (`schema:Report`). | term Technical report |
| publication availability | `ICON:0009010` | information content entity (`IAO:0000030`) | Who can read a paper or report. Values follow the open-access status Unpaywall and Crossref report. |  |

## Relations

| Relation | ID | Reverse | From → to | Definition | Explorer |
|---|---|---|---|---|---|
| has publication type | `ICON:0009100` | is publication type of | paper or report → any | Links a paper or report to the class it belongs to: peer-reviewed paper or technical report. The explorer's way of stating its class. | phrase has publication type |
| is publication type of | `ICON:0009101` | has publication type | any → any | The reverse of has publication type. | phrase is publication type of |
| authored by | `ICON:0009102` | authored | paper or report → agent (Core) | A person or organization that wrote the work. The full author list as printed is the authors attribute, since most authors have no record of their own. close match Creator (`dcterms:creator`); close match author (`schema:author`). Kind of: is involved with (Core). | phrase authored by |
| authored | `ICON:0009103` | authored by | any → any | The reverse of authored by. Kind of: is involved with (Core). | phrase authored |
| commissioned by | `ICON:0009104` | commissioned | paper or report → organization (`OBI:0000245`) | The organization a technical report was prepared for, when someone else wrote it, as a consultant's report for an agency. close match sponsor (`schema:sponsor`). Kind of: is involved with (Core). | phrase commissioned by |
| commissioned | `ICON:0009105` | commissioned by | any → any | The reverse of commissioned by. Kind of: is involved with (Core). | phrase commissioned |
| describes | `ICON:0009106` | is described by | paper or report → any | The work is about this project, program, organization or data resource: it reports, evaluates or documents it. A data paper describes its dataset. close match describes (`cito:describes`); close match about (`schema:about`). Kind of: is about (`IAO:0000136`). | phrase describes |
| is described by | `ICON:0009107` | describes | any → any | The reverse of describes. | phrase is described by |
| uses data from | `ICON:0009108` | provides data for | paper or report, tool (Tools) → data resource (Data) | The work's analysis, or the tool, draws on this dataset, database or repository. For a tool, the workbook's inDataset column. close match uses data from (`cito:usesDataFrom`); close match isBasedOn (`schema:isBasedOn`). | phrase uses data from |
| provides data for | `ICON:0009109` | uses data from | any → any | The reverse of uses data from. close match provides data for (`cito:providesDataFor`). | phrase provides data for |
| cites | `ICON:0009110` | is cited by | paper or report → paper or report | The work cites another paper or report in the graph. exact match cites (`cito:cites`); close match citation (`schema:citation`). | phrase cites |
| is cited by | `ICON:0009111` | cites | any → any | The reverse of cites. exact match is cited by (`cito:isCitedBy`). | phrase is cited by |
| studied at | `ICON:0009112` | is study site of | paper or report → infrastructure (Infrastructure) | A place where the work's field study or monitoring was done, such as a reserve, a creek or a dam. close match spatialCoverage (`schema:spatialCoverage`). | phrase studied at |
| is study site of | `ICON:0009113` | studied at | any → any | The reverse of studied at. | phrase is study site of |

## Attributes

| Attribute | ID | Definition | Explorer |
|---|---|---|---|
| authors | `ICON:0009200` | The author list as printed on the work: Smith, J., Lee, K. and Ortiz, M. Public bibliographic information, not contact details. close match list of authors (`bibo:authorList`). | field publication.authors |
| published in | `ICON:0009201` | The journal a paper appeared in, or the series a report belongs to, by name: Conservation Biology, USGS Open-File Report. Kept as text: journals are not records in the graph. close match isPartOf (`schema:isPartOf`). | field publication.published_in |
| report number | `ICON:0009202` | A report's number in its series, such as 2019-1123. close match number (`bibo:number`). | field publication.report_number |
| volume | `bibo:volume` (reused) |  | field publication.volume |
| issue | `bibo:issue` (reused) |  | field publication.issue |
| pages | `bibo:pages` (reused) |  | field publication.pages |
| doi | `bibo:doi` (reused) | Written without the https://doi.org/ prefix. | field publication.doi |
| Abstract | `dcterms:abstract` (reused) |  | field publication.abstract |
| keywords | `schema:keywords` (reused) |  | field publication.keywords |

## Controlled values

| Value | ID | Kind | Definition | Explorer |
|---|---|---|---|---|
| open access publication | `ICON:0009011` | publication availability | Anyone can read it free from the publisher or a repository. | choice Open access |
| free to read publication | `ICON:0009012` | publication availability | Free to read on the publisher's site but without an open license. | choice Free to read |
| subscription or purchase publication | `ICON:0009013` | publication availability | Behind a journal paywall. | choice Subscription or purchase |
| publication on request | `ICON:0009014` | publication availability | The authors or issuing agency send it when asked. | choice On request |
| publication not public | `ICON:0009015` | publication availability | Internal or restricted. | choice Not public |
