# Unsupervised Learning with the Seeds Dataset

## Project overview

In this project, I use K-means clustering to explore the structure of the Seeds dataset without initially using the true variety labels. The dataset contains 210 observations, each described by seven numerical features of wheat kernels.

## Data and methods

I use the elbow method and silhouette score to determine a suitable number of clusters. Based on these diagnostics, I select a two-cluster solution. I then examine the cluster profiles and evaluate the clustering using a cross-tabulation and the purity score.

Finally, I reveal the true variety labels and compare them with the resulting clusters. I also use PCA to visualize the data in two dimensions.

## Results

The silhouette score was highest for two clusters, at approximately 0.466. The resulting clustering achieved a purity score of approximately 0.657. The cross-tabulation showed that the second variety was concentrated in one cluster, while the first and third varieties were predominantly assigned to the other cluster.

These results suggest that the two-cluster solution captures some, but not all, of the structure of the three original varieties.

## Reflection

One important challenge was choosing the number of clusters when the elbow method and silhouette score did not point to exactly the same solution. I selected two clusters based on the higher silhouette score and evaluated the result against the true labels only afterward.

The analysis also illustrates the limitations of clustering and visualization: the number of clusters that best describes the data does not necessarily match the number of original categories, and a two-dimensional PCA plot cannot show all the information contained in the seven-dimensional feature space.
