# Patterns in Online Retail

👉 Start here: [main_notebook.ipynb](main_notebook.ipynb)

## Overview

This project studies more than 500,000 online retail transactions from the UCI Online Retail II dataset to understand how purchasing behavior is structured across products, customers, and time. The final notebook is a curated analysis that moves from cleaning and feature engineering into market basket mining, customer segmentation, seasonal analysis, and shipping-cost modeling.

The goal is to turn messy transaction logs into a readable analytical story: what customers tend to buy together, which customers are most valuable, when demand peaks, and which carts are likely to incur special logistics overhead.

## Project Video

[YouTube](https://youtu.be/BfZJh6oDZ4s)

## Research Questions

1. What cross-category purchasing behaviors appear in the transaction data, and what product bundles do they suggest?
2. How can customers be grouped by recency, frequency, and monetary value?
3. Which products and categories show strong seasonal or intraday demand cycles?
4. Can cart composition predict whether an invoice will trigger POST or DOT shipping behavior?

## Data

Primary dataset:

- Online Retail II from the UCI Machine Learning Repository
- Source: https://archive.ics.uci.edu/dataset/502/online+retail+ii

The raw data contains invoice-level retail transactions with product descriptions, quantities, prices, timestamps, and partially missing customer identifiers. In the notebook, the data is cleaned by standardizing column names, parsing dates, removing invalid or non-purchase rows, and filtering out negative quantities and zero prices.

Feature engineering steps in the final notebook include:

- line-item revenue calculations
- season and day-of-week extraction
- time-zone mapping by country
- customer-level RFM aggregates
- category labels generated from product descriptions
- invoice-level features for shipping prediction

The file [unique_stock_codes_categorized.csv](data/unique_stock_codes_categorized.csv) is the cached output of the product categorization step. If you already have this file, you can reuse it directly and skip regenerating the LLM-based categorization, which is the most time-consuming part of the pipeline.

## Reproducibility

This project was developed in Google Colab and curated into a final notebook for submission. To reproduce the work:

1. Install the dependencies listed in [requirements.txt](requirements.txt).
2. Download the UCI dataset and place the Excel file expected by the notebook at the project root, or update the input path in the notebook.
3. Open [main_notebook.ipynb](main_notebook.ipynb) and run it from top to bottom.
4. Review the checkpoint notebooks in [checkpoints/](checkpoints/) if you want to see the project progression.

If you are refreshing the Colab export, also capture the exact runtime with `!python --version` and regenerate `requirements.txt` with `!pip freeze > requirements.txt` before committing.

## Key Dependencies

The full dependency list lives in [requirements.txt](requirements.txt). The main packages used in the notebook are:

- Python 3.9.6
- pandas 2.3.3
- numpy 2.0.2
- scikit-learn 1.6.1
- mlxtend 0.23.4
- google-generativeai 0.8.6
- matplotlib 3.9.4
- seaborn 0.13.2
- scipy 1.13.1
- statsmodels 0.14.6

## Repo Structure

```text
.
├── README.md
├── requirements.txt
├── main_notebook.ipynb
├── data/
│   └── unique_stock_codes_categorized.csv
├── checkpoints/
│   ├── checkpoint_1.ipynb
│   └── checkpoint_2.ipynb
└── .gitignore
```

## Results Summary

The analysis shows that retail behavior in this dataset is highly structured rather than random. The notebook finds strong “complete the set” basket patterns, meaningful customer segments such as VIP and at-risk groups, pronounced temporal cycles including early seasonal peaks, and highly predictive shipping behavior, with DOT reaching an ROC-AUC of 0.985 and POST reaching 0.804.

## Notes

- The final deliverable notebook is [main_notebook.ipynb](main_notebook.ipynb).
- The two checkpoint notebooks are preserved in [checkpoints/](checkpoints/) to show the project’s progression.
- Generated analysis artifacts can be recreated by rerunning the notebook.

## Author
Shravan Bhat

UIN: 735007755