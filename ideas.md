# Ideas

Speculative/ambitious directions raised in `#fpl-esg` (not yet scoped as project-management issues). Concise by design — follow the Slack links for full context.

## 1. Data provenance tracking

Prof Seth wants a way to trace the provenance of any CoreStack data point back through the pipeline that produced it.

- Ask relayed + framed as a general SE problem ("common in domains like finance"): [Smayan, 27 Jul](https://fplaunchpad.slack.com/archives/C0B3GBWL97U/p1785143110212129)
- Reading-group prep, no ready literature found: [Alina, 27 Jul (f.luid.org)](https://fplaunchpad.slack.com/archives/C0B3GBWL97U/p1785147467684329), [Alina, 27 Jul (dl.acm.org/3498668)](https://fplaunchpad.slack.com/archives/C0B3GBWL97U/p1785147495834169)
- Verdict — substantial, needs planning as a major todo: [Alina, 29 Jul](https://fplaunchpad.slack.com/archives/C0B3GBWL97U/p1785323742951669)
- Foundational reading, found and shared: [Alina, 4 Aug](https://fplaunchpad.slack.com/archives/C0B3GBWL97U/p1785831080422749) — [*Provenance in Databases: Why, How, and Where*](https://dl.acm.org/doi/pdf/10.1145/1639950.1640064)

## 2. Code repetition / duplication detection

Surfaced inside the CoreStack Python-rehab thread ([project-management#53 comment](https://github.com/fplaunchpad/project-management/issues/53#issuecomment-5434894374)) as a tech-debt proxy metric, alongside the type-coverage measurement work.

- Idea — measure approximate code duplication in the backend: [Sanjay, 24 Aug](https://fplaunchpad.slack.com/archives/C0B3GBWL97U/p1787561797696859)
- Tool found: [Kaustubh, 24 Aug](https://fplaunchpad.slack.com/archives/C0B3GBWL97U/p1787562067640149) — [waza-agency/repetition-hunter-py](https://github.com/waza-agency/repetition-hunter-py) ("naive but would probably cover many elementary cases")

## 3. Satellite-derived building/tree height (GOBS-style)

- [S Naveen, 11 Aug](https://fplaunchpad.slack.com/archives/C0B3GBWL97U/p1786437699485889): found [GOBS](https://gobs.aeee.in/) (Geospatial Open Building Stack) measures building heights from satellite imagery; proposed the same approach for tree height in CoreStack.
- Data source identified: [Kaustubh, 11 Aug](https://fplaunchpad.slack.com/archives/C0B3GBWL97U/p1786454045620749) — GOBS sources buildings data from Google's [open-buildings v3 GEE dataset](https://developers.google.com/earth-engine/datasets/catalog/GOOGLE_Research_open-buildings_v3_polygons), which includes height estimates.

## 4. IITM campus green-space change tracking

Off a high-res-satellite LinkedIn post: "campus has had a lot of construction in the past 10 years, so if the data is available, tracking green space?" — [Sanjay, 10 Aug](https://fplaunchpad.slack.com/archives/C0B3GBWL97U/p1786351096279269). Untouched since; ties to the "built-up land area in IITM" question Kaustubh separately flagged TESSERA might help answer ([11 Aug](https://fplaunchpad.slack.com/archives/C0B3GBWL97U/p1786451717877999)).

## 5. Reliable LLM-generated UIs / chat as universal interface

- Speculation that chat-based NL interfaces become universal for decision-makers, vs. scientists wanting raw data/stats: [Sanjay, 18 Aug](https://fplaunchpad.slack.com/archives/C0B3GBWL97U/p1787043056037389)
- Pushback — we're far from chat being universal; hallucination risk scales badly; narrower framing proposed — closing the reliability gap for LLM-generated dashboards/webmaster-style UIs on a chosen narrow domain: [Kaustubh, 18 Aug](https://fplaunchpad.slack.com/archives/C0B3GBWL97U/p1787044793869209)
- Prior art cited: [Kaustubh, 18 Aug](https://fplaunchpad.slack.com/archives/C0B3GBWL97U/p1787044837897599) — [thesys.dev](https://www.thesys.dev/)

## 6. Frappe-like no-code public-tech platform

A generic, extendable platform (schemas, websites, databases, no code) for public-tech use cases — pitched as a more robust alternative to [Frappe Framework](https://frappe.io/framework), which is versatile but fragile/slow. [Kaustubh, 18 Aug](https://fplaunchpad.slack.com/archives/C0B3GBWL97U/p1787042812043029). Unstaffed. Also noted in [other-collaborators.md](other-collaborators.md).

## 7. x-ocaml notebook output-state caching

Save/cache the output of code blocks (Jupyter-style) so results (visualizations, downloaded embeddings) can be viewed without re-running everything — inspired by a [TESSERA-in-the-browser demo](https://jon.recoil.org/notebooks/interactive_map.html) that downloads embeddings client-side. [Kaustubh, 10 Aug (demo + idea)](https://fplaunchpad.slack.com/archives/C0B3GBWL97U/p1786345600684809), [Kaustubh, 11 Aug (todo, non-blocking)](https://fplaunchpad.slack.com/archives/C0B3GBWL97U/p1786451717877999). Possibly overlapping with an existing upstream request: [KC's issue on art-w/x-ocaml#2](https://github.com/art-w/x-ocaml/issues/2) — flagged as maybe-the-same-feature by [Kaustubh, 10 Aug](https://fplaunchpad.slack.com/archives/C0B3GBWL97U/p1786345674846779).
