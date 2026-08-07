# CoRE Stack — Master Source Inventory for RAG Construction
# Compiled: 2026-07-20
# Purpose: exhaustive list of information sources about CoRE Stack (IIT Delhi, Prof. Aaditeshwar Seth / ACT4D group).
# Format per entry: URL | TYPE | CRAWL METHOD | one-liner description.
# TYPE values: html, html-js (JavaScript-rendered, needs headless browser), repo (git clone), pdf, gdoc, gsheet, colab, api, video, wiki.
# PRIORITY tiers: T1 = must ingest, T2 = should ingest, T3 = supplementary context.

## GLOBAL CRAWLER INSTRUCTIONS
1. For `repo` entries: `git clone` the repo, ingest all `.md`, `.rst`, `.txt`, docstrings, and the `docs/` folder. Chunk code files separately from prose.
2. For `wiki` entries on GitHub: clone with `git clone <repo-url>.wiki.git`.
3. For `html` entries on core-stack.org and docs.core-stack.org: crawl the page, then follow ONLY internal links on the same domain; both sites are fully server-rendered and crawlable.
4. For `gdoc`/`gsheet`: append `/export?format=txt` (docs) or `/export?format=csv` (sheets) to fetch plain text; some require access requests.
5. For `pdf`: download and OCR/extract text.
6. For `html-js` entries (dashboards, GEE apps): do NOT try to scrape; instead ingest the descriptive blog post listed next to it.
7. Deduplicate: `www.explorer.core-stack.org` == `explorer.core-stack.org`; `fplaunchpad/core-stack-backend` is a FORK of `core-stack-org/core-stack-backend` (ingest upstream as truth, fork only for team-specific diffs/wiki).

---

## TIER 1A — OFFICIAL DEVELOPER DOCUMENTATION (highest value for understanding the codebase)

- https://docs.core-stack.org/ | html | crawl whole site (MkDocs, sitemap at /sitemap.xml) | Official developer documentation portal: architecture, data structure, installers, pipeline guides, API usage, glossary.
  Sub-pages to guarantee coverage of:
  - https://docs.core-stack.org/concepts/watershed-data-structure/ | html | fetch | Explains the core data model: micro-watersheds, nested/connected spatial entities.
  - https://docs.core-stack.org/concepts/how-pipelines-work-algorithmically/ | html | fetch | Algorithmic explanation of how the computation pipelines work.
  - https://docs.core-stack.org/use-precomputed-data/ | html | fetch | How to consume the pre-computed geospatial data.
  - https://docs.core-stack.org/use-precomputed-data/how-current-data-was-computed/ | html | fetch | Provenance of the currently published datasets.
  - https://docs.core-stack.org/use-precomputed-data/public-apis/ | html | fetch | Guide to the public data APIs.
  - https://docs.core-stack.org/use-precomputed-data/stac-specs/ | html | fetch | STAC catalog specifications for CoRE Stack data.
  - https://docs.core-stack.org/developers/ | html | fetch | Entry point for backend development.
  - https://docs.core-stack.org/developers/installer/ | html | fetch | Backend installation instructions.
  - https://docs.core-stack.org/developers/backend-code-map/ | html | fetch | Map of the backend codebase — key for navigating the sprawling repo.
  - https://docs.core-stack.org/pipelines/ | html | fetch | Guide to developing new pipelines.
  - https://docs.core-stack.org/pipelines/computing-endpoints/ | html | fetch | How to trigger pipeline computation via API endpoints for a region of interest.
  - https://docs.core-stack.org/developers/setup-troubleshooting/ | html | fetch | Known setup problems and fixes.
  - https://docs.core-stack.org/developers/stack-platforms/ | html | fetch | Overview of the platforms making up the stack.
  - https://docs.core-stack.org/developers/coding-standards-and-guidelines/ | html | fetch | Team coding conventions.
  - https://docs.core-stack.org/reference/glossary/ | html | fetch | Domain glossary (NRM/hydrology/geospatial terms).
  - https://docs.core-stack.org/reference/abbreviations/ | html | fetch | Abbreviation expansions used across code and docs.
  - https://docs.core-stack.org/reference/standardised-field-constant-variable-names/ | html | fetch | Naming conventions for fields/constants/variables in the data.
  - https://docs.core-stack.org/reference/api-errors/ | html | fetch | API error reference.
  - https://docs.core-stack.org/reference/scientific-papers-and-research-repositories/ | html | fetch | Index of the team's research papers and research repos — follow every link on this page.
  - https://docs.core-stack.org/community/ (+ subpages) | html | fetch | Contribution guide, code of conduct, innovation challenges, how the stack is used.
  - https://docs.core-stack.org/blog/ | html | crawl | Developer-docs blog archive (2026+).

- https://deepwiki.com/core-stack-org/core-stack-backend | html-js | fetch each section page | AI-generated deep documentation of the backend repo, officially endorsed by the team; treat as helpful but machine-generated (verify against code).

- https://api-doc.core-stack.org/ | html/api | fetch (likely Swagger/OpenAPI; also try /openapi.json) | Official reference documentation for all CoRE Stack REST APIs.

## TIER 1B — CODE REPOSITORIES (canonical org: core-stack-org, 20 repos)

- https://github.com/core-stack-org | html | enumerate via GitHub API: api.github.com/orgs/core-stack-org/repos | Canonical GitHub organization holding all CoRE Stack code.
- https://github.com/core-stack-org/core-stack-backend | repo | clone; ingest README, docs/ folder, all module docstrings | Main Django backend: computes layers, CRUD, resources/demands; integrates GeoServer + Google Earth Engine.
- https://github.com/core-stack-org/core-stack-backend/blob/main/docs/challenges/core_stack_innovation_2025/core_stack_innovation_challenge_brief_problem_set.md | repo-file | included in clone | Innovation challenge brief with worked example problems on the data — good "how to use the stack" prose.
- https://github.com/core-stack-org/landscape-explorer | repo | clone | React/OpenLayers frontend for the Landscape Explorer (Know Your Landscape) GIS web interface.
- https://github.com/core-stack-org/Commons-Connect | repo | clone | React app for Commons Connect, the community NRM-planning tool.
- https://github.com/core-stack-org/cc-android-offline | repo | clone | Flutter/Dart offline-first Android app for Commons Connect field use.
- https://github.com/core-stack-org/Commons-Connect-Offline | repo | clone | HTML offline variant of Commons Connect.
- https://github.com/core-stack-org/admin-dashboard | repo | clone | JavaScript admin dashboard for managing the stack.
- https://github.com/core-stack-org/core-stack-public-backend | repo | clone | Python public-facing backend service.
- https://github.com/core-stack-org/core-stack-backend-onprem | repo | clone | On-premise deployment variant of the backend.
- https://github.com/core-stack-org/core-stack-docs | repo | clone | Source of the docs.core-stack.org documentation site (ingesting this = ingesting the docs site as markdown).
- https://github.com/core-stack-org/corestack-notebooks | repo | clone; convert .ipynb to text | Official Jupyter notebooks demonstrating API usage and analyses (starter-kit).
- https://github.com/core-stack-org/layers_metadata | repo | clone | Metadata and layer descriptions for every dataset/layer in the stack — key for a data dictionary.
- https://github.com/core-stack-org/QGIS-Styles | repo | clone | QGIS .qml style files for every published data layer.
- https://github.com/core-stack-org/Tree-Health-Monitoring | repo | clone | ML pipeline for tree canopy density/height detection and tree-health change tracking.
- https://github.com/core-stack-org/FLR-Priority-Potential | repo | clone | Pipeline assessing Forest Landscape Restoration priority scores and restoration potential.
- https://github.com/core-stack-org/data_science_and_algorithms | repo | clone | Data-science and algorithm experiments repository.
- https://github.com/core-stack-org/corestack-chatbot | repo | clone | Chatbot built on CoRE Stack APIs.
- https://github.com/core-stack-org/cc-android-rn | repo | clone | Older React Native Android app for Commons Connect.
- https://github.com/core-stack-org/cc-web-app | repo | clone | ARCHIVED earlier Commons Connect web app (historical context only).
- https://github.com/core-stack-org/cc-web-app-offline | repo | clone | ARCHIVED earlier offline web app (historical context only).
- https://github.com/core-stack-org/.github | repo | clone | Org-level profile/README and community health files.
- https://github.com/ICTD-IITD/IndiaSAT_LULC_Version2 | repo | clone | IndiaSAT land-use/land-cover classification code from the same lab (pre-CoRE-Stack lineage of the LULC layers).

### Team's own fork (user-provided; NOT upstream)
- https://github.com/fplaunchpad/core-stack-backend | repo | clone; diff against upstream | fplaunchpad's fork of the backend (this is the working copy the user's team is on).
- https://github.com/fplaunchpad/core-stack-backend/wiki | wiki | clone fplaunchpad/core-stack-backend.wiki.git | Fork's wiki, 2 pages including "Change Detection — Pipeline Spec & Known Bugs".
- https://github.com/fplaunchpad/core-stack-backend/wiki/Change-Detection-%E2%80%94-Pipeline-Spec-&-Known-Bugs | wiki | included in wiki clone | Spec and known bugs of the change-detection pipeline (written Jun 2026 by S Naveen).
- https://github.com/fplaunchpad/core-stack-backend/tree/wip-feature-ocaml-geocompute | repo-branch | `git fetch origin wip-feature-ocaml-geocompute` in the fork clone | Work-in-progress branch adding an OCaml geocompute feature (likely tied to the TESSERA/Cambridge OCaml collaboration).

### TIER 1D — STUDENT / CONTRIBUTOR REPOS LINKED FROM OFFICIAL DOCS
# Source of truth for this list: https://docs.core-stack.org/reference/scientific-papers-and-research-repositories/ and https://docs.core-stack.org/reference/wonderful-github-repos/ — re-crawl both pages periodically; several entries there say "uploading soon", meaning MORE student repos will be added.

- https://github.com/Dhruvi-Goyal/Tree-Health-Monitoring | repo | clone | Original student repo (Dhruvi Goyal) behind the tree canopy density/height monitoring pipeline; upstream of core-stack-org/Tree-Health-Monitoring.
- https://ee-ictd-dhruvi.projects.earthengine.app/view/tree-health-monitoring | html-js | do not crawl; noted as demo | GEE demo app for the tree-health monitoring work.
- https://github.com/Dhruvi-Goyal/Plantation-Site-Suitability | repo | clone | Plantation site-suitability analysis (climate/soil/ecology/socio-economic factors); directly behind the plantation-suitability workflow in the backend.
- https://github.com/SanyaKapoor/Site-Level-Impact-Assessment-of-Farm-Ponds | repo | clone | Farm-pond impact assessment code (Sanya Kapoor) linked to the surface-waterbody/pond analytics.
- https://github.com/aatifnisar01/Ponds_and_wells_detection | repo | clone | Pond and well detection/processing (Aatif Nisar); aligned with the merged surface-waterbody workflows in the stack.
- https://github.com/ramank1137/Scrubland-Field-Delineation | repo | clone | Scrubland mapping / field delineation (Raman Kumar); informs LULC and scrubland classification.
- https://github.com/badri1995/ADI_complete | repo | clone | Aggregate Development Index code (satellite-derived socio-economic indicators) behind the ADI layers.
- https://github.com/souraavv/ai-based-market-intelligence-system | repo | clone | AI market-intelligence system for farmer collectives (Sourav); adjacent lab work, not a backend module.
- https://github.com/ICTD-IITD/IndiaSAT_LULC_Deliverables | repo | clone | IndiaSAT LULC deliverables repo from the lab's ICTD-IITD org (linked from the papers page).
- https://github.com/ICTD-IITD | html | enumerate via api.github.com/orgs/ICTD-IITD/repos | The lab's older GitHub org (ICTD IIT Delhi) — sweep ALL repos here; pre-CoRE-Stack student code (IndiaSAT versions, etc.) lives in this org.

### "Useful neighbors" listed by the team (external dependencies, T3 — index names only, don't ingest code)
- https://github.com/gee-community/geemap | repo | skip ingest | GEE Python mapping library the team recommends.
- https://github.com/qgis/QGIS | repo | skip ingest | QGIS, used for layer styling/consumption.
- https://github.com/developmentseed/titiler | repo | skip ingest | Dynamic tile server relevant to their serving stack.
- https://github.com/stac-utils/pystac and https://github.com/stac-utils/stac-fastapi | repo | skip ingest | STAC tooling underlying stac.core-stack.org.
- https://github.com/google/earthengine-api | repo | skip ingest | GEE client API the pipelines depend on.
- https://github.com/geopandas/geopandas | repo | skip ingest | Core geospatial Python dependency.

### Also enumerate (issues/PRs contain undocumented design decisions)
- https://api.github.com/repos/core-stack-org/core-stack-backend/issues?state=all | api | paginate JSON | 19 open issues + 30 PRs on the backend; discussions double as informal documentation.
- Same pattern for landscape-explorer (19 issues, 25 PRs) and other active repos.

## TIER 1C — LIVE SERVICES & APIs (ingest their docs/spec endpoints, not the UIs)

- https://geoserver.core-stack.org/ | api | probe /api/v1/ endpoints listed in api-doc.core-stack.org and backend code | GeoServer instance serving computed layers and report-generation APIs.
- https://geoserver.core-stack.org/api/v1/generate_tehsil_report/?state=tamil_nadu&district=tiruppur&block=udumalaippettai | api | fetch example output; enumerate params from backend code | Example endpoint that generates a full tehsil-level landscape report (sample: Udumalaippettai, Tiruppur, TN).
- https://stac.core-stack.org/ | api | fetch STAC root, walk /collections and /items JSON | SpatioTemporal Asset Catalog listing all CoRE Stack geospatial datasets with machine-readable metadata.
- https://dashboard.core-stack.org/ | html-js | do not crawl; register manually for API keys | User dashboard for registration and API-key generation (prerequisite for using data APIs).
- https://explorer.core-stack.org/ (alias: https://www.explorer.core-stack.org/kyl_dashboard) | html-js | do not crawl; ingest source repo landscape-explorer + KYL blog post instead | "Know Your Landscape" dashboard for browsing/downloading all layers per tehsil/micro-watershed.
- https://ee-corestackdev.projects.earthengine.app/view/core-stack-gee-app | html-js | do not crawl; note asset IDs from notebooks/code | Google Earth Engine app: directory of pan-India CoRE Stack GEE datasets.
- https://ee-corestackdev.projects.earthengine.app/view/gee-app | html-js | do not crawl | Sub-district-level GEE app for layer browsing.
- https://core-stack-gee-app.projects.earthengine.app/view/layers | html-js | do not crawl | GEE app exposing pan-India layers for import into user scripts.

## TIER 2A — TECHNICAL MANUALS, GUIDES, AND METHOD DOCS (team-authored)

- https://drive.google.com/file/d/1ZxovdpPThkN09cB1TcUYSE2BImI7M3k_/view | pdf | download (CoRE_v2_layers_6March2025.pdf) | Technical Manual v2 (Mar 2025): methodology for every geospatial layer in the stack — the core "what does each layer mean" document.
- https://core-stack.org/core-stack-technical-manual-v2/ | html | fetch | Blog post announcing/framing the Technical Manual v2 with context on the new layers.
- https://www.cse.iitd.ernet.in/~aseth/core-stack-layers-apr-2024.pdf | pdf | download | Technical manual v1 (Apr 2024): earlier geospatial data layers documentation, lists team, partners, donors.
- https://docs.google.com/document/d/1yyt6QR6gAAunyqd9Wn-QIGkkClI8kQKnjJ6IlSQ3dj4/edit | gdoc | export as txt | Detailed guide on how to contribute new pipelines for generating/processing datasets.
- https://docs.google.com/spreadsheets/d/1NrSojGE4WiFYjAsXO4QTz2c4LRFvyrigjX9egw7PV5g/edit | gsheet | export as csv | Wishlist of datasets and indicators the team wants built (roadmap signal).
- https://sites.google.com/oniondev.com/qgisdoc/home | html | crawl subpages | Team guide on importing CoRE Stack datasets into QGIS or GEE.
- https://colab.research.google.com/drive/1uZH1KZFbe0TUIgCECOz_2cQ1jUfZglsA | colab | download .ipynb via Drive export | Official Water Balance Analysis notebook demonstrating API invocation.
- https://colab.research.google.com/drive/1zv9TWdzfaEanE_i1kKw2Cr2snoCEhuIg | colab | download .ipynb via Drive export | Official Cropping Intensity Analysis notebook demonstrating API invocation.
- https://core-stack.org/lulc/ | html | fetch | Documentation page for the Land Use / Land Cover classification dataset.
- Dataset documentation PDFs on Drive (from core-stack.org/datasets/):
  - https://drive.google.com/file/d/1DFR7PRiGCxgMmri_jFwAPoebn32OmJz7/view | pdf | download | Admin boundaries dataset documentation (state/district/block/GP/village/agro-climatic zones, 2001-vs-2011 changes).
  - https://drive.google.com/file/d/1AfYesx2eAFbmkyrbHMnEBJBBabISXSjZ/view | pdf | download | NREGA geotagged assets dataset documentation.
  - https://drive.google.com/file/d/1BWQffkyk0vmzd4vHcC5mX5zfhFBTc8cN/view | pdf | download | NREGA panchayat-level dataset documentation.
  - https://docs.google.com/document/d/1JOeuoCYIipQ1shV2eaQiatKel2RJcS2g/edit | gdoc | export | Aggregate Development Index (ADI) socio-economic dataset documentation.
- Download folders (data, not docs — index but don't ingest as text): the Drive folder links on https://core-stack.org/datasets/ for state/district/GP/village/block/agro-climatic boundaries, NREGA data, and ADI csv.

## TIER 2B — THE core-stack.org BLOG (primary knowledge base; crawl entire site)

- https://core-stack.org/ | html | crawl all internal links; sitemap at /sitemap.xml; also paginate /category/updates/ | Main project website; nearly every technical/field learning is published as a blog post here.
Category hubs to paginate through:
- https://core-stack.org/category/knowledge/nuts-bolts/ | html | paginate | "Nuts & bolts" technical deep-dives (most valuable category for developers).
- https://core-stack.org/category/knowledge/research/ | html | paginate | Research write-ups (soil health ML, tree canopy monitoring, MGNREGA analysis, STACD).
- https://core-stack.org/category/knowledge/case-studies/ | html | paginate | Field case studies of Commons Connect and KYL deployments.
- https://core-stack.org/category/knowledge/playlists/ | html | paginate | Curated knowledge-video playlists (watershed dev, water structures).
- https://core-stack.org/category/restoration/ | html | paginate | Ecological restoration toolkit posts.
- https://core-stack.org/category/news-events/ | html | paginate | Workshops, challenges, awards, community events.
Individual high-value technical posts (ensure captured):
- https://core-stack.org/the-core-stack-data-structure/ | html | fetch | ER diagram + explanation of the CoRE Stack data structure (entities/relations).
- https://core-stack.org/core-stack-starter-kit-for-geospatial-programming/ | html | fetch | Starter-kit walkthrough for programming against the stack.
- https://core-stack.org/a-micro-watershed-registry-for-india/ | html | fetch | Design of the standardized pan-India micro-watershed registry (the stack's core spatial unit).
- https://core-stack.org/building-reproducible-geospatial-pipelines-a-stac-extension-with-dags/ | html | fetch | STACD: the team's STAC extension with DAGs for reproducible pipelines.
- https://core-stack.org/planning-river-rejuvenation-over-a-large-stretch/ | html | fetch | Worked example combining stack data for river-rejuvenation water-flow analysis.
- https://core-stack.org/tracker-for-protected-areas/ | html | fetch | GEE app combining news articles with protected-area data.
- https://core-stack.org/from-landscape-data-to-explainable-diagnosis-neurosymbolic-evidence-cards-on-the-core-stack/ | html | fetch | Neurosymbolic "evidence cards" approach for explainable landscape diagnosis.
- https://core-stack.org/contribute-datasets-pipelines-and-tools/ | html | fetch | Contribution overview post; hub linking repo, deepwiki, manuals, wishlist, dev calls.
- https://core-stack.org/use-apis/ | html | fetch | API onboarding page (dataset APIs + community APIs + registration flow).
- https://core-stack.org/tools-2/ | html | fetch | Methodologies page describing computation methods behind the tools.
- https://core-stack.org/facilitate-stewardship/ | html | fetch | Commons Connect product page.
- https://core-stack.org/contribute-artifacts/ | html | fetch | Apps gallery / architecture page.
- https://core-stack.org/datasets/ | html | fetch | (Semi-deprecated) curated datasets page with Drive doc/download links for boundaries, LULC, NREGA, hydrology, ADI.
- https://core-stack.org/our-team-2/ and https://core-stack.org/our-team/ | html | fetch | Team pages.
- https://core-stack.org/implementation/ | html | fetch | Impact/implementation overview (400+ stewards, 9+ states, 1500+ villages).
- https://core-stack.org/explore-social-ecological-insights-with-the-know-your-landscape-dashboard/ | html | fetch | Explainer for the KYL dashboard.
- https://core-stack.org/empowering-communities-through-data-for-improved-socio-ecological-sustainability-and-resilience/ | html | fetch | Framework post on comprehensive social-ecological indicators.
- https://core-stack.org/a-digital-public-infrastructure-for-climate-change-adaptation/ | html | fetch | Foundational 2024 post framing CoRE Stack as DPI for climate adaptation.
- https://core-stack.org/core-stack-updates-september-2024-to-april-2025/ | html | fetch | Consolidated progress update Sep 2024–Apr 2025.

## TIER 2C — COMMUNITY CHANNELS & RECORDINGS (tacit knowledge; much is video)

- https://core-stack.org/core-stack-developer-community/ | html | fetch; extract the recordings table links | Developer community page with a living, weekly-updated table of dev-call recordings and suggested viewing order (Fridays 3–4pm IST).
- https://core-stack.org/core-stack-innovation-challenge-1st-edition/ | html | fetch | Innovation Challenge #1 page (problem sets, rolling contributions, links to recordings).
- https://core-stack.org/innovation-challenge-2-mining-insights-from-events/ | html | fetch | Innovation Challenge #2: mining insights from geotagged news events.
- https://groups.google.com/g/core-stack-dev | html-js | join group; export via member access | core-stack-dev Google Group mailing list (Q&A archive).
- https://discord.gg/PSkZX4hvWx | app | join manually; not crawlable | Official Discord (linked from docs site).
- https://discord.gg/FpMArraM2X | app | join manually; not crawlable | Discord invite linked from the contribution blog post (may be same server).
- https://www.youtube.com/watch?v=NyQced4oJVM | video | transcript via YouTube captions (talk starts ~1:58:25) | IndiaFOSS 2025 talk presenting the CoRE stack open-source initiative.
- Dev-call recording links | video | extract URLs from developer-community page table; pull YouTube/Drive transcripts | Weekly developer call recordings — the closest thing to oral documentation of the codebase.
- https://linkedin.com/company/core-stack | html-js | skip or manual | Official LinkedIn page (announcements only).

## TIER 2D — DEPLOYMENTS, PARTNERS, AND PROJECT HISTORY (the "in deployment" references)
# Deployments are documented on the /implementation/ page, the case-studies category, and the co-creators sheet. Known deployment partners/geographies (extracted from team publications): FES, PRADAN (Ramgarh, Jharkhand), SUPPORT (Dumka), 4S (Gaya), Jan Jagran Kendra (Giridih), CCD (Adilabad), SPWD & JJBA (Latehar), IIT-IIT (Kolar), Magasool (Tamil Nadu), Well Labs, Gram Vaani, CommonsTech Foundation; funders GIZ, Rainmatter, Common Ground, Tower Research, HellermannTyton, Tarides. Stated scale: 400+ stewards, 9+ states, 1500+ villages.

- https://docs.google.com/spreadsheets/d/1zF1SjGD0jaIBtgdvPIjNz5RKtgyW7pDo8sU88LdfgtA/edit | gsheet | export as csv | THE master ecosystem sheet: the team's own list of all co-creators, users, and organizations building on / deploying the stack — best single index of deployments.
- https://core-stack.org/implementation/ | html | fetch all tabs (Process / Research / Current Geographies) | Impact page describing the steward model, training, government engagement, and current deployment geographies.
- https://core-stack.org/wp-content/uploads/2025/08/Commons-Connect-User-Stories.pdf | pdf | download | "Commons Connect User Stories": early field experiences of landscape stewards using the app in deployment.
- https://core-stack.org/early-lessons-from-the-corestack-pilots/ | html | fetch | July 2025 synthesis of lessons from the first Commons Connect pilots (2024 cohort).
- https://core-stack.org/enhancing-water-security-in-rural-india-with-digital-tools-insights-from-field-testing/ | html | fetch | Insights from the earliest field testing of the tools (late 2023 / early 2024).
- https://core-stack.org/pradans-use-of-commons-connect-for-scaling-nrm-planning-in-ramgarh-district-jharkhand-and-integration-with-the-yuktadhara-platform/ | html | fetch; extract embedded presentation link | PRADAN's at-scale deployment in Ramgarh (Jharkhand) building community DPRs, and integration with ISRO/Bhuvan's Yuktadhara MGNREGA-planning platform.
- https://core-stack.org/front-page-coverage-in-dainik-bhaskar/ | html | fetch | Press coverage of the PRADAN/Jharkhand deployment (Dainik Bhaskar front page, Jul 2026).
- https://core-stack.org/stories-from-the-ground/ | html | fetch; extract video links | Field reflections from SUPPORT (Jharkhand) stewards on data-driven participatory NRM governance.
- https://core-stack.org/towards-data-driven-and-community-centered-water-governance/ | html | fetch | Case study on participatory water-governance planning with the stack.
- https://core-stack.org/towards-effective-and-equitable-natural-resource-management-field-stories-on-commons-connect/ | html | fetch | Jun 2026 compilation of field stories from Commons Connect deployments across rural India.
- https://core-stack.org/validating-impact-field-observations-from-waterbody-rejuvenation-in-madhya-pradesh/ | html | fetch | Field validation study of waterbody-rejuvenation impact in Madhya Pradesh (Ramneek Kaur, ACT4D postdoc).
- https://core-stack.org/looking-for-the-ai-in-inclusive-ai/ | html | fetch | Anuradha Ganapathy's field observations of Commons Connect deployments with FES ("more participation, less AI").
- https://core-stack.org/on-highways-and-backroads-of-ai-and-perspectives-on-commons-connect/ | html | fetch | Follow-up reflection on AI's role in the Commons Connect deployments.
- https://core-stack.org/revealing-inequities-in-mgnrega-what-data-and-field-insights-tell-us/ | html | fetch | MGNREGA equity analysis combining stack data with field insights.
- https://core-stack.org/solving-landscapes-together-reflections-from-the-2nd-solvability-workshop-dec-2025/ | html | fetch | Dec 2025 solvability workshop at IIT Delhi (80+ people, partner orgs) — snapshot of who is deploying what.
- https://core-stack.org/core-stack-at-the-participatory-ai-research-symposium/ | html | fetch | Talk on the participatory-AI design approach used in deployments.
- https://core-stack.org/complexities-in-assessing-farm-ponds/ | html | fetch | Early (2023) field study on assessing MGNREGA farm ponds — motivating deployment problem.
- https://core-stack.org/initial-experiments-with-a-scalable-machine-learning-based-approach-for-downscaling-the-mod16a2-evapotranspiration-product/ | html | fetch | ET-downscaling research feeding the hydrology layers.
- https://core-stack.org/knowledge-playlist-watershed-development/ and https://core-stack.org/knowledge-playlist-water-structures/ | html | fetch; extract video links | Bilingual training-video playlists used to train deployment stewards.
- https://docs.core-stack.org/community/how-core-stack-is-used/ | html | fetch | Docs-site page cataloguing how organizations use the stack in practice.
- https://docs.core-stack.org/community/contributions/ | html | fetch | Log of community contributions accepted into the stack.

### Partner / ecosystem organizations (T3 — context on deployment counterparts; crawl shallow)
- https://gramvaani.org/ | html | fetch homepage + CoRE-related pages | Gram Vaani, Seth's social-tech enterprise whose engineering team seeded the stack (later CommonsTech Foundation).
- CommonsTech Foundation | search | crawler should search for official site | The nonprofit now employing the full-time CoRE Stack engineering team. [UNVERIFIED URL]
- https://fes.org.in/ | html | fetch shallow | Foundation for Ecological Security — largest deployment partner (Commons Connect at scale).
- https://www.pradan.net/ | html | fetch shallow | PRADAN — Jharkhand deployment partner integrating with Yuktadhara.
- https://bhuvan.nrsc.gov.in/ (Yuktadhara portal) | html | fetch shallow | ISRO's Bhuvan/Yuktadhara geospatial MGNREGA-planning platform that Commons Connect integrates with.
- https://welllabs.org/ | html | fetch shallow | Well Labs — research collaborator credited in the technical manual.
- Magasool (https://magasool.org/ or similar) | search | verify URL | Tamil Nadu agri nonprofit; co-author org on the layers manual. [UNVERIFIED URL]
- https://www.tessera.wiki or Cambridge TESSERA project page | search | verify URL | Cambridge geospatial-AI project (Anil Madhavapeddy) that ran a joint hackathon; connects to the wip-feature-ocaml-geocompute branch. [UNVERIFIED URL]

### Project history & lab context
- https://www.cse.iitd.ernet.in/~aseth/ongoing-projects-24-25.html | html | fetch; follow every project link | Seth's list of ongoing student projects with skillsets — maps students to the components they built.
- https://core-stack.org/a-digital-public-infrastructure-for-climate-change-adaptation/ | html | fetch | Feb 2024 foundational framing of the stack as DPI.
- https://core-stack.org/core-stack-updates-september-2024-to-april-2025/ | html | fetch | Consolidated progress report.

## TIER 3A — RESEARCH PAPERS & LAB PAGES

- https://www.cse.iitd.ac.in/~aseth/ | html | fetch; follow publication links | Aaditeshwar Seth's homepage: project list, research philosophy, links to papers and PhD topics around CoRE Stack.
- https://docs.core-stack.org/reference/scientific-papers-and-research-repositories/ | html | fetch; follow every listed paper | Team-maintained index of scientific papers and research repositories underlying the stack.
- https://dl.acm.org/doi/10.1145/3460112.3471953 | pdf | download via ACM (open) | IndiaSat paper (COMPASS 2021): pixel-level LULC dataset behind the land-cover layers.
- https://dl.acm.org/doi/pdf/10.1145/3759536.3763803 | pdf | download | STACD paper: the STAC-with-DAGs extension for geospatial data/algorithm lineage used in the stack's metadata.
- https://dl.acm.org/doi/pdf/10.1145/3674829.3675085 | pdf | download | Farm-pond impact-on-productivity paper (pairs with SanyaKapoor repo).
- https://dl.acm.org/doi/full/10.1145/3624774 | pdf | download | Land-use change near mining sites paper (behind the mining overlays).
- https://dl.acm.org/doi/pdf/10.1145/3700794.3700816 | pdf | download | Field-testing paper on the digital participatory water-security tool (early Commons Connect).
- https://dl.acm.org/doi/full/10.1145/3700794.3700798 | pdf | download | Tree canopy density/height monitoring paper (pairs with Dhruvi-Goyal repo).
- https://dl.acm.org/doi/pdf/10.1145/3700794.3700815 | pdf | download | Caste-based inequity in NREGA welfare allocation paper.
- https://dl.acm.org/doi/pdf/10.1145/3615361 | pdf | download | Two-decade satellite tracking of rural socio-economic development (behind ADI).
- https://dl.acm.org/doi/full/10.1145/3609262 | pdf | download | AI market-intelligence for farmer collectives paper (adjacent lab work).
- https://www.cse.iitd.ac.in/~aseth/caste-based-ictd2024-field-report-precise-policy-recommendations.pdf | pdf | download | ICTD 2024 field report: caste-based MGNREGA inequities and precision policy advisory.
- https://core-stack.org/notes-from-the-core-stack-research-to-impact-collaborative-held-on-july-8th-2024/ | html | fetch | Notes from the COMPASS 2024 research-to-impact collaborative session.
- ACT4D group page (search "ACT4D IIT Delhi") | html | locate and fetch | Lab page of the Appropriate Computing Technologies for Development group that builds CoRE Stack. [UNVERIFIED URL — crawler should search]

## TIER 3B — THIRD-PARTY & PRESS (context, not technical truth)

- https://core-stack.org/core-stack-in-the-news/ | html | fetch; follow outbound press links | Team-curated press roundup incl. Indian Express interview of Seth.
- https://core-stack.org/why-the-commons-need-community-led-data/ | html | fetch | Pointer to IDR (India Development Review) article on data in commons governance.
- https://www.theindiaforum.in/forum/bringing-back-public-digital-public-goods | html | fetch | India Forum essay by Seth articulating the "public digital public goods" philosophy behind the stack.
- https://fossunited.org/c/indiafoss/2025/cfp/8h350au2vu | html | fetch | IndiaFOSS 2025 talk proposal summarizing the stack in the team's own words.
- https://core-stack.org/front-page-coverage-in-dainik-bhaskar/ | html | fetch | Dainik Bhaskar front-page coverage of PRADAN's Commons Connect use in Jharkhand.
- https://era-india.org/community/aaditeshwar-seth/ | html | fetch | Third-party bio confirming Seth as CoRE Stack co-founder.
- https://homecse.iitd.ac.in/?id=90 | html | fetch | IIT Delhi CSE announcement: CoRE Stack top-20 finalist, AI for ALL challenge 2026.

## KNOWN GAPS / MANUAL-ACCESS ITEMS (flag for a human)
- dashboard.core-stack.org API keys: needed before the notebooks/API docs can be exercised end-to-end.
- Google Group archive and Discord history: require joining; contain undocumented Q&A.
- Some Drive docs may be permission-gated; request access via contact@core-stack.org.
- "Closed datasets" (community-generated, e.g., QA dataset) listed on /datasets/ are not public.
- The recordings table on the developer-community page is updated weekly — schedule re-crawls.

## SUGGESTED INGESTION ORDER FOR THE RAG
1. docs.core-stack.org (or its source repo core-stack-docs)  → structural understanding.
2. Technical Manual v2 PDF + layers_metadata repo → data dictionary.
3. core-stack-backend repo (upstream) + deepwiki + backend-code-map page → code understanding.
4. api-doc.core-stack.org + STAC catalog + notebooks → API surface.
5. Blog "nuts & bolts" + "research" categories → design rationale.
6. Remaining repos, then community/press material.
