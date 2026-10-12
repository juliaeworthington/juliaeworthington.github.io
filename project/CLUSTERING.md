---
layout: single
title: "Clustering"
permalink: /clustering/
sidebar:
  image: <img width="1543" height="1875" alt="Team-Vitality-Logo-Vector svg-" src="https://github.com/user-attachments/assets/b810f6f5-9120-48b8-8c93-7afc3573d0e5" />
  nav: "project"
published: true
---
## Overview
Clustering is the process of grouping data. Clusters come in a variety of shapes and sizes, and how data is prepared and clustered can affect how clusters are formed and what they represent. This project uses two clustering methods, k-means clustering and hierarchical clustering. In k-means clustering, first, the number of clusters k is chosen using an elbow or silhouette plot. Second, k different points are chosen as initial centroids, and the distance from each point to each centroid is calculated. Data points are assigned to the cluster with the nearest centroid, centroids are recalculated for each cluster, and the process is repeated until convergence is achieved. In hierarchical clustering, each point starts in its own cluster. At every following step, the two clusters with the closest point are merged. For n data points, hierarchical clustering always begins with n clusters and ends with 1. After forming the hierarchical clustering dendrogram, one can simply "cut" the dendrogram to achieve the desired number of clusters, which again can be given by an elbow or silhouette plot. Clustering has previously been used in Counter-Strike analytics to identify "star" players. The following image from Sam Carder of rdy.gg uses (PCA)[https://juliaeworthington.github.io/pca/] and kNN clustering to group players by position and play-style. 

<img width="787" height="787" alt="Gr8yXFiWQAA6Df2" src="https://github.com/user-attachments/assets/92796bf8-9593-4e08-b27f-fe22340901ca" />
((source)[https://x.com/LuzRaposa/status/1927314539835519100])

In combination with (PCA)[https://juliaeworthington.github.io/pca/], this project will use clustering to analyze and group players by performance; however, to avoid simply recreating the image above, different data will be used. In fact, the data used to create this plot is not provided by rdy.gg; only the Duel Swing statistic is provided, not the components that form it. As well as individual player statistics, clustering will also be used on team statistics to show changes in overall team performance over time. 




## Data Prep
All models and methods require specific data formats. Clustering requires ONLY unlabeled numeric data. Explain this and show an image of the sample of data you plan to use. LINK to the sample of data as well. 

## Code
Use R or Python to code k-means clustering and to code hierarchical clustering. Use Cosine Similarity as the distance measure for the h-clust.

## Results
Discuss, illustrate, describe, and visualize the results. Have at least one dendrogram and at least one clustering image (that's not a dendrogram). What values of k did you use for k - means (you should use at least 3 different k values to compare). What did the Silhouette method tell you about the "best k". Include a vis of the silhouette results. Using the hierarchical clustering, how did this compare and coincide with the k-means? What value of k does hclust suggest?

<img width="640" height="480" alt="stats_elbow" src="https://github.com/user-attachments/assets/d5fd69be-b95c-460e-b4f2-392dba4d80fd" />
<img width="640" height="480" alt="stats_silhouette" src="https://github.com/user-attachments/assets/50a92c5c-178a-48ed-b61b-c0316d92ab55" />
<img width="640" height="480" alt="stats_pca" src="https://github.com/user-attachments/assets/e378f2ed-b209-4b01-a42f-847c13a0f170" />



## Conclusions
What did you learn that pertains to your topic?
