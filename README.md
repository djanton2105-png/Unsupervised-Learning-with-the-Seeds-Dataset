# Unsupervised Learning with the Seeds Dataset

## Project overview

In this project, I use K-means clustering to explore the structure of the Seeds dataset without initially using the true variety labels. The dataset contains 210 observations of wheat kernels, each described by seven numerical features.

The goal is to investigate how well unsupervised learning can identify meaningful groups in the data without prior knowledge of the original varieties.

## Data

The dataset was retrieved from [OpenML](https://www.openml.org/) using the `seeds` dataset, version 1, via `fetch_openml()` in Python.

The dataset contains seven geometric measurements of wheat kernels:

- Area
- Perimeter
- Compactness
- Kernel length
- Kernel width
- Asymmetry
- Groove length

The original variety labels were set aside during clustering and used only afterward to evaluate how well the resulting clusters corresponded to the known varieties.

## Preprocessing

Before clustering, I standardized the seven numerical features using `StandardScaler` from scikit-learn. This transforms each feature to have a mean of approximately zero and a standard deviation of approximately one.

Standardization is important because the measurements use different scales. Without scaling, features with larger numerical values or variances could have a disproportionate influence on the distance calculations used by K-means.

## Methods

I used K-means clustering to identify groups of similar wheat kernels.

To select the number of clusters, I compared the elbow method and silhouette scores. The elbow plot suggested a low number of clusters, while the silhouette score was highest for two clusters. I therefore selected a two-cluster solution.

I then examined the cluster centres, converted them back to the original measurement units, and compared the clusters with the original variety labels using a cross-tabulation and the purity score.

Finally, I used principal component analysis (PCA) to visualize the observations in two dimensions, coloured by their true varieties.

## Results

The silhouette score was approximately 0.466 for two clusters, the highest among the tested solutions. The resulting clustering achieved a purity score of approximately 0.657.

The cross-tabulation showed that 68 of the 70 observations from Variety 2 were assigned to one cluster. The other cluster contained all 70 observations from Variety 3 and 61 of the 70 observations from Variety 1.

These results indicate that the two-cluster solution captured some of the structure of the original varieties but did not fully reproduce the three-category classification.

## Reflection and limitations

An important challenge was choosing the number of clusters because the elbow method and silhouette score did not point to exactly the same solution. I selected two clusters based on the higher silhouette score and evaluated the result against the true labels only afterward.

The analysis illustrates that the number of clusters that best describes the structure of the data does not necessarily match the number of original categories. Furthermore, the PCA visualization represents the data in only two dimensions, whereas K-means used all seven standardized features. The plot may therefore conceal separations that exist in the original feature space.

Overall, this project demonstrates how unsupervised learning can reveal structure in data and how external labels can subsequently be used to evaluate the results.
