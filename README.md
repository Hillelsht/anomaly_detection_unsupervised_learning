# E-Commerce Anomaly Detection Using Unsupervised Learning

## Overview

This project focuses on **detecting anomalies** in an e-commerce dataset using **unsupervised machine learning models**. The dataset contains transactions from a UK-based online retail store, including information such as product descriptions, quantities, prices, and customer IDs. By identifying unusual purchasing patterns or outliers, we aim to detect potential fraudulent transactions or system errors.

---

## Problem Statement

In an e-commerce environment, identifying suspicious transactions or irregular customer behavior is critical to prevent fraud and operational issues. This project aims to solve the problem of anomaly detection by focusing on key factors like:

- **Unusually large purchases** (high `Quantity` and `TotalSpent`).
- **Abnormal product descriptions** (using NLP techniques).
- **Duplicate or frequent transactions** (potential system or customer errors).

---

## Machine Learning Approach

This project uses **unsupervised learning techniques** to detect anomalies, which means there are no labeled "normal" or "fraudulent" transactions. The models used are:

1. **Isolation Forest**: This model isolates data points and identifies outliers based on how different they are from the majority of transactions.
2. **HDBSCAN**: A clustering algorithm that groups data points based on density, identifying points in low-density regions as anomalies.
3. **Natural Language Processing (NLP)**: Applied to product descriptions to detect unusual or suspicious text entries that may indicate product listing errors or fraud.

### Key Features Used:
- `Quantity`
- `UnitPrice`
- `TotalSpent` (derived from `Quantity` × `UnitPrice`)
- `CustomerID`
- `InvoiceDate`
- `Description`

---

## Exploratory Data Analysis (EDA)

Before applying the models, we explored the data through various visualizations to understand the distributions and identify potential outliers. Key steps included:
- **Boxplots** for `Quantity`, `UnitPrice`, and `TotalSpent` to visualize outliers.
- **Word Cloud** to visualize frequent terms in product descriptions.
- **Time-series analysis** to investigate anomaly trends over time.

---

## Results

### Model Performance:

- **Isolation Forest** detected **4,001 anomalies** after tuning.
- **HDBSCAN** detected **6,425 anomalies**, reflecting its ability to capture local outliers.
- **Common anomalies** detected by both models: **2,133 transactions**.

These common anomalies are highly suspicious and require further investigation.

### Insights from Analysis:

- Some anomalies involved **extremely large transactions** (e.g., £168,469.60 for 80,995 units of "PAPER CRAFT, LITTLE BIRDIE").
- **Duplicate transactions** were found, with **694 instances**, which could indicate system errors or fraudulent activity.
- The analysis of product descriptions revealed some with extremely short or incomplete descriptions (e.g., labeled as "Manual"), indicating potential data-entry issues.

---

## Technologies Used

- **Python**: The main programming language used for data manipulation, modeling, and visualization.
- **Pandas**: For data processing and manipulation.
- **Scikit-learn**: For implementing the **Isolation Forest** model.
- **HDBSCAN**: For density-based clustering and anomaly detection.
- **Matplotlib/Seaborn**: For visualizations.
- **NLP**: For analyzing product descriptions.

---

## How to Run the Project

### Prerequisites:
- Python 3.6 or higher.
- Install the required Python libraries using:
  
  ```bash
  pip install -r requirements.txt
