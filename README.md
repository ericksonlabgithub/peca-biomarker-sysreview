# Penile Cancer Biomarker Systematic Review — Analysis Code

This repository contains the data processing and statistical analysis code accompanying the manuscript:

> **Prognostic biomarkers of penile squamous cell carcinoma: A systematic review**
> Christian E.A. Reincke*, Laura K.M. Sysivirta*, Franziska Niemeyer, Sari Tulokas, Hanna K. Vasarainen, Andrew M. Erickson 

---

## Overview

This systematic review investigates prognostic and predictive biomarkers in penile cancer. The repository provides full reproducibility of all figures and statistical analyses reported in the manuscript. The underlying data table is available as a supplementary file of the publication and as a CSV in this repository.

---

## Repository structure

```
peca-biomarker-sysreview/
├── data/                         # Raw and pre-processed data
├── pre-processing/               # Data standardization notebooks
├── descriptive_statistics/       # Notebooks for descriptive figures
├── comparative_statistics/       # Notebooks for comparative analyses
└── pyproject.toml                # Dependency management (Poetry)
```

### `pre-processing`
Standardizes the raw extracted data table for downstream analysis. This includes parsing hazard ratios, confidence intervals, p-values, and other numerical values, and standardizing survival outcome names across studies.

### `descriptive_statistics`
Covers the characteristics of the included studies and biomarkers, frequency distributions, and summary visualizations of the extracted data.

### `comparative_statistics`
Covers outcome association analyses across biomarkers, forest plots, and investigation of methodological parameters associated with the direction and magnitude of reported outcome associations.

---

## Data

The primary data table used in all analyses is available
- as a supplementary file of the publication (see above)
- as `data/PeCa_Final_Included_freeze_2026-02-26.csv` and `data/preprocessed_data.csv` in this repository

The data table contains one row per reported biomarker-outcome association analysis result, with columns covering study metadata, biomarker characteristics, detection and scoring methods, and extracted survival statistics (HR, CI, p-value).

---

## Reproducing the analyses

### Requirements

- Python ≥ 3.11
- [Poetry](https://python-poetry.org/) for dependency management

### Setup

Clone the repository and install the dependencies as follows.

```bash
git clone https://github.com/ericksonlabgithub/peca-biomarker-sysreview.git
cd peca-biomarker-sysreview
poetry install
poetry shell
```

### Running the notebooks

Run notebooks in the following order:

1. `pre-processing/` — run first to generate the standardized data table
2. `descriptive_statistics/` — individual notebooks for each descriptive statistical analysis
3. `comparative_statistics/` — individual notebooks for each comparative statistical analysis

Each notebook loads the data table into a `df` variable at the top and is otherwise self-contained.

---

## Dependencies

Key packages (see `pyproject.toml` for full list):

- `pandas` — data manipulation
- `matplotlib` / `seaborn` — visualization
- `scipy` — statistical tests

For versions and other additional information on the packages used, see `poetry.lock`.

---

## Contact

For questions about the analysis code, please open a GitHub issue or contact andrew.erickson@helsinki.fi.

---

## License

[License — e.g. MIT]