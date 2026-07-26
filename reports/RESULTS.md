# Dossi — Paper 1 results (public artifact)

Clean, publication-facing presentation of the results cited in the preprint. All
values are reproduced from `study1-cohort-2026-07-25.tsv` (Study 1) and the
retrospective decision-divergence analysis (Study 2). **These are
in-silico / decision-level results under the tested conditions — not clinical claims,
and not a superiority or non-inferiority comparison** (see caveats below).

## Study 1 — in-silico cohort

The Dossi arms are pinned at `0d43d13cabf169531970cc07d0387dbb74f1b127`.
Comparator algorithm-boundary references are pinned at
`LoopAlgorithm@2f5c630084aa`, `oref0@88cf032aa74f`, and
`trio-oref@8282ce71a57d`. Source audit confirmed the same deterministic cohort,
seeds, plant, arm configuration, and comparator wrappers. The plant is Dossi's
independent `GroundTruthPhysiology`, **not** the licensed UVA/Padova T1DMS.

### Table 1 — adult stratum (primary target population, n = 100/arm)

| Arm | TIR 70–180 | TBR<70 | worst TBR<54 | 70–120 | 70–160 | TAR>180 |
|---|---:|---:|---:|---:|---:|---:|
| Dossi+AB | 82.88% | 0.00% | 0.00% | 54.04% | 76.71% | 17.13% |
| LoopAlgorithm+AB | 79.17% | 0.00% | 0.00% | 43.63% | 71.92% | 20.83% |
| TrioOref+SMB | 80.83% | 0.58% | 0.00% | 45.54% | 73.46% | 18.58% |
| OpenAPS+SMB | 74.58% | 0.25% | 0.00% | 42.25% | 70.92% | 25.17% |
| Dossi-noAB | 69.29% | 0.00% | 0.00% | 40.38% | 64.75% | 30.71% |
| LoopAlgorithm-noAB | 69.04% | 0.00% | 0.00% | 38.67% | 64.00% | 30.96% |
| TrioOref-noSMB | 69.00% | 0.00% | 0.00% | 40.63% | 64.00% | 31.00% |
| OpenAPS-noSMB | 68.92% | 0.00% | 0.00% | 41.08% | 65.88% | 31.08% |

### Table 2 — overall cohort (300 subjects: 100 adult / 100 adolescent / 100 child)

| Arm | TIR 70–180 | TBR<70 | 70–120 | 70–160 | TAR>180 | Mean BG | Total U | Auto U |
|---|---:|---:|---:|---:|---:|---:|---:|---:|
| Dossi+AB | 81.32% | 0.125% | 51.26% | 75.22% | 18.56% | 136.9 | 2.499 | 1.450 |
| LoopAlgorithm+AB | 79.53% | 0.181% | 48.78% | 73.67% | 20.29% | 138.4 | 2.259 | 1.482 |
| TrioOref+SMB | 80.22% | 0.694% | 49.88% | 74.19% | 19.08% | 135.9 | 2.505 | 1.633 |
| OpenAPS+SMB | 74.67% | 0.278% | 43.82% | 71.88% | 25.06% | 144.3 | 2.107 | 1.109 |
| Dossi-noAB | 71.01% | 0.069% | 42.49% | 66.32% | 28.92% | 152.5 | 1.447 | 0.000 |
| LoopAlgorithm-noAB | 70.90% | 0.00% | 42.00% | 66.54% | 29.10% | 153.1 | 1.323 | 0.000 |
| TrioOref-noSMB | 70.58% | 0.097% | 43.13% | 66.19% | 29.32% | 151.7 | 1.372 | 0.000 |
| OpenAPS-noSMB | 69.43% | 0.00% | 42.11% | 67.25% | 30.57% | 152.6 | 1.065 | 0.000 |

Severe-low (TBR<54) is reported at the adult stratum, where it is 0.0% for every
arm. The overall worst-row TBR<54 is omitted because for the +correction comparator
arms it is dominated by isolated single-subject *pediatric* fixtures the
algorithm-boundary bridges mishandle (a validated harness artifact, out of Dossi's
target population). Dossi+AB held worst-row TBR<54 at 0.0% across all 300 subjects.

### Interpretation

Automated correction accounts for most between-arm separation: with correction
disabled, adult arms converge near 69% TIR. Dossi's correction setting was selected
on this cohort while comparators retained pinned defaults, so the comparison
characterizes controller posture rather than superiority. The next comparative
test requires matched tuning on a held-out cohort with stochastic-input noise or an
independent licensed simulator.

## Study 2 — retrospective decision-divergence (JAEB-Loop, HUPA-UCM)

The authoritative Study 2 source is the frozen replay identified in
`study2-provenance-2026-07-25.md`. The adjacent headline, suspend-tail,
settings-slice, row-cap-sensitivity, and HUPA TSVs are the machine-readable
aggregate sources.

A point-in-time recommendation comparison: at each observed timestep, Dossi's headless
decision-stack recommendation is compared to the therapy actually delivered. This
measures **decisions, not outcomes** — after the first divergence the observed future
reflects the delivered system, not Dossi's hypothetical actions.

**JAEB-Loop, full adult cohort (467 participants, participant-level, bootstrap CIs):**
the median participant had Dossi recommending *more* total insulin than delivered in
**54.55%** of >180 mg/dL rows (95% CI 51.95–56.69) and **57.66%** of >250 mg/dL rows
(95% CI 54.83–62.82). The low-window direction was weaker and more variable (median
19.29% of pre-<70 rows Dossi-less; 13.34% of pre-<54). Falling-low Dossi zero-basal
was 88.89% at the participant median.

The audit found and corrected a replay-state plumbing defect and a production
post-low zero-basal invariant violation. No residual delivered-zero/Dossi-nonzero
row occurred during post-low recovery.

The audited set contains 100 rows from 33 participants and 37 fixture-days,
mapping to **40 distinct subsequently observed <54 mg/dL onsets**. Dossi retained
nonzero basal (median 0.75 U/hr; range 0.325–2.1) under `trustedPredictedLow` (62
rows) or `fallingTrendBlock` (38 rows). Sixty-minute predicted minima were
70.09–100 mg/dL. Forecasts exceeded the observed 60-minute nadir by a median 36.45
mg/dL (range 17.09–60.80), and median lead time to the observed <54 onset was 41.99
minutes. These 40 episodes are residual prediction/suspension validation targets,
not 100 independent safety events. The observed future followed delivered therapy
rather than Dossi, so they are not Dossi-caused outcomes. “Delivered zero basal” is
used because the dataset does not establish the source application's reason for
every zero-basal row.

A smaller settings-complete sub-slice shows a stronger high-glucose signal, but that
figure is sensitive to row-cap extraction (e.g. >250 Dossi-more 74.6% capped → 54.2%
uncapped); the full-cohort participant-level numbers above are the reported result.

### Settings-complete capped sub-slice (secondary analysis)

| Scope | Steps | Total Δ median (U) | Dossi more | Dossi less | Equal | >180 more | >250 more | Falling-low zero basal (Dossi/source) |
|---|---:|---:|---:|---:|---:|---:|---:|---:|
| All | 7,118 | +0.042 | 46.85% | 15.44% | 37.71% | 68.07% | 74.62% | 73.02% / 77.34% |
| Overnight | 2,312 | +0.058 | 56.36% | 13.11% | 30.54% | 65.99% | 66.09% | 59.46% / 62.16% |
| Day | 4,806 | +0.008 | 42.28% | 16.56% | 41.16% | 69.26% | 86.59% | 75.10% / 79.67% |
| Post-meal | 2,426 | +0.000 | 32.73% | 22.14% | 45.14% | 55.61% | 60.71% | 98.18% / 80.91% |
| Fasting | 4,692 | +0.054 | 54.16% | 11.98% | 33.87% | 77.19% | 84.96% | 56.55% / 75.00% |

This table is a capped extraction of 14 participants, not the primary result. Under
uncapped extraction of the same participants, >250 Dossi-more falls from 74.62% to
54.22% and pre-<70 Dossi-less rises from 12.07% to 30.00%.

### HUPA-UCM manual-therapy contrast

The HUPA-UCM contrast covers 8 adult Medtronic subjects, 16 subject-days, and 4,616
decision rows. At the participant level, median total delta was +0.004 U; Dossi was
equal to delivered therapy in 48.90% of rows, higher in 33.19%, and lower in 17.92%.
Before observed <70 mg/dL windows Dossi was lower in 49.64% of rows; no <54 windows
occurred in this slice. Dossi recommended zero basal in 83.20% of falling-low rows
versus 0.00% source zero-basal. This is a manual-therapy contrast and does not support
a generalized claim that Dossi suspends at least as readily as delivered AID therapy.

*These are recommendation-divergence observations on data the models never trained or
tuned on — not patient-outcome evidence.*

## Provenance
See `MANIFEST.md` for pinned revisions, artifact hashes, and source mapping.
Per-step and per-participant patient-derived files are withheld under the JAEB and
HUPA-UCM data-use terms (`ATTRIBUTION.md`); only these non-identifiable aggregates are
released.
