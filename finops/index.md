# Reactome API FinOps

## Cost Summary

Reactome is a fully free and open biological pathway database. There are no
costs, subscription fees, usage-based charges, or overage fees for any of its
APIs, data downloads, or software packages. The project is funded by NIH
NHGRI and EMBL-EBI grants and operates as a public scientific resource.

| Service | Cost |
|---------|------|
| Content Service API | Free |
| Analysis Service API | Free |
| R packages (ReactomePA, rbioapi) | Free |
| Python package (reactome2py) | Free |
| Data downloads (BioPAX, SBML, JSON) | Free |
| Neo4j graph database dump | Free |
| Self-hosted deployment (software) | Free (open source) |

## Budget Planning

Because Reactome has no pricing tiers or usage fees, there are no direct API
costs to plan for in a FinOps budget. Cost exposure for teams integrating
Reactome is limited to:

- **Engineering time** for integration development and maintenance
- **Infrastructure costs** for systems consuming the API (compute, storage,
  network egress from your environment)
- **Self-hosting costs** if running a local Reactome instance (Neo4j, Solr,
  MySQL, application server compute and storage)

## Cost Optimization Strategies

### For API Consumers

1. **Cache Content Service responses** — Pathway and entity data only changes
   between Reactome quarterly releases. Cache responses for hours or days to
   avoid redundant network calls.

2. **Use Analysis Service tokens** — After submitting an identifier list for
   enrichment analysis, the returned token allows repeated result retrieval
   for 7 days (longer via LRU cache). Do not re-submit the same identifier
   list on each request.

3. **Download bulk data for large-scale needs** — For processing full pathway
   coverage or building local indexes, download dataset dumps from
   https://reactome.org/download-data rather than scraping via API. This
   eliminates network round-trips and removes API load.

4. **Use R or Python clients** — The `ReactomePA` and `reactome2py` packages
   include built-in logic for batching requests and handling responses
   efficiently, reducing integration development time.

5. **Limit diagram export calls** — Pathway diagram export endpoints (PNG,
   SVG, PDF) are compute-intensive on Reactome servers. Cache exported images
   in your application layer rather than re-requesting on each page load.

### For Self-Hosted Deployments

1. **Right-size Neo4j** — The Reactome graph database is the primary resource
   consumer. Benchmark against your expected query patterns before committing
   to instance size.

2. **Use Neo4j memory configuration** — Reactome's graph database benefits
   significantly from heap and page cache tuning. Follow Neo4j's memory
   configuration guide for production deployments.

3. **Isolate the Analysis Service** — The Analysis Service is CPU-intensive
   for large identifier list submissions. Running it on dedicated compute
   prevents it from affecting Content Service response times.

4. **Schedule bulk data ingestion off-hours** — If ingesting Reactome dump
   files into a local system, schedule during low-demand periods to avoid
   competing with interactive API users.

## Sustainability and Funding

Reactome is sustained by:

- NIH National Human Genome Research Institute (NHGRI) grants
- European Bioinformatics Institute (EMBL-EBI) support
- Ontario Institute for Cancer Research (OICR) contributions
- New York University (NYU) contributions

The project is not a commercial entity. Organizations benefiting from Reactome
are encouraged to acknowledge it in publications:

> Gillespie M, et al. (2022). The reactome pathway knowledgebase 2022. Nucleic
> Acids Research, 50(D1), D687–D692. https://doi.org/10.1093/nar/gkab1028

## Contact

- help@reactome.org
- https://reactome.org/about/contact-us
- https://reactome.org
