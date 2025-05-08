# Cryptocurrency Clustering with K-Means and PCA

This project applies machine learning techniques to cluster cryptocurrencies based on their price change behavior. Using `scikit-learn`, `hvPlot`, and `Pandas`, the analysis explores how dimensionality reduction via PCA affects clustering outcomes, and compares clustering quality before and after PCA.

## Project Structure
-`crypto_data.csv`: Input data file (assumed to contain normalized features and coin identifiers).
-`crypto_clustering.ipynb`: Jupyter notebook with all processing, modeling, and visualizations.
-`README.md`: Project overview and instructions.

## Objectives
1. Normalize Data
  - Standardize all numerical feastures using `StandardScaler`.
  - Create a new DataFrame with the scaled values and `coin_id` as the index.
2. Determine Optimal Clusters (Elbow Method)
  - Test `k` values from 1 to 11 using the elbow method to determine the optimal number of clusters.
  - Visualize inertia values to identify the best `k`.
3. K-Means Clustering
  - Apply K-means clustering to the scaled data using the optimal `k`.
  - Plot clusters using `hvPlot`:
      - X-axis: `price_change_perecentage_24h`
      - Y-axis: `price_change_percentage_7d`
      - Use `coin_id` in the hover tooltip
4. Dimensionality Reduction with PCA
  - Reduce the scaled data to 3 principal components.
  - Calculate the explained variance to evaluate the PCA performance.
  - Create a new PCA DataFrame indexed by `coin_id`.
5. Repeat Elbow Method and Clustering on PCA Data
  - Redetermine the best `k` using the PCA-transformed data.
  - Compare the optimal `k` values from both versions.
  - Cluster using K-means on PCA data and visualize:
      - X-axis: `PCA1`
      - Y-axis: `PCA2`
      - Color by the cluster label, include `coin_id` in hover data
6. Insights and Reflections
  - Analyze how PCA impacts clustering performance and interpret cluster differences.

## Technologies & Libraries Used
- Python
- Pandas
- scikit-learn
- hvPlot
- Jupyter Notebook
