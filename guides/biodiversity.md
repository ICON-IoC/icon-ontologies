# ICON Taxa and habitats ontology

The living things and habitats records concern: taxa (species and groups, identified by NatureServe) habitat types (California Wildlife Habitat Relationships), vegetation types (Manual of California Vegetation alliances under the US National Vegetation Classification) coastal and marine habitat types (CMECS) and the IUCN Global Ecosystem Typology, the links between those classifications, and the links that say a record concerns a taxon or a habitat type, or that a place is habitat for a taxon.

- Files: `icon-biodiversity.ttl` (Turtle) and `icon-biodiversity.owl` (RDF/XML), built from `src/biodiversity.terms`.
- Ontology IRI: `https://w3id.org/icon-ioc/biodiversity.owl`; this release `https://w3id.org/icon-ioc/releases/2026-11-21/biodiversity.owl`.
- Its own terms are numbered ICON:0011000 to ICON:0011999.

## Existing ontologies used

| Ontology | How | Terms |
|---|---|---|
| Environment Ontology | built on | habitat (`ENVO:01000739`) |
| Information Artifact Ontology | built on | information content entity (`IAO:0000030`) |
| Population and Community Ontology | built on | taxon as collection of organisms (`PCO:0000059`) |
| Dublin Core terms | mapped to | Identifier (`dcterms:identifier`), Subject (`dcterms:subject`) |
| Darwin Core | reused | Scientific Name (`dwc:scientificName`), Taxon ID (`dwc:taxonID`), Vernacular Name (`dwc:vernacularName`) |
| Darwin Core | mapped to | Taxon (`dwc:Taxon`) |
| SKOS | reused | definition (`skos:definition`) |
| SKOS | built on | note (`skos:note`) |
| SKOS | mapped to | has broader match (`skos:broadMatch`), has broader (`skos:broader`), has narrower match (`skos:narrowMatch`), has narrower (`skos:narrower`), notation (`skos:notation`), has related (`skos:related`) |

*Reused* terms are used as they are, under their own IDs. *Built on* terms are parents, domains or ranges of this module's terms. *Mapped to* terms are recorded as SKOS matches for exchange with other systems.

## Links to other ICON modules

None: this module stands alone.

## Classes

| Term | ID | Is a | Definition | Explorer |
|---|---|---|---|---|
| taxon | `ICON:0011000` | taxon as collection of organisms (`PCO:0000059`) | A species or a group of species that records concern, identified by its NatureServe element where it has one. Groups (salmonids, bats) are taxa at a higher rank or informal groupings of them. close match Taxon (`dwc:Taxon`). | vocab Taxa |
| CWHR habitat type | `ICON:0011001` | habitat (`ENVO:01000739`) | A habitat type of the California Wildlife Habitat Relationships system, the state's standard classification of wildlife habitats (59 types, such as Valley Foothill Riparian or Blue Oak Woodland), identified by its CWHR code. | vocab Habitat |
| vegetation type | `ICON:0011004` | habitat (`ENVO:01000739`) | A unit of vegetation: an alliance of the Manual of California Vegetation, as CDFW's California Natural Communities List names it (such as Valley oak woodland and forest, or Fremont's goldfields - Downingia vernal pools), or a group, macrogroup or division of the US National Vegetation Classification above it (#1409). | vocab Vegetation |
| coastal and marine habitat type | `ICON:0011005` | habitat (`ENVO:01000739`) | A unit of the Coastal and Marine Ecological Classification Standard (CMECS, FGDC-STD-018-2012): a system, subsystem or tidal zone of its Aquatic Setting (such as Estuarine Coastal Intertidal Tidal Zone), or a biotic setting, class, subclass or group of its Biotic Component (such as Seagrass Bed), identified by its CMECS ID (#1410). | vocab CMECS |
| IUCN ecosystem type | `ICON:0011006` | habitat (`ENVO:01000739`) | A unit of the IUCN Global Ecosystem Typology 2.0 (Keith et al. 2022), the global classification of ecosystems by how they function: one of its 11 realms (such as Terrestrial), 25 biomes (such as Savannas and grasslands biome) or 110 ecosystem functional groups (such as T4.4 Temperate woodlands), identified by its GET code and IRI (#1411). | vocab GET |
| invasive rating | `ICON:0011002` | information content entity (`IAO:0000030`) | How invasive a non-native species is in California: for plants, the California Invasive Plant Council (Cal-IPC) rating in its Inventory, High, Moderate, Limited, or Watch for a plant at high risk of becoming invasive (#410); for animals, listing by the California Department of Fish and Wildlife (CDFW), which does not rate them (#435). | vocab InvasiveRating |
| California Rare Plant Rank | `ICON:0011003` | information content entity (`IAO:0000030`) | The California Native Plant Society's rank of how rare a plant, bryophyte, or lichen is in California, from 1A (presumed extirpated or extinct) to 4 (a watch list of limited distribution), assigned with CDFW's California Natural Diversity Database and printed in its Special Vascular Plants, Bryophytes, and Lichens List. The decimal threat rank that follows it (.1 seriously, .2 moderately, .3 not very threatened) is kept as the link's source note (#1210). | vocab RarePlantRank |

## Relations

| Relation | ID | Reverse | From → to | Definition | Explorer |
|---|---|---|---|---|---|
| concerns taxon | `ICON:0011100` | is taxon of | any → taxon | The record is about, works for or affects the species or group. close match Subject (`dcterms:subject`). | phrase concerns taxon |
| is taxon of | `ICON:0011101` | concerns taxon | any → any | The reverse of concerns taxon. | phrase is taxon of |
| has habitat type | `ICON:0011102` | is habitat type of | any → CWHR habitat type, vegetation type, coastal and marine habitat type | A CWHR habitat type (#169), vegetation type (#1409) or coastal and marine habitat type (#1410) the record covers, works in or affects. close match Subject (`dcterms:subject`). | phrase has habitat type |
| is habitat type of | `ICON:0011103` | has habitat type | any → any | The reverse of has habitat type. | phrase is habitat type of |
| has broader habitat type | `ICON:0011108` | has narrower habitat type | CWHR habitat type, vegetation type, coastal and marine habitat type, IUCN ecosystem type → CWHR habitat type, vegetation type, coastal and marine habitat type, IUCN ecosystem type | Links a habitat or vegetation type to a broader one that contains it: an MCV alliance to its USNVC group, a group to its macrogroup, a CMECS unit to the unit above it, a GET functional group to its biome and a biome to its realm, and an alliance or CMECS unit to the one CWHR habitat type it falls in. A record that has the narrower type has the broader one too (#1409, #1410, #1411). exact match has broader (`skos:broader`). | phrase has broader habitat type |
| has narrower habitat type | `ICON:0011109` | has broader habitat type | any → any | The reverse of has broader habitat type. exact match has narrower (`skos:narrower`). | phrase has narrower habitat type |
| is related to habitat type | `ICON:0011110` |  | CWHR habitat type, vegetation type, coastal and marine habitat type → CWHR habitat type, vegetation type, coastal and marine habitat type | Links an MCV alliance or CMECS unit to each CWHR habitat type it may fall in, when there is more than one: a stand of it falls within one of them, but not always the same one. Nothing passes along it (#1409, #1410). exact match has related (`skos:related`). (symmetric) | phrase is related to habitat type |
| has IUCN ecosystem group | `ICON:0011111` | is IUCN ecosystem group of | CWHR habitat type, vegetation type, coastal and marine habitat type → IUCN ecosystem type | Links a CWHR, MCV or CMECS habitat type to the IUCN GET ecosystem functional groups it falls in, or to the biome or realm when it spans several of their groups. Mapped by hand in reference/get-crosswalk.csv at the broadest unit where the match holds and stated on every unit below it. Nothing passes along it: records are not tagged with GET (#1411). exact match has broader match (`skos:broadMatch`). | phrase has IUCN ecosystem group |
| is IUCN ecosystem group of | `ICON:0011112` | has IUCN ecosystem group | any → any | The reverse of has IUCN ecosystem group. exact match has narrower match (`skos:narrowMatch`). | phrase is IUCN ecosystem group of |
| has invasive rating | `ICON:0011104` | is invasive rating of | taxon → invasive rating | The taxon is invasive in California, or at risk of becoming so, with this Cal-IPC rating (#410) or CDFW listing (#435). | phrase has invasive rating |
| is invasive rating of | `ICON:0011105` | has invasive rating | any → any | The reverse of has invasive rating. | phrase is invasive rating of |
| has rare plant rank | `ICON:0011106` | is rare plant rank of | taxon → California Rare Plant Rank | The plant, bryophyte, or lichen has this California Rare Plant Rank in CDFW's Special Vascular Plants, Bryophytes, and Lichens List (#1210). | phrase has rare plant rank |
| is rare plant rank of | `ICON:0011107` | has rare plant rank | any → any | The reverse of has rare plant rank. | phrase is rare plant rank of |

## Attributes

| Attribute | ID | Definition | Explorer |
|---|---|---|---|
| Scientific Name | `dwc:scientificName` (reused) | Source: The full scientific name, with authorship and date information if known. When forming part of a dwc:Identification, this should be the name in lowest level taxonomic rank that can be determined. | field taxon.scientific_name; field vegetation_type.scientific_name |
| Vernacular Name | `dwc:vernacularName` (reused) | The common name. Source: A common or vernacular name. | field taxon.common_name |
| Taxon ID | `dwc:taxonID` (reused) | The NatureServe element global ID. Source: An identifier for a dwc:Taxon. | field taxon.natureserve_id |
| NatureServe global rank | `ICON:0011200` | The taxon's NatureServe conservation status across its whole range, G1 (critically imperiled) to G5 (secure), with T ranks for subspecies. | field taxon.g_rank |
| taxon kind | `ICON:0011201` | Whether the term is a single NatureServe taxon (taxon), a group of taxa (group), or matched nothing in NatureServe (none). | field taxon.kind |
| informal group | `ICON:0011202` | NatureServe's informal taxonomy path for the taxon, such as Animals \| Vertebrates \| Birds. | field taxon.informal_group |
| group level | `ICON:0011203` | For a group, what defines it: NatureServe's informal taxonomy, or a rank of its scientific taxonomy (kingdom, phylum, class, order, family, subfamily, genus). | field taxon.group_level |
| group value | `ICON:0011204` | For a group, the name at its group level, such as Salmoninae for a subfamily group. | field taxon.group_value |
| genera | `ICON:0011205` | For a subfamily group, which NatureServe cannot search by rank, the genera it spans, separated by semicolons: Oncorhynchus; Salmo; Salvelinus. | field taxon.genera |
| vegetation classification level | `ICON:0011210` | Where the vegetation type sits: an MCV Alliance, Semi-Natural Alliance (dominated by non-native plants) or Special Stands, or a USNVC Group, Macrogroup or Division. | field vegetation_type.level |
| CDFW CaCode | `ICON:0011211` | The alliance's code on CDFW's California Natural Communities List, such as 71.035.00 for Valley oak woodland and forest. | field vegetation_type.cacode |
| life form | `ICON:0011212` | The alliance's primary life form on the Natural Communities List: Tree, Shrub, Herb or Non-vascular. | field vegetation_type.life_form |
| natural community global rank | `ICON:0011213` | How rare and threatened the alliance is across its whole range, G1 (very rare and threatened) to G5 (secure), from NatureServe's method as CDFW applies it. | field vegetation_type.g_rank |
| natural community state rank | `ICON:0011214` | How rare and threatened the alliance is in California, S1 to S5; SNA for a semi-natural alliance, which is not ranked. | field vegetation_type.s_rank |
| sensitive natural community | `ICON:0011215` | Yes for an alliance with a state rank of S1 to S3, which CDFW counts as a sensitive natural community for environmental review under CEQA. | field vegetation_type.sensitive |
| CMECS classification level | `ICON:0011220` | Where the CMECS unit sits: a System, Subsystem or Tidal Zone of the Aquatic Setting, or a Biotic Setting, Biotic Class, Biotic Subclass or Biotic Group of the Biotic Component. | field cmecs_unit.level |
| CMECS code | `ICON:0011221` | The unit's code in the CMECS Catalog, its component's letter (A for the Aquatic Setting, B for the Biotic Component) followed by its unit code, such as B2.5.2.1 for Seagrass Bed. exact match notation (`skos:notation`). | field cmecs_unit.code |
| CMECS ID | `ICON:0011222` | The unit's permanent identifier in the CMECS Catalog, such as CMECS_00000721; https://w3id.org/CMECS/ followed by it is the unit's IRI. close match Identifier (`dcterms:identifier`). | field cmecs_unit.cmecs_id |
| GET classification level | `ICON:0011230` | Where the IUCN GET unit sits: a Realm, a Biome or a Functional group (an ecosystem functional group). | field get_unit.level |
| GET code | `ICON:0011231` | The unit's code in the IUCN Global Ecosystem Typology: a realm's letters (T, or MT for a transitional realm), a biome's (T4) or a functional group's (T4.4). exact match notation (`skos:notation`). | field get_unit.code |
| GET IRI | `ICON:0011232` | The unit's permanent identifier in the IUCN GET SKOS vocabulary, such as https://w3id.org/iucn-get/EFG_T4_4. close match Identifier (`dcterms:identifier`). | field get_unit.iri |
| definition | `skos:definition` (reused) | A CMECS unit's definition in the CMECS Catalog, or an IUCN GET unit's description in its profile. Source: A statement or formal explanation of the meaning of a concept. | field cmecs_unit.definition; field get_unit.definition |

## Controlled values

| Value | ID | Kind | Definition | Explorer |
|---|---|---|---|---|
| high invasive rating | `ICON:0011010` | invasive rating | Cal-IPC: severe ecological impacts on physical processes, plant and animal communities and vegetation structure, with rates of dispersal and establishment that are moderate to high; most are widely distributed. | term Invasive - High |
| moderate invasive rating | `ICON:0011011` | invasive rating | Cal-IPC: substantial and apparent, but generally not severe, ecological impacts, with moderate to high rates of dispersal, though establishment generally depends on disturbance. | term Invasive - Moderate |
| limited invasive rating | `ICON:0011012` | invasive rating | Cal-IPC: invasive, but with ecological impacts that are minor statewide, or too little information to rate it higher; often locally persistent and problematic. | term Invasive - Limited |
| watch invasive rating | `ICON:0011013` | invasive rating | Cal-IPC: not yet invasive in California's wildlands, but assessed as at high risk of becoming invasive here. | term Invasive - Watch |
| CDFW listed invasive rating | `ICON:0011014` | invasive rating | CDFW: an animal on the Invasive Species Program's list California's Invaders, as invasive in California or a threat to the state; CDFW does not rate how invasive it is (#435). | term Invasive - CDFW listed |
| California Rare Plant Rank 1A | `ICON:0011020` | California Rare Plant Rank | CNPS: Plants presumed extirpated in California and either rare or extinct elsewhere: not seen or collected in the wild in California for many years. | term Rare Plant Rank 1A |
| California Rare Plant Rank 1B | `ICON:0011021` | California Rare Plant Rank | CNPS: Plants rare, threatened, or endangered in California and elsewhere; most are endemic to California and have declined significantly over the last century. | term Rare Plant Rank 1B |
| California Rare Plant Rank 2A | `ICON:0011022` | California Rare Plant Rank | CNPS: Plants presumed extirpated in California but common elsewhere. | term Rare Plant Rank 2A |
| California Rare Plant Rank 2B | `ICON:0011023` | California Rare Plant Rank | CNPS: Plants rare, threatened, or endangered in California but more common elsewhere. | term Rare Plant Rank 2B |
| California Rare Plant Rank 3 | `ICON:0011024` | California Rare Plant Rank | CNPS: Review list: plants about which more information is needed, nearly all taxonomically problematic. | term Rare Plant Rank 3 |
| California Rare Plant Rank 4 | `ICON:0011025` | California Rare Plant Rank | CNPS: Watch list: plants of limited distribution or infrequent throughout a broader area of California, whose status should be monitored. | term Rare Plant Rank 4 |
