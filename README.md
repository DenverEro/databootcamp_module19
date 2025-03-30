# Crypto Clustering with K-Means and PCA

## 📌 Overview

This project applies **unsupervised machine learning** techniques to analyze cryptocurrency market behavior based on their **24-hour** and **7-day price changes**. Using **K-Means clustering** and **Principal Component Analysis (PCA)**, the goal is to group cryptocurrencies with similar short-term price movement patterns.

The analysis is performed in two stages:
1. Using the original scaled features (`price_change_percentage_24h`, `price_change_percentage_7d`)
2. Using a PCA-reduced dataset with fewer features to simplify and visualize clustering

---

## 📊 Methods

### Data Preparation
- Loaded crypto market data from `crypto_market_data.csv`
- Normalized numerical features using `StandardScaler` for fair clustering input

### Clustering (Original Features)
- Used the **Elbow Method** to identify the optimal number of clusters (`k`)
- Found that **k = 3** was the best value based on inertia drop-off
- Applied **KMeans** to cluster the cryptocurrencies using the original features
- Visualized the clusters using `hvPlot` with crypto names on hover

### Dimensionality Reduction with PCA
- Applied **PCA** to reduce the 2D feature set into **2 principal components**
- Verified that PCA retained **100% of the original variance**
- Repeated the Elbow Method and KMeans clustering on the PCA-reduced data
- Found that the optimal `k` remained **3**, even after dimensionality reduction

### Visual Comparisons
- Created composite plots comparing:
  - Elbow curves (original vs. PCA data)
  - Clustering results (original vs. PCA data)
- Verified that cluster structure was preserved using fewer features

---

## ✅ Results Summary

- **Best value for `k`:** 3 (consistent across original and PCA data)
- **Impact of PCA:** PCA preserved the cluster structure with no loss of variance, and simplified visualization without sacrificing clustering accuracy.
- **Conclusion:** Cryptocurrencies can be grouped meaningfully using short-term price movements, and PCA offers an efficient way to analyze and visualize such patterns.

---

## 📁 Files

- `Crypto_Clustering.ipynb` – Main Jupyter Notebook with all code and analysis
- `Resources/crypto_market_data.csv` – Input data file
- `README.md` – This file

---

## 🚀 Technologies Used

- Python (Pandas, scikit-learn, hvPlot, NumPy)
- Unsupervised Learning (KMeans, PCA)
- Visualization (Matplotlib, hvPlot)

