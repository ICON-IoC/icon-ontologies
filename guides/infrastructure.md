# ICON Infrastructure ontology

Places and structures on the landscape that conservation works on or around: waters (blue), conservation lands (green), water works, energy, food production and sensors. Covers their types, ownership and management, and how they lie relative to one another (upstream, adjacent, intersecting).

- Files: `icon-infrastructure.ttl` (Turtle) and `icon-infrastructure.owl` (RDF/XML), built from `src/infrastructure.terms`.
- Ontology IRI: `https://w3id.org/icon/infrastructure.owl`; this release `https://w3id.org/icon/releases/2026-11-21/infrastructure.owl`.
- Its own terms are numbered ICON:0005000 to ICON:0005999.

## Existing ontologies used

| Ontology | How | Terms |
|---|---|---|
| Core Ontology for Biology and Biomedicine | built on | device (`COB:0001300`) |
| Environment Ontology | reused | canal (`ENVO:00000014`), stream (`ENVO:00000023`), reservoir (`ENVO:00000025`), wetland area (`ENVO:00000043`), estuary (`ENVO:00000045`), levee (`ENVO:00000178`), floodway (`ENVO:00000256`), dry lake (`ENVO:00000277`), weir (`ENVO:00000535`), marine water body (`ENVO:00001999`), power plant (`ENVO:00002214`), geothermal power plant (`ENVO:00002215`), lentic water body (`ENVO:01000617`), ecological corridor (`ENVO:01000930`) |
| Environment Ontology | built on | human construction (`ENVO:00000070`), protected area (`ENVO:01001567`), landform (`ENVO:01001886`) |
| Environment Ontology | mapped to | dam (`ENVO:00000074`), farm (`ENVO:00000078`), agricultural field (`ENVO:00000114`), area of protected biodiversity (`ENVO:00000358`), marine park area (`ENVO:00000362`), aquifer (`ENVO:00012408`), feedlot (`ENVO:01000627`), electric power system (`ENVO:01000865`), solar panel array (`ENVO:01000867`) |
| Information Artifact Ontology | built on | information content entity (`IAO:0000030`) |
| Ontology for Biomedical Investigations | built on | organization (`OBI:0000245`) |
| Relation Ontology | built on | adjacent to (`RO:0002220`) |
| Relation Ontology | mapped to | has habitat (`RO:0002303`) |
| GeoSPARQL | mapped to | Feature (`gsp:Feature`) |

*Reused* terms are used as they are, under their own IDs. *Built on* terms are parents, domains or ranges of this module's terms. *Mapped to* terms are recorded as SKOS matches for exchange with other systems.

## Links to other ICON modules

- **Taxa and habitats**: taxon
- **Core**: is involved with, place

## Classes

| Term | ID | Is a | Definition | Explorer |
|---|---|---|---|---|
| infrastructure | `ICON:0005000` | place (Core) | A place or structure on the landscape that conservation works on or around: a water body, a conservation area, a water or energy work, a farm, a sensor, a road or trail. Called infrastructure in the PPOD model whether built or natural. close match Feature (`gsp:Feature`). | class Infrastructure; vocab InfrastructureType |
| blue infrastructure | `ICON:0005001` | infrastructure | A body of water: a river or stream, a lake or pond, a dry lake or playa, a wetland, an estuary or the ocean. |  |
| green infrastructure | `ICON:0005002` | infrastructure | Land or water held or designed for wildlife and habitat: conservation areas, mitigation banks, greenbelts, corridors and crossing structures. |  |
| water infrastructure | `ICON:0005003` | infrastructure | A work that stores, moves, controls or recharges water. |  |
| energy infrastructure | `ICON:0005004` | infrastructure | A work that generates or carries electric power. |  |
| food production infrastructure | `ICON:0005005` | infrastructure | Land or facilities used to grow crops or raise animals. |  |
| sensor infrastructure | `ICON:0005006` | infrastructure | A device placed in the landscape to record what passes or happens there. |  |
| transport infrastructure | `ICON:0005007` | infrastructure | A route that carries people, vehicles or goods across the landscape: a trail, a highway, a local road, a railway or a bridge. |  |
| waste infrastructure | `ICON:0005009` | infrastructure | A facility that receives, stores or disposes of solid waste, such as a landfill. |  |
| estuary | `ENVO:00000045` (reused) |  | Source: A semi-enclosed coastal body of water with one or more rivers or streams flowing into it, and with a free connection to the open sea. | term Blue - Estuary |
| lentic water body | `ENVO:01000617` (reused) |  | Lakes and ponds: still water. Source: A lentic water body is a water body in which the accumulated water, in its totality, has very little to no directed flow. | term Blue - Lake/Pond |
| dry lake | `ENVO:00000277` (reused) |  | The terminal basins that inland streams drain toward and fill only in wet years: Tulare Lake, Kern Lake, Rosamond Lake, Badwater Basin. Added so every stream has a downstream water (#1282). Source: A lake that has either permanently or temporally lost its water. | term Blue - Dry Lake/Playa |
| marine water body | `ENVO:00001999` (reused) |  | The ocean and its bays. Source: A lentic water body which is composed primarily of marine water. | term Blue - Ocean |
| stream | `ENVO:00000023` (reused) |  | ENVO's river is a kind of stream. Source: A watercourse which is linear and flows across the solid portion of a planetary surface. | term Blue - River/Stream |
| wetland area | `ENVO:00000043` (reused) |  | Source: An vegetated area which overlaps a wetland ecosystem. | term Blue - Wetland |
| canal | `ENVO:00000014` (reused) |  | Source: Artificial watercourse with no flow or a controlled flow used for navigation, drainage or irrigation. | term Water - Canal |
| floodway | `ENVO:00000256` (reused) |  | Source: The stream channel and adjacent areas that carry flood flows in a flood plain. | term Water - Floodway |
| levee | `ENVO:00000178` (reused) |  | Source: An artificial slope or wall, usually earthen, which parallels the course of a river, built for the purpose of containing the river. | term Water - Levee |
| reservoir | `ENVO:00000025` (reused) |  | Source: An artificial body of water, often contained by a dam, constructed for the purpose of water storage. | term Water - Reservoir |
| weir | `ENVO:00000535` (reused) |  | Source: A low obstruction built across the path of s stream to raise its level. | term Water - Weir |
| geothermal power plant | `ENVO:00002215` (reused) |  | Source: A geothermal power plant is a power plant which uses heat generated by the decay of radioactive isotopes in the Earth's mantle and crust as well as primordial heat left over from the formation of the Earth to drive its generators. | term Energy - Geothermal |
| power plant | `ENVO:00002214` (reused) |  | The explorer's other electric power generation, and the parent of the more specific kinds of power plant here. Source: A power plant is a building which contains one or more generators which convert mechanical energy into electrical energy through the relative motion between a magnetic field and a conductor. The energy source harnessed to turn the generator varies widely. | term Energy - Other Electric Power Generation |
| ecological corridor | `ENVO:01000930` (reused) |  | Source: An ecosystem which bridges two or more adjoining ecosystems and through which organisms may move or propagate. | term Green - Wildlife Corridor |
| groundwater basin | `ICON:0005020` | water infrastructure | An aquifer or group of aquifers managed as a unit, such as a basin or subbasin of California's Bulletin 118. close match aquifer (`ENVO:00012408`). | term Water - Ground Water |
| water pipeline | `ICON:0005021` | water infrastructure, human construction (`ENVO:00000070`) | A pipe or aqueduct that carries water over a distance. | term Water - Water Pipeline |
| pumping station | `ICON:0005022` | water infrastructure, human construction (`ENVO:00000070`) | A facility that lifts or moves water with pumps. | term Water - Pumping Station |
| groundwater recharge facility | `ICON:0005023` | water infrastructure, human construction (`ENVO:00000070`) | Basins or works that put surface water into the ground to refill an aquifer. | term Water - Recharge Facility |
| water retention structure | `ICON:0005024` | water infrastructure, human construction (`ENVO:00000070`) | A structure that holds water back, such as a dam, a check dam or a detention basin. close match dam (`ENVO:00000074`). | term Water - Water Retention Structure |
| natural gas-fired power plant | `ICON:0005025` | energy infrastructure, power plant (`ENVO:00002214`) | A power plant that burns natural gas. | term Energy - Natural Gas-fired Generator |
| hydroelectric powerhouse | `ICON:0005026` | energy infrastructure, power plant (`ENVO:00002214`) | The building at a dam or penstock that holds the turbines and generators. | term Energy - Powerhouse |
| pumped storage facility | `ICON:0005027` | energy infrastructure, power plant (`ENVO:00002214`) | A hydroelectric plant that pumps water uphill when power is cheap and releases it through turbines when power is needed. | term Energy - Pumped Storage Facility |
| solar power plant | `ICON:0005028` | energy infrastructure, power plant (`ENVO:00002214`) | A power plant that makes electricity from sunlight. close match solar panel array (`ENVO:01000867`). | term Energy - Solar |
| wind power plant | `ICON:0005029` | energy infrastructure, power plant (`ENVO:00002214`) | A group of wind turbines that makes electricity. | term Energy - Wind |
| electric transmission line | `ICON:0005030` | energy infrastructure, human construction (`ENVO:00000070`) | A high-voltage power line carrying electricity from plants to substations. close match electric power system (`ENVO:01000865`). | term Energy - Transmission Line |
| electrical substation | `ICON:0005031` | energy infrastructure, human construction (`ENVO:00000070`) | A facility where transmission lines meet and voltage is changed. | term Energy - Transmission Substation |
| natural gas compressor station | `ICON:0005053` | energy infrastructure, human construction (`ENVO:00000070`) | A facility on a natural gas transmission pipeline that raises the gas pressure to keep it moving along the line. Example: San Diego Gas & Electric's Moreno Compressor Station in Moreno Valley, which boosts the gas supply into San Diego County. | term Energy - Natural Gas Compressor Station |
| animal production site | `ICON:0005032` | food production infrastructure | A ranch, dairy, feedlot or other place where animals are raised. close match farm (`ENVO:00000078`); close match feedlot (`ENVO:01000627`). | term Food - Animal Production |
| crop production site | `ICON:0005033` | food production infrastructure | A farm, orchard, vineyard or field where crops are grown. close match agricultural field (`ENVO:00000114`). | term Food - Crop Production |
| conservation easement area | `ICON:0005034` | green infrastructure, protected area (`ENVO:01001567`) | Land protected by a conservation easement while its owner keeps title. | term Green - Conservation Area (Easement) |
| fee-title conservation area | `ICON:0005035` | green infrastructure, protected area (`ENVO:01001567`) | Land owned outright by an agency or organization for conservation, such as a reserve, refuge, park or wildlife area. close match area of protected biodiversity (`ENVO:00000358`). | term Green - Conservation Area (Fee Title) |
| marine conservation area | `ICON:0005036` | green infrastructure, protected area (`ENVO:01001567`) | Ocean or bay waters protected for conservation, such as a marine protected area or sanctuary. close match marine park area (`ENVO:00000362`). | term Green - Conservation Area (Marine) |
| conservation area under several protections | `ICON:0005037` | green infrastructure, protected area (`ENVO:01001567`) | A conservation area made of parts held by fee title, easement or other protections together. | term Green - Conservation Area (Multple) |
| greenbelt | `ICON:0005038` | green infrastructure | Open land kept undeveloped around or between towns. | term Green - Greenbelt |
| mitigation bank | `ICON:0005039` | green infrastructure, protected area (`ENVO:01001567`) | Land restored or protected so that credits can be sold to offset habitat loss elsewhere. | term Green - Mitigation Bank |
| wildlife crossing structure | `ICON:0005040` | green infrastructure, human construction (`ENVO:00000070`) | An overpass, underpass, culvert or bridge built or adapted so that animals can cross a road or railway. | term Green - Wildlife Crossing Structure |
| camera trap | `ICON:0005041` | sensor infrastructure, device (`COB:0001300`) | A camera set off by motion or heat that photographs animals passing. | term Sensor - Camera Trap |
| field station | `ICON:0005042` | green infrastructure | A research station or reserve that a university or agency runs for research and teaching, often with housing and labs, giving access to protected lands it may not own. | term Green - Field Station |
| trail | `ICON:0005043` | transport infrastructure, human construction (`ENVO:00000070`) | A path for walking, cycling or riding, such as a regional trail like the Bay Area Ridge Trail or a preserve's trail network. | term Transport - Trail |
| highway | `ICON:0005044` | transport infrastructure, human construction (`ENVO:00000070`) | A road in the state or federal highway system: an Interstate, a U.S. route or a California state route. | term Transport - Highway |
| local road | `ICON:0005045` | transport infrastructure, human construction (`ENVO:00000070`) | A road a county or city owns and maintains, outside the state and federal highway systems. | term Transport - Local Road |
| railway | `ICON:0005046` | transport infrastructure, human construction (`ENVO:00000070`) | A rail line for freight or passenger trains. | term Transport - Railway |
| bridge | `ICON:0005057` | transport infrastructure, human construction (`ENVO:00000070`) | A structure that carries a road, trail or railway over a creek, river or other obstacle. Example: the Pope-Chaucer Bridge over San Francisquito Creek between Menlo Park and Palo Alto. | term Transport - Bridge |
| GAP status | `ICON:0005008` | information content entity (`IAO:0000030`) | How a protected place is managed for biodiversity on the USGS Gap Analysis Project scale, as California's 30x30 Conserved Areas rate it; only GAP 1 and 2 count toward 30x30 (#427). | vocab GAPStatus |
| fish hatchery | `ICON:0005049` | animal production site | A facility that spawns and rears fish, mostly salmon and trout, for release into rivers and lakes to supply fisheries or to make up for spawning habitat a dam has blocked. | term Food - Fish Hatchery |
| native plant nursery | `ICON:0005050` | green infrastructure | A farm or nursery that grows native plants and their seed from local wild sources for habitat restoration, rather than for sale or food. | term Green - Native Plant Nursery |
| marine conservation priority area | `ICON:0005051` | green infrastructure | An area of ocean, estuary or shoreline that a conservation plan marks as a priority for protecting marine biodiversity, without itself being protected, such as a portfolio conservation area of a marine ecoregional assessment. | term Green - Marine Conservation Priority Area |
| important bird area | `ICON:0005052` | green infrastructure | A site that BirdLife International's Important Bird Areas program, run in the United States by the National Audubon Society, identifies as essential for birds because it holds species of conservation concern, range-restricted species or large concentrations of birds, without itself being protected. | term Green - Important Bird Area |
| important plant area | `ICON:0005124` | green infrastructure | An area that the California Native Plant Society's Important Plant Areas Initiative identifies as among the most important places in the state for rare plants and rare vegetation types, without itself being protected. Example: a Tier 1 area of the Northwestern California ecoregion around the Mendocino pygmy forest, home to 37 California Rare Plant Rank 1B species. | term Green - Important Plant Area |
| named landform | `ICON:0005054` | green infrastructure, landform (`ENVO:01001886`) | A named natural feature of the land surface, such as a range of hills, a ridge or a valley, that a conservation plan treats as an area to protect or work in, without itself being protected. Example: the Dunnigan Hills of Yolo County, where the Yolo HCP/NCCP protects grassland for California tiger salamander. | term Green - Landform |
| water treatment plant | `ICON:0005055` | water infrastructure, human construction (`ENVO:00000070`) | A facility that treats raw water from reservoirs, rivers or wells to drinking water standards before it enters a distribution system. Example: the San Francisco Public Utilities Commission's Sunol Valley Water Treatment Plant, which treats water from San Antonio and Calaveras reservoirs. | term Water - Water Treatment Plant |
| wastewater treatment plant | `ICON:0005059` | water infrastructure, human construction (`ENVO:00000070`) | A facility that treats sewage and other wastewater before it is discharged or reused, for example as recycled water for irrigation. Example: the City of Santa Rosa's Laguna Treatment Plant, on the floodplain of the Laguna de Santa Rosa. | term Water - Wastewater Treatment Plant |
| landfill | `ICON:0005056` | waste infrastructure, human construction (`ENVO:00000070`) | A site where solid waste is buried in the ground, usually in lined cells that are covered and capped when full. Example: the Sanitation Districts of Los Angeles County's Puente Hills Landfill, which closed in 2013. | term Waste - Landfill |
| species recovery area | `ICON:0005058` | green infrastructure | An area that a federal or state recovery plan designates as essential to the recovery of listed species, such as a core area whose habitat the plan says to protect, without itself being protected. Example: the Mather Core Recovery Area of the 2005 Recovery Plan for Vernal Pool Ecosystems of California and Southern Oregon, where the South Sacramento HCP must mitigate vernal pool losses. | term Green - Recovery Area |
| national heritage area | `ICON:0005125` | green infrastructure | A region that the United States Congress designates for its nationally important natural, cultural, and historic resources, managed through partnerships led by a local coordinating entity under a management plan approved by the Secretary of the Interior, without federal ownership or land use regulation. Example: the Sacramento-San Joaquin Delta National Heritage Area, designated in 2019, whose local coordinating entity is the Delta Protection Commission. | term Green - National Heritage Area |

## Relations

| Relation | ID | Reverse | From → to | Definition | Explorer |
|---|---|---|---|---|---|
| has infrastructure type | `ICON:0005100` | is infrastructure type of | infrastructure → any | Links a place to one of the infrastructure type classes it belongs to. The explorer's way of stating the place's class. | phrase has infrastructure type |
| is infrastructure type of | `ICON:0005101` | has infrastructure type | any → any | The reverse of has infrastructure type. | phrase is infrastructure type of |
| owned by | `ICON:0005102` | owns | infrastructure → organization (`OBI:0000245`) | The organization holding legal title to the place. Kind of: is involved with (Core). | phrase owned by |
| owns | `ICON:0005103` | owned by | any → any | The reverse of owned by. Kind of: is involved with (Core). | phrase owns |
| managed by | `ICON:0005104` | manages | infrastructure → organization (`OBI:0000245`) | The organization that operates or manages the place, whether or not it owns it. Kind of: is involved with (Core). | phrase managed by |
| manages | `ICON:0005105` | managed by | any → any | The reverse of managed by. Kind of: is involved with (Core). | phrase manages |
| is upstream of | `ICON:0005106` | is downstream of | infrastructure → infrastructure | Water flows from this place to the other, directly or through places between: Lake Berryessa is upstream of Monticello Dam. (transitive) | phrase is upstream of |
| is downstream of | `ICON:0005107` | is upstream of | any → any | The reverse of is upstream of. (transitive) | phrase is downstream of |
| is adjacent to | `ICON:0005108` |  | infrastructure → infrastructure | Two places share a boundary. Symmetric, unlike the Relation Ontology's adjacent to, which it narrows. Kind of: adjacent to (`RO:0002220`). (symmetric) | phrase is adjacent to |
| is habitat for | `ICON:0005109` | is found in | infrastructure → taxon (Taxa and habitats) | The place supports a population of the taxon. | phrase is habitat for |
| is found in | `ICON:0005110` | is habitat for | any → any | The taxon lives in or uses the place: the reverse of is habitat for. close match has habitat (`RO:0002303`). | phrase is found in |
| built for | `ICON:0005111` | has crossing | infrastructure → taxon (Taxa and habitats) | The structure was built or adapted so that the taxon can get past a barrier, as a wildlife crossing is built for the animals it lets cross a road. Unlike is habitat for, it says nothing about the taxon living there. | phrase built for |
| has crossing | `ICON:0005112` | built for | any → any | The taxon has a structure built or adapted to let it get past a barrier: the reverse of built for. | phrase has crossing |
| crosses | `ICON:0005117` | crossed by | infrastructure → transport infrastructure | The structure carries animals under or over the road or railway, as a wildlife crossing structure crosses the highway it passes beneath. | phrase crosses |
| crossed by | `ICON:0005118` | crosses | any → any | The road or railway has a structure that carries animals under or over it: the reverse of crosses. | phrase crossed by |
| monitors | `ICON:0005113` | monitored by | infrastructure → taxon (Taxa and habitats) | The sensor or array was set up to watch the taxon, as a camera trap study of fishers monitors the fisher. It says nothing about whether the taxon was found. | phrase monitors |
| monitored by | `ICON:0005114` | monitors | any → any | The taxon is watched by a sensor or array set up for it: the reverse of monitors. | phrase monitored by |
| detected | `ICON:0005115` | detected by | infrastructure → taxon (Taxa and habitats) | The sensor or array recorded the taxon, as a camera trap photographs a bobcat. Unlike is habitat for, it says only that the taxon passed the sensor. | phrase detected |
| detected by | `ICON:0005116` | detected | any → any | The taxon was recorded by a sensor or array: the reverse of detected. | phrase detected by |
| exchanges water with | `ICON:0005119` |  | infrastructure → infrastructure | Water flows between the two places in either direction, as through an intertie that pumps both ways: the Cross Valley Canal exchanges water with the California Aqueduct. Unlike is upstream of it does not chain, so what lies upstream of one is not taken to lie upstream of the other. (symmetric) | phrase exchanges water with |
| spills into | `ICON:0005120` | receives spill from | infrastructure → infrastructure | Some of this place's water leaves for the other at one point, as a river spills over a weir into a flood bypass, while the place as a whole may lie downstream of the other too: the Sacramento River spills into the Yolo Bypass, which rejoins it lower down. Unlike is upstream of it does not chain, so the river's tributaries are not taken to lie upstream of the bypass. | phrase spills into |
| receives spill from | `ICON:0005121` | spills into | infrastructure → infrastructure | The reverse of spills into. | phrase receives spill from |
| has GAP status | `ICON:0005122` | is GAP status of | infrastructure → GAP status | The GAP status of the place's lands, as the 30x30 Conserved Areas rate them; a place with lands at both levels has both. | phrase has GAP status |
| is GAP status of | `ICON:0005123` | has GAP status | any → any | The reverse of has GAP status. | phrase is GAP status of |

## Attributes

| Attribute | ID | Definition | Explorer |
|---|---|---|---|
| capacity | `ICON:0005200` | How much the place holds or delivers, written with its unit: a reservoir's storage in acre-feet, a plant's output in megawatts. | field infrastructure.capacity |

## Controlled values

| Value | ID | Kind | Definition | Explorer |
|---|---|---|---|---|
| GAP 1 | `ICON:0005047` | GAP status | Permanently protected and managed for biodiversity, with natural disturbance such as fire or flooding allowed to run its course. | term GAP 1 |
| GAP 2 | `ICON:0005048` | GAP status | Permanently protected and managed for biodiversity, with natural disturbance suppressed. | term GAP 2 |
