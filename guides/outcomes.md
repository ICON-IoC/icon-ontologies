# ICON Indicators, targets and outcomes ontology

What conservation work is measured by: indicators with their units, the targets that objectives, plans, programs and guidelines or mandates set on them, and the outcomes projects and places deliver, linked by the results chain (contributes to) so progress toward a target can be added up.

- Files: `icon-outcomes.ttl` (Turtle) and `icon-outcomes.owl` (RDF/XML), built from `src/outcomes.terms`.
- Ontology IRI: `https://w3id.org/icon-ioc/outcomes.owl`; this release `https://w3id.org/icon-ioc/releases/2026-11-21/outcomes.owl`.
- Its own terms are numbered ICON:0014000 to ICON:0014999.

## Existing ontologies used

| Ontology | How | Terms |
|---|---|---|
| Information Artifact Ontology | built on | objective specification (`IAO:0000005`), information content entity (`IAO:0000030`), directive information entity (`IAO:0000033`), measurement datum (`IAO:0000109`) |
| Ontology for Biomedical Investigations | mapped to | has specified output (`OBI:0000299`) |

*Reused* terms are used as they are, under their own IDs. *Built on* terms are parents, domains or ranges of this module's terms. *Mapped to* terms are recorded as SKOS matches for exchange with other systems.

## Links to other ICON modules

- **Infrastructure**: infrastructure
- **Guidelines and mandates**: guideline or mandate
- **Plans**: conservation plan, plan action, plan objective
- **Programs**: conservation program
- **Projects**: conservation project

## Classes

| Term | ID | Is a | Definition | Explorer |
|---|---|---|---|---|
| indicator | `ICON:0014000` | information content entity (`IAO:0000030`) | Something measurable that shows progress toward a conservation goal, with the unit it is counted in, such as acres of habitat restored or miles of stream opened to fish passage. Targets and outcomes on the same indicator can be added up and compared. | vocab Indicator |
| target | `ICON:0014001` | directive information entity (`IAO:0000033`) | The amount of an indicator that an objective, plan, program or guideline or mandate sets out to reach, by a year where it gives one: restore 5,000 to 7,000 acres of tidal marsh within 30 years. A range keeps its low and high values; a milestone is another target on the same indicator with an earlier year. |  |
| outcome | `ICON:0014002` | information content entity (`IAO:0000030`) | An amount of an indicator that a project, program or place delivers: expected, as a grant award or project plan states it, or measured, as a report or an inventory such as CPAD records it. |  |
| expected outcome | `ICON:0014003` | outcome, objective specification (`IAO:0000005`) | An outcome a project or program sets out to deliver and has not yet been shown to: the acres a grant award or a project plan states, or the planned and in-progress work a project tracker lists. |  |
| measured outcome | `ICON:0014004` | outcome, measurement datum (`IAO:0000109`) | An outcome recorded as delivered, by a report, a monitoring survey or an inventory such as CPAD, or by a project tracker that lists the work as completed. |  |

## Relations

| Relation | ID | Reverse | From → to | Definition | Explorer |
|---|---|---|---|---|---|
| is measured by | `ICON:0014100` | measures | conservation project (Projects), conservation program (Programs), infrastructure (Infrastructure), guideline or mandate (Guidelines and mandates), conservation plan (Plans), plan objective (Plans), plan action (Plans) → indicator | A record sets a target on the indicator, or reports an outcome on it. | phrase is measured by |
| measures | `ICON:0014101` | is measured by | any → any | The reverse of is measured by. | phrase measures |
| contributes to | `ICON:0014102` | is advanced by | conservation project (Projects), conservation program (Programs), infrastructure (Infrastructure) → conservation program (Programs), guideline or mandate (Guidelines and mandates), conservation plan (Plans), plan objective (Plans), plan action (Plans) | A project, program or place advances an objective, action, plan, program or guideline or mandate, so its outcomes count toward that record's targets. | phrase contributes to |
| is advanced by | `ICON:0014103` | contributes to | any → any | The reverse of contributes to. | phrase is advanced by |
| has outcome | `ICON:0014104` | is outcome of | conservation project (Projects), conservation program (Programs), infrastructure (Infrastructure) → outcome | A project, program or place delivers the outcome, expected or measured (#959). The explorer shows a record's outcomes in its panel rather than as links. close match has specified output (`OBI:0000299`). |  |
| is outcome of | `ICON:0014105` | has outcome | any → any | The reverse of has outcome. |  |
| has target | `ICON:0014106` | is target of | conservation program (Programs), guideline or mandate (Guidelines and mandates), conservation plan (Plans), plan objective (Plans), plan action (Plans) → target | An objective, action, plan, program or guideline or mandate sets the target (#959). The explorer shows a record's targets, with progress toward them, in its panel rather than as links. |  |
| is target of | `ICON:0014107` | has target | any → any | The reverse of has target. |  |

## Attributes

| Attribute | ID | Definition | Explorer |
|---|---|---|---|
| target low value | `ICON:0014200` | The target's amount in its indicator's unit, or the low end when the target is a range. |  |
| target high value | `ICON:0014201` | The high end of a target given as a range. |  |
| baseline value | `ICON:0014202` | The amount of the indicator before the target was set. Progress counts up from it: the baseline plus the outcomes achieved since. |  |
| baseline year | `ICON:0014203` | The year of the baseline value. |  |
| target year | `ICON:0014204` | The year by which the target is to be met. |  |
| outcome value | `ICON:0014205` | The outcome's amount in its indicator's unit. |  |
| outcome year | `ICON:0014206` | The year the outcome was measured, or is expected to be delivered. |  |
| target total | `ICON:0014208` | The whole a target's percentages are of, in its indicator's unit, such as California's land area for a goal of conserving 30 percent of its lands. A target with a total is shown in both amounts and percentages. |  |
| outcome status | `ICON:0014207` | Expected (an expected outcome, as a grant award or proposal states it) or measured (a measured outcome, as a report or inventory records it). |  |

## Controlled values

| Value | ID | Kind | Definition | Explorer |
|---|---|---|---|---|
| area conserved | `ICON:0014010` | indicator | Acres of land or water protected for conservation in fee title or by easement. | term Area conserved |
| habitat restored | `ICON:0014011` | indicator | Acres where a habitat lost or degraded was re-established, such as tidal marsh restored from diked land. | term Habitat restored |
| habitat enhanced | `ICON:0014012` | indicator | Acres of existing habitat whose condition was improved without changing its type. | term Habitat enhanced |
| area under conservation management | `ICON:0014013` | indicator | Acres managed under a plan that benefits habitat or species, such as managed wetlands or grazing under a conservation plan. | term Area under conservation management |
| floodplain reconnected | `ICON:0014014` | indicator | Acres of floodplain reconnected to its river, so that it floods again. | term Floodplain reconnected |
| area treated for invasive species | `ICON:0014015` | indicator | Acres where invasive plants or animals were removed or controlled. | term Area treated for invasive species |
| area treated for wildfire resilience | `ICON:0014016` | indicator | Acres of fuel reduction, prescribed fire or forest thinning. | term Area treated for wildfire resilience |
| area opened to public access | `ICON:0014017` | indicator | Acres newly opened to the public for recreation or access to nature. | term Area opened to public access |
| stream habitat restored | `ICON:0014018` | indicator | Miles of stream channel or bank restored. | term Stream habitat restored |
| stream opened to fish passage | `ICON:0014019` | indicator | Miles of stream made reachable by migratory fish by removing or fixing barriers. | term Stream opened to fish passage |
| levee improved | `ICON:0014020` | indicator | Miles of levee repaired, raised or set back. | term Levee improved |
| trail built or opened | `ICON:0014021` | indicator | Miles of trail built or opened to the public. | term Trail built or opened |
| water for the environment | `ICON:0014022` | indicator | Acre-feet a year of water dedicated to streams, wetlands or habitat. | term Water for the environment |
| groundwater recharged | `ICON:0014023` | indicator | Acre-feet a year of water added to groundwater by recharge projects. | term Groundwater recharged |
| fish passage barriers remediated | `ICON:0014024` | indicator | The number of dams, culverts or other barriers to fish removed or fitted with passage. | term Fish passage barriers remediated |
| wildlife crossings built | `ICON:0014025` | indicator | The number of wildlife crossing structures built or retrofitted. | term Wildlife crossings built |
| populations secured | `ICON:0014026` | indicator | The number of populations of a species that meet a plan's test of being secure, such as protected and self-sustaining. | term Populations secured |
| population size | `ICON:0014027` | indicator | The number of individuals of a species counted or estimated, such as adult fish returning to spawn. | term Population size |
| projects completed | `ICON:0014028` | indicator | The number of projects of a kind carried out to completion. | term Projects completed |
| partnerships formed | `ICON:0014029` | indicator | The number of partnerships or agreements formed among organizations. | term Partnerships formed |
| funding invested | `ICON:0014030` | indicator | Dollars spent or awarded on the work. | term Funding invested |
| carbon stored | `ICON:0014031` | indicator | Metric tons of carbon dioxide equivalent stored or kept from release. | term Carbon stored |
| projects funded | `ICON:0014032` | indicator | The number of projects of a kind a funder approves a grant or acquisition for, counted when the award is made, whether or not the work is done yet. | term Projects funded |
| projects monitored | `ICON:0014033` | indicator | The number of completed projects checked in a year for whether they are operated, used and maintained as their grant agreements require. | term Projects monitored |
| outreach events held | `ICON:0014034` | indicator | The number of meetings, workshops or conferences held or sponsored to reach the public, partners or prospective grantees. | term Outreach events held |
| process improvements made | `ICON:0014035` | indicator | The number of changes put in place to make an organization's processes, such as grant applications, reporting or payment, simpler or faster. | term Process improvements made |
| land conserved | `ICON:0014036` | indicator | Acres of land durably protected and managed for biodiversity, as California counts its 30x30 Conservation Areas on land. Narrower than area conserved, which takes in water and any protection by fee or easement. | term Land conserved |
| coastal waters conserved | `ICON:0014037` | indicator | Acres of coastal waters durably protected and managed for biodiversity, as California counts its 30x30 Conservation Areas in its coastal state waters. | term Coastal waters conserved |
| habitat created | `ICON:0014038` | indicator | Acres where a habitat was established where it did not exist before, such as a wetland built on upland. Habitat restored is where it once was. | term Habitat created |
