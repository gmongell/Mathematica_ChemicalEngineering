# Chemical-engineering models and mathematical-method notebooks

A mixed archive of reaction-engineering calculations, process-modeling work, and partial-differential-equation teaching materials. Some entries retain third-party textbook or demonstration provenance.

## Functions and engineering applications

| Files | Observed or inferred function | Engineering use and status |
|---|---|---|
| `SingleCSTR.nb`, `CSTRs_Single_Series.nb`, `SinglePFTR.nb`, `PFTRthenCSTR.nb`, `PFTRrecycle.nb` | Reactor concentration/conversion calculations; `SingleCSTR.nb` defines `CaCSTR[t]`, `CbCSTR[t]`, and related expressions | Comparing ideal reactor arrangements and residence-time sensitivity [1] |
| `galerkin.nb`, `fd.nb`, `greens.nb`, `eigenpair.nb`, `bessel.nb` | Weighted residual, finite-difference, Green-function, eigenvalue, and special-function material | Analytical/numerical approaches to transport and boundary-value models [2] |
| `Transfer Function.nb`, `Pulse Disturbance.nb`, `Unit Operation.nb` | Process-dynamics topics suggested by the archive titles | Candidate educational material requiring notebook-level review |
| `Separation column_v3.nb`, `Separation column_v4+control (2).nb` | Intact notebook text describing dynamic absorber/stripper column models and pulse disturbances | Candidate source material for restoring column-model work; execution unverified |
| `ChE272_SeparationColumn_*.nb`, `PIDControlOfATankLevel-source.nb` | Intended column/control topics inferred from filenames | Several files are null-filled and cannot currently supply functioning models |

## Example function calls

Open an intact notebook in Mathematica with the working directory set to the repository root:

```wolfram
nb = NotebookOpen[FileNameJoin[{Directory[], "SingleCSTR.nb"}]];
```

Evaluate the parameter and function-definition cells for `Cao`, the rate constants, and `CaCSTR` before calling:

```wolfram
N[CaCSTR[1]]
Plot[CaCSTR[t], {t, 0.01, 5}]
```

Here `t` follows the notebook’s residence-time parameterization. The example range is illustrative; its unit must be consistent with the selected rate constants. Outputs are a concentration value and a concentration-versus-time-parameter plot. There is no universal unit system or package API across this archive, and these calls were not evaluated in Mathematica during this review.

## File integrity and provenance

The following tracked files were found to consist entirely of null bytes: `ChE272_SeparationColumn_v3.nb`, `ChE272_SeparationColumn_v4+control.nb`, `ChE272_SeparationColumn_v5+control.nb`, `ChE272_SeparationColumn_v6_CodeToAdd.nb`, `ChE272_SeparationColumn_v6expt.nb`, `ChE272_SeparationColumn_v7.nb`, and `PIDControlOfATankLevel-source.nb`. Restore them from a known-good backup before use. This documentation update does not repair or replace those files. Two intact alternatives already exist in the repository: [`Separation column_v3.nb`](Separation%20column_v3.nb) (547,546 bytes) and [`Separation column_v4+control (2).nb`](Separation%20column_v4%2Bcontrol%20%282%29.nb) (86,734 bytes). They contain readable Wolfram notebook expressions with column-model problem statements. The v3 candidate has the same byte length as its null-filled counterpart, but that alone cannot prove identical historical content. The v4 candidate differs in size from the damaged v4 file. Library searches on 2026-10-08 did not locate matching replacement notebooks; that is not proof no backup exists.

`ReadMe.nb` identifies material accompanying *Partial Differential Equations and Boundary Value Problems with Mathematica* and credits M. R. Schäferkotter. Preserve the original authorship and any file-specific terms; repository-level notices do not relicense third-party material. Some notebooks use old Mathematica formats or external package references. Check missing packages, symbolic assumptions, residuals, mass balances, and limiting cases before using a result in engineering work.

## Review scope and software citation

Documentation reviewed on 2026-10-08 against source commit [`963ac355e828`](https://github.com/gmongell/Mathematica_ChemicalEngineering/tree/963ac355e82816898bd1f538c802d778809c1096). “Observed” means supported by source inspection; engineering applications are reasoned possibilities unless explicitly demonstrated. Scholarly references provide methodological context and do not certify these implementations. Runtime validation is stated separately above.

For software attribution, cite Guy Francis Mongelli, *Mathematica_ChemicalEngineering*, the [repository](https://github.com/gmongell/Mathematica_ChemicalEngineering), the exact commit used, and your access date. Also cite the relevant method publications and any original third-party contributors. No unverified software DOI or release version is assigned by this documentation.

## Scholarly references

1. P. V. Danckwerts (1953). “Continuous flow systems: Distribution of residence times.” *Chemical Engineering Science* 2, 1–13. [DOI: 10.1016/0009-2509(53)80001-1](https://doi.org/10.1016/0009-2509(53)80001-1). Context for interpreting ideal-flow reactor models and their limitations; an RTD fitting implementation is not claimed.

2. P. K. Kythe, M. R. Schäferkotter, and P. Puri (2003). *Partial Differential Equations and Boundary Value Problems with Mathematica*, 2nd ed., Chapman & Hall/CRC, ISBN 1584883146. [Wolfram bibliographic record](https://www.wolfram.com/books/search.html?year=2003). Scholarly background for symbolic and numerical boundary-value methods.

## Ownership and existing license notices

Copyright (c) 2025 Guy Francis Mongelli

The existing project notice declares Apache License 2.0 for project code. Preserve all file-level and third-party notices. This README update does not change ownership or licensing terms.
