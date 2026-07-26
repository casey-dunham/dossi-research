# Study 2 aggregate provenance

The publication-facing Study 2 aggregates were regenerated on 2026-07-25 from
Dossi evaluation revision `0d43d13cabf169531970cc07d0387dbb74f1b127`.
The replay contains 285,906 unique decision rows from 933 fixture-days and 467
adult JAEB-Loop participants. Analysis used the repository scripts
`analyze_decision_divergence_reports.py` and
`analyze_participant_level_decision_divergence.py` at that frozen revision.

The following hashes identify the withheld, participant-derived inputs and full
analysis outputs from which the public aggregate TSVs were produced:

| Withheld artifact | SHA-256 |
|---|---|
| `decision-divergence-steps.tsv` | `4d477549ac60119ca2c07c00485644617305bf16b4c4cda19751259a59c1461f` |
| `participant-level-summary.tsv` | `6bad317506bced49511de2990c81a21cba401d3ae60247a5c6e244ddc13b715f` |
| `source-suspend-without-dossi-audit.tsv` | `3c2b6fa44596c23731851a6d870ceda04afa72e2e6b21bfd068b4ad3e38f8503` |

The source rows are withheld under the dataset terms because they contain
participant- and timestep-level information. The two adjacent public TSVs contain
only non-identifiable aggregate statistics.

An older replay generated on 2026-07-09 remains in the private workspace and is
not the paper's source of truth. It has the same 285,906 row keys and 933 fixtures
but was produced before the frozen 2026-07-25 Dossi evaluation revision; its
headline and suspend-tail values must not be mixed with this release.
