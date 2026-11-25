# Surface-defect detection on a hot-rolling line (C06)

## Industrial problem

Severstal deployed high-frequency cameras on a production line and needed pixel-level localisation and classification of four surface defect classes; manual inspection misses faint and small defects.

**Why it happens.** Severe class imbalance, low contrast, thin/small defects, and real-time throughput constraints.

## Data (no plant data)

Open data only: Kaggle Severstal Steel Defect Detection (D03/Y2R14, public under competition terms) and NEU-DET (D02). Raw images are NOT redistributed in this repository.

> Only open datasets and published literature are used. No plant or proprietary data are held here; plant numbers quoted from papers are external literature, not independently reproduced results.

## Tool chain

PyTorch, U-Net / FPN, RLE mask decoder, per-class Dice, inference timing, error gallery, on-device benchmark.

## Journal references

- **Y2R11** ([DOI](https://doi.org/10.1145/3376067.3376113)) — real-time semantic-segmentation methodology and reported Dice as external literature.
- **Y2R14** ([source](https://www.kaggle.com/competitions/severstal-steel-defect-detection)) — Severstal competition data, rules and evaluation metric.
- **D02** ([source](https://scholar.google.com/)) — NEU-DET provenance and licence.
- **D03** ([source](https://www.kaggle.com/competitions/severstal-steel-defect-detection)) — Kaggle Severstal competition terms.

## Deliverables

`cases/severstal_segmentation/`; per-class Dice table; inference benchmark on one declared device; error gallery of small/faint defects; limitations section.

## Validation & claims

Per-class metrics (not only mean Dice); timing measured on one declared device; at least one failure mode analysed qualitatively; competition terms recorded in `data/SOURCES.md`.

## Limitations

No claim of production-line latency without the same hardware. Competition terms forbid redistributing raw images.

## Repository layout

- `README.md` — case summary, data policy, method, results and limitations.
- `CONTRIBUTING.md` — how to propose changes.
- `docs/index.md` — documentation map.
- `docs/model_card.md` and `docs/vv_template.md` — reporting templates.
- `.github/workflows/ci.yml` — automated checks.

Only open data and published literature are used. No plant or proprietary data
are included. All artefacts are written in English.
