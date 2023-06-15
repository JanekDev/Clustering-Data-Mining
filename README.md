# Final Report: Clustering Analysis on Dataset

## Introduction

In this project, I explored the performance of two clustering algorithms, namely KMeans and DBSCAN, on a high-dimensional dataset. The project involved conducting PCA to reduce the dimensionality of the data, fitting the models, visualizing the clusters, and assessing the similarities between the clusters formed by the two methods.

## Data Preprocessing

Before diving into the clustering analysis, I first prepared the dataset by performing normalization to ensure that all features were on the same scale. I used the StandardScaler from the sklearn library for this process. 
The other normalizations schemas are left in the notebook.

## Dimensionality Reduction

Given the high dimensionality of the dataset, I applied Principal Component Analysis (PCA) to reduce the dimensions to seven for work and three for easier visualization and efficient computation.

## Clustering Analysis

### KMeans

The KMeans algorithm was first applied to the dataset. I chose a number of clusters (k=5) based on the knowledge of the dataset and the exploratory data analysis. The model was then fit to the PCA-transformed data, and the resulting clusters were visualized in a 3D scatter plot.

### DBSCAN

Next, I implemented the DBSCAN clustering algorithm, a density-based clustering method that can find arbitrarily shaped clusters and identify outliers. Unlike KMeans, DBSCAN does not require the number of clusters to be specified beforehand. Instead, it requires two parameters: `eps`, the maximum distance between two samples for them to be considered as in the same neighborhood, and `min_samples`, the number of samples in a neighborhood for a point to be considered as a core point. After tuning these parameters, I fit the model to the PCA-transformed data and visualized the resulting clusters.

## Cluster Similarity Assessment

To evaluate the similarity between the clusters produced by the two methods, I computed the Jaccard and Cosine similarity scores. However, I faced some challenges in properly aligning the labels of the two methods for accurate comparisons. The similarity assessment should be viewed as a high-level indication of similarity rather than an exact measure due to these challenges.

To visualize the inter-cluster similarities within each method, I calculated and visualized similarity matrices for the clusters formed by KMeans and DBSCAN, using cosine, euclidean and manhattan distances.

## Conclusions

The experiments showed that both methods produced meaningful clusters, though with differences in their structures. The two methods revealed different aspects of the data due to their different underlying algorithms. 

It's worth noting that the performance of these clustering methods could be influenced by several factors including the appropriateness of the chosen clustering method for the specific dataset, the normalization schema, and computational constraints affecting the search for optimal parameters.

Despite the challenges, the winning solution for this task was not from either of these algorithms, but rather a custom Gaussian Mixture Model (GMM). This GMM model accounted for the specific structure in the data, dividing it into 42 clusters, structured as 7 groups of 6 clusters each. The implementation involved a custom Expectation Maximization (EM) algorithm, taking into account the details of the data structure and hardcoding means of all the floating point variables to ensure convergence to true cluster centers. This highlights the importance of understanding the underlying data structure in clustering tasks.

For future works, the cluster quality could potentially be improved by exploring other clustering methods such as Gaussian Mixture Models or Spectral Clustering, revising the normalization schema, and harnessing more computational power to optimize the parameters for the clustering methods. Furthermore, feature engineering or feature selection could be employed to enhance the performance of the clustering algorithms. 

In conclusion, this project provided valuable experience in applying and comparing clustering methods on a high-dimensional dataset. The results illustrate

 the complexity of unsupervised learning tasks and underscore the importance of understanding the algorithms and the underlying data.
