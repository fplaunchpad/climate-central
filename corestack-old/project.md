# COREStack

**Marquee:** M2 — Env/Social/Governance  
**External collaborator:** Aaditeshwar Seth (Microsoft Chair Professor, IIT Delhi)  
**FPL lead:** Alina Banerjee  
**GitHub issues:** [#48](https://github.com/fplaunchpad/project-management/issues/48) · [#53](https://github.com/fplaunchpad/project-management/issues/53)

COREStack is Aaditeshwar Seth's data pipeline infrastructure for environment/social/governance work. FPL is contributing to the codebase and exploring how typed programming tools can improve its reliability and maintainability.

## Resources

- Repo: https://github.com/core-stack-org/core-stack-backend
- Docs: https://docs.core-stack.org
- Developer community: https://core-stack.org/core-stack-developer-community/
- Google Groups: [core-stack-dev](https://groups.google.com/g/core-stack-dev) · [core-stack-nrm](https://groups.google.com/g/core-stack-nrm)
- Roadmap deck: [core-stack-2.0.pptx](core-stack-2.0.pptx)

### Roadmap summary (May 2026 deck)

**Current state:** Multiple pipelines on Google Earth Engine produce tehsil-level raster/vector files. Data for any entity is spread across multiple files; STAC specs describe each. APIs and static JSONs pull it together for the frontend (KYL, CC).

**June (ongoing):**
- Shift compute from GEE to local GPU workstations; GEE retained only for raw satellite layers (LULCs)
- STACD: single-click generation of all layers for a location instead of layer-by-layer
- Build GeoParquets for all vector data, one per entity type, with standardised columns
- Two problems being addressed: (1) column/structure changes ripple through the whole codebase, (2) computations are not centralised, causing bugs from different people re-implementing the same logic

**July (goal):**
- Backend serves well-structured GeoParquets via STACD; raster data via Raquet or DuckDB geospatial extension
- Frontend reads exclusively from GeoParquets via a library API
- Natural language frontend on top of the library
- Global variables (start-year, end-year) so the frontend is flexible to change detection and statistics
- Generalisable: any region globally can spin up a local instance from a minimal base dataset

## Work streams

### 1. Data pipeline and library ([#48](https://github.com/fplaunchpad/project-management/issues/48))

Organize CoRE stack data and pipelines as geoparquets, build a library of common functions (correlations, graph embeddings, clustering), and make the data queryable using natural language. Aadi has students working on this and FPL fellows are joining in.

### 2. Python static typing ([#53](https://github.com/fplaunchpad/project-management/issues/53))

Add a type system to the Python `core-stack-backend` codebase to improve maintainability. The pipeline has been fragile due to lack of typing. KC leading this.

Tools under consideration:
- [`astral ty`](https://github.com/astral-sh/ty) — fast, from the Ruff/uv team
- [Pyrefly](https://pyrefly.org) (Meta, v1.0 released May 2026) — strong framework support (Pydantic, Django), `pyrefly infer` for auto-generating annotations on existing untyped code, 125x faster incremental updates

### 3. Local storage and compute (exploratory)

Store and process TESSERA satellite embeddings (~300TB for India) locally rather than relying on Google Earth Engine. Aadi is building a GPU cluster at IITD; potential to set up matching infra at IITM.

## Meetings

See [README](README.md) for the meetings log.
