# ICON Tools ontology

Software people use to plan, assess and track conservation work: decision-support tools, map viewers, dashboards, calculators and models, and software packages. Covers who builds and uses them, the issues they address, and the data they take in and produce.

- Files: `icon-tools.ttl` (Turtle) and `icon-tools.owl` (RDF/XML), built from `src/tools.terms`.
- Ontology IRI: `https://w3id.org/icon-ioc/tools.owl`; this release `https://w3id.org/icon-ioc/releases/2026-11-21/tools.owl`.
- Its own terms are numbered ICON:0013000 to ICON:0013999.

## Existing ontologies used

| Ontology | How | Terms |
|---|---|---|
| Information Artifact Ontology | built on | software (`IAO:0000010`), information content entity (`IAO:0000030`), software application (`IAO:0000594`) |
| Dublin Core terms | built on | Description (`dcterms:description`) |
| PROV-O (W3C provenance) | mapped to | wasGeneratedBy (`prov:wasGeneratedBy`) |
| schema.org | mapped to | SoftwareApplication (`schema:SoftwareApplication`), WebApplication (`schema:WebApplication`), applicationCategory (`schema:applicationCategory`), featureList (`schema:featureList`) |

*Reused* terms are used as they are, under their own IDs. *Built on* terms are parents, domains or ranges of this module's terms. *Mapped to* terms are recorded as SKOS matches for exchange with other systems.

## Links to other ICON modules

- **Core**: information resource
- **Data**: data resource, data type

## Classes

| Term | ID | Is a | Definition | Explorer |
|---|---|---|---|---|
| tool | `ICON:0013000` | information resource (Core), software (`IAO:0000010`) | Software people use to plan, assess or track conservation work: a decision-support tool, a map viewer, a dashboard, a calculator or model, a software package or an identification key. A site whose main job is holding and serving data is a data repository, not a tool; a tool that works with such data links to it. Read from the master PPOD workbook's Tools sheet. close match SoftwareApplication (`schema:SoftwareApplication`). | class Tool; vocab ToolType |
| decision-support tool | `ICON:0013001` | tool | A tool that helps choose where or how to act: it ranks or prioritizes sites, compares scenarios, or screens a proposal against conservation values. Example: Ecosystem Management Decision Support System. | term Decision-support tool |
| map viewer | `ICON:0013002` | tool, software application (`IAO:0000594`) | A web application for browsing and querying map layers. Example: Wetlands Mapper. close match WebApplication (`schema:WebApplication`). | term Map viewer |
| dashboard | `ICON:0013003` | tool, software application (`IAO:0000594`) | A web page that tracks a set of indicators in charts and maps, often over time. Example: California Carbon Dashboard. close match WebApplication (`schema:WebApplication`). | term Dashboard |
| calculator or model | `ICON:0013004` | tool | A tool that computes an estimate from its user's inputs or runs a model, such as the carbon a riparian planting stores or the habitat a site provides. Example: Carbon in Riparian Ecosystems Estimator for California. | term Calculator or model |
| software package | `ICON:0013006` | tool | Software its users install and run themselves, such as an R package, a desktop program or a trained model, rather than use on the web. Example: InVEST. close match SoftwareApplication (`schema:SoftwareApplication`). | term Software package |
| identification key | `ICON:0013007` | tool | A guide that leads its user, step by step or by comparing pictures, to the name of a plant or animal they have found. Example: Berkeley BioKeys. | term Identification key |
| tool function | `ICON:0013010` | information content entity (`IAO:0000030`) | What a tool does for its user, such as prioritizing places or estimating carbon. A tool can have several. close match featureList (`schema:featureList`). | vocab ToolFunction |

## Relations

| Relation | ID | Reverse | From → to | Definition | Explorer |
|---|---|---|---|---|---|
| has tool type | `ICON:0013100` | is tool type of | tool → any | Links a tool to a kind of tool it is. A tool can be of several kinds, as a map viewer that also prioritizes sites. close match applicationCategory (`schema:applicationCategory`). | phrase has tool type |
| is tool type of | `ICON:0013101` | has tool type | any → any | The reverse of has tool type. | phrase is tool type of |
| produces | `ICON:0013102` | is produced by | tool → data resource (Data) | The tool creates or serves this data: the layers a map viewer publishes, the estimates a calculator outputs. The workbook's outDataset column. | phrase produces |
| is produced by | `ICON:0013103` | produces | any → any | The reverse of produces. close match wasGeneratedBy (`prov:wasGeneratedBy`). | phrase is produced by |
| has tool function | `ICON:0013104` | is tool function of | tool → any | Links a tool to something it does for its user. | phrase has tool function |
| is tool function of | `ICON:0013105` | has tool function | any → any | The reverse of has tool function. | phrase is tool function of |
| takes input | `ICON:0013106` | is input to | tool → data type (Data) | A kind of data, or a format, the tool takes in, from the Data type list that also describes Data records, so data can be matched to the tools that take it. A specific Data record the tool uses is a uses data from link instead. | phrase takes input |
| is input to | `ICON:0013107` | takes input | any → any | The reverse of takes input. | phrase is input to |
| gives output | `ICON:0013108` | is output from | tool → data type (Data) | A kind of data, or a format, the tool gives back, from the Data type list. A specific Data record the tool creates is a produces link instead. | phrase gives output |
| is output from | `ICON:0013109` | gives output | any → any | The reverse of gives output. | phrase is output from |

## Controlled values

| Value | ID | Kind | Definition | Explorer |
|---|---|---|---|---|
| prioritizing function | `ICON:0013011` | tool function | Ranks or scores places, sites or projects so the best ones can be chosen first. | term Prioritize places or projects |
| screening function | `ICON:0013012` | tool function | Checks a proposed project against rules, sensitive resources or eligibility criteria before it goes ahead. | term Screen a project |
| carbon estimating function | `ICON:0013013` | tool function | Calculates carbon stored or greenhouse gases emitted or avoided. | term Estimate carbon or greenhouse gases |
| projecting function | `ICON:0013014` | tool function | Shows how conditions may change under future climate, sea level rise or land use. | term Project future conditions |
| habitat quantifying function | `ICON:0013015` | tool function | Measures how much habitat there is and how good it is. | term Quantify habitat |
| mapping function | `ICON:0013016` | tool function | Shows where resources, conditions or hazards are, for browsing and querying. | term Map resources or hazards |
| vulnerability assessing function | `ICON:0013017` | tool function | Judges how exposed and sensitive people, places or species are to a threat. | term Assess vulnerability or risk |
| scenario comparing function | `ICON:0013018` | tool function | Runs alternative management or development choices side by side to weigh their effects. | term Compare scenarios |
| recommending function | `ICON:0013019` | tool function | Suggests what to do or plant, such as fertilizer rates, seedlots or meadow species. | term Recommend practices or species |
| tracking function | `ICON:0013020` | tool function | Records projects, prices or indicators over time and reports on them. | term Track projects or indicators |
| species detecting function | `ICON:0013021` | tool function | Finds and counts animals or plants, as in images. | term Detect or count species |
| funding application function | `ICON:0013022` | tool function | Helps applicants build a proposal or meet the requirements of a grant program. | term Prepare a funding application |
