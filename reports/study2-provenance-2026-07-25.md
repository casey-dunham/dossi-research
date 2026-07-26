# Study 2 aggregate provenance

The publication-facing Study 2 aggregates were generated from Dossi evaluation
revision `f68531d9e3933c5eb7d085a24cd29be31cb545fc`, which includes the audited post-low replay-state and
zero-basal invariant corrections.
The replay contains 285,906 unique decision rows from 933 fixture-days and 467
adult JAEB-Loop participants. Analysis used the repository scripts
`analyze_decision_divergence_reports.py` and
`analyze_participant_level_decision_divergence.py` at that frozen revision.

The following hashes identify the withheld, participant-derived inputs and full
analysis outputs from which the public aggregate TSVs were produced:

| Withheld artifact | SHA-256 |
|---|---|
| `decision-divergence-steps.tsv` | `26dfaf9bbe4e5ca60c049ab934bae09d05141cad13c68a0e9c055ea43fcf10b6` |
| `participant-level-summary.tsv` | `7f21c11954c4520cffb53587a5b82d95fe0efdb13b016c60be258ed023a19fef` |
| `source-suspend-without-dossi-audit.tsv` | `26de40e1424e405239f97f9acd1f7cc750e04ef8b759cf07c7e1c11a43f14420` |

The source rows are withheld under the dataset terms because they contain
participant- and timestep-level information. The two adjacent public TSVs contain
only non-identifiable aggregate statistics.
