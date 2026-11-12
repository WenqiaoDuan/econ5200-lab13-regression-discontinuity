# econ5200-lab13-regression-discontinuity
# Regression Discontinuity: Bandwidths, Manipulation and Close Elections

## Objective
To understand how bandwidth selection, manipulation of the running variable, and model specification affect regression discontinuity (RD) estimates, and to apply RD to close US House elections.

## Methodology
- Simulated a grant program with a true treatment effect of 8 percentage points at the cutoff.
- Compared a global quadratic regression with a local linear RD estimator using a data-driven bandwidth of 16.1.
- Repeated the simulation 300 times to examine how bandwidth selection affects root mean squared error (RMSE).
- Conducted a density test to detect manipulation of the running variable and a covariate continuity test to examine whether characteristics change at the cutoff.
- Applied RD to US House election data from Lee, Moretti, and Butler (2004) to estimate the effect of a narrow Democratic victory on ADA scores.
- Implemented my own local linear RD estimator using a triangular kernel and compared its results with the `rdrobust` package.

## Key Findings
- **Model specification:** The global quadratic regression estimated a treatment effect of 0.0357, while the local linear estimator produced 0.0789, much closer to the true effect of 0.08.
- **Bandwidth selection:** Across 300 simulations, the lowest RMSE occurred at a bandwidth of 20, showing that bandwidth choice affects estimation accuracy.
- **Manipulation test:** The density test returned a p-value of 0.0022 for data with units moving across the cutoff, indicating a statistically significant discontinuity in the running variable's density.
- **Close elections:** A narrow Democratic victory increased the district's ADA score by an estimated 46.491 points, indicating substantially more liberal representation.
- **Custom estimator:** I implemented a local linear RD estimator with triangular kernel weights and checked its estimates against `rdrobust`.

Overall, this lab helped me understand why local estimation, bandwidth selection, and validity checks matter when using regression discontinuity to estimate causal effects.
