# Unsupervised Learning with the Seeds Dataset

In this project, I use K-means clustering to explore the structure of the Seeds dataset without initially using the true variety labels. The dataset contains 210 observations, each described by seven numerical features of wheat kernels.

I use the elbow method and the silhouette score to determine a suitable number of clusters. Based on these diagnostics, I select a two-cluster solution. I then examine the cluster profiles and evaluate the clustering using a cross-tabulation and the purity score.

Finally, I reveal the true variety labels and compare them with the resulting clusters to assess how well the unsupervised approach captures the original structure of the data. I also discuss the limitations of interpreting the clusters through a two-dimensional PCA visualization.
