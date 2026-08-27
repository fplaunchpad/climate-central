# TESSERA Applications Paper: Benchmarks

[Applications of the TESSERA Geospatial Foundation Model to Diverse Environmental Mapping Tasks](https://anil.recoil.org/papers/2025-tessera-tasks) (Anil Madhavapeddy et al., SSRN preprint, 2026).

Evaluates the TESSERA foundation model (self-supervised, 128-dim pixel embeddings from Sentinel-1/2, 10m resolution, trained on 800M global pixels spanning 2017-2024) across 5 downstream benchmarks:

1. **Crop type classification** — Austria
2. **Wildfire burn area detection** — California
3. **Canopy height estimation** — Bornean tropical rainforests
4. **Above-ground biomass prediction** — Finnish forests
5. **Carbon market stocking indices** — Brazilian agroforestry

TESSERA matches or exceeds task-specific supervised models on all 5, typically reaching over 90% of final performance using less than 1% of available training data.

See the paper itself for why each benchmark matters to climate scientists, policymakers, and other stakeholders in that domain.
