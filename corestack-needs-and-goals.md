# CoreStack Needs and Goals

Faithful record of CoreStack's goals, technical asks, and roadmap, drawn from four sources:

1. Three long-running email threads between FP Launchpad (Sanjay Karanth, KC Sivaramakrishnan, Alina Banerjee) and Aaditeshwar Seth (CoRE Stack, IIT Delhi) and his team (Kapil Dadheech of Gram Vaani, and others). Compiled from Gmail, 2026-08-27.
2. The `core-stack-2.0.pptx` deck Aadi shared 16 May 2026 (2 slides), transcribed verbatim from the slide XML — now archived at [corestack-old/core-stack-2.0.pptx](corestack-old/core-stack-2.0.pptx) in this repo.
3. Aadi's "Bugs and first issues" Google Doc (May 2026), his own laid-out list of the concerns and open problems he wants FPL's help on, including Sanjay's open inline comments on it.
4. `fpl-core-stack`, FPL's former internal CoreStack coordination repo (now retired and archived at [corestack-old/](corestack-old/) in this repo).

Note: `references-and-plans/` in `corestack-old/` (S Naveen's personal domain-study notes) is deliberately excluded — not goals/roadmap content.

Quotes are attributed by name and date; paraphrase is used only for connective tissue, never to replace substantive content.

---

## Thread 1: "CoRE Stack x FP Launchpad: Minutes" (20 Mar – 24 Aug 2026)

### Meeting notes, 19 March 2026 (Sanjay Karanth's minutes, sent 20 Mar)

Attendees: Sanjay Karanth, KC Sivaramakrishnan, Aadi Seth, Mukulika Maity. Full formatted version: [corestack-old/meetings/2026-03-19-aadi-seth.md](corestack-old/meetings/2026-03-19-aadi-seth.md).

> Core-Stack works on climate change adaptation. Key technical challenges span data pipelines, community engagement, and systems correctness.

**Technical Challenges** (as minuted):

- **Data Pipeline**
  - Current stack: Google Earth Engine → processing → Airflow pipeline
  - Key needs: DAG-based graph computing with caching and versioning — for both code and data
- **Graph ML**
  - Containment and adjacency relationships modelled via graph embeddings
  - Adjacency structure could inform spatial/climate modelling
- **Analysis Library**
  - Build a library to speed up the *human* process of data analysis — reducing friction for analysts working with climate datasets
  - Natural language → LLM → data analysis is a promising direction; notable working examples:
    - [Vanna AI](https://github.com/vanna-ai/vanna) — RAG-based text-to-SQL; deployed at scale by NVIDIA ([case study](https://developer.nvidia.com/blog/accelerating-text-to-sql-inference-on-vanna-with-nvidia-nim-for-faster-analytics/))
    - [PandasAI](https://docs.pandas-ai.com/v2/llms) — plain-English queries over dataframes; LLM generates and executes Pandas/plotting code in-process
- **Systems: Gradual Typing for Python**
  - Existing Python codebase needs to be made safer and more maintainable without a full rewrite
  - Approach: add type hints incrementally using gradual typing — annotate one function/file at a time, grow safety guarantees over time
  - Precedent: Meta's [Hack language](https://engineering.fb.com/2014/03/20/developer-tools/hack-a-new-programming-language-for-hhvm/) layered a gradual type system on top of Facebook's billion-line PHP codebase. Key ingredients: a fast incremental type checker (<200ms), automated codemods to insert annotations at scale, and organic adoption. Migrated nearly the entire codebase within a year.
- **Policy and Community**
  - Policy design requires local input: dashboards, workshops, in-person meetings
  - Mobile apps for capturing community demand and local knowledge
  - Visualization tooling needed for community-facing outputs
- **Other Topics**
  - Mukulika: WiFi interference and rainfall correlation — potential sensing/data angle

**Next Steps** (as minuted): fortnightly meetings going forward; two recurring themes to anchor joint work — *Computing for the Commons* and a joint *Workshop* (details TBD).

KC Sivaramakrishnan (20 Mar) flagged only a formatting nit (dark background in the HTML minutes in dark mode).

### Aadi's three proposals, 22 March 2026

> Thanks a lot for the call and these pointers. I'm looking them over. What kind of timelines should we look at for starting out some fellows on these ideas? I can accordingly try to spec them out in more detail.
>
> 1. Organizing the CoRE stack data and pipelines more neatly to publish in geoparquets, build a library on top of common functions like drawing correlations or graph embeddings, clustering, etc., and make it queryable using natural language. I have some students working on a few of these elements and the fellows can join in.
>
> 2. Building a type system on the current codebase to make it more maintainable. I'll spend some time reading more on this so that I can help plan it out. I'm not very familiar with this line of work.
>
> 3. Something we've been discussing with Anil is the ability to store and process large datasets locally. We otherwise use Google Earth Engine for any processing of raw satellite data, but the performance there is somewhat unpredictable and Google is also about to impose quotas very soon. TESSERA embeddings done by Cambridge avoid the need to work on raw satellite data but still need about 300TB of storage for India, and the ability to mount them on adjacent GPU workshops or HPC infra to build and run models on the embeddings. If something like this can be set up at IITM, and we can build teams who re-learn models on TESSERA embeddings instead of raw satellite data, it'll be a big boost to build new datasets and refresh them in a timely manner.
>
> — Aadi (Aaditeshwar Seth), 22 Mar 2026

### Timelines and repo confirmation, 25 March 2026

Sanjay Karanth (25 Mar):

> We expect the fellows to join summer onwards (late May) and stay on for 2 years.
>
> We are currently looking at https://github.com/core-stack-org/ and will get back regarding 1 and 3.
>
> Regarding 2, what we proposed is a low-effort and potentially high impact update. Could you please confirm if https://github.com/core-stack-org/core-stack-backend is the primary repo (in python) with the issues that you brought up during our call?

Aaditeshwar Seth's reply, same day:

> Great, that's not too far away, so I'll try to write up a bit about each of the problems in the coming week or two.
>
> Yes, this is the correct repo and certainly the type checker will be extremely useful. I'll also try to learn more. I'm also working with the team to release a documentation for the repo which should make it easier for others to understand the setup. I'm afraid it may currently not be very nicely done!

The thread's last message (24 Aug 2026) is Sanjay forwarding the full history with "+ Smayan, Kaustubh for context" — no new content, just looping them in.

---

## Thread 2: "Alina (FP Launchpad) x CoRE stack" (30 Apr – 24 Aug 2026)

### Introduction (30 Apr – 2 May)

KC Sivaramakrishnan introduced Alina to Aadi (30 Apr), returning from a UK trip meeting Anil (Madhavapeddy):

> Alina is a project staff at FP Launchpad since Q3 last year. She joined us after a long stint as a research programmer at UIUC after her Master's degree at IU Bloomington. Alina is keen to have a look at the CoRE stack and contribute to it. The semester gets over in 2 weeks, and then Alina can jump in.

Aaditeshwar Seth's reply (2 May):

> 1. The timing is perfect. I'll get a few things organized with the students working on this and we can plan a kickoff call in the week of May 10th or later whenever you folks get free. And Alina is welcome to visit any time.
>
> 2. You have the repo correct. Here's also a documentation website https://core-stack-org.github.io/core-stack-docs/ in progress. We will also set up a docker by next week to make it easier for anyone to contribute on the codebase. And I'll line up a set of issues we want to solve for. We should be able to kick this off by the time we connect.
>
> 3. This problem too might get solved. I got some funds for equipment purchase and mostly as a workaround to purchase norms at IITD, we are now buying a number of GPU workstations that we will set up in a cluster. Will seek your advice as we begin to work on this.

### Onboarding logistics (15–16 May)

Alina (15 May) asked whether [core-stack-dev](https://groups.google.com/g/core-stack-dev) was where meeting times were posted, and what else to familiarize herself with besides the docs site.

Aadi (16 May):

> Yes that's the group, and you can also join https://groups.google.com/g/core-stack-nrm/ where we post more general news and articles.
>
> The documentation has also been put up on https://docs.core-stack.org/ and perhaps some links here would be good to start with https://core-stack.org/core-stack-developer-community/.
>
> I also put two slides together on some ongoing threads and the immediate roadmap.
>
> The dev calls will be good to attend although they end up being more about us giving feedback to some external students who are trying to build stuff using the stack. We should set up a separate cadence between us and others in our core team on the specific project. Does next week Thursday between 12-3pm work by any chance, or Friday in the first half? I'll loop in the others.

### Roadmap deck ("two slides... on some ongoing threads and the immediate roadmap", shared 16 May)

The "two slides" Aadi mentions above are [`core-stack-2.0.pptx`](corestack-old/core-stack-2.0.pptx) (now archived at [corestack-old/](corestack-old/)). Transcribed verbatim below, bullet-for-bullet, preserving the deck's own grouping headers (`CoRE stack backend` / `CoRE stack library` / `CoRE stack frontend: KYL, CC` recur as mini-headers within each time period on the actual slides):

**Slide 1 — "May 2026: Current"**
- *CoRE stack backend*
  - Multiple pipelines that run on GEE → Produce tehsil-level raster and vector files
  - Data for a given entity is spread across multiple files
  - STAC specs describe each file
- *CoRE stack backend* (APIs)
  - APIs help pull together data from multiple sources to provide a comprehensive view for entity
  - Also archived in static JSONs
- *CoRE stack frontend: KYL, CC*
  - Operate on a mix of APIs, JSONs, and layers
  - Also do some computations themselves on the frontend, minor though

**Slide 1 (cont'd) — "June 2026: Ongoing"**
- *CoRE stack backend*
  - Modify to using local GPU workstations instead of GEE
  - GEE to be used only for layers that require raw satellite data, like annual pan-India LULCs
- *Parallel backend*
  - Trigger computations using STACD. Single-click generation of all layers for a location, instead of layer-by-layer or sub-graph based generation
  - Trigger Geoparquet builds too
- *CoRE stack library*
  - Build GeoParquets for vector data. One GeoParquet per entity type
  - Renamed columns
  - Standard structure for static datapoints, time-series, etc.
  - Key problems:
    - Changes in the structure of the underlying vector layers (column name changes, new columns, etc.) require changes at multiple points in the code.
    - Computations are not isolated in one place, leads to bugs due to different people implementing these methods.

**Slide 2 — "July 2026: Goal"**
- *CoRE stack backend*
  - Well structured GeoParquets for vector data. Generated through STACD.
  - Handling of raster data: Do it through Raquet or new DuckDB geospatial extension.
- *CoRE stack frontend: KYL, CC*
  - Read well formed data from the library invoked via an API.
  - Library reads from GeoParquets.
  - Natural language frontend to the data using the library.
  - Eliminate need to maintain multiple copies of the same data
  - Have data arise from a single-source, be visible throughout the codebase, and make it easy to propagate any changes in the underlying layers to the frontend:
    - Have global variables like start-year, end-year on which change detection and means and statistics are computed. Load base datasets accordingly and make the frontend flexible to pick up these variables.
    - Make it easy to handle any changes in the underlying base layers. Currently, GEE or local GPU workflows process the layers and the pipelines will eventually write to specific columns in GeoParquets. Need to build a clean method to handle whether and how these changes should propagate to the frontend.
    - Prepare a minimum generalized selection of base datasets that can be instantiated anywhere globally, so that local instances can be brought up by anyone for any choice of region like a country or group of countries. Frontend to be made flexible to pick up this smaller set of base datasets and their downstream variables.
- **"Next set of improvements"** — trailing section header on slide 2 with no bullets under it; the deck ends here (2 slides total, matching Aadi's "two slides").

**Work streams**, as FPL's now-archived `corestack-old/project.md` broke this roadmap down (cross-referenced to FPL's own project-management issues):

1. **Data pipeline and library** ([project-management#48](https://github.com/fplaunchpad/project-management/issues/48)): organize CoRE Stack data and pipelines as geoparquets, build a library of common functions (correlations, graph embeddings, clustering), and make the data queryable using natural language. Aadi has students working on this and FPL fellows are joining in. (This is the same ask as proposal 1 in Aadi's 22 Mar email, above.)
2. **Python static typing** ([project-management#53](https://github.com/fplaunchpad/project-management/issues/53)): add a type system to the Python `core-stack-backend` codebase to improve maintainability; the pipeline has been fragile due to lack of typing. KC leading this, per `project.md`. Tools under consideration: [`astral ty`](https://github.com/astral-sh/ty) (fast, from the Ruff/uv team) vs. [Pyrefly](https://pyrefly.org) (Meta, v1.0 released May 2026 — strong framework support for Pydantic/Django, `pyrefly infer` for auto-generating annotations on existing untyped code, 125x faster incremental updates). (Same ask as proposal 2 above; note the later `#53` comment thread — see [project-management#53](https://github.com/fplaunchpad/project-management/issues/53#issuecomment-5434894374) — settled on Pyrefly in practice.)
3. **Local storage and compute** (exploratory): store and process TESSERA satellite embeddings (~300TB for India) locally rather than relying on Google Earth Engine. Aadi is building a GPU cluster at IITD; potential to set up matching infra at IITM. (Same ask as proposal 3 above.)

### Kickoff meeting scheduling (18–21 May)

Aadi invited KC and Sanjay to join a 12pm Thursday call; Sanjay confirmed. Aadi (19 May) sent the invite and added Kislaya, Apoorva, and Akshat (students working on CoRE Stack) to the [meet link]. The call happened 21 May (Aadi ran a couple minutes late).

### Post-meeting: notes and docker status (21–22 May)

Alina (21 May) circulated meeting notes and asked about next steps:

> Corrections and/or additions to the attached file containing notes from this afternoon's meeting are most welcome.
>
> We'll wait for an update on the Docker container for running the CoreStack backend. If we should also get in touch with members of engineering team, an introduction would be most helpful. We would be happy to set up a call/email the team for their input.

Attachment: `FPL- IITDelhi CoreStack Meeting - 21_05_2026.md` — mirrored in this repo at [channel-files/FPL-IITDelhi-CoreStack-Meeting-2026-05-21.md](channel-files/FPL-IITDelhi-CoreStack-Meeting-2026-05-21.md).

Aadi (22 May), CCing the engineering team:

> Thanks a lot for the call yesterday! I am CCing the engineering team and reattaching the call notes. Will update the team about our discussion.
>
> Have listed out a few points here https://docs.google.com/document/d/1xmHbL3Em0XG4whKvdqqa8ShNr3pjQVH7uF23nv6DszM/edit?usp=sharing. We will try to add more examples.
>
> Also check the docker installation here: https://docs.core-stack.org/developers/installer/. Whenever you want to start Alina, please let us know and we can have one of us on a call in case you run into any issues. You'll be the first guinea pig I guess to test out the docker.

Alina (22 May) hit a Docker install issue, logged it on GitHub, and asked whether the team should log issues from the points doc onto the same GitHub tracker, or keep it on FPL's own instance if CoreStack preferred it stay internal — "It would be most helpful to break down each one of them, document terms and tools we need to learn and plan tasks accordingly."

Aadi's reply (22 May, from his phone):

> Pls go ahead with putting up github issues, alina. We had put up some issues earlier for new datasets and pipelines but got mostly pr spam, but lets try again.

### Kapil Dadheech (Gram Vaani, Director – Tech Operations) joins to help with Docker (22–26 May)

Kapil Dadheech offered to help resolve the Docker issue directly:

> Can we connect for that Docker issue? Installation directory is inside the code you cloned in step 1. Please let me know suitable time to connect and resolve it.

Back-and-forth scheduling followed (22, 25, 26 May) landing on a call.

### Loop-in, 24 Aug 2026

Thread's last message: Sanjay forwarding the full history with "+ Smayan, Kaustubh for context" — no new content.

---

## Docker / GEE / GCS setup saga (29 May – 2 Jun 2026)

This detailed back-and-forth is not in the top-level message list of any of the three threads above — it survives only as a forwarded quote chain embedded inside the "CoRE Stack GEE accounts" thread. Chronological order, reconstructed from the quote nesting:

**29 May, Aadi** (checking in): "Hi Alina and Kapil, Just checking if the docker issues have been sorted out? Alina, we've not been using Macs so it will be great if you can help on this a bit."

**29 May, Alina** (reply): waiting on Kapil's update on the Docker instance (the Celery service instance needs an update/correction). Also raised two asks:

> Another point that would be most helpful is if there are ready accounts for Google Earth (and any other service) that we can use here when running instances. Creating new accounts is not a problem but having ready credentials for which parameters have already been set would be easier to start with.
>
> And lastly, if there is a Slack channel or other online messaging tool that is used by the team, it would be most helpful to be added to it. It would make it much quicker to ask questions or just coordinate whenever needed.

**29 May, Kapil Dadheech** (reply): a shared GEE account isn't feasible —

> We cannot set up a GEE account for use. It requires setting up payment info and Google also imposed some quota on compute. So it will run out of quota very soon.

Shared a Discord invite (`discord.com/invite/HpEFwUMP` — later noted as broken; see below for the working link).

**29 May, Aadi** (follow-up): "Alina, the GEE and GCS setup should not be too difficult. Kapil and team can also be on a call with you to guide you through the process. All this process will be useful to also get a sense of how easy is it for anyone to build for the CoRE stack and what more should we be doing to make it simpler."

**1 Jun, Alina → Kapil**, reporting concrete install bugs:

> Hi Kapil,
>
> Thanks for the updated Discord link. The documentation should have:
>
> `export USER=root`
>
> as the environment variable in the install.sh script is `$USER`.
>
> After the "Generate/update .env" step, the Docker instance runs into a QEMU segmentation fault:
>
> ```
> ==============================================
> Run Django migrations
> ==============================================
> Running Django migrations...
> Resetting Django migrations...
> Migrations cleaned.
> /root/miniconda3/envs/corestackenv/lib/python3.10/site-packages/drf_yasg/__init__.py:2: UserWarning: pkg_resources is deprecated as an API. See https://setuptools.pypa.io/en/latest/pkg_resources.html. The pkg_resources package is slated for removal as early as 2025-11-30. Refrain from using this package or pin to Setuptools<81.
> from pkg_resources import DistributionNotFound, get_distribution
> qemu: uncaught target signal 11 (Segmentation fault) - core dumped
> installation/install.sh: line 1193: 2581 Segmentation fault python manage.py makemigrations --skip-checks
> ```
>
> The link - https://setuptools.pypa.io/deprecated/pkg_resources.html - seems to have moved to another location, so I am not sure what updates should be made here.
>
> I am logged in the corestack-developers Discord channel now, so if it's easier to work the steps out there, I can definitely do so.

**Kapil's inline responses** to an earlier round of Alina's issues (interleaved in the same chain):

- On Colima not starting the container on Mac: "This is MAC specific issue. Since MAC is on M4 Chipset and our docker is build on x86 architecture. We need to work with Colima otherwise rabbitmq server will not work. Since most of us are working on linux or window based system. Can you please help us troubleshoot and solve this issue. We will add those instructions on our installation document specific to MAC based installation."
- On RabbitMQ failure + `installation/install.sh: line 1160: USER: unbound variable`: "For some instances we found enviourment variable User is not available we need to explicitly export this. You need to use export User=root before executing installation script. I also added this into our instructions over docs.core-stack.org"
- On the broken Discord link: "You can use this link to join https://discord.gg/FQBawGkmhQ" (this is the working link, distinct from the one shared 29 May)

**1 Jun, Aadi** (to Alina): "Hi Alina, Can I request that you try setting this up on a linux environment. Let's see if the same problems arise there too."

**2 Jun, Alina** (reply): "I will try. As far as I know, all of the team here works on systems with macOS but I can check for other options. If there is any other documentation that I should look up to help resolve setting up the Docker instance, please just let me know."

**2 Jun, Aadi** (reply): "Actually I don't know about the new docker version but I'd done one test docker earlier which could run on windows WSL as well, so that's another option. And just for making sure, maybe try running the docker inside an Ubuntu VM? The non-docker installation instructions are on the same link too https://docs.core-stack.org/developers/installer/. It's a bit complicated and messy but this might give some hints too."

---

## Thread 3: "CoRE Stack GEE accounts - FPL (IITM)" (8–9 Jun, 24 Aug 2026)

**Alina, 8 Jun** (following on from the Docker saga above):

> Hi Prof. Aaditeshwar,
>
> I did try and run the installation instructions on a Linux machine but they could not be completed as we have not yet set up/have access to GEE accounts.
>
> It has been instructive to go through https://docs.core-stack.org/developers/integrations/google-earth-engine/#step-1-configure-google-cloud-for-earth-engine. I expect we can be added to the existing CoREStack project in GEE but will have to pay for our own compute time/access. Sanjay Karanth, Program Manager at FPL will have to work out the details to do so.
>
> In the meantime, if there is pre-existing data in JSON or some other format that we can convert to JSON to start work with, I'll happily take up the task to set that up.

**Aaditeshwar Seth, 9 Jun** — the key policy statement on account/data access:

> It'll be best to set up your own account on GEE and GCS. Some students who've been directly contributing to the codebase have done this as well. For the most part you'll fall under the free tier limit, or at most will get billed a minor cost for storage which we (or FP launchpad) can reimburse. I am afraid we won't be able to share the CoRE stack keys which are used on the production or test infra.
>
> I think some of this will also get sorted out on a task by task basis, like if to start off you want to take up a task to build a new pipeline in the CoRE stack at a tehsil level that that will just need some small amount of storage, or if you want to start writing out test cases or type checks on the data and code then we can figure out a way to send you a data dump.
>
> That said, GEE has recently released a functionality for data export which will let us bypass GCS altogether. This will simply things even more.
>
> Regarding your question on pre-existing data in JSON or some other format, what task are you planning to take up. We can surely figure out a way to send the data to you.

**Sanjay Karanth, 9 Jun:**

> Thanks Prof. We were able to generate some LU/LC layers ourselves with free GEE/GCS accounts. We will explore further and get back to you.

**Aaditeshwar Seth, 9 Jun** (reply): "Awesome! Please do document the issues you ran into so that we can simplify things further."

**24 Aug 2026**: Sanjay forwards the thread with "+ Smayan, Kaustubh for context" — no new content.

---

## "Bugs and first issues" (Aaditeshwar Seth, May 2026)

Aadi's own Google Doc laying out CoRE Stack's concerns and open problems for FPL. Linked from [climate-central's README](README.md). Reproduced in full below, including Sanjay's open inline comments (marked, unresolved as of this writing).

### Different types of bugs

- **Pipeline correctness**: Pipeline is not doing what it should be doing.
  - E.g. change detection between years i and j should compute the modal LULC of years (i, i+1, i+2) and of years (j-2, j-1, j), then compute a change matrix of the area under class x that has transitioned to class y for all pairs of classes.
    - *Todo*: Write a specification of the pipeline in natural language. Ask Claude to create a dummy test LULC and a unit test on this LULC to check for correctness of the pipeline. Do this for all pipelines.
- **Output sanity**: Weird output.
  - E.g. runoff is calculated as zero on days of non-zero rainfall.
    - Possible cause: Some corner case caused an exception but the error was not logged and code silently exited.
    - *Todo*: Write a list of such sanity checks in natural language. Ask Claude to write checks that scan various outputs and flag cases for manual examination. Configure this as a test to run after any new location or project is activated.
- **Frontend data use**: Incorrect usage.
  - E.g. definition of drought is # weeks of moderate drought + # weeks of severe drought >= 5, but code flags a drought year at > 5 only.
    - *Todo*: Provide a definition in natural language for each datapoint. Have Claude trace the code on how each datapoint was computed, right from the pipeline that generated raw data to intermediate JSONs to final usage in the frontend, and check if the implementation throughout this data flow is as per the definition.
- **Apache Superset data use**: Incorrect usage.
  - E.g. find mean surface water availability over waterbodies with area > 1ha, but the implementation calculates this over all waterbodies.
    - *Todo*: Similar to the above, provide a definition in natural language for each datapoint shown on the Superset dashboard, and verify the Superset ETL queries that have been written. Alternatively, create a dummy test waterbody map and a unit test to check for correctness of the results.

### Good first issue

- Take up a new simple dataset to ingest in the CoRE stack, e.g. temperature or humidity related indicators available from various sources, or water quality data available in PDFs, or biodiversity data from [GBIF](https://www.gbif.org/country/IN/summary) (most exciting!), and work through an end-to-end integration in the current version of the stack: from backend pipelines that build pan-India raster layers, to vectorization pipelines for micro-watershed units, filters and visualizations on KYL, and new sections in MWS and tehsil reports.

  > **Sanjay Karanth's comment**: https://www.gbif.org/country/IN/summary — (this is where the GBIF link footnote points; matches S Naveen's GBIF workstream, [project-management#48](https://github.com/fplaunchpad/project-management/issues/48) goals sub-issue.)

### Type checking

- Currently each pipeline generates output datasets and STAC specs for each output dataset. The STAC specs are derived for vector datasets through an externally created CSV which lists the property names expected in the vector datasets, and for raster datasets through QGIS style files that list the class codes expected in the raster datasets.
- The data is used in downstream code such as to aggregate variables for the same entity in entity-wise JSONs, do some simple computation like min/max/trend, and make these outputs available to frontend applications and APIs.
- A type-check can start with verifying whether the property names and class codes in the datasets match the STAC specs, and their datatype (str/int8/float32/etc) is maintained all throughout from the dataset → JSONs → APIs → UI elements.
- A utility based on this can also help list all points in the code that might need changes if any of the base pipelines are updated to change the dataset schema.
- Note that raster pipelines → vector pipelines is also a path, i.e. there are dependencies across the pipelines, and the type check and utility should catch these as well.

### TESSERA usage

- One drop-in replacement can be if some datasets like LULC or canopy density or tree health etc. can be computed using TESSERA. This will be an involved project though. The current methodology is quite complex where ML classifiers on raw satellite data are used to break up some classes, Alphaearth embeddings are used in some other places, rules are used somewhere, etc. Our core student team which worked on some of these datasets has mostly graduated though, so a new team will be needed here.

  > **Sanjay Karanth's comment**: does tessera do LULC? if so, how does its calculation differ from Corestack?

- An alternative is to have a parallel project to develop very locally contextual LULC for small areas, like a forest or a cluster of villages. Hi-res drone imagery over a few patches in an AoI can be taken through computer vision pipelines like semantic segmentation, tree crown detection, farm boundary delineation, etc. followed by VLMs to label these segments and a human-in-the-loop to correct the labels or identify correct ones. Through such an iterative process, we can create a training dataset in the drone patches, and use that to train TESSERA embeddings to produce a wall-to-wall LULC over the AoI. A student has already started working on building such a framework. This can in fact be grown into a data commons project where users can mark if their verified labels can be put up in a public open repository. This could help create, for example, datasets on invasive tree species across India. The drone processing itself can be provided as a free service — we are getting a bunch of GPU workstations which can crank out the computer vision computations and TESSERA classification.

### Geodata library

- Can get to this later. Students here will continue to develop this to pull various (currently somewhat ad hoc organized) datasets into well-formed GeoParquets and write an FP-like library to query the data. A natural language interface to generate code to use the library and execute it will be the next step.

  > **Sanjay Karanth's comment**: How does Geoparquets differ from the (output) data stored currently? why is it needed?

---

## Cross-references

- CoreStack docs: [docs.core-stack.org](https://docs.core-stack.org/), [core-stack-org.github.io/core-stack-docs](https://core-stack-org.github.io/core-stack-docs/) (earlier doc site, now superseded), [developer community page](https://core-stack.org/core-stack-developer-community/)
- Google Groups: [core-stack-dev](https://groups.google.com/g/core-stack-dev) (meeting times), [core-stack-nrm](https://groups.google.com/g/core-stack-nrm) (general news/articles)
- Discord: https://discord.gg/FQBawGkmhQ (working invite, per Kapil, replacing an earlier broken one)
- GEE/GCS setup guide: https://docs.core-stack.org/developers/integrations/google-earth-engine/
- Docker/non-docker installer docs: https://docs.core-stack.org/developers/installer/
- Aadi's "few points" doc (issues from the 21 May call, referenced 22 May): https://docs.google.com/document/d/1xmHbL3Em0XG4whKvdqqa8ShNr3pjQVH7uF23nv6DszM/edit — note: a different document ID from the "Bugs and first issues" doc below; relationship between the two (same content restated, or genuinely separate) is unconfirmed.
- Aadi's "Bugs and first issues" doc (May 2026, full content reproduced above): https://docs.google.com/document/d/1AdriKFhdt2SkbsSQr6f9e0gQMpJjfOiMv0TPbS4y3og/edit
- Primary repo confirmed by Aadi: [core-stack-org/core-stack-backend](https://github.com/core-stack-org/core-stack-backend)
- FPL's former internal planning repo `fplaunchpad/fpl-core-stack` (retired and deleted 2026-08-27) is archived at [corestack-old/](corestack-old/) in this repo — includes the formatted meeting notes, `project.md` (roadmap + work streams), the `core-stack-2.0.pptx` deck, and S Naveen's `references-and-plans/` notes (glossary, backend architecture explainer, scientific-model writeups, feature-idea dashboard)
- Related project-management issues: [#48 Corestack new features](https://github.com/fplaunchpad/project-management/issues/48), [#53 Corestack codebase refactor+upgrade](https://github.com/fplaunchpad/project-management/issues/53) (the "type system on the current codebase" ask from Thread 1), [#130 Corestack understanding and documentation](https://github.com/fplaunchpad/project-management/issues/130) (closed, `status:complete`)
