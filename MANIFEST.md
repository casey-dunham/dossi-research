# Provenance manifest — paper table → source artifact

The two Dossi Study-1 arms were rerun on 2026-07-25 at frozen revision
`0d43d13cabf169531970cc07d0387dbb74f1b127`. Comparator values are retained from
the 2026-06-27 evaluation and were not rerun contemporaneously. They are pinned
algorithm boundaries: `LoopAlgorithm@2f5c630084aa0d72b8d14999e1e0f7c836b0c341`,
`oref0@88cf032aa74ff25f69464a7d9cd601ee3940c0b3`, and
`trio-oref@8282ce71a57d09a160e92ecd2baf28a70c89694d`, not full applications. A
source audit found no changes to the deterministic cohort, seeds, plant, arm
configuration, or comparator wrappers used by these references. The plant is
Dossi's independent `GroundTruthPhysiology` implementation, not the licensed
UVA/Padova T1DMS.

Study 2 uses Dossi evaluation revision
`f68531d9e3933c5eb7d085a24cd29be31cb545fc`, including the audited post-low
replay-state and zero-basal invariant corrections.

| Paper element | Source in this repo |
|---|---|
| Table 1 (adult, 8 arms) | `reports/study1-cohort-2026-07-25.tsv` (adult rows); presented in `reports/RESULTS.md` |
| Table 2 (overall, 8 arms) | `reports/study1-cohort-2026-07-25.tsv` (overall rows); presented in `reports/RESULTS.md` |
| Study 2 JAEB headline | `reports/study2-headline-2026-07-25.tsv`; interpreted in `reports/RESULTS.md` |
| Study 2 suspend-mismatch tail | `reports/study2-suspend-tail-2026-07-25.tsv`; interpreted in `reports/RESULTS.md` |
| Tables 3A–B (JAEB settings-complete slice) | `reports/study2-jaeb-settings-slice-2026-07-25.tsv` |
| JAEB row-cap sensitivity | `reports/study2-jaeb-row-cap-sensitivity-2026-07-25.tsv` |
| HUPA-UCM manual-therapy contrast | `reports/study2-hupa-contrast-2026-07-25.tsv` |
| Study 2 source revision and withheld-artifact hashes | `reports/study2-provenance-2026-07-25.md` |
| Dossi+AB headline (adult 82.875%, overall 81.319%) | `reports/study1-cohort-2026-07-25.tsv` |

The aggregate TSVs are licensed separately under CC BY 4.0; see `DATA-LICENSE.md`.

Raw internal analysis logs are withheld (see README); `RESULTS.md` is the clean
publication-facing interpretation. Non-identifiable Study 2 aggregates and hashes
of the withheld source artifacts are provided so the frozen run can be identified
without releasing participant- or timestep-level data.
