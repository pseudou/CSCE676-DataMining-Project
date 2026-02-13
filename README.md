# CSCE676-DataMining-Project

## Overview

This project explores real‑world e‑commerce transaction data using the **Online Retail II** dataset from the UCI Machine Learning Repository. The goal is to understand purchasing behavior at multiple levels—items, baskets, customers, and time—through careful exploratory data analysis and pattern mining.

The analysis begins with data cleaning and descriptive exploration, then moves toward discovering structure in the data using frequent itemsets and association rules. Based on insights from EDA, the project extends beyond unordered basket analysis to consider temporal and customer‑level patterns.

---

## Dataset

**Online Retail II**  
- Over 1 million transaction line items  
- Variable‑length shopping baskets grouped by invoice  
- Timestamps and partially missing customer identifiers  
- Data spans December 2009 to December 2011  

Each row represents a single product purchased within an invoice. Invoices form the basic unit for basket‑level analysis.

Dataset source:  
https://archive.ics.uci.edu/dataset/502/online+retail+ii

---

## Project Focus

The project is organized around three core questions:

- What structural properties characterize real‑world retail transaction data?
- How do frequent itemsets and association rules behave under long‑tailed, sparse conditions?
- What additional structure emerges when temporal order and customer identity are incorporated?

---

## Methods Used

- Data cleaning and preprocessing with explicit assumptions
- Exploratory data analysis at the item, basket, customer, and temporal levels
- Frequent itemset mining and association rule analysis
- Customer‑level aggregation and sequence construction
- Sequential pattern mining motivated by observed temporal structure

---

## Key Findings from EDA

- Product frequency follows a strong long‑tail distribution
- Revenue is highly concentrated among a small fraction of products
- Basket sizes are heavily skewed, with extreme wholesale‑like outliers
- Item co‑occurrence is sparse even among frequent products
- Clear seasonality and intraday purchasing patterns exist
- Customer‑level analysis applies only to a subset of identifiable customers

These findings motivate moving beyond unordered basket analysis toward sequence‑aware methods.

---

## Notes

- Customer identifiers are missing for a significant portion of transactions; customer‑level analyses are performed on a filtered subset.
- Large baskets are flagged rather than removed to preserve transparency around their influence.
- All preprocessing and modeling decisions are documented and justified in the analysis notebooks.

---

## License

This project is for academic use. The Online Retail II dataset is distributed under **CC BY 4.0** and must be cited appropriately.
