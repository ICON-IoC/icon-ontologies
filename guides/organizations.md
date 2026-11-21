# ICON Organizations ontology

Organizations in conservation: agencies, non-profits, tribes, companies, universities and partnerships, their types and activities, how they nest and join one another, and the links by which they publish, host, fund or partner in other work.

- Files: `icon-organizations.ttl` (Turtle) and `icon-organizations.owl` (RDF/XML), built from `src/organizations.terms`.
- Ontology IRI: `https://w3id.org/icon-ioc/organizations.owl`; this release `https://w3id.org/icon-ioc/releases/2026-11-21/organizations.owl`.
- Its own terms are numbered ICON:0001000 to ICON:0001999.

## Existing ontologies used

| Ontology | How | Terms |
|---|---|---|
| Basic Formal Ontology | built on | part of (`BFO:0000050`), has part (`BFO:0000051`) |
| Core Ontology for Biology and Biomedicine | built on | planned process (`COB:0000082`) |
| Environment Ontology | built on | ecoregion (`ENVO:01000276`) |
| Geographical Entity Ontology | built on | nongovernmental organization (`GEO:000000393`), governmental organization (`GEO:000000400`) |
| Ontology for Biomedical Investigations | reused | organization (`OBI:0000245`) |
| Ontology for Biomedical Investigations | built on | is member of organization (`OBI:0000846`), has organization member (`OBI:0001688`) |
| Ontology for Biomedical Investigations | mapped to | investigation (`OBI:0000066`), grant agency (`OBI:0001942`) |
| Relation Ontology | reused | capable of (`RO:0002215`) |
| Relation Ontology | built on | located in (`RO:0001025`) |
| Dublin Core terms | mapped to | Publisher (`dcterms:publisher`) |
| FOAF | mapped to | Organization (`foaf:Organization`) |
| W3C Organization Ontology | mapped to | Organization (`org:Organization`), Endeavour (`org:OrganizationalCollaboration`), OrganizationalUnit (`org:OrganizationalUnit`), has member (`org:hasMember`), primary Site (`org:hasPrimarySite`), member of (`org:memberOf`) |
| schema.org | mapped to | CollegeOrUniversity (`schema:CollegeOrUniversity`), Corporation (`schema:Corporation`), GovernmentOrganization (`schema:GovernmentOrganization`), NGO (`schema:NGO`), Organization (`schema:Organization`), location (`schema:location`), memberOf (`schema:memberOf`), publisher (`schema:publisher`) |

*Reused* terms are used as they are, under their own IDs. *Built on* terms are parents, domains or ranges of this module's terms. *Mapped to* terms are recorded as SKOS matches for exchange with other systems.

## Links to other ICON modules

- **Core**: is involved with
- **Places**: county, in ecoregion, located in area

## Classes

| Term | ID | Is a | Definition | Explorer |
|---|---|---|---|---|
| organization | `OBI:0000245` (reused) |  | Reused from OBI as the explorer's Organization class. Its subclasses below are the Terms sheet's organization types. Source: An organization is a continuant entity which can play roles,  has members, and has a set of organization rules.  Members of organizations are either organizations themselves or individual people. Members can bear specific organization member roles that are determined in the organization rules. The organization rules also determine how decisions are made on behalf of the organization by the organization members. close match Organization (`org:Organization`); close match Organization (`foaf:Organization`); close match Organization (`schema:Organization`). | class Organization; vocab OrgType |
| academic organization | `ICON:0001001` | organization (`OBI:0000245`) | A university, college or research institute, or a department of one. close match CollegeOrUniversity (`schema:CollegeOrUniversity`). | term Academic |
| commercial organization | `ICON:0001002` | organization (`OBI:0000245`) | A business run for profit, such as a consultancy, a utility company, a farm business or a developer. close match Corporation (`schema:Corporation`). | term Commercial |
| federal government organization | `ICON:0001003` | governmental organization (`GEO:000000400`) | An agency or office of the United States government, such as the Fish and Wildlife Service or the Bureau of Reclamation. close match GovernmentOrganization (`schema:GovernmentOrganization`). | term Federal Government |
| state government organization | `ICON:0001004` | governmental organization (`GEO:000000400`) | An agency, department, board or commission of the State of California, such as the Department of Fish and Wildlife. close match GovernmentOrganization (`schema:GovernmentOrganization`). | term State Government |
| local government organization | `ICON:0001005` | governmental organization (`GEO:000000400`) | A county, city, special district (water, resource conservation, flood control) or one of their departments. close match GovernmentOrganization (`schema:GovernmentOrganization`). | term Local Government |
| joint powers authority | `ICON:0001006` | governmental organization (`GEO:000000400`) | A public agency formed by two or more public agencies under California's Joint Exercise of Powers Act to carry out a shared purpose, such as a regional water or habitat authority. | term Joint Powers Authority |
| tribal organization | `ICON:0001007` | organization (`OBI:0000245`) | A tribal government or an organization of one or more tribes or tribal members. | term Tribal |
| non-profit organization | `ICON:0001008` | nongovernmental organization (`GEO:000000393`) | A private organization that does not distribute profit, such as a land trust, a watershed group or a conservation society. close match NGO (`schema:NGO`). | term Non-profit |
| foundation | `ICON:0001009` | organization (`OBI:0000245`) | A private organization, usually endowed, that makes grants to others' work. close match grant agency (`OBI:0001942`). | term Foundation |
| partnership | `ICON:0001010` | organization (`OBI:0000245`) | A standing collaboration of several organizations with a name of its own, such as a regional conservation partnership or a working group. close match Endeavour (`org:OrganizationalCollaboration`). | term Partnership |
| team | `ICON:0001011` | organization (`OBI:0000245`) | A unit inside an organization with a name of its own, such as a program office or a field crew. close match OrganizationalUnit (`org:OrganizationalUnit`). | term Team |
| international organization | `ICON:0001012` | organization (`OBI:0000245`) | An organization whose members are national governments, set up by a treaty or convention, such as a regional fisheries management commission. | term International |
| city government organization | `ICON:0001013` | local government organization | An incorporated city or town of California, or one of its departments, boards or commissions. | term City Government |
| county government organization | `ICON:0001014` | local government organization | A county of California, or one of its departments, boards or commissions, such as a county parks department or fish and game commission. | term County Government |
| special district | `ICON:0001015` | local government organization | A local agency formed under state law to provide one or a few services within set boundaries, such as a water, irrigation, resource conservation, park, flood control or sanitation district. | term Special District |
| regional agency | `ICON:0001016` | local government organization | A local agency that serves several cities or counties together, such as a council of governments or a regional transportation commission. | term Regional Agency |
| organizational activity | `ICON:0001020` | planned process (`COB:0000082`) | A kind of work an organization carries out, from the Terms sheet's organization activities. An organization is linked to the kinds it is capable of. | vocab OrgActivity |
| acquisition activity | `ICON:0001021` | organizational activity | Buying land, water or easements, or rights in them, for conservation. | term Acquisition |
| advising activity | `ICON:0001022` | organizational activity | Giving expert advice to landowners, agencies or other organizations. | term Advising |
| advocacy activity | `ICON:0001023` | organizational activity | Arguing for a cause or a policy before the public or decision makers. | term Advocacy |
| agricultural production activity | `ICON:0001024` | organizational activity | Growing crops or raising livestock. | term Agricultural Production |
| certification activity | `ICON:0001025` | organizational activity | Checking that land, products or practices meet a standard and certifying them. | term Certification |
| construction activity | `ICON:0001026` | organizational activity | Building or rebuilding structures, such as fish passage, levees or crossings. | term Construction |
| coordinating activity | `ICON:0001027` | organizational activity | Bringing organizations together and keeping their work aligned. | term Coordinating |
| education activity | `ICON:0001028` | organizational activity | Teaching the public, students or practitioners. | term Education |
| funding activity | `ICON:0001029` | organizational activity | Paying for other organizations' work, as through grants or contracts. | term Funding |
| governing activity | `ICON:0001030` | organizational activity | Exercising public authority over a jurisdiction. | term Governing |
| habitat enhancement activity | `ICON:0001031` | organizational activity | Restoring or improving habitat, such as replanting, removing invasive plants or reconnecting floodplains. | term Habitat Enhancement |
| management activity | `ICON:0001032` | organizational activity | Managing land, water or wildlife over time. | term Management |
| planning activity | `ICON:0001033` | organizational activity | Preparing plans for conservation, land use or resources. | term Planning |
| policy activity | `ICON:0001034` | organizational activity | Making or shaping policy. | term Policy |
| production activity | `ICON:0001035` | organizational activity | Producing goods or energy other than crops and livestock. | term Production |
| regulating activity | `ICON:0001036` | organizational activity | Issuing and enforcing permits and rules. | term Regulating |
| research activity | `ICON:0001037` | organizational activity | Studying nature or conservation. close match investigation (`OBI:0000066`). | term Research |
| services activity | `ICON:0001038` | organizational activity | Providing services to others, such as technical, legal or financial services. | term Services |
| monitoring activity | `ICON:0001039` | organizational activity | Repeating surveys or measurements over years to track the status of species, habitats, water or fisheries. | term Monitoring |

## Relations

| Relation | ID | Reverse | From → to | Definition | Explorer |
|---|---|---|---|---|---|
| has org type | `ICON:0001100` | is org type of | organization (`OBI:0000245`) → any | Links an organization to one of the organization type classes it belongs to. The explorer's way of stating the organization's class. | phrase has org type |
| is org type of | `ICON:0001101` | has org type | any → any | The reverse of has org type. | phrase is org type of |
| capable of | `RO:0002215` (reused) |  | any → any | An organization is capable of a kind of organizational activity. The explorer's does. Source: A relation between a material entity (such as a cell) and a process, in which the material entity has the ability to carry out the process.  | phrase does |
| is activity of | `ICON:0001102` | capable of (`RO:0002215`) | any → any | A kind of activity an organization carries out: the reverse of capable of. | phrase is activity of |
| is member of | `ICON:0001103` | has member | organization (`OBI:0000245`) → organization (`OBI:0000245`) | An organization belongs to a coalition, association or partnership as a member while keeping its own identity. A kind of part of in the explorer. close match member of (`org:memberOf`); close match memberOf (`schema:memberOf`). Kind of: is member of organization (`OBI:0000846`), part of (`BFO:0000050`). | phrase is member of |
| has member | `ICON:0001104` | is member of | any → any | The reverse of is member of. close match has member (`org:hasMember`). Kind of: has organization member (`OBI:0001688`), has part (`BFO:0000051`). | phrase has member |
| has partner | `ICON:0001105` | is partner of | any → any | An organization that works on a project or program alongside its lead, without leading or funding it. Kind of: is involved with (Core). (symmetric) | phrase has partner |
| is partner of | `ICON:0001106` | has partner | any → any | The reverse of has partner. Kind of: is involved with (Core). (symmetric) | phrase is partner of |
| is published by | `ICON:0001107` | published | any → organization (`OBI:0000245`) | The organization responsible for making data or a publication available, when it is not the creator. close match Publisher (`dcterms:publisher`); close match publisher (`schema:publisher`). | phrase is published by |
| published | `ICON:0001108` | is published by | any → any | The reverse of is published by. | phrase published |
| located in county | `ICON:0001109` | is county location of | organization (`OBI:0000245`) → county (Places) | The county that holds the organization's headquarters, main office or seat. An organization is located in at most one county, and may operate in many (#949). close match location (`schema:location`); close match primary Site (`org:hasPrimarySite`). Kind of: located in area (Places). (functional) | phrase located in county |
| is county location of | `ICON:0001110` | located in county | any → any | The reverse of located in county: the county holds the organization's headquarters. | phrase is county location of |
| located in ecoregion | `ICON:0001111` | is ecoregion location of | organization (`OBI:0000245`) → ecoregion (`ENVO:01000276`) | The ecoregion section that holds the organization's headquarters, main office or seat. An organization is located in at most one ecoregion section, and may work in many (#949). close match location (`schema:location`); close match primary Site (`org:hasPrimarySite`). Kind of: in ecoregion (Places), located in (`RO:0001025`). (functional) | phrase located in ecoregion |
| is ecoregion location of | `ICON:0001112` | located in ecoregion | any → any | The reverse of located in ecoregion: the ecoregion section holds the organization's headquarters. | phrase is ecoregion location of |
