# AI-Based Academic Performance Prediction System

Predict a student's future academic performance from current and historical data to flag at-risk students early for intervention.

## Overview

Many students fall behind academically before instructors or advisors can intervene, because declining grades, reduced engagement, and inconsistent study habits often go unnoticed until after a failed exam or low midterm grade. Manually tracking these patterns across a class or cohort is time-consuming and inconsistent. This project builds a system that predicts future academic performance using data such as grades, attendance, and study habits, so instructors and students can act before performance drops significantly.

See the full proposal: [docs/Group12_ProjectProposal.pdf](docs/Group12_ProjectProposal.pdf)

## Team

| Team Member | Role | Primary Responsibilities |
|---|---|---|
| Rafiatou | Project Manager | Keeps timeline on track, writes/compiles the report, prepares the final presentation or demo, coordinates team meetings |
| Fredda | Evaluation & Testing Lead | Tests model accuracy, checks for overfitting/bias |
| Omuwa | Data Engineer | Finds/collects the dataset, cleans and preprocesses data (handling missing values, formatting grades/attendance), documents data sources |
| Mitchelle | AI Engineer | Builds and trains the AI model (e.g. Random Forest), handles feature selection, and tunes model performance |

## Repository Structure

```
Group 12 Project/
├── data/
│   ├── raw/
│   └── processed/
├── notebooks/
|   └── archive/
├── references/
├── src/
├── reports/
│   └── figures/
└── docs/
```

| Folder | Purpose |
|---|---|
| `data/raw/` | Original, unmodified datasets |
| `data/processed/` | Cleaned and transformed data ready for modeling |
| `notebooks/` | Exploratory analysis and modeling notebooks |
| `archive/` | Old exploratory analysis and modeling notebooks |
| `references/` | External reference materials (e.g. third-party Kaggle notebooks) |
| `src/` | Reusable Python code shared across notebooks |
| `reports/figures/` | Saved charts and figures for the report |
| `docs/` | Written project documents |

## Datasets

Three raw datasets are stored under `data/raw/`:

| Subfolder | File | Status |
|---|---|---|
| `student_performance_predictions/` | `student_performance_updated_1000.csv` | **Initial dataset** — used in the earlier stages of the project |
| `student_alcohol_consumption/` | `student-mat.csv` | **Primary dataset** — used for modeling going forward |
| `student_performance_analysis/` | `Student_performance_data _.csv` | Reference/comparison only — not used in the final model |

## Dataset Selection
An earlier version of this project used the "Student Performance Predictions" 
dataset, but correlation analysis and baseline modeling 
revealed no meaningful relationship between the available features and 
FinalGrade (all |r| < 0.04), and the trained Random Forest performed at 
baseline accuracy, correctly predicting only the majority class. 

Following this, we decided to switch to the UCI Student Alcohol 
Consumption dataset, which showed genuine, interpretable signal (failures: 
r = -0.36, Medu: r = 0.22) and produced a model that meaningfully 
outperformed baseline (46.8% vs 41.8% accuracy) with real per-class 
discrimination. See data/raw/student_performance_predictions/SOURCE.md 
for the original dataset.

Citation details for the (updated) primary dataset: [data/raw/student_alcohol_consumption/SOURCE.md](data/raw/student_alcohol_consumption/SOURCE.md)

## Prior Work / References

`references/prior_work_student_perf_ipynb/` contains a third-party Kaggle notebook (`college-data-exploratory-data-analysis.ipynb`) kept for reference during exploration. It was **not authored by our team**.

Source:
- [Joelknapp — Student Performance Analysis (Kaggle)](https://www.kaggle.com/code/joelknapp/student-performance-analysis/input)

## Milestone Plan

| Week | Milestone / Key Deliverables |
|---|---|
| Week 10 | Collect & clean data. Sketch system design. Set up GitHub repo + README |
| Week 11 | Build baseline model (Random Forest). Commit code regularly. |
| Week 12 | Tune model, start evaluation. Bring a working prototype for the progress demo. |
| Week 13 | Finish evaluation. Run ethics/bias audit. Draft report & slides. |

## AI Technique

The candidate technique is **Random Forest**. It works well with mixed data types (grades, attendance, habits) without extensive cleanup, handles missing or messy data, and surfaces which factors matter most — making results easier to explain to instructors. The main trade-offs are potential overfitting on small datasets and reduced interpretability compared to a single decision tree.

The team may re-evaluate and consider other techniques later in the project lifecycle.
