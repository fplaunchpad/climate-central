# climate-docs
Main page for Climate related projects: Info and study material on Tessera, Corestack etc

Bugs and First Issues from Aadi Seth:
https://docs.google.com/document/u/1/d/1AdriKFhdt2SkbsSQr6f9e0gQMpJjfOiMv0TPbS4y3og/edit?usp=sharing

[Drought calculation math](corestack-drought-model.pdf)

See [Links and Docs](links-and-docs.md) for a full archive of every resource shared in #fpl-esg.

## CoRE Stack

CoRE Stack (Aaditeshwar Seth's project) is the main platform underlying FPL's climate/ESG work. Code lives across two orgs: `core-stack-org` (upstream) and `fplaunchpad` (FPL's contributions).

- **Backend**: [core-stack-org/core-stack-backend](https://github.com/core-stack-org/core-stack-backend) — Django app that computes layers (LULC, drought, hydrology, etc.), serves the API, and orchestrates GEE/GeoServer. FPL fork: [fplaunchpad/core-stack-backend](https://github.com/fplaunchpad/core-stack-backend).
- **Frontend**: [core-stack-org/landscape-explorer](https://github.com/core-stack-org/landscape-explorer) — React + OpenLayers app for viewing layers.
- **Mobile**: [core-stack-org/Commons-Connect](https://github.com/core-stack-org/Commons-Connect) — Vite/React app for watershed planning, run inside a Flutter WebView.

FPL project work on CoRE Stack:

- [CoRE Stack new features](https://github.com/fplaunchpad/project-management/issues/48) — [fplaunchpad/fpl-core-stack](https://github.com/fplaunchpad/fpl-core-stack), bringing OxCaml to the backend pipeline.
- [CoRE Stack codebase refactor+upgrade](https://github.com/fplaunchpad/project-management/issues/53) — exploring static typing for the Python backend.
- [CoRE Stack understanding and documentation](https://github.com/fplaunchpad/project-management/issues/130) — [fplaunchpad/corestack-rag](https://github.com/fplaunchpad/corestack-rag), shared knowledge base for the ESG group's CoRE Stack work.
