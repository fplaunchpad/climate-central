# climate-docs

## FPL Internal

- ["FPL INTERNAL: Bugs and first issues"](https://docs.google.com/document/d/1AdriKFhdt2SkbsSQr6f9e0gQMpJjfOiMv0TPbS4y3og/edit?usp=sharing) — Aadi Seth's original doc, annotated by the team.
- [Links and Docs](links-and-docs.md) — full archive of every document and link shared in `#fpl-esg`, plus [`channel-files/`](channel-files/) with the actual files mirrored out of Slack.

## CoreStack

CoRE Stack (Aaditeshwar Seth's project) is the main platform underlying FPL's climate/ESG work. Code lives across two orgs: `core-stack-org` (upstream) and `fplaunchpad` (FPL's contributions).

- **Backend**: [core-stack-org/core-stack-backend](https://github.com/core-stack-org/core-stack-backend) — Django app that computes layers (LULC, drought, hydrology, etc.), serves the API, and orchestrates GEE/GeoServer. FPL fork: [fplaunchpad/core-stack-backend](https://github.com/fplaunchpad/core-stack-backend).
- **Frontend**: [core-stack-org/landscape-explorer](https://github.com/core-stack-org/landscape-explorer) — React + OpenLayers app for viewing layers.
- **Mobile**: [core-stack-org/Commons-Connect](https://github.com/core-stack-org/Commons-Connect) — Vite/React app for watershed planning, run inside a Flutter WebView.
- [Drought calculation math](corestack-drought-model.pdf) — reference on the drought layer's algorithm.

FPL project work on CoRE Stack:

- [Corestack new features](https://github.com/fplaunchpad/project-management/issues/48) — [fplaunchpad/fpl-core-stack](https://github.com/fplaunchpad/fpl-core-stack), bringing OxCaml to the backend pipeline.
- [Corestack codebase refactor+upgrade](https://github.com/fplaunchpad/project-management/issues/53) — exploring static typing for the Python backend.
- [Corestack understanding and documentation](https://github.com/fplaunchpad/project-management/issues/130) — [fplaunchpad/corestack-rag](https://github.com/fplaunchpad/corestack-rag), shared knowledge base for the ESG group's CoRE Stack work.

## TESSERA

TESSERA is Cambridge's geospatial foundation-model project (Anil Madhavapeddy's group); FPL is exploring where it overlaps with CoRE Stack's pipelines.

- [TESSERA paper](https://arxiv.org/abs/2506.20380)
- [ucam-eo/geotessera](https://github.com/ucam-eo/geotessera), [ucam-eo/tessera](https://github.com/ucam-eo/tessera)
- [TESSERA notebooks](https://github.com/fplaunchpad/project-management/issues/52) — [fplaunchpad/x-ocaml](https://github.com/fplaunchpad/x-ocaml), interactive browser-based OCaml notebooks explored for integration with CoRE Stack's data pipelines.

## Other climate projects

- [Climate applications: planning](https://github.com/fplaunchpad/project-management/issues/133) — planning and coordination for the ESG group's climate applications beyond CoRE Stack/TESSERA: identifying concrete milestones, research questions, and the two main prongs of activity (helping other groups doing environmental work in India, and enhancing OCaml climate libraries).
