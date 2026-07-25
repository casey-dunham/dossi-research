# Data attribution & use terms

Study 2 uses two external, de-identified research datasets. Only **non-identifiable
aggregate statistics** derived from them are published in this repository; all
per-step and per-participant patient-derived files are **withheld** under the
datasets' respective terms.

## JAEB-Loop (Loop Observational Study)
- Source: Jaeb Center for Health Research, Loop Observational Study (NCT03838900).
- Obtain the dataset directly from its custodian; it is not redistributed here.
- Dataset-specific attribution and disclaimer required by the JAEB Read Me:
  > The source of the data is the Loop Study (sponsored by the Jaeb Center for
  > Health Research and funded by the Helmsley Charitable Trust), but the analyses,
  > content and conclusions presented herein are solely the responsibility of the
  > authors and have not been reviewed or approved by the study sponsor.
- Use: this repository publishes only derived aggregate/participant-level summary
  statistics. The source dataset is not redistributed here.

## HUPA-UCM
- Source: Mendeley Data, DOI `10.17632/3hbcscwz44.1`
  (SHA-256 of the retrieved archive: `db60753024508a3ccf8003858b65a610449ffb38bb6ff1cf5c9ff41bf0b44de3`).
- License: CC BY 4.0, as stated on the dataset record.
- Citation: Hidalgo JI, Alvarado J, Botella M, Aramendi A, Velasco JM, Garnica O.
  *HUPA-UCM Diabetes Dataset*. Mendeley Data, 2024, version 1.
  https://doi.org/10.17632/3hbcscwz44.1

## Pinned comparator algorithms (for the deferred code release only)
When the simulation/comparison code is released, include and comply with the
licenses of the vendored/pinned controllers used as comparator boundaries:
`LoopAlgorithm` (`@2f5c630`), `nightscout/trio-oref` (`@8282ce71`), and the oref0
bridge. These are **not** included in the current artifact-only release.
