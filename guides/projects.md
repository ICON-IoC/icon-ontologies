# ICON Projects ontology

Conservation projects: bounded efforts with a lead, partners and funders that restore, protect, acquire, study or manage something in a place. Covers project types and the links of a project to programs and to the places it works on.

- Files: `icon-projects.ttl` (Turtle) and `icon-projects.owl` (RDF/XML), built from `src/projects.terms`.
- Ontology IRI: `https://w3id.org/icon-ioc/projects.owl`; this release `https://w3id.org/icon-ioc/releases/2026-11-21/projects.owl`.
- Its own terms are numbered ICON:0003000 to ICON:0003999.

## Existing ontologies used

| Ontology | How | Terms |
|---|---|---|
| Basic Formal Ontology | built on | part of (`BFO:0000050`), has part (`BFO:0000051`) |
| Ontology for Biomedical Investigations | built on | organization (`OBI:0000245`) |
| Ontology for Biomedical Investigations | mapped to | investigation (`OBI:0000066`) |
| FOAF | mapped to | Project (`foaf:Project`) |
| schema.org | mapped to | Project (`schema:Project`) |

*Reused* terms are used as they are, under their own IDs. *Built on* terms are parents, domains or ranges of this module's terms. *Mapped to* terms are recorded as SKOS matches for exchange with other systems.

## Links to other ICON modules

- **Core**: endeavor
- **Infrastructure**: infrastructure
- **Plans**: conservation plan
- **Programs**: conservation program

## Classes

| Term | ID | Is a | Definition | Explorer |
|---|---|---|---|---|
| conservation project | `ICON:0003000` | endeavor (Core) | A bounded effort with a lead and usually partners and funders that restores, protects, acquires, studies, plans or manages something in a place, and ends when its work is done. close match Project (`schema:Project`); close match Project (`foaf:Project`). | class Project; vocab ProjType |
| acquisition project | `ICON:0003001` | conservation project | A project that buys land, water or easements for conservation. | term Acquisition |
| education project | `ICON:0003002` | conservation project | A project that teaches the public, students or practitioners. | term Education |
| habitat enhancement project | `ICON:0003003` | conservation project | A project that restores or improves habitat. | term Habitat Enhancement |
| infrastructure project | `ICON:0003004` | conservation project | A project that builds, removes or rebuilds a structure, such as a fish ladder, a levee setback or a wildlife crossing. | term Infrastructure |
| land protection project | `ICON:0003005` | conservation project | A project that secures land against conversion by easement, designation or agreement rather than purchase. | term Land Protection |
| management project | `ICON:0003006` | conservation project | A project that manages land, water or wildlife, such as grazing, burning or invasive species control. | term Management |
| planning project | `ICON:0003007` | conservation project | A project that produces a plan. | term Planning |
| remediation project | `ICON:0003008` | conservation project | A project that cleans up contamination or reverses damage, such as mine waste or polluted runoff. | term Remediation |
| research project | `ICON:0003009` | conservation project | A project that studies or monitors nature or conservation. close match investigation (`OBI:0000066`). | term Research |
| compensatory mitigation project | `ICON:0003010` | conservation project | A project that restores, creates or preserves habitat to make up for habitat a permitted development destroys elsewhere. | term Compensatory Mitigation |
| wildlife crossing project | `ICON:0003011` | conservation project | A project that plans, builds, improves or studies a structure that lets wildlife cross a road or railway, or that restores or secures the land leading to one. | term Wildlife Crossing |

## Relations

| Relation | ID | Reverse | From → to | Definition | Explorer |
|---|---|---|---|---|---|
| has project type | `ICON:0003100` | is project type of | conservation project → any | Links a project to one of the project type classes it belongs to. The explorer's way of stating the project's class. | phrase has project type |
| is project type of | `ICON:0003101` | has project type | any → any | The reverse of has project type. | phrase is project type of |
| is part of program | `ICON:0003102` | has project | conservation project → conservation program (Programs) | A project carried out within a program, as one grant within a grant program. Kind of: part of (`BFO:0000050`). | phrase is part of program |
| has project | `ICON:0003103` | is part of program | any → any | The reverse of is part of program. Kind of: has part (`BFO:0000051`). | phrase has project |
| tracked by | `ICON:0003104` | tracks | conservation project, conservation plan (Plans) → organization (`OBI:0000245`) | The organization that keeps a project's or plan's record in a project tracker such as EcoAtlas, often the agency that permitted or funded it, without necessarily leading it. Keeping the record is not taking part in the work, so this is not a kind of is involved with. | phrase tracked by |
| tracks | `ICON:0003105` | tracked by | any → any | The reverse of tracked by. | phrase tracks |
| works on | `ICON:0003106` | worked on by | conservation project → infrastructure (Infrastructure) | The project acts on the place itself: it restores, manages, builds, repairs, widens or studies it, or mitigates for work on it. A fuel reduction project works on the national forest it thins, a coho habitat project works on its creek, and a Caltrans culvert replacement works on the highway it runs under. A project that only uses the place to say where it is intersects it instead. | phrase works on |
| worked on by | `ICON:0003107` | works on | any → any | The reverse of works on. | phrase worked on by |
