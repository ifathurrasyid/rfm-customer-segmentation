# RFM Customer Segmentation & K-Means Clustering 🎯

## Overview
An Unsupervised Machine Learning pipeline designed to transition a retail business from generic mass-marketing to targeted, mathematically optimized campaigns. By leveraging **Recency, Frequency, and Monetary (RFM)** analysis paired with the **K-Means clustering** algorithm, this engine processes hundreds of thousands of raw transactions to identify distinct customer personas.

## The Dataset
This project utilizes the benchmark **UCI Online Retail Dataset**, comprising over 500,000 raw transactional records from a UK-based online retailer. 
* **Data Cleansing:** Filtered out null IDs, negative quantities (returns/cancellations), and zero-cost items, resulting in a clean matrix of ~397,000 valid purchases.

## Mathematical Methodology
1. **RFM Aggregation:** Transformed item-level transactional data into customer-centric metrics (Days since last purchase, total unique invoices, lifetime spend).
2. **Feature Normalization:** Applied a Logarithmic Transformation to neutralize severe right-skewness in the 'Monetary' column, followed by a Standard Scaler ($Mean = 0$, $Variance = 1$) to ensure equal weighting for the Euclidean distance calculations.
3. **Model Optimization:** Executed K-Means simulations across $k=1$ to $k=10$. Utilized the **Elbow Method (Inertia)** and **Silhouette Scores** to mathematically validate $k=4$ as the optimal number of clusters.

## Executive Business Personas
The algorithm successfully segmented the customer base into four highly actionable cohorts:

* 👑 **The Champions:** High Spend, High Frequency, Recent Activity. 
  * *Strategy:* VIP exclusivity, early product access, zero discounting.
* ⚠️ **At-Risk Whales:** High Spend, High Frequency, *Low* Recent Activity.
  * *Strategy:* Immediate, aggressive Win-Back campaigns to prevent high-value churn.
* 📈 **Active Buyers:** Medium Spend, Moderate Frequency, Recent Activity.
  * *Strategy:* Targeted up-sell and cross-sell pipelines to maximize Lifetime Value (LTV).
* 👻 **Lost Customers:** Low Spend, Single Purchase, Stale Activity.
  * *Strategy:* Cease active ad spend; downgrade to automated drip campaigns.

## 3D Interactive Visualization
*(Add a screenshot of your Plotly 3D scatter plot here)*
`![3D Clustering Matrix](./path-to-your-image.png)`

## Tech Stack
* **Core:** `Python`, `Pandas`, `NumPy`
* **Machine Learning:** `Scikit-Learn` (K-Means, StandardScaler, Silhouette Score)
* **Visualization:** `Matplotlib`, `Seaborn`, `Plotly` (3D Interactive)