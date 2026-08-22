# Reactome

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

Reactome is a free, open-source, curated, and peer-reviewed biological pathway database. It provides comprehensive pathway data covering human biology and orthologous reactions for over 14 non-human species. The platform exposes two primary REST APIs for programmatic access to pathway data, molecular interactions, species comparisons, reaction network visualization, and pathway enrichment analysis.

## APIs

### Content Service

Base URL: `https://reactome.org/ContentService`

Provides access to all Reactome knowledgebase content:

- Query pathways, reactions, physical entities, and complexes by identifier
- Retrieve pathway hierarchies and ancestor relationships
- Export pathway diagrams in PNG, JPG, SVG, GIF, PDF, SBML, and SBGN formats
- Search via Solr full-text search with faceting and autocomplete
- Query PSICQUIC interactor databases
- Map external identifiers (Ensembl, UniProt, etc.) to Reactome entities
- Compare orthologous reactions across species

Documentation: https://reactome.org/dev/content-service
Interactive API: https://reactome.org/ContentService/

### Analysis Service

Base URL: `https://reactome.org/AnalysisService`

Enables pathway enrichment analysis for gene and protein identifier lists:

- Submit identifier lists via POST, file upload, or URL reference
- Automatic detection of overrepresentation or expression analysis
- Results include pathway hits, p-values, FDR, entity and reaction counts
- Token-based result retrieval (valid 7+ days) without data re-submission
- Filter results by species
- Export results as CSV, JSON, or PDF report
- Species comparison against Homo sapiens

Documentation: https://reactome.org/dev/analysis
Interactive API: https://reactome.org/AnalysisService/

## Access

Both APIs are freely accessible without authentication or API keys. There are no usage fees or registration requirements.

## Client Libraries

- Python: `pip install reactome2py` — https://reactome.github.io/reactome2py/
- R: `ReactomePA` via Bioconductor — https://bioconductor.org/packages/ReactomePA
- R: `rbioapi` via CRAN — https://cran.r-project.org/package=rbioapi

## Data Downloads

Full dataset downloads available at https://reactome.org/download-data including BioPAX, SBML, PSI-MITAB, GMT, and Neo4j database dumps.

## License

All Reactome data is released under Creative Commons Attribution 4.0 International (CC BY 4.0). Application source code is available at https://github.com/reactome under open-source licenses.

## Links

- Website: https://reactome.org
- Developer Zone: https://reactome.org/dev
- Documentation: https://reactome.org/documentation
- GitHub: https://github.com/reactome
- Contact: help@reactome.org
