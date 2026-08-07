# Links and Docs

Every document and link shared in [#fpl-esg](https://fplaunchpad.slack.com/archives/C0B3GBWL97U) on Slack, channel history 2026-05-13 through 2026-08-07, collected in full. Status notes (dead, superseded, personal account, unconfirmed) are informational, not a recommendation to skip them.

The channel also has a pinned Slack canvas called "References/Links" (F0BBM6RDQUC) with an overlapping curated list, maintained by the team directly in Slack.

## CoRE Stack official resources

- [core-stack.org](https://core-stack.org) — main site
- [core-stack.org/our-team-2](https://core-stack.org/our-team-2)
- [docs.core-stack.org](https://docs.core-stack.org) — main docs
- [docs.core-stack.org/developers/installer](https://docs.core-stack.org/developers/installer/#__tabbed_1_2) — install docs (flagged stale/incorrect by Alina and KC, 2026-06-01 to 06-06)
- [core-stack.org/category/knowledge/nuts-bolts](https://core-stack.org/category/knowledge/nuts-bolts/) — best broad-overview entry point
- [core-stack.org/core-stack-developer-community](https://core-stack.org/core-stack-developer-community/)
- [core-stack.org/core-stack-technical-manual-v2](https://core-stack.org/core-stack-technical-manual-v2/) — technical manual, dated 6 Mar 2025; companion PDF: [CoRE_v2_layers](https://drive.google.com/file/d/1ZxovdpPThkN09cB1TcUYSE2BImI7M3k_/view)
- [core-stack.org/early-lessons-from-the-corestack-pilots](https://core-stack.org/early-lessons-from-the-corestack-pilots/)
- [groups.google.com/u/2/g/core-stack-dev](https://groups.google.com/u/2/g/core-stack-dev) — Google Group
- Discord: ~~discord.gg/KNxtgt6Aa~~ (dead, shared twice) — replaced by [discord.gg/FQBawGkmhQ](https://discord.gg/FQBawGkmhQ)
- [eeg.zulipchat.com/login](https://eeg.zulipchat.com/login/) — Cambridge EEG group Zulip
- [core-stack-backend wiki](https://github.com/fplaunchpad/core-stack-backend/wiki)
- [deepwiki.com/core-stack-org/core-stack-backend](https://deepwiki.com/core-stack-org/core-stack-backend/1-overview) — auto-generated docs from latest commits
- [stac.core-stack.org](https://stac.core-stack.org/?.language=en) — generic STAC Browser, not CoreStack-specific code
- [explorer.core-stack.org/kyl_dashboard](https://www.explorer.core-stack.org/kyl_dashboard) — candidate current frontend (unconfirmed)
- [ee-shiva GEE app](https://ee-shiva.projects.earthengine.app/view/gee-app-2) — reported non-functional
- CoP call (monthly): [Zoom](https://us02web.zoom.us/j/85110791924), meeting ID 851 1079 1924 (passcode shared separately in-channel, omitted here since this repo is public)
- Upstream repo: [core-stack-org/core-stack-backend](https://github.com/core-stack-org/core-stack-backend), incl. [PR #1055](https://github.com/core-stack-org/core-stack-backend/pull/1055)

## FPL internal planning docs

- ["Bugs and first issues" — Aadi's original doc](https://docs.google.com/document/d/1xmHbL3Em0XG4whKvdqqa8ShNr3pjQVH7uF23nv6DszM)
- ["FPL INTERNAL: Bugs and first issues"](https://docs.google.com/document/d/1AdriKFhdt2SkbsSQr6f9e0gQMpJjfOiMv0TPbS4y3og) — annotated internal copy, the actively used version (also linked from the main README)
- [Alina's IIT-D visit notes](https://docs.google.com/document/d/1SsQ5lZ3Lq1r9tm6opPSps7s-8thol6pU0rAwiON7RYo)
- [Initial meeting notes, 2026-05-21](https://docs.google.com/document/d/1HScK6D5i_sNOdUoqQgP9VCU3Sm3APpPu-AfFTfX6S90)
- [Project objectives/outline doc](https://docs.google.com/document/d/1gbKquHlHJRJA2ESPYiaxQ68b_OasRbcTp1H-JpN6jNc) — current, finalized 2026-08-05; earlier draft: [17TU_uia3tZploNgFoaqnzXYqfRg4aEP1_XVwqHN0yjQ](https://docs.google.com/document/d/17TU_uia3tZploNgFoaqnzXYqfRg4aEP1_XVwqHN0yjQ)
- [hackmd draft](https://hackmd.io/@alina-fpl/HJEKRVD4Ml)
- [GEE from-scratch tutorial doc](https://docs.google.com/document/d/1dLSaGXlAnI0jK6LAB6F-gQLBA30NTT0pz1tovHfOmvI)
- [Gemini meeting notes, 2026-06-08](https://docs.google.com/document/d/1-sq7-a78bMTNVR4CfDhbhmOJFsSAdYtaC_b-N9FGgxc)
- Docker setup gists, in sequence (each superseding the last):
  1. [gist 794160a9](https://gist.github.com/alinab/794160a9e1fea9b3c46b37abed4ba6d3) — first write-up
  2. [gist bb0c98e5](https://gist.github.com/alinab/bb0c98e5aaa4c41c9b46bd9d662cc79c) — working script
  3. [gist 97acafa60e](https://gist.github.com/alinab/97acafa60e452e741108318acde5b211) — final: Dockerfile + RUNCORESTACK.md, confirmed working by two testers
  4. [gist ce5a4b04](https://gist.github.com/alinab/ce5a4b04106c347a24bd6e81132eb2d3) — rewritten notes

## Code repos and branches

- [fplaunchpad/core-stack-backend](https://github.com/fplaunchpad/core-stack-backend) — the FPL fork
  - branch [wip-typify](https://github.com/fplaunchpad/core-stack-backend/blob/wip-typify/computing/crop_grid/crop_grid.py) — pyrefly typing work
  - branch [wip-feature-ocaml-geocompute](https://github.com/fplaunchpad/core-stack-backend/tree/wip-feature-ocaml-geocompute) — OCaml port, see [Geocaml-exploring.md](https://github.com/fplaunchpad/core-stack-backend/blob/wip-feature-ocaml-geocompute/myref/Geocaml-exploring.md) and [Geocml-usage-on-15-Branches.md](https://github.com/fplaunchpad/core-stack-backend/blob/wip-feature-ocaml-geocompute/myref/Geocml-usage-on-15-Branches.md)
  - branch [docker-install](https://github.com/fplaunchpad/core-stack-backend/tree/docker-install)
  - setup docs on `main`: [fpl-setup-mac.md](https://github.com/fplaunchpad/core-stack-backend/blob/main/docs/fpl-setup-mac.md), [fpl-setup-linux.md](https://github.com/fplaunchpad/core-stack-backend/blob/main/docs/fpl-setup-linux.md), [lulc_pipeline_test.py](https://github.com/fplaunchpad/core-stack-backend/blob/main/computing/misc/lulc_pipeline_test.py)
- [alinab/fork-core-stack-backend](https://github.com/alinab/fork-core-stack-backend/tree/docker-install) — personal fork, abandoned 2026-06-12 in favor of the org fork above
- [fplaunchpad/fpl-core-stack](https://github.com/fplaunchpad/fpl-core-stack), incl. [PR #1](https://github.com/fplaunchpad/fpl-core-stack/pull/1)
- [fplaunchpad/corestack-rag](https://github.com/fplaunchpad/corestack-rag)
- [Sajjan-Naveen-87/codeatlas](https://github.com/Sajjan-Naveen-87/codeatlas) — personal account (S Naveen)
- [github.com/geocaml](https://github.com/geocaml), incl. [ocaml-geojson](https://github.com/geocaml/ocaml-geojson), [ocaml-parquet](https://github.com/geocaml/ocaml-parquet)
- [tangled.org/gazagnaire.org/ocaml-parquet](https://tangled.org/gazagnaire.org/ocaml-parquet) — alternate Parquet library
- [github.com/raven-ml/raven](https://github.com/raven-ml/raven)

## Academic papers and external reading

- [TESSERA paper](https://arxiv.org/abs/2506.20380)
- [ucam-eo/geotessera](https://github.com/ucam-eo/geotessera) (incl. [issue #314](https://github.com/ucam-eo/geotessera/issues/314)), [ucam-eo/tessera](https://github.com/ucam-eo/tessera)
- [Data provenance, foundational paper](https://dl.acm.org/doi/pdf/10.1145/1639950.1640064)
- [STACD: STAC Extension with DAGs for Geospatial Data and Algorithm Management](https://dl.acm.org/doi/10.1145/3759536.3763803)
- [Program slicing / dependency tracking](https://arxiv.org/pdf/2403.04403)
- [Type slicing](https://arxiv.org/pdf/2607.12197)
- [Verified pipelines inspiration](https://arxiv.org/abs/2602.22631)
- [ACM paper, 10.1145/3498668](https://dl.acm.org/doi/pdf/10.1145/3498668)
- [f.luid.org](https://f.luid.org/) and [f.luid.org/faq](https://f.luid.org/faq) — data provenance tool
- [Practical Alloy: About Alloy](https://practicalalloy.github.io/chapters/about-alloy/)
- [pyrefly autotype docs](https://pyrefly.org/en/docs/autotype/), [pyrefly v1.0 blog post](https://pyrefly.org/blog/v1.0/)
- [Pydantic validation get-started](https://pydantic.dev/docs/validation/latest/get-started/)
- [What Is Gradual Typing](https://jsiek.github.io/home/WhatIsGradualTyping.html)
- [QGIS gentle GIS introduction](https://docs.qgis.org/3.44/en/docs/gentle_gis_introduction/index.html#gentle-introduction-gis)
- [isaac.earth/geospatial-skills](https://isaac.earth/geospatial-skills)

## Files shared in-channel

Slack file uploads, not public URLs, listed here for reference:

- `core-stack-rag-source-inventory.md` — Smayan, 2026-07-20; AI-compiled inventory of every code/doc link for CoreStack
- `CoRE-Stack-Briefing.pdf` — Smayan, 2026-07-22; LLM Q&A briefing built from the RAG
- `corestack-reference.pdf` — Sanjay, 2026-05-26
- `Species-Plan.md`, `SPECIES_CHANGE_DETECTION_FEASIBILITY.md`, `species plan.pdf` — S Naveen, 2026-07-01
- `TESSERA understanding.pdf`, `CoRE Stack Backend pipeline understanding.pdf` — Uttkarsh, 2026-06-03
- GBIF block-diagram image — S Naveen, 2026-07-20

## Meeting and event links

- Weekly sync (Monday): [meet.google.com/gev-uegp-vza](https://meet.google.com/gev-uegp-vza)
- Reading group (recurring, varies): e.g. [meet.google.com/sap-qvuu-nmt](https://meet.google.com/sap-qvuu-nmt), [meet.google.com/ieo-eroa-wrx](https://meet.google.com/ieo-eroa-wrx)
- IIT-D pairing meet: [meet.google.com/ugc-tefk-xjo](https://meet.google.com/ugc-tefk-xjo)
- CoP Zoom call: see CoRE Stack official resources above

## Miscellaneous / tangential reading

- [LinkedIn: Aaditeshwar Seth / Veena Srinivasan podcast post](https://www.linkedin.com/posts/aaditeshwarseth_veena-srinivasan-is-the-perfect-podcast-host-ugcPost-7486037036681003008-tssX/)
- [LinkedIn: James Ball paper-share post](https://www.linkedin.com/posts/james-ball-b406a15a_really-pleased-to-share-that-our-paper-is-share-7481937380652904448-J6Q3/)
- [X: rajrao121 on fallen-tree detection](https://x.com/rajrao121/status/2076120570664747339)
- [X: paulnovosad](https://x.com/paulnovosad/status/2077372221996044423)
- [anil.recoil.org/notes/2026w28](https://anil.recoil.org/notes/2026w28)
- [Aneesh Naik](https://aneeshnaik.github.io/) — [weeknote](https://www.aneeshnaik.com/blogposts/20260703_weeknotes_2026_27.html)
- [Well Labs water-data podcast](https://welllabs.org/podcasts/water-data-podcast/)
- [Planet: forest health monitoring](https://www.planet.com/pulse/forest-health-monitoring/)
- [Nature Scientific Data paper](https://www.nature.com/articles/s41597-023-02634-w)
- [NPTEL course](https://nptel.ac.in/courses/106102001)
- [ml4eo.org workshops](https://ml4eo.org/workshops/)
