# Survey Evaluation Analysis

This repository contains the analysis notebooks and outputs for the survey-based evaluation, organized into separate phases. Each phase follows the same analysis workflow: raw data is read first, cleaned data is generated and saved, consistency is checked, descriptive analysis is performed to inform statistical test selection, and the final hypothesis results are produced.

## Project Structure

```text
main/
├── data/
│   ├── raw/
│   │   ├── survey1.csv
│   │   └── survey2.csv
│   └── cleaned/
│       ├── survey1_cleaned.csv
│       └── survey2_cleaned.csv
│
├── notebooks/
│   ├── phase1_evaluations.ipynb
│   └── phase2_evaluations.ipynb
│
└── outputs/
    ├── figures/
    │   ├── phase1/
    │   └── phase2/
    │
    └── tables/
        ├── phase1/
        └── phase2/
```

## Analysis Workflow

Both phases are organized according to the following sequence:

1. **Read raw data**
   - Raw survey data is loaded from `data/raw/`.

2. **Clean and prepare data**
   - The required data-cleaning and variable-preparation operations are performed.
   - The resulting cleaned dataset is saved in `data/cleaned/`.

3. **Check data consistency**
   - Existing consistency/reliability analyses are performed.
   - The associated results are saved as tables under the corresponding phase folder in `outputs/tables/`.

4. **Descriptive analysis and statistical test selection**
   - Descriptive characteristics such as data shape, distributions, and other existing descriptive results are examined.
   - These results are used to understand the data and support the selection of the appropriate statistical tests.
   - Existing figures and descriptive tables are saved under the corresponding phase folders.

5. **Final hypothesis analysis**
   - The existing hypothesis-testing procedures are applied to the cleaned data.
   - Final statistical results, figures, and tables are saved under the corresponding phase folders.

No additional tests or plots are introduced beyond the analyses already implemented in the notebooks.

---

# Phase 1

## Input

Phase 1 uses:

```text
data/raw/survey1.csv
```

The notebook is located in:

```text
notebooks/phase1_evaluations.ipynb
```

Because the notebook is inside `notebooks/`, paths are relative to that directory.

## Cleaned Data

The cleaned Phase 1 dataset is saved as:

```text
data/cleaned/survey1_cleaned.csv
```

The analysis includes preparation of the NASA-TLX workload measure (`Overall_NASA_TLX`) and the existing survey variables required for the Phase 1 analyses.

## Consistency and Reliability

The existing reliability/consistency analyses are performed after cleaning.

The resulting table is stored in:

```text
outputs/tables/phase1/reliability_analysis_results.csv
```

## Descriptive Analysis

The Phase 1 descriptive analysis includes the existing:

- Data shape/descriptive summary
- University distribution
- NASA-TLX workload distribution
- Q-Q plot for NASA-TLX
- Workload and missed-information breakdowns by channel strategy
- App-switching and workload relationship

The descriptive tables are stored in:

```text
outputs/tables/phase1/
```

The existing figures are stored in:

```text
outputs/figures/phase1/
```

## Normality Diagnostics

NASA-TLX workload scores are examined for normality using the existing normality-analysis code.

The Shapiro-Wilk normality result is stored in:

```text
outputs/tables/phase1/nasa_tlx_normality_test.csv
```

The normality assessment is used to support the selection of the subsequent statistical procedures.

## Final Hypothesis Results

The existing Phase 1 hypothesis analyses are performed using the cleaned data.

These include:

- **Q7:** Comparison of single-channel and multi-channel strategies for workload and missed information using the existing Mann-Whitney U analyses and associated effect-size calculations.
- **Q8:** Existing Spearman correlation analyses examining app switching in relation to workload and missed information.

The corresponding results are stored under:

```text
outputs/tables/phase1/
```

and the existing hypothesis-related figures are stored under:

```text
outputs/figures/phase1/
```

---

# Phase 2

## Input

Phase 2 uses:

```text
data/raw/survey2.csv
```

The notebook is located in:

```text
notebooks/phase2_evaluations.ipynb
```

## Cleaned Data

The cleaned Phase 2 dataset is saved as:

```text
data/cleaned/survey2_cleaned.csv
```

The existing SUS-related data preparation and scoring procedures are retained.

## Consistency and Reliability

The Phase 2 notebook performs the existing SUS reliability analysis, including the existing Cronbach's alpha calculations.

The reliability results are stored in:

```text
outputs/tables/phase2/rq3_reliability_results.csv
```

## Descriptive Analysis

The existing Phase 2 descriptive analysis includes:

- Dataset shape
- Overall SUS descriptive statistics
- SUS item-level statistics
- Task completion/perception proportions

The associated tables are stored under:

```text
outputs/tables/phase2/
```

## Final Hypothesis / RQ3 Results

The existing Phase 2 analysis evaluates the usability results using the SUS score and the existing analysis procedures in the notebook.

The corresponding descriptive/RQ3 results are stored in:

```text
outputs/tables/phase2/
```

## Figures

The existing Phase 2 figures are retained and saved under:

```text
outputs/figures/phase2/
```

These include:

- SUS score distribution
- SUS item means
- Task metrics

---

# Output Organization

All generated outputs are separated by phase to make the results easier to locate and prevent files from different analyses from being mixed.

### Phase 1 figures

```text
outputs/figures/phase1/
```

### Phase 1 tables

```text
outputs/tables/phase1/
```

### Phase 2 figures

```text
outputs/figures/phase2/
```

### Phase 2 tables

```text
outputs/tables/phase2/
```

This organization allows each notebook to be run independently while keeping its cleaned data, figures, and tables clearly associated with the corresponding evaluation phase.

# Running the Notebooks

Open the notebooks from the `notebooks/` directory and run the cells in order.

The notebooks use relative paths, so the expected project structure should be preserved.

For example, from a notebook:

```python
../data/raw/survey1.csv
```

refers to:

```text
data/raw/survey1.csv
```

Similarly:

```python
../outputs/figures/phase1/
```

refers to:

```text
outputs/figures/phase1/
```

The same pattern applies to Phase 2.

# Dependencies

The analyses use Python scientific-data-analysis libraries already referenced by the notebooks, including:

```text
pandas
numpy
scipy
matplotlib
seaborn
```

Install them if necessary:

```python
%pip install pandas numpy scipy matplotlib seaborn
```

# Notes

- Raw survey files are kept in `data/raw/`.
- Cleaned datasets are generated in `data/cleaned/`.
- Figures and tables are separated by phase.
- Existing analysis procedures and visualizations are retained.
- No additional statistical tests or plots are introduced beyond the existing notebook analyses.
