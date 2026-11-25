# C06 · Surface-defect detection on a hot-rolling line — W22–W25

> **Real industrial case dossier.** Copied from the authoritative case card in
> `CASES.md` §4 so this repository stays self-contained after it is pushed to
> GitHub. Planning links: [`CASES.md`](https://github.com/ahmadishamulayadyakmal/metallurgy-project/blob/main/CASES.md) ·
> [`JOURNALS.md`](https://github.com/ahmadishamulayadyakmal/metallurgy-project/blob/main/JOURNALS.md) ·
> [`WEEKLY_PLAN.md`](https://github.com/ahmadishamulayadyakmal/metallurgy-project/blob/main/WEEKLY_PLAN.md).
> **Evidence level: A** · No plant data is held in this repository.

**Repository:** `e06-steel-defect-cv` · **Evidence: A** ·
**References:** Y2R11, Y2R14, D02, D03.

**Industrial problem.** Severstal deployed high-frequency cameras on a production
line and needed pixel-level localisation and classification of four surface
defect classes; manual inspection misses faint and small defects (Y2R14).

**Why it happens.** Severe class imbalance, low contrast, thin/small defects, and
real-time throughput constraints.

**Data (open, no plant data).** Kaggle Severstal Steel Defect Detection (D03,
public under competition terms) and NEU-DET (D02). Raw images are **not**
redistributed in the repository.

**Tool chain.** RLE mask decoder → U-Net / FPN baseline (Y2R11) → per-class Dice
→ inference timing on one declared device → error gallery of small/faint defects.

**What each reference validates.**
- Y2R11 — real-time semantic-segmentation methodology and reported Dice as
  external literature.
- Y2R14 — competition data, rules and evaluation metric.
- D02, D03 — provenance and licensing.

**Deliverables.** `cases/severstal_segmentation/`; per-class Dice table;
inference benchmark; error gallery; limitations on class imbalance.

**Validation.** Per-class metrics, not only mean Dice; timing measured on one
declared device; no claim of production-line latency without hardware.

**Acceptance.** At least one failure mode analysed qualitatively; competition
terms recorded in `data/SOURCES.md`.

## Claim boundary

See [`evidence.md`](evidence.md) for the evidence level and the exact wording
that must be used when quoting literature numbers. All datasets and references
are listed in [`sources.md`](sources.md); the four-week execution plan is in
[`week_plan.md`](week_plan.md).
