# PUBH 6854 Lab 2: Framingham Analysis Notebooks

## Project overview

This repository contains Python and R analyses of a public Framingham Heart Study teaching subset. Both notebooks investigate how the observed 10-year coronary heart disease outcome varies across age groups and current-smoking status.

## Research question

How does observed 10-year coronary heart disease prevalence vary across age groups and current-smoking status in the Framingham teaching subset?

## Dataset

The dataset is a derived, de-identified teaching subset containing one row per participant. It is not the restricted-access NHLBI Framingham research dataset and should not be treated as a primary research source.

Both notebooks load the CSV directly from:

https://raw.githubusercontent.com/GauravPadawe/Framingham-Heart-Study/master/framingham.csv

An internet connection is therefore required when rerunning the notebooks. No manually cleaned local copy is used.

## Repository structure

```text
.
├── README.md
├── AI_USAGE.md
├── environment.yml
├── renv.lock
├── notebooks/
│   ├── lab2_framingham_heart_study_python.ipynb
│   ├── lab2_framingham_heart_study_python.html
│   ├── lab2_framingham_heart_study_R.Rmd
│   └── lab2_framingham_heart_study_R.html
└── renv/
```

## Analysis

The notebooks:

1. Load the teaching dataset directly from its public URL.
2. Examine the table structure, variable coding, and missing values.
3. Create four age groups and readable smoking-status labels.
4. Calculate participant counts, CHD case counts, and observed CHD prevalence.
5. Calculate current-smoker minus non-current-smoker prevalence differences.
6. Produce a grouped bar chart.
7. Interpret the results using non-causal language.

## Reproduce the Python notebook

Create the Conda environment from the repository root:

```bash
conda env create -f environment.yml
conda activate pubh6854-lab2
```

Open JupyterLab:

```bash
jupyter lab
```

Open `notebooks/lab2_framingham_heart_study_python.ipynb`, restart the kernel, and run all cells.

The notebook can also be executed and rendered from the repository root:

```bash
jupyter nbconvert \
  --to html \
  --execute notebooks/lab2_framingham_heart_study_python.ipynb \
  --output lab2_framingham_heart_study_python.html
```

## Reproduce the R notebook

Restore the R packages from the repository root:

```bash
Rscript -e 'renv::restore(prompt = FALSE)'
```

Render the notebook:

```bash
Rscript -e 'rmarkdown::render(
  "notebooks/lab2_framingham_heart_study_R.Rmd",
  clean = TRUE
)'
```

The rendered file is `notebooks/lab2_framingham_heart_study_R.html`.

## Main findings

The dataset contains 4,240 participants and 644 recorded 10-year CHD outcomes. The observed proportion with the CHD outcome was higher in older age groups and was higher among current smokers within each age group. The largest current-smoker versus non-current-smoker difference was approximately 5.7 percentage points among participants aged 50–59.

These findings are unadjusted associations from an observational teaching dataset and do not establish causation. Potential confounding and the limited generalizability of the teaching subset should be considered.

## AI assistance

Generative AI assistance is documented in [`AI_USAGE.md`](AI_USAGE.md).
