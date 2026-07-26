# dossi-research

Aggregate research artifacts for **Dossi**, an iPhone-native automated insulin
delivery (AID) controller intended for future release under AGPL-3.0. The
deployable application and evaluation code are not released in this repository.
This repository accompanies the preprint:

> *Engineering Characterization of an Automated Insulin Delivery Controller:
> In-Silico Cohort Evaluation and Retrospective Decision Replay.*
> Casey Dunham, Georgia Institute of Technology. (medRxiv, in preparation.)

## ⚠️ Research artifacts, not clinical guidance

Dossi is **not FDA cleared or approved**. It is a do-it-yourself, open-source
research system and is not intended or marketed for clinical use. Nothing here is medical advice, and no result in this repository
is a clinical claim, nor a superiority or non-inferiority claim over any system.
Every number is an **in-silico** or **decision-level** result under the tested
conditions. See [`DISCLAIMER.md`](DISCLAIMER.md).

## What's here

- [`reports/RESULTS.md`](reports/RESULTS.md) — the publication-facing results cited
  in the paper (Study 1 cohort tables and Study 2 decision-divergence),
  with the applicable methodological boundaries (comparator tuning asymmetry,
  author-built plant).
- [`reports/study1-cohort-2026-07-25.tsv`](reports/study1-cohort-2026-07-25.tsv)
  — the per-arm aggregate data behind Study 1 Tables 1–2.
- [`reports/study2-headline-2026-07-25.tsv`](reports/study2-headline-2026-07-25.tsv)
  — participant-level aggregate headline metrics and bootstrap intervals.
- [`reports/study2-suspend-tail-2026-07-25.tsv`](reports/study2-suspend-tail-2026-07-25.tsv)
  — aggregate characterization of the residual prediction/suspension disagreements.
- [`reports/study2-jaeb-settings-slice-2026-07-25.tsv`](reports/study2-jaeb-settings-slice-2026-07-25.tsv)
  — aggregate rows behind manuscript Tables 3A–B.
- [`reports/study2-jaeb-row-cap-sensitivity-2026-07-25.tsv`](reports/study2-jaeb-row-cap-sensitivity-2026-07-25.tsv)
  — capped-versus-uncapped sensitivity for the settings-complete JAEB slice.
- [`reports/study2-hupa-contrast-2026-07-25.tsv`](reports/study2-hupa-contrast-2026-07-25.tsv)
  — aggregate HUPA-UCM manual-therapy contrast.
- [`reports/study2-provenance-2026-07-25.md`](reports/study2-provenance-2026-07-25.md)
  — frozen source revision, row counts, and hashes of withheld source artifacts.
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
| `reports/*.tsv` aggregate data | CC BY 4.0 — see `DATA-LICENSE.md` |
| Simulation/benchmark code (when released) | AGPL-3.0 |
| Figures / manuscript text | CC BY 4.0 |
| External datasets (JAEB, HUPA-UCM) | governed by their own terms — see `ATTRIBUTION.md` |

## Citation

If you use these artifacts before a preprint DOI is assigned, cite the title and
author shown above together with the immutable repository release revision.
