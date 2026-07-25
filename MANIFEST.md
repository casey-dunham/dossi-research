# Provenance manifest — paper table → source artifact

All Study-1 arms come from a single coherent 2026-06-27 run (four controllers ×
automated-correction on/off = eight arms), executed against the same plant and the
same virtual subjects. Comparators are pinned algorithm boundaries
(`LoopAlgorithm@2f5c630`, `trio-oref@8282ce71`), not full applications. The plant is
Dossi's independent `GroundTruthPhysiology` implementation, not the licensed
UVA/Padova T1DMS.

| Paper element | Source in this repo |
|---|---|
| Table 1 (adult, 8 arms) | `reports/study1-cohort-2026-06-27.tsv` (adult rows); presented in `reports/RESULTS.md` |
| Table 2 (overall, 8 arms) | `reports/study1-cohort-2026-06-27.tsv` (overall rows); presented in `reports/RESULTS.md` |
| Table 3 (Dossi+AB loss slices) | `reports/RESULTS.md` (loss-slice decomposition of the same 6/27 Dossi+AB arm) |
| Study 2 (JAEB full cohort + sub-slice) | `reports/RESULTS.md` |
| Reported Dossi+AB headline (adult 83.583%, overall 82.583%) | `reports/study1-cohort-2026-06-27.tsv` |

The aggregate TSV is licensed separately under CC BY 4.0; see `DATA-LICENSE.md`.

**Not a source for any reported value:** a later-commit (`dbd0e4f85`, 2026-07-22)
Dossi-arm re-run gave adult TIR 84.0% (within ~0.5 pp of the reported 6/27 value);
the paper reports the coherent 6/27 values throughout. Raw internal analysis logs
are withheld (see README); `RESULTS.md` is the clean publication-facing summary.
