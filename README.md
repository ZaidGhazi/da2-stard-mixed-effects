# STAR*D Longitudinal Mixed-Effects Analysis

## Overview
This project analyzes STAR*D depression symptom trajectories using longitudinal mixed-effects models. The workflow cleans demographic and QIDS symptom data, explores baseline characteristics and symptom patterns over time, and compares candidate random-effects models for repeated measures.

## Problem Statement
Estimate how QIDS depression scores change over treatment weeks while accounting for repeated observations within subjects and subject-level covariates such as sex, race, age, episode history, and family psychiatric history.

## Key Features
- Merges demographic and symptom-tracking files by subject ID.
- Filters to subjects with at least three visits and handles invalid missing-value codes.
- Builds exploratory summaries and spaghetti/loess plots for symptom trajectories.
- Fits random-intercept and random-slope mixed-effects models with `lme4`.
- Compares candidate models using AIC, BIC, AICc weights, and fitted-vs-observed plots.

## Data Source
The project uses course-provided STAR*D demographic and QIDS files:

- `STARD Demo 1.csv`
- `STARD Demo 2.csv`
- `STARD QIDS.csv`

The raw STAR*D files are confidential/restricted and are intentionally not committed to this public repository. The rendered report and source workflow are included so employers can review the modeling approach, but only authorized users with access to the STAR*D files can rerun the analysis.

## Methods and Tools
- Quarto
- R, tidyverse, lme4, AICcmodavg, gtsummary, e1071, ggplot2
- Longitudinal EDA, data cleaning, mixed-effects regression, model comparison

## How to Run Locally
1. Install R and Quarto.
2. Copy `.Renviron.example` to `.Renviron` if you want to track local data paths.
3. If you are authorized to use the STAR*D data, add the CSV files to the repository root, matching the filenames above.
4. Render the report:

```bash
quarto render scr.qmd
```

Install R packages:

```r
install.packages(c(
  "tidyverse", "lme4", "AICcmodavg", "gtsummary", "e1071"
))
```

## Required Packages
- `tidyverse`
- `lme4`
- `AICcmodavg`
- `gtsummary`
- `dplyr`
- `e1071`

## Main Files to Review
- `scr.qmd`: Quarto source analysis.
- `Report.pdf`: rendered final report.
- `Instructions.pdf`: assignment instructions.
- `.Renviron.example`: placeholder data path configuration.

## Screenshots
Screenshots are not committed yet. Suggested additions:

- `screenshots/qids-spaghetti-plot.png`
- `screenshots/loess-symptom-trajectory.png`
- `screenshots/observed-vs-predicted-qids.png`

## Limitations
- Raw STAR*D CSV files are confidential/restricted and are not committed.
- Public reviewers can inspect the rendered report and source code, but cannot rerun the analysis without authorized data access.
- Some interpretation text remains embedded in the Quarto report rather than summarized in separate documentation.
- The analysis uses complete-case filtering for selected modeling variables, which may affect generalizability.

## Future Improvements
- Add a data dictionary describing the STAR*D variables used in the model.
- Move model-comparison results into a compact README table.
- Add reproducible data-path handling through `.Renviron`.
- Add screenshots from the rendered report for quick portfolio scanning.

