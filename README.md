# Crypto Clustering

## Overview
This project applies machine learning techniques to cluster cryptocurrencies based on market performance data. It utilizes K-Means clustering and Principal Component Analysis (PCA) to explore the relationships between cryptocurrencies.

---

## Workflow

### 1. Data Preparation
- Load and inspect `crypto_market_data.csv`.
- Normalize data using `StandardScaler()` from scikit-learn.
- Create a scaled DataFrame with the `coin_id` column as the index.

### 2. Finding the Best Value for k
- Use the **Elbow Method** to determine the optimal number of clusters (`k`).
- Plot inertia values for `k = 1 to 11`.
- Optimal value of `k`: **4**.

### 3. Clustering with K-Means
- Perform K-Means clustering using the best value of `k`.
- Visualize clusters with a scatter plot:
  - **X-axis**: `price_change_percentage_24h`
  - **Y-axis**: `price_change_percentage_7d`
  - Points are colored by cluster label.

### 4. Dimensionality Reduction with PCA
- Reduce features to 3 principal components using PCA.
- Total explained variance of the three components: **88%**.
- Create a PCA DataFrame with `coin_id` as the index.

### 5. Optimizing Clusters with PCA
- Use the Elbow Method on PCA data to find the best value of `k` (remains **4**).
- Perform K-Means clustering on PCA data.
- Visualize clusters with a scatter plot:
  - **X-axis**: `PC1`
  - **Y-axis**: `PC2`
  - Points are colored by cluster label.

---

## Results
### Key Findings:
- Optimal clusters (`k`): **4**
- PCA-reduced data improves clustering by creating tighter and more distinct clusters.

### Visualizations:
- Scatter plots highlight clusters in both the original and PCA-reduced datasets.
- Elbow curves validate the optimal `k` value.

---

## Technologies Used
- **Python**: Core programming language.
- **Libraries**:
  - `pandas` for data manipulation.
  - `scikit-learn` for scaling, clustering, and PCA.
  - `hvPlot` for interactive visualizations.
  - `matplotlib` for plotting Elbow curves.

---

## Usage

1. Clone the repository:
   ```bash
   git clone https://github.com/kahan17/CryptoClustering.git
