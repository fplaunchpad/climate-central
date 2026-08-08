# Getting Started with GeoTessera

*A learning resource by Smayan Agarwal, documenting the process of learning GeoTessera. Ported from a [Slack post](https://fplaunchpad.slack.com/archives/C0B3GBWL97U/p1786178047916439) shared in `#fpl-esg`. Might be of help to others getting started as well.*

## Best introduction

[ESA: "Tessera AI model offers accessible way to view Earth"](https://www.esa.int/Applications/Observing_the_Earth/Copernicus/Tessera_AI_model_offers_accessible_way_to_view_Earth)

IMO the best resource to introduce yourself to the idea of what GeoTessera even is.

## Useful resources

[Quick Start Guide](https://geotessera.readthedocs.io/en/latest/quickstart.html)

- [Tutorials](https://geotessera.readthedocs.io/en/latest/tutorials.html) — covers downloading/analyzing embeddings in Python, and sampling embeddings at specific point locations.
- [CLI Reference](https://geotessera.readthedocs.io/en/latest/cli_reference.html) — for the download/visualize/serve command-line workflow instead of the Python API.
- [Architecture Guide](https://geotessera.readthedocs.io/en/stable/architecture.html) — once you're past basics, explains how the embeddings/foundation model are structured.

Anil Madhavapeddy's own [announcement post](https://anil.recoil.org/notes/geotessera-python) gives good context/motivation for why the library exists.

## Running the interactive notebook demo

The announcement post also has an entire Jupyter notebook you can run locally. Mixed reviews — it's pretty cool, but generating layers for even a small area takes a LONG time. An area triple the size of Cambridgeshire took 15 minutes. Might be nice as a small demonstration thing though.

Code to get the Jupyter notebook up and running:

```bash
git clone https://github.com/ucam-eo/tessera-interactive-map
cd tessera-interactive-map
uv venv
source .venv/bin/activate
uv pip install -r requirements.txt
code app.ipynb
```

## Other demos and resources

[tee.cl.cam.ac.uk/viewport_selector.html](https://tee.cl.cam.ac.uk/viewport_selector.html)

A small demonstration of what GeoTessera is. Not very deep though. Low cost, low reward.

[geotessera.org/docs/#tutorials](https://geotessera.org/docs/#tutorials)

A listing of a selection of the resources that GeoTessera has.

[isaac.earth/geospatial-skills](https://isaac.earth/geospatial-skills/)

A library of Claude skills that will be useful.

[Tessera announcement paper (arXiv:2506.20380)](https://arxiv.org/abs/2506.20380)

## Cool applications of GeoTessera

Two cool applications found:

- <https://arxiv.org/pdf/2604.09818>
- <https://arxiv.org/pdf/2311.16187>

## Gotchas

As of the time of downloading and trying to use things, downloading everything took a long time because of rate throttling on their end.
