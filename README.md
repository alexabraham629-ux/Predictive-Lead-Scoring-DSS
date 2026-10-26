# Predictive Lead Scoring & Decision Support System

A machine-learning decision-support system that predicts which B2C leads will convert and sorts them into priority tiers for the sales team, with an interactive ipywidgets scoring panel.

## Business challenge
Only 38.5% of leads in the data ever convert, so most sales effort goes to leads that won't buy. Scoring leads by conversion probability lets the team work the best ones first.

## Data and preparation
- **Dataset:** X Education lead-scoring data, 9,240 leads × 37 columns.
- **Cleaning:** dropped columns with more than 40% missing values, median / mode imputation, IQR clipping of outliers.
- **Feature engineering:** a composite **Engagement Score** built from normalised website activity (time on site, total visits, page views per visit).

## Models
| Model | Test ROC-AUC |
|---|---|
| Logistic Regression (baseline) | 0.872 |
| **Random Forest** (300 trees, class-balanced) | **0.884** |

The Random Forest reaches 81.3% accuracy and 81.9% recall on the test set, correctly identifying 862 of 1,068 converting leads.

## Decision support
The notebook's final cell launches an ipywidgets panel: enter a lead's attributes and get a conversion probability plus a tier (HOT / WARM / COLD / DEAD) with a recommended action. Trained artifacts are saved with `joblib`.

## Business impact (as projected in the report)
- Concentrating on HOT leads could lift the conversion rate of worked leads from 38.5% toward 70%.
- Less time spent on leads unlikely to convert.

## Repository structure
```
├── lead_scoring_dss.ipynb    # Cleaning, features, models, evaluation, scoring widget
├── data/
│   └── lead_scoring.csv      # X Education lead data
└── reports/
    ├── report.pdf            # Full project report
    └── presentation.pptx
```

## How to run
```bash
pip install -r requirements.txt
jupyter notebook lead_scoring_dss.ipynb
```
Run from the repository root; the notebook finds `data/lead_scoring.csv` automatically. Run the second cell to open the scoring panel.

## Tech stack
Python · pandas · scikit-learn · Matplotlib · Seaborn · ipywidgets · joblib
