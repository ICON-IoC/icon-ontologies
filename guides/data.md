# ICON Data ontology

Data resources at three levels (dataset, database, data repository): who creates, publishes, hosts, funds and uses them, what they cover in time, space and subject, and how they derive from and hold one another.

- Files: `icon-data.ttl` (Turtle) and `icon-data.owl` (RDF/XML), built from `src/data.terms`.
- Ontology IRI: `https://w3id.org/icon/data.owl`; this release `https://w3id.org/icon/releases/2026-11-21/data.owl`.
- Its own terms are numbered ICON:0008000 to ICON:0008999.

## Existing ontologies used

| Ontology | How | Terms |
|---|---|---|
| Information Artifact Ontology | built on | information content entity (`IAO:0000030`), data collection (`IAO:0001000`) |
| Ontology for Biomedical Investigations | built on | organization (`OBI:0000245`) |
| EU access-right authority list | mapped to | non-public (`access:NON_PUBLIC`), public (`access:PUBLIC`), restricted (`access:RESTRICTED`) |
| DCAT 3 (W3C Data Catalog Vocabulary) | reused | keyword (`dcat:keyword`), temporal resolution (`dcat:temporalResolution`), version (`dcat:version`) |
| DCAT 3 (W3C Data Catalog Vocabulary) | mapped to | Catalog (`dcat:Catalog`), Dataset (`dcat:Dataset`), Catalogued resource (`dcat:Resource`), dataset (`dcat:dataset`), end date (`dcat:endDate`), spatial resolution (meters) (`dcat:spatialResolutionInMeters`), start date (`dcat:startDate`) |
| Dublin Core terms | reused | Accrual Periodicity (`dcterms:accrualPeriodicity`), Identifier (`dcterms:identifier`) |
| Dublin Core terms | built on | Frequency (`dcterms:Frequency`), Access Rights (`dcterms:accessRights`), Description (`dcterms:description`), Date Issued (`dcterms:issued`), License (`dcterms:license`) |
| Dublin Core terms | mapped to | Conforms To (`dcterms:conformsTo`), Format (`dcterms:format`), Spatial Coverage (`dcterms:spatial`), Type (`dcterms:type`) |
| EU frequency authority list | reused | annual (`freq:ANNUAL`), biennial (`freq:BIENNIAL`), continuous (`freq:CONT`), daily (`freq:DAILY`), irregular (`freq:IRREG`), monthly (`freq:MONTHLY`), never (`freq:NEVER`), quarterly (`freq:QUARTERLY`), quinquennial (`freq:QUINQUENNIAL`), weekly (`freq:WEEKLY`) |
| PROV-O (W3C provenance) | mapped to | wasDerivedFrom (`prov:wasDerivedFrom`) |
| schema.org | mapped to | CreativeWork (`schema:CreativeWork`), DataCatalog (`schema:DataCatalog`), Dataset (`schema:Dataset`), includedInDataCatalog (`schema:includedInDataCatalog`), isBasedOn (`schema:isBasedOn`), provider (`schema:provider`) |

*Reused* terms are used as they are, under their own IDs. *Built on* terms are parents, domains or ranges of this module's terms. *Mapped to* terms are recorded as SKOS matches for exchange with other systems.

## Links to other ICON modules

- **Core**: information resource
- **Infrastructure**: infrastructure
- **Guidelines and mandates**: guideline or mandate

## Classes

| Term | ID | Is a | Definition | Explorer |
|---|---|---|---|---|
| data resource | `ICON:0008000` | information resource (Core) | Data at any of three levels: a dataset, a database or a data repository. Replaced the PPOD Dataset class. close match Catalogued resource (`dcat:Resource`); close match CreativeWork (`schema:CreativeWork`). | class Data; vocab DataLevel |
| dataset | `ICON:0008001` | data resource, data collection (`IAO:0001000`) | One collection of data published as a unit by its creator, such as a map layer, a table or a time series. Example: Cropland Data Layer. close match Dataset (`dcat:Dataset`); close match Dataset (`schema:Dataset`). | term Dataset |
| database | `ICON:0008002` | data resource, data collection (`IAO:0001000`) | A maintained collection of related datasets kept together under one design, usually by one organization and usually queryable. Its datasets are part of it. Example: California Natural Diversity Database. close match Dataset (`dcat:Dataset`); close match Dataset (`schema:Dataset`). | term Database |
| data repository | `ICON:0008003` | data resource | A platform that holds and publishes datasets and databases, often from many creators. Example: CDFW BIOS. close match Catalog (`dcat:Catalog`); close match DataCatalog (`schema:DataCatalog`). | term Data repository |
| data type | `ICON:0008080` | information content entity (`IAO:0000030`) | The kind of data, or the form it comes in. One list holds both, so a Data record and a tool's input or output are described in the same terms and a dataset can be matched to the tools that take it: Land cover or vegetation map and Raster describe both the Cropland Data Layer and an input InVEST takes. close match Type (`dcterms:type`). | vocab DataType |
| data format | `ICON:0008010` | data type | The form data comes in, from the Terms sheet's dataset types; formats are data types, listed with the kinds of data (#304). DCAT records format on each downloadable distribution; the graph keeps it on the data until a resource has more than one form worth recording. |  |
| data access level | `ICON:0008020` | information content entity (`IAO:0000030`) | Who can get the data. The Dataset Dictionary's Availability. Each value maps to the EU access-right list and to the DCAT-US access levels data.gov uses. |  |
| temporal resolution value | `ICON:0008030` | information content entity (`IAO:0000030`) | How far apart in time the data's values are. Each value carries, as a cross-reference, the ISO 8601 duration that dcat:temporalResolution takes on export. |  |
| social unit | `ICON:0008040` | information content entity (`IAO:0000030`) | A unit of people or property that social data is recorded for. The analysis unit of DDI Discovery. |  |

## Relations

| Relation | ID | Reverse | From → to | Definition | Explorer |
|---|---|---|---|---|---|
| has data level | `ICON:0008100` | is data level of | data resource → any | Links a data resource to the level class it belongs to: dataset, database or data repository. The explorer's way of stating its class, so it can filter and colour by level. | phrase has data level |
| is data level of | `ICON:0008101` | has data level | any → any | The reverse of has data level. | phrase is data level of |
| has data type | `ICON:0008102` | is data type of | data resource → data type | A kind of data the record is, or the form it comes in, from the Data type list. close match Type (`dcterms:type`); close match Format (`dcterms:format`). | phrase has data type |
| is data type of | `ICON:0008103` | has data type | any → any | The reverse of has data type. | phrase is data type of |
| is held in | `ICON:0008104` | holds | data resource → data repository | A dataset, database or smaller repository is held and published by a repository. One resource can be held in several. close match includedInDataCatalog (`schema:includedInDataCatalog`). | phrase is held in |
| holds | `ICON:0008105` | is held in | any → any | The reverse of is held in. close match dataset (`dcat:dataset`). | phrase holds |
| is hosted by | `ICON:0008106` | hosts | data resource → organization (`OBI:0000245`) | The organization that runs the systems the data is served from. The Dataset Dictionary's Host role. close match provider (`schema:provider`). | phrase is hosted by |
| hosts | `ICON:0008107` | is hosted by | any → any | The reverse of is hosted by. | phrase hosts |
| is derived from | `ICON:0008108` | is source of | data resource → data resource | Data built from other data, such as a connectivity map made from land cover and roads. close match wasDerivedFrom (`prov:wasDerivedFrom`); close match isBasedOn (`schema:isBasedOn`). | phrase is derived from |
| is source of | `ICON:0008109` | is derived from | any → any | The reverse of is derived from. | phrase is source of |
| conforms to | `ICON:0008110` | is followed by | any → guideline or mandate (Guidelines and mandates) | A standard or guideline a data resource, tool, plan or plan action follows, recorded as a guideline: a data standard such as Darwin Core or the FGDC metadata standard, the policy whose required analyses a tool carries out, the agency guide a plan was written to, or the guidelines an action says to follow. close match Conforms To (`dcterms:conformsTo`). | phrase conforms to |
| is followed by | `ICON:0008111` | conforms to | any → any | The reverse of conforms to. | phrase is followed by |
| has extent | `ICON:0008112` | is extent of | data resource → infrastructure (Infrastructure) | A place whose boundary is the data's extent, such as a watershed or a preserve. close match Spatial Coverage (`dcterms:spatial`). | phrase has extent |
| is extent of | `ICON:0008113` | has extent | any → any | The reverse of has extent. | phrase is extent of |
| collected at | `ICON:0008114` | is collection site of | data resource → infrastructure (Infrastructure) | A place where the data was gathered, such as a monitoring station. | phrase collected at |
| is collection site of | `ICON:0008115` | collected at | any → any | The reverse of collected at. | phrase is collection site of |
| social resolution | `ICON:0008204` |  | data resource → social unit | The smallest social unit the data describes or can be broken down to, such as household or census tract. | field data.social_resolution |

## Attributes

| Attribute | ID | Definition | Explorer |
|---|---|---|---|
| purpose | `ICON:0008200` | Why the data was made. | field data.purpose |
| coverage start | `ICON:0008201` | The first year the data describes. With coverage end, the Dataset Dictionary's Time Period; exported as dcterms:temporal with a dcat:startDate. close match start date (`dcat:startDate`). | field data.coverage_start |
| coverage end | `ICON:0008202` | The last year the data describes; blank while it is still being added to. close match end date (`dcat:endDate`). | field data.coverage_end |
| spatial resolution | `ICON:0008203` | Grid cell size, mapping unit or positional accuracy, written with its unit: 30 m for C-CAP, 4 km for gridMET. Converted to dcat:spatialResolutionInMeters on export when the unit is a length. close match spatial resolution (meters) (`dcat:spatialResolutionInMeters`). | field data.spatial_resolution |
| Identifier | `dcterms:identifier` (reused) | A DOI or the repository's own accession number. | field data.identifier |
| version | `dcat:version` (reused) | Source: The version indicator (name or identifier) of a resource. | field data.version |
| Accrual Periodicity | `dcterms:accrualPeriodicity` (reused) | How often the data is updated, as a value of the EU frequency list above. | field data.update_frequency |
| temporal resolution | `dcat:temporalResolution` (reused) | How far apart in time the values are, as a temporal resolution value above. Source: minimum time period resolvable in a dataset. | field data.temporal_resolution |
| keyword | `dcat:keyword` (reused) | Free words for search, beside the issues the data addresses. Source: A keyword or tag describing a resource. | field data.keywords |

## Controlled values

| Value | ID | Kind | Definition | Explorer |
|---|---|---|---|---|
| observation records | `ICON:0008081` | data type | Individual sightings or detections of a species or feature, each with a place and a date, such as CNDDB occurrences or camera trap detections. | term Observation records |
| survey and monitoring data | `ICON:0008082` | data type | Measurements taken by a protocol across sites or over time: counts, plots, catch, water samples. | term Survey and monitoring data |
| species range or distribution | `ICON:0008083` | data type | Where a species lives or is known to occur, mapped as a range or distribution. | term Species range or distribution |
| habitat suitability model | `ICON:0008084` | data type | Modelled predictions of where habitat is suitable for a species or community. | term Habitat suitability model |
| land cover or vegetation map | `ICON:0008085` | data type | A map of what covers the land: vegetation types, crops, forest structure, developed and bare ground. | term Land cover or vegetation map |
| satellite and aerial imagery | `ICON:0008086` | data type | Images of the ground taken from satellites, aircraft or drones, and products derived directly from them. | term Satellite and aerial imagery |
| elevation model | `ICON:0008087` | data type | A surface of ground elevation, slope or water depth (bathymetry). | term Elevation model |
| climate grids and projections | `ICON:0008088` | data type | Gridded climate variables, observed or projected, such as temperature, precipitation or evapotranspiration. | term Climate grids and projections |
| stream and water network | `ICON:0008089` | data type | Mapped streams, rivers, lakes, wetlands and the barriers, diversions and conveyances on them. | term Stream and water network |
| sensor time series | `ICON:0008090` | data type | Readings over time from gauges, weather stations or other sensors. | term Sensor time series |
| boundaries and areas | `ICON:0008091` | data type | Administrative, planning, regulatory and survey boundaries, and the areas a user draws or picks. | term Boundaries and areas |
| parcels and ownership | `ICON:0008092` | data type | Land parcels and records of who owns or holds rights in them, such as easements. | term Parcels and ownership |
| infrastructure locations | `ICON:0008093` | data type | Mapped locations of built structures and facilities: roads, ports, crossings, stations, platforms. | term Infrastructure locations |
| scenarios and settings | `ICON:0008094` | data type | Choices a user enters: practices, targets, parameters, costs, management or development scenarios. | term Scenarios and settings |
| estimates and indices | `ICON:0008095` | data type | Computed values: estimates of carbon, cost or yield, and scores, ranks or indices that compare places or options. | term Estimates and indices |
| project records | `ICON:0008096` | data type | Records of conservation projects: where they are, what they do, their funding and status. | term Project records |
| funding opportunities | `ICON:0008097` | data type | Listings of grants, loans and other funding that people can apply for: the funder, what it pays for, award size and deadline. | term Funding opportunities |
| image data format | `ICON:0008011` | data format | Photographs or scanned images. | term Images |
| raster data format | `ICON:0008012` | data format | A grid of cells, each with a value, such as a land cover map or a climate surface. | term Raster |
| shapefile data format | `ICON:0008013` | data format | Points, lines or polygons with attributes, in the Esri shapefile or a similar vector format. | term Shapefile |
| tabular data format | `ICON:0008014` | data format | Rows and columns, as a spreadsheet or a database table. | term Tabular |
| map data format | `ICON:0008015` | data format | A finished map, interactive on the web or printed, made for people to read rather than as data to analyse. Mostly a tool's output. | term Map |
| report data format | `ICON:0008016` | data format | A written document, such as a PDF report or a site summary. Mostly a tool's output. | term Report |
| open data access | `ICON:0008021` | data access level | Anyone can download the data without signing in. close match public (`access:PUBLIC`). | choice Open |
| open access with registration | `ICON:0008022` | data access level | The data is free after creating an account or accepting terms. broad match public (`access:PUBLIC`). | choice Open with registration |
| sensitive locations withheld | `ICON:0008023` | data access level | The data is published with sensitive detail, such as rare species locations, generalized or held back unless a request is approved. broad match restricted (`access:RESTRICTED`). | choice Sensitive locations withheld |
| access by request or license | `ICON:0008024` | data access level | The data is available only through an agreement, a subscription or a fee. close match restricted (`access:RESTRICTED`). | choice By request or license |
| data not public | `ICON:0008025` | data access level | The data is held for its creator's own use. close match non-public (`access:NON_PUBLIC`). | choice Not public |
| hourly resolution | `ICON:0008031` | temporal resolution value | A value every hour. | choice Hourly |
| daily resolution | `ICON:0008032` | temporal resolution value | A value every day. | choice Daily |
| weekly resolution | `ICON:0008033` | temporal resolution value | A value every week. | choice Weekly |
| monthly resolution | `ICON:0008034` | temporal resolution value | A value every month. | choice Monthly |
| annual resolution | `ICON:0008035` | temporal resolution value | A value every year. | choice Annual |
| multi-year resolution | `ICON:0008036` | temporal resolution value | Values for periods longer than a year, such as decades. | choice Multi-year |
| single snapshot | `ICON:0008037` | temporal resolution value | One point or period in time. | choice Single snapshot |
| continuous | `freq:CONT` (reused) | Frequency (`dcterms:Frequency`) | Updated continuously. Source: The item is updated more frequent than daily. | choice Continuous |
| daily | `freq:DAILY` (reused) | Frequency (`dcterms:Frequency`) | Source: The event occurs once a day. | choice Daily |
| weekly | `freq:WEEKLY` (reused) | Frequency (`dcterms:Frequency`) | Source: The event occurs once a week. | choice Weekly |
| monthly | `freq:MONTHLY` (reused) | Frequency (`dcterms:Frequency`) | Source: The event occurs once a month. | choice Monthly |
| quarterly | `freq:QUARTERLY` (reused) | Frequency (`dcterms:Frequency`) | Source: The event occurs every three months. | choice Quarterly |
| annual | `freq:ANNUAL` (reused) | Frequency (`dcterms:Frequency`) | Source: The event occurs once a year. | choice Annual |
| biennial | `freq:BIENNIAL` (reused) | Frequency (`dcterms:Frequency`) | Source: The event occurs every two years. | choice Every two years |
| quinquennial | `freq:QUINQUENNIAL` (reused) | Frequency (`dcterms:Frequency`) | Source: The event occurs every five years. | choice Every five years |
| irregular | `freq:IRREG` (reused) | Frequency (`dcterms:Frequency`) | Source: The event occurs at uneven intervals. | choice Irregular |
| never | `freq:NEVER` (reused) | Frequency (`dcterms:Frequency`) | Finished data, which most PPOD datasets are. Dublin Core's own frequency list has no such value, which is why the EU list is used. Source: The item is never updated. | choice Never (finished) |
| individual person unit | `ICON:0008041` | social unit | Data recorded person by person. | choice Individual |
| household unit | `ICON:0008042` | social unit | Data recorded household by household. | choice Household |
| parcel or landowner unit | `ICON:0008043` | social unit | Data recorded by land parcel or landowner. | choice Parcel or landowner |
| organization unit | `ICON:0008044` | social unit | Data recorded organization by organization. | choice Organization |
| census block group unit | `ICON:0008045` | social unit | Data recorded by Census block group. | choice Census block group |
| census tract unit | `ICON:0008046` | social unit | Data recorded by Census tract. | choice Census tract |
| city or town unit | `ICON:0008047` | social unit | Data recorded by city or town. | choice City or town |
| county unit | `ICON:0008048` | social unit | Data recorded by county. | choice County |
