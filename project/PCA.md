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
Here, describe PCA. Explain the concept of eigenvalues and eigenvectors, which sit at the heart of PCA. What's dimensionality reduction and why is reducing the dimensionality of data is important for simplifying analysis and visualization? Elaborate the challenges posed by high-dimensional data and how dimensionality reduction can help address them. Have two images. More is fine.

Principal component analysis (or PCA) finds the directions that carry the most variance of data. Oftentimes, data has too many dimensions to be visualized in 2D. PCA can solve this by reducing the dimension of the data to just two: PC1 and PC2. PC1 describes the largest spread of the data, followed by PC2, a vector orthogonal to PC1. To find PC1 and PC2, the covariance matrix of the prepped data is calculated using $$C=\frac{1}{n-1}X^TX$$

## Data Prep
PCA, like clustering, simply requires that each feature column be standardized. Unlike clustering, dividing by the variance goes a step too far, as it changes the spread of every column to 1, defeating the purpose of PCA. 

## Code
Use R or Python to code PCA. LINK to the code.

## Results
Discuss, illustrate, describe, and visualize the results. Understand and explain how to visualize the relationship between variables and principal components. Include at least 2 visualizations for your data.
Below is a visualization of PCA and k-means clustering on the `hltv/player_stats.csv` data. Because the clusters are formed from PC1 and PC2, the clusters appear jumbled in the plots PC3 and PC4.  
<img width="640" height="480" alt="stats_pca12" src="https://github.com/user-attachments/assets/679d413b-b7f7-4aca-9b6e-5a189126b99e" />
<img width="640" height="480" alt="stats_pca34" src="https://github.com/user-attachments/assets/ad338ec4-317d-4c6d-b349-ff043c6d4eca" />




## Conclusions
What did you learn that pertains to your topic?
