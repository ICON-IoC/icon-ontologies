# ICON Places ontology

The areas records are placed in: California counties, USDA ecoregion sections, the HUC8 subbasins and HUC10 watersheds of the USGS Watershed Boundary Dataset, and the State Assembly, State Senate, congressional, and county supervisorial districts that elected officials represent, with statewide scope, and the links that say a record operates, applies or lies in one of them.

- Files: `icon-places.ttl` (Turtle) and `icon-places.owl` (RDF/XML), built from `src/places.terms`.
- Ontology IRI: `https://w3id.org/icon/places.owl`; this release `https://w3id.org/icon/releases/2026-11-21/places.owl`.
- Its own terms are numbered ICON:0010000 to ICON:0010999.

## Existing ontologies used

| Ontology | How | Terms |
|---|---|---|
| Environment Ontology | reused | ecoregion (`ENVO:01000276`) |
| Environment Ontology | built on | administrative region (`ENVO:00000004`), drainage basin (`ENVO:00000291`) |
| Geographical Entity Ontology | mapped to | has jurisdiction in (`GEO:000000336`) |
| Information Artifact Ontology | built on | information content entity (`IAO:0000030`) |
| Relation Ontology | built on | located in (`RO:0001025`) |
| Dublin Core terms | mapped to | Spatial Coverage (`dcterms:spatial`) |
| schema.org | mapped to | AdministrativeArea (`schema:AdministrativeArea`), areaServed (`schema:areaServed`) |

*Reused* terms are used as they are, under their own IDs. *Built on* terms are parents, domains or ranges of this module's terms. *Mapped to* terms are recorded as SKOS matches for exchange with other systems.

## Links to other ICON modules

- **Core**: uses
- **Infrastructure**: manages, owns
- **Plans**: at site

## Classes

| Term | ID | Is a | Definition | Explorer |
|---|---|---|---|---|
| county | `ICON:0010000` | administrative region (`ENVO:00000004`) | One of California's 58 counties, as an administrative region rather than as its government. close match AdministrativeArea (`schema:AdministrativeArea`). | vocab County |
| ecoregion | `ENVO:01000276` (reused) |  | Reused from ENVO. The values are the USDA Forest Service ECOMAP ecological sections in California (#38). Source: A large unit of land or water containing a geographically distinct assemblage of species, natural communities, and environmental conditions. | vocab Ecoregion |
| HUC8 subbasin | `ICON:0010001` | drainage basin (`ENVO:00000291`) | A drainage basin at the subbasin level (eight-digit hydrologic unit code) of the USGS Watershed Boundary Dataset. | vocab HUC8 |
| HUC10 watershed | `ICON:0010002` | drainage basin (`ENVO:00000291`) | A drainage basin at the watershed level (ten-digit hydrologic unit code) of the USGS Watershed Boundary Dataset. Each lies within one HUC8 subbasin. | vocab HUC10 |
| electoral district | `ICON:0010005` | administrative region (`ENVO:00000004`) | An area whose voters elect an official to a legislature or a county board: a California State Assembly, State Senate, congressional or county supervisorial district (#1432). close match AdministrativeArea (`schema:AdministrativeArea`). |  |
| State Assembly district | `ICON:0010006` | electoral district | One of the 80 districts that each elect a member of the California State Assembly, as the Citizens Redistricting Commission drew them in 2021. | vocab AssemblyDistrict |
| State Senate district | `ICON:0010007` | electoral district | One of the 40 districts that each elect a California State Senator, as the Citizens Redistricting Commission drew them in 2021. | vocab SenateDistrict |
| congressional district | `ICON:0010008` | electoral district | One of California's 52 districts that each elect a member of the U.S. House of Representatives, as the map in force draws them: the 2021 Citizens Redistricting Commission map until January 3, 2027, then the Proposition 50 (AB 604) map. | vocab CongressionalDistrict |
| supervisorial district | `ICON:0010009` | electoral district | A district of a California county that elects one member of the county's board of supervisors, as the county's own current map draws it. | vocab SupervisorialDistrict |
| geographic scope | `ICON:0010003` | information content entity (`IAO:0000030`) | An extent a record can claim in place of a list of areas. | vocab Scope |

## Relations

| Relation | ID | Reverse | From → to | Definition | Explorer |
|---|---|---|---|---|---|
| operates in | `ICON:0010100` | is place of work of | any → any | The record works in, covers or is about the area. A county cell of All in a workbook links the record to statewide instead. close match Spatial Coverage (`dcterms:spatial`); close match areaServed (`schema:areaServed`). | phrase operates in |
| is place of work of | `ICON:0010101` | operates in | any → any | The reverse of operates in. | phrase is place of work of |
| applies in | `ICON:0010102` | is jurisdiction of | any → any | A guideline, mandate or plan has force or scope in the area. close match has jurisdiction in (`GEO:000000336`). | phrase applies in |
| is jurisdiction of | `ICON:0010103` | applies in | any → any | The reverse of applies in. | phrase is jurisdiction of |
| located in area | `ICON:0010104` | is location of | any → any | A place, objective or action lies in the area. A kind of operates in, and a kind of the Relation Ontology's located in. Kind of: operates in, located in (`RO:0001025`). | phrase located in |
| is location of | `ICON:0010105` | located in area | any → any | The reverse of located in area. | phrase is location of |
| covers | `ICON:0010106` | is covered by | any → any | The record's area takes in the area. Listed with the place links since the explorer's phrase table began (#35); no link uses it at present. | phrase covers |
| is covered by | `ICON:0010107` | covers | any → any | The reverse of covers. | phrase is covered by |
| in ecoregion | `ICON:0010108` | is ecoregion of | any → ecoregion (`ENVO:01000276`) | The record works in, covers or lies in the ecoregion section. close match Spatial Coverage (`dcterms:spatial`). | phrase in ecoregion |
| is ecoregion of | `ICON:0010109` | in ecoregion | any → any | The reverse of in ecoregion. | phrase is ecoregion of |
| in subbasin | `ICON:0010110` | is subbasin of | any → HUC8 subbasin | The record works in, covers or lies in the HUC8 subbasin. close match Spatial Coverage (`dcterms:spatial`). | phrase in subbasin |
| is subbasin of | `ICON:0010111` | in subbasin | any → any | The reverse of in subbasin. | phrase is subbasin of |
| in watershed | `ICON:0010112` | is watershed of | any → HUC10 watershed | The record works in, covers or lies in the HUC10 watershed. close match Spatial Coverage (`dcterms:spatial`). | phrase in watershed |
| is watershed of | `ICON:0010113` | in watershed | any → any | The reverse of in watershed. | phrase is watershed of |

## Controlled values

| Value | ID | Kind | Definition | Explorer |
|---|---|---|---|---|
| statewide | `ICON:0010004` | geographic scope | The whole of California. A record that operates, applies or lies statewide is linked to this value rather than to every county, ecoregion, subbasin and watershed (#281). | term Statewide |
