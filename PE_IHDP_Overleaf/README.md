# Probing-Enhanced IHDP -- Overleaf project

Upload `main.tex`, `references.bib`, and the `sections/` folder to a new Overleaf project, or upload the entire ZIP. Set `main.tex` as the main document and compile using pdfLaTeX.

- `main.tex`: document class, packages, title, abstract, and references.
- `sections/model.tex`: paper-style introduction, problem definition, modeling notation, complete two-stage formulation, discussion of constraints, a dosing proposition, and a finite-scenario representation.
- `references.bib`: reference to the supplied revised IHDP manuscript. This bibliographic item is intentionally described as a manuscript, not a published article.

Modeling assumptions to review before extending to computational experiments:
1. One crop and one nutrient; fixed number K of nonempty contiguous zones.
2. Nutrient status and potential test outcomes have a known joint probability distribution.
3. Testing occurs before delineation and nutrient-rate decisions.
4. Each management zone receives a uniform nutrient rate per hectare.
5. Crop yield is represented by a nutritional sufficiency target rather than an explicit response curve.
6. The homogeneity measure is an expected *within-zone* variance, not the global relative-variance (RV) index in the source IHDP manuscript. This is a purposeful modeling choice.
7. The conditional chance constraints guarantee nutritional sufficiency *per geographic unit*, not jointly for the entire field.
8. For the exact finite-scenario representation, potential test signals must be represented by appropriate finite/discretized outcomes. A naive independent sample-average approximation of continuous signals can artificially reveal the entire scenario.
9. Feasibility of the recourse problem for (almost) every realized testing outcome is assumed; if that is not credible, one can add explicitly penalized homogeneity/nutritional slacks or otherwise restrict the first-stage feasible designs.

No solution method, linearization claim, data-calibrated agronomic relationship, or numerical results are implied by this draft.
