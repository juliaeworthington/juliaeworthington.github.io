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
Clustering is the process of grouping data. Clusters come in a variety of shapes and sizes, and how data is prepared and clustered can affect how clusters are formed and what they represent. This project uses two clustering methods, k-means clustering and hierarchical clustering. In k-means clustering, first, the number of clusters k is chosen using an elbow or silhouette plot. Second, k different points are chosen as initial centroids, and the distance from each point to each centroid is calculated. Data points are assigned to the cluster with the nearest centroid, centroids are recalculated for each cluster, and the process is repeated until convergence is achieved. In hierarchical clustering, each point starts in its own cluster. At every following step, the two clusters with the closest point are merged. For n data points, hierarchical clustering always begins with n clusters and ends with 1. After forming the hierarchical clustering dendrogram, one can simply "cut" the dendrogram to achieve the desired number of clusters, which again can be given by an elbow or silhouette plot. Clustering has previously been used in Counter-Strike analytics to identify "star" players. The following image from Sam Carder of rdy.gg uses [PCA](https://juliaeworthington.github.io/pca/) and kNN clustering to group players by position and play-style. 

<img width="787" height="787" alt="Gr8yXFiWQAA6Df2" src="https://github.com/user-attachments/assets/92796bf8-9593-4e08-b27f-fe22340901ca" />
([source](https://x.com/LuzRaposa/status/1927314539835519100))

In combination with [PCA](https://juliaeworthington.github.io/pca/), this project will use clustering to analyze and group players by performance; however, to avoid simply recreating the image above, different data will be used. In fact, the data used to create this plot is not provided by rdy.gg; only the Duel Swing statistic is provided, not the components that form it. In addition to individual player statistics, clustering will also be used on team statistics to show changes in overall team performance over time. 

## Data Prep
For k-means clustering, data must be standardized before any clustering can begin. This is because, in order for distance from centroids to be measured fairly, each axis needs to be shifted to have a mean of 0 and rescaled to have a variance of 1. For this, the `X = StandardScaler().fit_transform(data)` line in Python will be sufficient after removing any non-numerical rows from the data. In [`top_teams_clustering.ipynb`](), the following code block is used to standardize dataset `hltv/top_teams.csv` with two features: Maps and Rating3.0.
```python
data = df.drop(columns=['Team', 'K-D Diff', 'K/D'])
X = StandardScaler().fit_transform(data)
```
<img width="640" height="480" alt="maps_v_rating_scatter (2)" src="https://github.com/user-attachments/assets/be0ee4ce-b110-4a3a-9087-fc773d56bf0b" />

Above is the original data. Below is the standardized data. Notice the differences between the axes of the two plots. 

<img width="640" height="480" alt="maps_v_rating_scatter_standard (1)" src="https://github.com/user-attachments/assets/6cefe095-b2a9-447b-b568-95e5e544b8f4" />

Each point on the plot is a different team. The purpose of this particular clustering analysis is to break the teams into categories: the definitive Tier 1 teams, Tier 1.5 and Tier 2 teams. While this would inherently call for only three clusters, elbow and silhouette plots may provide a different number of clusters that is specific to the shape of the data.

## Code
All coding was done in Python and can be found in full in [`top_teams_clustering.ipynb`](). The following code block was used to perform and plot k-means clustering using k=6 clusters. 

```python
km = KMeans(n_clusters = 6)
km.fit(X)
```
## Results
Below are the elbow and silhouette plots for the Maps and Rating3.0 features from `hltv/top_teams.csv`. The plots indicate that a k value between 6 and 8 provides the optimal number of clusters. 

<img width="640" height="480" alt="maps_v_rating_elbow (2)" src="https://github.com/user-attachments/assets/06af7836-e253-4cf0-9208-841ba1c9f768" />
<img width="640" height="480" alt="maps_v_rating_silhouette (1)" src="https://github.com/user-attachments/assets/264b631b-081e-4e27-b08d-9ef8247549f3" />

Below are the clustered data plots, where the different colors on each plot represent different clusters. The plots have 6, 7, and 8 clusters, respectively.

<img width="640" height="480" alt="teams_6_clusters" src="https://github.com/user-attachments/assets/ee97b6cd-1b3d-4a23-8bf3-60a952ad118d" />
<img width="640" height="480" alt="teams_7_clusters" src="https://github.com/user-attachments/assets/30e5c210-fd5c-49ec-8707-c1adc52807cb" />
<img width="640" height="480" alt="teams_8_clusters" src="https://github.com/user-attachments/assets/d095a24c-83df-4055-84b8-94e25ded266d" />


<!-- <img width="640" height="480" alt="stats_elbow" src="https://github.com/user-attachments/assets/d5fd69be-b95c-460e-b4f2-392dba4d80fd" />
<img width="640" height="480" alt="stats_silhouette" src="https://github.com/user-attachments/assets/50a92c5c-178a-48ed-b61b-c0316d92ab55" />
<img width="640" height="480" alt="stats_pca" src="https://github.com/user-attachments/assets/e378f2ed-b209-4b01-a42f-847c13a0f170" />
-->

## Conclusions
Each plot and its number of clusters tells a different story about the data. The k=6 and k=7 plots combine the two points with the highest Rating3.0, while k=8 breaks them in two. The point with the highest Rating3.0 is Team Vitality; the other is Team Spirit. These two teams have been neck and neck for the latter half of the year so far, with Spirit taking up the number one spot that was once occupied by Vitality. The elbow plot suggests that this is the optimal number of clusters, while the silhouette plot does not. Between k=6 and k=7 clusters, we only see shifts in the clustering of the other teams. Going forward, it might be especially important to compare Vitality with Spirit, the dominant team as of late. 
