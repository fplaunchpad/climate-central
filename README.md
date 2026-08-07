# climate-docs

## FPL Internal

#### 📝 Internal Docs & Notes

- ["FPL INTERNAL: Bugs and first issues"](https://docs.google.com/document/d/1AdriKFhdt2SkbsSQr6f9e0gQMpJjfOiMv0TPbS4y3og/edit?usp=sharing) — Aadi Seth's original doc, annotated by the team.
- [Links and Docs](links-and-docs.md) — full archive of every document and link shared in `#fpl-esg`, plus [`channel-files/`](channel-files/) with the actual files mirrored out of Slack.

---

## CoreStack

CoRE Stack (Aaditeshwar Seth's project) is the main platform underlying FPL's climate/ESG work. Code lives across two orgs: `core-stack-org` (upstream) and `fplaunchpad` (FPL's contributions).

#### 🔗 Repo

- [core-stack-org/core-stack-backend](https://github.com/core-stack-org/core-stack-backend) — Django app that computes layers (LULC, drought, hydrology, etc.), serves the API, and orchestrates GEE/GeoServer.
- [core-stack-org/landscape-explorer](https://github.com/core-stack-org/landscape-explorer) — React + OpenLayers frontend for viewing layers.
- [core-stack-org/Commons-Connect](https://github.com/core-stack-org/Commons-Connect) — Vite/React app for watershed planning, run inside a Flutter WebView.

#### 📘 Official Documentation

- [docs.core-stack.org](https://docs.core-stack.org)
- [core-stack.org/category/knowledge/nuts-bolts](https://core-stack.org/category/knowledge/nuts-bolts/) — best broad-overview entry point
- [core-stack.org/core-stack-developer-community](https://core-stack.org/core-stack-developer-community/)
- [core-stack.org/core-stack-technical-manual-v2](https://core-stack.org/core-stack-technical-manual-v2/) — technical manual (6 Mar 2025); companion PDF: [CoRE_v2_layers](https://drive.google.com/file/d/1ZxovdpPThkN09cB1TcUYSE2BImI7M3k_/view)
- [deepwiki.com/core-stack-org/core-stack-backend](https://deepwiki.com/core-stack-org/core-stack-backend/1-overview) — auto-generated from latest commits
- [groups.google.com/u/2/g/core-stack-dev](https://groups.google.com/u/2/g/core-stack-dev) — Google Group
- [Discord](https://discord.gg/FQBawGkmhQ)

#### 🏠 Internal Repo

- [fplaunchpad/core-stack-backend](https://github.com/fplaunchpad/core-stack-backend) — FPL's fork of the backend, incl. [wiki](https://github.com/fplaunchpad/core-stack-backend/wiki)
- [fplaunchpad/fpl-core-stack](https://github.com/fplaunchpad/fpl-core-stack) — joint FPL↔CoreStack planning/coordination (not a fork)
- [fplaunchpad/corestack-rag](https://github.com/fplaunchpad/corestack-rag) — RAG over the CoreStack codebase and docs

#### 📝 Internal Docs & Notes

- [Drought calculation math](corestack-drought-model.pdf)
- [Alina's IIT-D visit notes](https://docs.google.com/document/d/1SsQ5lZ3Lq1r9tm6opPSps7s-8thol6pU0rAwiON7RYo)
- [Project objectives/outline doc](https://docs.google.com/document/d/1gbKquHlHJRJA2ESPYiaxQ68b_OasRbcTp1H-JpN6jNc)
- [channel-files/FPL-IITDelhi-CoreStack-Meeting-2026-05-21.md](channel-files/FPL-IITDelhi-CoreStack-Meeting-2026-05-21.md)
- [channel-files/gbif-biodiversity-implementation-guide.md](channel-files/gbif-biodiversity-implementation-guide.md), [channel-files/Species-Plan.md](channel-files/Species-Plan.md), [channel-files/SPECIES_CHANGE_DETECTION_FEASIBILITY.md](channel-files/SPECIES_CHANGE_DETECTION_FEASIBILITY.md), [channel-files/species-plan.pdf](channel-files/species-plan.pdf) — GBIF biodiversity layer work
- [channel-files/CoRE-Stack-Backend-pipeline-understanding.pdf](channel-files/CoRE-Stack-Backend-pipeline-understanding.pdf), [channel-files/CoRE-Stack-Briefing.pdf](channel-files/CoRE-Stack-Briefing.pdf)
- [channel-files/core-stack-rag-source-inventory.md](channel-files/core-stack-rag-source-inventory.md) — exhaustive source list used to build the RAG

#### 🗂️ Project Management

- [![#48](https://img.shields.io/badge/%2348-in%20progress-brightgreen)](https://github.com/fplaunchpad/project-management/issues/48) [Corestack new features](https://github.com/fplaunchpad/project-management/issues/48)
- [![#53](https://img.shields.io/badge/%2353-in%20progress-brightgreen)](https://github.com/fplaunchpad/project-management/issues/53) [Corestack codebase refactor+upgrade](https://github.com/fplaunchpad/project-management/issues/53)
- [![#130](https://img.shields.io/badge/%23130-in%20progress-brightgreen)](https://github.com/fplaunchpad/project-management/issues/130) [Corestack understanding and documentation](https://github.com/fplaunchpad/project-management/issues/130)

---

## TESSERA

TESSERA is Cambridge's geospatial foundation-model project (Anil Madhavapeddy's group); FPL is exploring where it overlaps with CoRE Stack's pipelines.

#### 🔗 Repo

- [ucam-eo/geotessera](https://github.com/ucam-eo/geotessera)
- [ucam-eo/tessera](https://github.com/ucam-eo/tessera)

#### 📘 Official Documentation

- [TESSERA paper](https://arxiv.org/abs/2506.20380)
- [geotessera issue #314](https://github.com/ucam-eo/geotessera/issues/314)
- [eeg.zulipchat.com](https://eeg.zulipchat.com/login/) — Cambridge EEG group Zulip

#### 🏠 Internal Repo

- [fplaunchpad/x-ocaml](https://github.com/fplaunchpad/x-ocaml) — interactive browser-based OCaml notebooks (built on `x-ocaml` and `js_top_worker`)

#### 📝 Internal Docs & Notes

- [channel-files/TESSERA-understanding.pdf](channel-files/TESSERA-understanding.pdf)

#### 🗂️ Project Management

- [![#52](https://img.shields.io/badge/%2352-todo-yellow)](https://github.com/fplaunchpad/project-management/issues/52) [TESSERA notebooks](https://github.com/fplaunchpad/project-management/issues/52)

---

## Other climate projects

Planning-stage work not yet tied to a specific platform.

#### 🗂️ Project Management

- [![#133](https://img.shields.io/badge/%23133-in%20progress-brightgreen)](https://github.com/fplaunchpad/project-management/issues/133) [Climate applications: planning](https://github.com/fplaunchpad/project-management/issues/133) — identifying concrete milestones and research questions across two prongs: helping other groups doing environmental work in India, and enhancing OCaml climate libraries. No repo or dedicated docs yet.
