# Reactome API Plans

Reactome is a free, open-source biological pathway database funded by grants
from the NIH National Human Genome Research Institute (NHGRI) and the European
Bioinformatics Institute (EMBL-EBI). Both the Content Service and the Analysis
Service are available at no cost with no registration required.

## Free Open Access (Default)

All Reactome API endpoints are publicly accessible without authentication,
API keys, or account registration.

- Full access to the Content Service at `https://reactome.org/ContentService`
- Full access to the Analysis Service at `https://reactome.org/AnalysisService`
- All pathway data, reaction data, and molecular interaction data
- Diagram export in PNG, JPG, SVG, GIF, PDF, SBML, and SBGN formats
- Pathway enrichment analysis for gene and protein identifier lists
- Coverage of human biology and 14+ non-human species orthologs
- No usage quotas or hard rate limits published for research use
- Data licensed under Creative Commons Attribution 4.0 (CC BY 4.0)

## Programmatic R Access (Free)

Reactome provides the `ReactomePA` Bioconductor R package and the `rbioapi`
R package for programmatic access through familiar R workflows.

- `ReactomePA` available via Bioconductor: https://bioconductor.org/packages/ReactomePA
- `rbioapi` available via CRAN: https://cran.r-project.org/package=rbioapi
- No cost; open-source packages

## Python Access (Free)

The `reactome2py` Python package wraps both the Content Service and Analysis
Service for convenient scripted access.

- Available via PyPI: `pip install reactome2py`
- Documentation: https://reactome.github.io/reactome2py/
- No cost; open-source

## Data Downloads (Free)

For bulk data access, Reactome provides full database downloads rather than
encouraging heavy API usage:

- Download portal: https://reactome.org/download-data
- Available formats: BioPAX, SBML, PSI-MITAB, GMT, JSON
- Full Neo4j graph database dumps available for self-hosting
- No cost; data released under CC BY 4.0

## Self-Hosted Instance

Reactome software is open source and can be deployed locally:

- GitHub: https://github.com/reactome
- Requires Neo4j, Solr, and MySQL infrastructure
- Apache License applies to application code
- Suitable for air-gapped environments or high-volume institutional use

## Contact

- General questions: help@reactome.org
- Website: https://reactome.org/about/contact-us
