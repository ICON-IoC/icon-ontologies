# ICON Issues ontology

The conservation issues records address, from water quality to wildfire: one class for the issue vocabulary and the link that says a record addresses an issue.

- Files: `icon-issues.ttl` (Turtle) and `icon-issues.owl` (RDF/XML), built from `src/issues.terms`.
- Ontology IRI: `https://w3id.org/icon/issues.owl`; this release `https://w3id.org/icon/releases/2026-11-21/issues.owl`.
- Its own terms are numbered ICON:0012000 to ICON:0012999.

## Existing ontologies used

| Ontology | How | Terms |
|---|---|---|
| Basic Formal Ontology | built on | entity (`BFO:0000001`) |
| DCAT 3 (W3C Data Catalog Vocabulary) | mapped to | theme (`dcat:theme`) |
| SKOS | mapped to | has broader (`skos:broader`), has narrower (`skos:narrower`), has related (`skos:related`) |

*Reused* terms are used as they are, under their own IDs. *Built on* terms are parents, domains or ranges of this module's terms. *Mapped to* terms are recorded as SKOS matches for exchange with other systems.

## Links to other ICON modules

- **Core**: funds, leads
- **Infrastructure**: manages
- **Programs**: administers

## Classes

| Term | ID | Is a | Definition | Explorer |
|---|---|---|---|---|
| conservation issue | `ICON:0012000` | entity (`BFO:0000001`) | A problem, pressure or concern conservation work responds to, such as water quality, wildfire, habitat loss or a declining species. Issues are of many kinds (processes, qualities, entities), so the class sits directly under entity. | vocab Issues |

## Relations

| Relation | ID | Reverse | From → to | Definition | Explorer |
|---|---|---|---|---|---|
| addresses issue | `ICON:0012100` | is addressed by | any → conservation issue | The record responds to, studies or bears on the issue. An organization that funds, leads, administers or manages work addressing an issue addresses it too. close match theme (`dcat:theme`). | phrase addresses issue |
| is addressed by | `ICON:0012101` | addresses issue | any → any | The reverse of addresses issue. | phrase is addressed by |
| has broader issue | `ICON:0012102` | has narrower issue | conservation issue → conservation issue | Links a component issue to an integrated issue it is primarily part of, as the issue list of Springer et al. (2022) records: Floods has broader issues Water and Disasters. A record that addresses the component issue addresses the integrated one too. exact match has broader (`skos:broader`). | phrase has broader issue |
| has narrower issue | `ICON:0012103` | has broader issue | any → any | The reverse of has broader issue: an integrated issue's component issues. exact match has narrower (`skos:narrower`). | phrase has narrower issue |
| is related to issue | `ICON:0012104` |  | conservation issue → conservation issue | Links a component issue to an integrated issue it bears on secondarily, as the issue list of Springer et al. (2022) records. Nothing rolls up along it. exact match has related (`skos:related`). (symmetric) | phrase is related to issue |
