# Microsoft AI Engineer Program

Course projects from the Microsoft AI Engineer Program, taken through Simplilearn and completed in July 2026. Each folder holds the submitted notebook, executed end to end with its real output, plus the writeup and the rendered-notebook PDF that went in with it.

| Project | Course | What it does | Result |
|---|---|---|---|
| [Mercedes-Benz Greener Manufacturing](01-mercedes-benz-greener-manufacturing) | Machine Learning using Python, course-end project 1 | Predicts test-bench time from about 360 anonymized configuration features: zero-variance removal, label encoding, PCA, XGBoost regression | Validation R² 0.39, RMSE 9.8 |
| [Lending Club loan default](02-lending-club-loan-default) | Deep Learning Specialization, course-end project | Predicts whether a borrower will default from 2007 to 2015 LendingClub data: feature transformation, EDA, correlation pruning, a Keras model with class weighting for the 84/16 split | Recall on the default class 0.58, ROC-AUC 0.69 |
| [Sales forecasting](03-capstone-sales-forecasting) | AIML Capstone, option 3 | Restaurant item sales: outlier checks, day-of-week and seasonal patterns, item and restaurant comparisons, then Linear Regression vs Random Forest vs XGBoost with the last six months held out, and a one-year forecast from the best model | XGBoost RMSE 797 against 2,234 for linear regression |

`exercises/` has an earlier course exercise (customer order analysis). Datasets are not included; they are the course-provided files and the public Kaggle originals of the same names.

## What carried into production

I build and run multi-tenant AI systems for support ticket routing and outbound lead handling. The parts of this program I use every week are the data handling and the evaluation habits: a precision and recall sweep across cutoffs is how the knowledge-base match threshold in my support routing service is set, and the classifier eval there fails the build on any missed unsubscribe. The modeling libraries from the course are not in that code; an LLM call does the classification. The statistics lessons are what I am putting to work next, starting with sample sizes for outbound copy tests.

## Reproducing

Each notebook lists its imports at the top. They were run with Python 3.11, pandas, scikit-learn, XGBoost and TensorFlow/Keras. Place the course dataset next to the notebook under the filename the first cell reads.
