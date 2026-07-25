# dossi-research

Open research artifacts for **Dossi**, an open-source, iPhone-native automated
insulin delivery (AID) system. This repository accompanies the preprint:

> *Designing Automated Insulin Delivery Around Cognitive Burden: An Operating
> Philosophy, an In-Silico Cohort Evaluation, and a Retrospective Decision-Level
> Characterization of a Reduced-Input Controller.* Casey Dunham, Georgia Institute
> of Technology. (medRxiv, in preparation.)

## ⚠️ Research artifacts, not clinical guidance

Dossi is **not FDA cleared or approved**. It is a do-it-yourself, open-source
research system and is not intended or marketed for clinical use. Nothing here is medical advice, and no result in this repository
is a clinical claim, nor a superiority or non-inferiority claim over any system.
Every number is an **in-silico** or **decision-level** result under the tested
conditions. See [`DISCLAIMER.md`](DISCLAIMER.md).

## What's here

- [`reports/RESULTS.md`](reports/RESULTS.md) — the publication-facing results cited
  in the paper (Study 1 cohort tables, loss slices, Study 2 decision-divergence),
  with the load-bearing caveats (comparator tuning asymmetry, author-built plant).
- [`reports/study1-cohort-2026-06-27.tsv`](reports/study1-cohort-2026-06-27.tsv)
  — the per-arm aggregate data behind Study 1 Tables 1–2.
- [`MANIFEST.md`](MANIFEST.md) — maps each paper table to its source artifact.
- [`ATTRIBUTION.md`](ATTRIBUTION.md) — dataset sources, attribution, and use terms.

## What's *not* here (by design)

- **Patient-derived data.** Per-step and per-participant rows from JAEB-Loop and
  HUPA-UCM are **withheld** under those datasets' data-use terms; only
  non-identifiable aggregates are published. Source datasets are obtained directly
  from their custodians (see `ATTRIBUTION.md`).
- **Internal working documents.** The raw internal analysis logs (which contain
  development history, internal file paths, and dataset participant identifiers) are
  **not** published; `reports/RESULTS.md` is the clean, publication-facing summary.
- **Secrets / credentials / the deployable pump-commanding application.**
- **The simulation / comparison / replay *code***. Any future code release will
  undergo a separate licensing, privacy, and safety review.

## License map

| Content | License |
|---|---|
| `reports/RESULTS.md`, `MANIFEST.md`, docs | AGPL-3.0 (see `LICENSE`), © the author |
| `reports/*.tsv` aggregate data | released for reuse with attribution (CC BY 4.0) |
| Simulation/benchmark code (when released) | AGPL-3.0 |
| Figures / manuscript text | CC BY 4.0 |
| External datasets (JAEB, HUPA-UCM) | governed by their own terms — see `ATTRIBUTION.md` |

## Citation

If you use these artifacts before a preprint DOI is assigned, cite the title and
author shown above together with the immutable repository release revision.
