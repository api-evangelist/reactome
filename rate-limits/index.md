# Reactome API Rate Limits

## Overview

Reactome does not publish explicit numeric rate limits for the Content Service
or the Analysis Service. Both APIs are designed for research use and are
expected to be accessed at reasonable rates consistent with scientific
workflows. There is no authentication or API key system; access is anonymous
and free.

## Content Service (`https://reactome.org/ContentService`)

| Parameter | Value |
|-----------|-------|
| Authentication required | No |
| API key required | No |
| Published rate limit | Not specified |
| Expected usage pattern | Moderate research queries |
| Response format | JSON, plain text, TSV |

The Content Service is backed by a Neo4j graph database and Solr search index.
It handles pathway queries, entity lookups, diagram exports, and interactor
searches. Best practice is to cache responses locally and avoid high-frequency
polling.

## Analysis Service (`https://reactome.org/AnalysisService`)

| Parameter | Value |
|-----------|-------|
| Authentication required | No |
| API key required | No |
| Published rate limit | Not specified |
| Token validity | 7 days from analysis submission |
| Result caching | LRU queue after 7 days (may persist longer) |

The Analysis Service is compute-intensive. After submitting an identifier list,
results are returned with a token that allows subsequent retrieval of results
without re-submitting data for up to 7 days (and potentially longer via LRU
cache). This token mechanism is the primary mechanism for avoiding repeated
heavy computation.

## HTTP Status Codes

| Code | Meaning |
|------|---------|
| 200 | Success |
| 400 | Bad request — invalid parameters or malformed input |
| 404 | Resource not found — invalid identifier or stale token |
| 406 | Not acceptable — unsupported response format requested |
| 500 | Internal server error |

## Best Practices

1. **Cache pathway data locally** — Reactome releases new versions
   approximately quarterly; pathway structure does not change between releases.
2. **Use the Analysis Service token** — After submitting identifiers, store the
   returned token and use it to retrieve paginated results rather than
   re-submitting the same identifier list.
3. **Download bulk data instead of scraping** — For large-scale data
   requirements, use the download portal at https://reactome.org/download-data
   rather than issuing many individual API requests.
4. **Use species-scoped endpoints** — When querying pathways for non-human
   species, use the species-specific endpoints to reduce result set size.
5. **Export diagrams sparingly** — Diagram export (PNG, SVG, PDF) is
   resource-intensive on the server; cache exported images on your side.
6. **Contact for high-volume access** — For unusually high volume use,
   contact help@reactome.org or consider deploying a local Reactome instance
   using the open-source software at https://github.com/reactome.

## Self-Hosted Deployments

For environments requiring guaranteed performance, high throughput, or data
privacy, Reactome can be deployed locally. The full technology stack is
open source:

- Content Service: https://github.com/reactome/content-service
- Analysis Service: https://github.com/reactome/analysis-service
- Graph Database: Neo4j with Reactome dump from https://reactome.org/download-data

Self-hosted deployments have no external rate limits.

## Contact

- Technical questions: help@reactome.org
- Website: https://reactome.org
