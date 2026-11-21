# ICON ontologies

The Internet of Conservation ontologies: one module per kind of record in the conservation knowledge graph, each usable on its own.

Version 2026-11-21: 15 modules and 594 ICON terms, licensed
CC BY 4.0. Browse them, with the module map and a page for every term, at
https://w3id.org/icon-ioc/ (https://icon-ioc.github.io/icon-ontologies/).

These files are published from the Internet of Conservation build; edit the sources
there, not here. Every push to this repository updates the pages.

## Addresses

- Every term: `https://w3id.org/icon-ioc/ICON_nnnnnnn`. A browser gets the term's page; a client that
  asks for `text/turtle` or `application/rdf+xml` gets the term's triples.
- All modules: `https://w3id.org/icon-ioc/icon.owl` (imports each module).
- One module: `https://w3id.org/icon-ioc/<module>.owl` or `.ttl`, such as `https://w3id.org/icon-ioc/projects.owl`.
- One release: `https://w3id.org/icon-ioc/releases/<version>/<module>.owl`, kept under `releases/`.
- LinkML: `https://w3id.org/icon-ioc/linkml/<schema>`, such as `https://w3id.org/icon-ioc/linkml/icon`.

`w3id.htaccess` is a copy of the redirect rules held at
https://github.com/perma-id/w3id.org/tree/master/icon.

## Files

| Module | Turtle | RDF/XML | LinkML |
|---|---|---|---|
| Core | `icon-core.ttl` | `icon-core.owl` | `linkml/icon-core.yaml` |
| Organizations | `icon-organizations.ttl` | `icon-organizations.owl` | `linkml/icon-organizations.yaml` |
| People | `icon-people.ttl` | `icon-people.owl` | `linkml/icon-people.yaml` |
| Projects | `icon-projects.ttl` | `icon-projects.owl` | `linkml/icon-projects.yaml` |
| Programs | `icon-programs.ttl` | `icon-programs.owl` | `linkml/icon-programs.yaml` |
| Infrastructure | `icon-infrastructure.ttl` | `icon-infrastructure.owl` | `linkml/icon-infrastructure.yaml` |
| Guidelines and mandates | `icon-mandates.ttl` | `icon-mandates.owl` | `linkml/icon-mandates.yaml` |
| Plans | `icon-plans.ttl` | `icon-plans.owl` | `linkml/icon-plans.yaml` |
| Data | `icon-data.ttl` | `icon-data.owl` | `linkml/icon-data.yaml` |
| Papers and reports | `icon-publications.ttl` | `icon-publications.owl` | `linkml/icon-publications.yaml` |
| Tools | `icon-tools.ttl` | `icon-tools.owl` | `linkml/icon-tools.yaml` |
| Places | `icon-places.ttl` | `icon-places.owl` | `linkml/icon-places.yaml` |
| Taxa and habitats | `icon-biodiversity.ttl` | `icon-biodiversity.owl` | `linkml/icon-biodiversity.yaml` |
| Issues | `icon-issues.ttl` | `icon-issues.owl` | `linkml/icon-issues.yaml` |
| Indicators, targets and outcomes | `icon-outcomes.ttl` | `icon-outcomes.owl` | `linkml/icon-outcomes.yaml` |

`catalog-v001.xml` lets Protégé and ROBOT open the modules from disk. `mappings/` holds
SSSOM tables, and `guides/` one Markdown guide per module.

## Cite

Internet of Conservation, Information for the Conservation of Nature (ICON). ICON
ontologies, version 2026-11-21. https://w3id.org/icon-ioc/. Licensed under CC BY 4.0.

## License

CC BY 4.0; see `LICENSE`. The ICON names and logos in `brand/` are not covered by it.
The ontologies build on the PPOD schema (github.com/adhollander/PPOD_Core), released
under CC0 1.0.