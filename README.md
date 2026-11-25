# Surface-defect detection on a hot-rolling line (C06)

> Workspace folder: `e06-steel-defect-cv` · Suggested GitHub repository: `metallurgy-defect-cv`
> Epic: E06 · Weeks: W22–W25 · Evidence level: **A**
> Master specification: [`CASES.md`](https://github.com/ahmadishamulayadyakmal/metallurgy-project/blob/main/CASES.md) §4 · Download the papers: [`JOURNALS.md`](https://github.com/ahmadishamulayadyakmal/metallurgy-project/blob/main/JOURNALS.md)

## Industrial problem

Severstal deployed high-frequency cameras on a production line and needed pixel-level localisation and classification of four surface defect classes; manual inspection misses faint and small defects.

**Why it happens.** Severe class imbalance, low contrast, thin/small defects, and real-time throughput constraints.

## Data (no plant data)

Open data only: Kaggle Severstal Steel Defect Detection (D03/Y2R14, public under competition terms) and NEU-DET (D02). Raw images are NOT redistributed in this repository. Evidence level A.

> The author cannot supply factory data. This project uses **only open datasets and
> credible peer-reviewed journals**. If this is a B-level case, the case report
> must contain the exact disclaimer from `CASES.md` §1 and must **never** claim
> plant validation.

## Tool chain

PyTorch, U-Net / FPN, RLE mask decoder, per-class Dice, inference timing, error gallery, on-device benchmark.

## Journal references

- **Y2R11** — real-time semantic-segmentation methodology and reported Dice as external literature.
- **Y2R14** — Severstal competition data, rules and evaluation metric.
- **D02** — NEU-DET provenance and licence.
- **D03** — Kaggle Severstal competition terms.

Each reference above is listed with its DOI or stable URL, access status and
manual download route in [`JOURNALS.md`](https://github.com/ahmadishamulayadyakmal/metallurgy-project/blob/main/JOURNALS.md) §4, and in the shared
BibTeX library `papers/references.bib`. Do not cite a paper you have not been
able to obtain; if it is inaccessible, record that in `JOURNALS.md` §8.

## Deliverables

`cases/severstal_segmentation/`; per-class Dice table; inference benchmark on one declared device; error gallery of small/faint defects; limitations section.

## Validation & claims

Per-class metrics (not only mean Dice); timing measured on one declared device; at least one failure mode analysed qualitatively; competition terms recorded in `data/SOURCES.md`.

## Limitations

No claim of production-line latency without the same hardware. Competition terms forbid redistributing raw images.

## Definition of Done

1 merged PR · green tests · 1 new artefact · 1 README paragraph · 1 sprint note
`docs/sprints/wNN.md` · tag `wNN`. Before the case tag `c06` is created,
this README must contain all six sections: Industrial problem, Data (no plant
data), Tool chain, Journal references, Validation & claims, Limitations.

## Repository skeleton

Shared files: `CONTRIBUTING.md` (sprint contract), `.github/` (issue, PR and
CI templates), `docs/sprints/wNN.md`, `docs/vv_template.md` and
`docs/model_card.md`. `CASES.md`, `JOURNALS.md` and `REPOSITORIES.md` are in a
separate planning repository; their links above remain valid after this folder
is pushed as its own repository.

The real industrial case dossier is in `case/`: `README.md` (full case card),
`evidence.md`, `sources.md` and `week_plan.md`.

## Push this folder to GitHub

This folder is prepared but is **not** a Git repository yet:

```bash
cd e06-steel-defect-cv
git init
git branch -M main
git remote add origin https://github.com/<your-user>/metallurgy-defect-cv.git
git add .
git commit -m "Initial import: C06 · W22–W25"
git push -u origin main
```

Use weekly tags `wNN` and one case tag `c06` inside this repository.
Never commit API keys, raw downloaded datasets or publisher PDFs.

## Language

All artefacts in this repository are written in **English**.
