# Reactome

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
