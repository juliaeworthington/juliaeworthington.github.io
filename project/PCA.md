---
layout: single
title: "PCA"
permalink: /pca/
sidebar:
  image: <img width="1543" height="1875" alt="Team-Vitality-Logo-Vector svg-" src="https://github.com/user-attachments/assets/b810f6f5-9120-48b8-8c93-7afc3573d0e5" />
  nav: "project"
published: true
---

## Overview
Principal component analysis (or PCA) finds the directions that carry the most variance of data. Oftentimes, data has too many dimensions to be visualized in 2D. PCA can solve this by reducing the dimension of the data to just two: PC1 and PC2. PC1 describes the largest spread of the data, followed by PC2, a vector orthogonal to PC1. To find PC1 and PC2, the covariance matrix of the prepped data is calculated using $$C=\frac{1}{n-1}X^TX$$. Then the singular value decomposition (SVD) is calculated, $$C=\frac{1}{n-1}V\Sigma^2V^T$$. In this decomposition, the principal directions/loadings are the right singular vectors of $$V$$ (equivalent to the eigenvectors). The variance of each loading is given by its corresponding singular value/entry in $$\Sigma$$ (equivalent to the eigenvalues). Reducing the rank of SVD helps greatly in dealing with large datasets, while only minimally reducing the accuracy for the features that carry the most variance.

## Data Prep
After removing non-numerical features, PCA, unlike clustering, simply requires that each feature column be centered. Unlike clustering, dividing by the variance goes a step too far, as it changes the spread of every column to 1, defeating the purpose of PCA. In the code, this is done via the following line. 
```python
X_tilda = StandardScaler(with_std = False).fit_transform(data)
```
Below is the code before cleaning and centering. 
<img width="1267" height="365" alt="image" src="https://github.com/user-attachments/assets/388b193b-f745-4957-b49c-684c1a54b747" />
Here is the code after centering. 
<img width="1065" height="371" alt="image" src="https://github.com/user-attachments/assets/d0178b47-900f-41b9-8ad1-45fca27e33bd" />

## Code
The code for PCA on the `hltv/player_stats.csv` dataset can all be found in [player_stats_pca.ipynb](https://github.com/juliaeworthington/juliaeworthington.github.io/blob/main/code/player_stats_pca.ipynb).

## Results
Below is a visualization of PCA and k-means clustering on the `hltv/player_stats.csv` data. Because the clusters are formed from PC1 and PC2, the clusters appear jumbled in the plots PC3 and PC4.  
<img width="640" height="480" alt="stats_pca12" src="https://github.com/user-attachments/assets/679d413b-b7f7-4aca-9b6e-5a189126b99e" />
<img width="640" height="480" alt="stats_pca34" src="https://github.com/user-attachments/assets/ad338ec4-317d-4c6d-b349-ff043c6d4eca" />


## Conclusions
Sniping and clutching contribute the most to PC1 and Opening and Firepower contribute the most to PC2.
