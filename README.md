# Tuwaiq-MiniProject-Evaluating-Clustering
## Evaluating Clustering on Wine Dataset

This project demonstrates the application and evaluation of clustering techniques on the UCI Wine dataset. It covers the complete data science workflow, from preprocessing and dimensionality reduction to model implementation and performance analysis.

## Table of Contents
* [Overview](#overview)
* [Dataset](#dataset)
* [Requirements](#requirements)
* [Workflow](#workflow)
    * [1. Data Preprocessing](#1-data-preprocessing)
    * [2. Dimensionality Reduction](#2-dimensionality-reduction)
    * [3. Clustering](#3-clustering)
* [Results](#results)
* [Key Insights](#key-insights)

## Overview
The goal of this project is to group different types of wine based on their chemical properties without using pre-defined labels. The notebook explores how scaling and dimensionality reduction (PCA) impact the performance of the K-Means and DBSCAN clustering algorithms.

## Dataset
The project uses the **Wine Recognition Dataset** from `sklearn.datasets`.
* **Samples**: 178
* **Features**: 13 chemical constituents (e.g., alcohol, malic acid, ash, magnesium, flavanoids)
* **Target**: Although the dataset includes 3 classes of wine, this project treats it as an unsupervised learning task by focusing only on the features.

## Requirements
To run this notebook, you will need the following Python libraries:
* `pandas`
* `numpy`
* `matplotlib`
* `seaborn`
* `scikit-learn`

## Workflow

### 1. Data Preprocessing
* **Loading**: Data is loaded into a pandas DataFrame.
* **Cleaning**: The dataset was checked for missing values and duplicates (none were found).
* **Scaling**: `StandardScaler` was applied to ensure all chemical features contribute equally to the distance calculations in clustering.

### 2. Dimensionality Reduction
To visualize the high-dimensional data (13 features) in 2D and improve clustering performance, the following technique is used:
* **Principal Component Analysis (PCA)**: Used for linear dimensionality reduction. The notebook tests reducing dimensions to 2 components for visualization, as well as testing 5, 8, and 10 components to balance variance retention and simplicity.

### 3. Clustering
* **Algorithms Tested**: K-Means Clustering and DBSCAN.
* **Optimization**: The project K-Means inertia across different numbers of clusters (k) to find the optimal grouping.
* **Comparison**: K-Means (spherical clusters) is compared against DBSCAN (density-based, noise-detecting).

## Results
The notebook provides visualizations comparing the original feature space against the reduced PCA spaces. 
* Clustering after PCA is shown to be highly effective because PCA removes noise and reduces dimensionality, helping the clustering algorithm identify patterns more effectively.
* Visualization became significantly clearer in the 2D PCA-projected space, allowing for observable cluster separation.

## Key Insights
1. **Dimensionality Reduction**: PCA reduces dimensionality while keeping the most important variance.
2. **Improved Clustering**: Clustering *after* PCA can dramatically improve visualization and cluster separation.
3. **Algorithm Selection**: K-Means works well when clusters are spherical, while DBSCAN is better suited for irregular shapes and noise detection.
