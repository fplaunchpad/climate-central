FPL- IITDelhi CoreStack Meeting - 21/05/2026
=============================================

Introduction:

1. [https://stac.core-stack.org/?.language=en](https://stac.core-stack.org/?.language=en)
2. Data pipelines from Google Earth Engine (GEE)
    - builds data layers (raster/vector) per tehsil (sub-districts)
3. Custom machine learning models trained on raw satellite data (GEE)
4. CoRE stack backend
   - Various APIs combine data
   - Data archived in static JSON format

Problems:

1. Backend APIs are brittle with updates in JSON formats
2. Updating entities (defined as anything distinct in a tehsil for which vector data is gathered and computed)
    is not modular and error-prone - requires changes throughout the code-base
3. Data computations for entities are spread out across the code-base making it error-prone

Ongoing work:

1. Use local GPUs; GEE only for raw satellite data
2. Move to GeoParquet format (background: [https://parquet.apache.org/blog/2026/02/13/native-geospatial-types-in-apache-parquet/](https://parquet.apache.org/blog/2026/02/13/native-geospatial-types-in-apache-parquet/))
3. Use STACD ([https://www.spatialnode.net/articles/building-reproducible-geospatial-pipelines-a-stac-extension-with-dags25119d](https://www.spatialnode.net/articles/building-reproducible-geospatial-pipelines-a-stac-extension-with-dags25119d)) for computations
   1. Data in JSON format/multiple copies/archives of data  no longer needed
   2. Overlap with Tessera - to be explored
   3. Drone data being used to generate training data for invasive tree species in Delhi - how is/can Tessera being used here?

  Planned improvements:

1. Make CoreStack customizable - any team interested in processing their own geospatial data should be able to set up an instance
   1. CoreStack should be able to handle entities from all geographies, not just those in India
   2. The front-end should configurable/robust enough to handle any changes in the underlying processing layers

FPL work/Follow-ups:

1. Use a list of good first issues as an entry point to explore the CoreStack backend repository
   1. Use Pyrefly ([https://pyrefly.org/](https://pyrefly.org/)) to annotate and statically typecheck existing code
   2. Use Pydantic ([https://pydantic.dev/](https://pydantic.dev/)) to extend data validation to more models than exists now
2. Use a list of specific requirements to come up with test cases; these should form a set of regression tests that are validated when making any change in the data pipelines (and/or backend processing?)
3. Follow up with the IIT-D engineering team on a Docker instance of the backend
4. OxCaml/Tessera: Come up to speed on both, specifically using OxCaml with Tessera based on https://www.tunbury.org/2026/02/15/ocaml-tessera/.
