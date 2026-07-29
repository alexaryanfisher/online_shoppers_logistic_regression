# Online Shoppers Purchasing Intention Analysis

## Overview

This project analyzes the **Online Shoppers Purchasing Intention** dataset from the UC Irvine Machine Learning Repository to identify which website session attributes are associated with a customer completing a purchase. The work was completed as part of the WGU MS Data Analytics capstone and received an Excellence Award for exemplary performance in Task 2.

## Business Problem

E-commerce teams collect large volumes of behavioral data, but not every session metric is equally useful for predicting conversion. This project evaluates which Google Analytics-style features are most strongly associated with purchase behavior so teams can improve targeting, page strategy, and customer retention efforts.

## Research Question

Which captured website session attributes contribute to the likelihood that a customer will complete a purchase?

## Hypothesis

- **Null hypothesis:** The logistic regression model shows no statistically significant relationship between the target variable `Revenue` and the explanatory variables.
- **Alternative hypothesis:** The logistic regression model shows a statistically significant relationship between `Revenue` and one or more explanatory variables.

## Dataset

- **Source:** UC Irvine Machine Learning Repository, *Online Shoppers Purchasing Intention* dataset.
- **Observations used:** 12,205 sessions.
- **Target variable:** `Revenue`.
- **Feature examples:** Administrative activity, informational activity, product-related activity, bounce rate, exit rate, page value, special day, weekend, and visitor type.

## Tools and Methods

This analysis was built in Python using a Jupyter Notebook and included:

- `pandas` and `numpy` for data preparation and transformation.
- `scikit-learn` for train/test split, scaling, logistic regression, and classification metrics.
- `statsmodels` for logistic regression interpretation and significance testing.
- `seaborn` and `matplotlib` for exploratory visualizations.

The workflow included exploratory data analysis, outlier review, categorical encoding, feature selection, multicollinearity checks with VIF, logistic regression modeling, and model evaluation with confusion matrices plus classification reports.

## Results

The notebook shows an initial logistic regression model accuracy of about 0.89 on the test set, with class 1 purchase recall notably lower than class 0 performance, which is common in imbalanced conversion problems.

An optimized model produced similar overall performance, with test accuracy around 0.88 and a statistically significant overall model fit based on the reported log-likelihood ratio p-value of 0.000.

The reduced model retained statistically significant variables including `ProductRelated`, `ProductRelatedDuration`, `BounceRates`, `ExitRates`, `PageValues`, `SpecialDay`, `Weekend`, and `VisitorType Returning_Visitor`.

Among these, `PageValues` showed a strong positive association with purchase likelihood, while `BounceRates`, `ExitRates`, and `SpecialDay` showed negative relationships in the reported coefficients.

## Business Impact

The findings support several practical e-commerce actions:

- Prioritize pages and sessions with stronger product engagement and page value signals.
- Investigate high-exit and high-bounce experiences to reduce abandonment.
- Refine marketing and retention strategies for returning customers and time-sensitive promotions.
- Use model insights to guide decisions across marketing, sales, and customer retention teams.

## Repository Structure

```text
online-shoppers-logistic-regression/
├── README.md
├── data/
│   └── raw/
│         └── onlinepurchasing.csv
│   └── cleaned/
│         └── onlinepurchasing_clean.csv
├── notebooks/
│   └── online_shoppers_logistic_regression.ipynb
├── reports/
│   ├── online_shoppers_capstone_report.pdf
│   └── online_shoppers_executive_summary.pdf
├── presentation/
│   └── online_shoppers_purchase_intention_presentation.pptx
└── recognition/
    └── wgu_capstone_excellence_award.pdf
```

## Deliverables

- [Project Notebook](./notebooks/online_shoppers_logistic_regression.ipynb)
- [Capstone Report](./reports/online_shoppers_capstone_report.pdf)
- [Executive Summary](./reports/online_shoppers_executive_summary.pdf)
- [Presentation Deck](./presentation/online_shoppers_purchase_intention_presentation.pptx)
- [Excellence Award](./recognition/wgu_capstone_excellence_award.pdf)

## Recognition

This project received a WGU Excellence Award for the Data Analytics Graduate Capstone, Task 2.

The accompanying project summary notes strengths in the review of the research question, analysis quality, interpretation of the logistic regression model, and use of visualizations.

## Repository Notes

This repository highlights an end-to-end analytics workflow for a supervised classification problem, from data preparation through model interpretation and business recommendations. It is intended as a portfolio project demonstrating applied statistics, machine learning, and stakeholder-focused communication.
