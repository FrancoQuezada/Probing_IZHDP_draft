# Probing-enhanced IHDP: four comparable models (Overleaf project)

Import the ZIP into Overleaf. The main file is `main.tex` and the compiler is `pdfLaTeX` (references use BibTeX).

## Files

- `main.tex`: preamble, article title and abstract.
- `sections/model.tex`: research-style model with derivations and scenario counterparts.
- `references.bib`: citation for the revised IHDP manuscript provided by the user.

## Formulations included

- **PE-0**: probing, fixed K connected zones, uniform zone-specific nutrient rates, and per-hectare conditional crop-nutrition chance constraints. No explicit homogeneity restriction.
- **PE-1 (H1)**: PE-0 with posterior expected global Relative Variance (RV) at least alpha.
- **PE-2 (H2)**: PE-0 with posterior probability of global RV >= alpha at least 1-beta.
- **PE-3 (H3)**: PE-0 with posterior expected within-zone variance at most delta^2 for every zone.

PE-1 and PE-2 use the same RV formula as the source deterministic IHDP, including its pooled sample-variance normalization. PE-3 is a different, zone-by-zone absolute dispersion criterion. They are **alternatives**, not simultaneous restrictions. Their stringency is not generally comparable at equal numerical thresholds.

## Modeling conventions and limitations

- One known crop and one nutrient; K is fixed and the adjacency graph is connected.
- Testing precedes the adaptive delineation and uniform fertilization decisions.
- The joint soil/test signal law is known; residual soil uncertainty remains after testing.
- The overall objective is testing cost plus expected fertilizer cost. Crop yield is proxied by a nutritional sufficiency target rather than an explicit yield-response function.
- Nutritional chance constraints apply individually to each geographic unit, conditional on each observed test result.
- All three homogeneity specifications concern **initial** nutrient levels, before fertilizer addition.
- For RV variants, the full-field realized variance is assumed positive almost surely.
- Conditional requirements must hold for almost every observation under the selected probing design; strong thresholds may lead to infeasible recourse.
- The finite-scenario representation is mathematically exact for a supplied finite joint distribution; the formulas are not a ready-to-run MILP because posterior coefficients and conditional homogeneity depend on probing decisions.
- No numerical experiments are claimed.
