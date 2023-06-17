# Exploring-Various-Clustering-Techniques

This repository contains a .ipynb file which contains code for exploring various clustering techniques.
This has 3 parts explained step by step.

## Part 1

Using the **Fashion-MNIST** dataset 

#### About the Dataset:
Each image is 28 pixels in height and 28 pixels in width, for a total of 784 pixels in total. Each pixel has a single pixel-value associated with it, indicating the lightness or darkness of that pixel, with higher numbers meaning darker. This pixel-value is an integer between 0 and 255. The training and test data sets have 785 columns. The first column consists of the class labels (see above), and represents the article of clothing. The rest of the columns contain the pixel-values of the associated image. You can check out the dataset here: https://www.kaggle.com/datasets/zalando-research/fashionmnist

1a) Loading the dataset and use the K Means algorithm and after that finding the optimal number of clusters using the
> i) Elbow method
    >> Plotting the graph between average distance and the number of clusters graph while using the elbow method. Report the optimal number of clusters found. Own Implementation of this without using any inbuilt library.

> ii) Silhoette method
    >> Plotting the graph between silhoutte score and number of clusters using silhoette method. Report the optimal number of clusters found. 
 
 ### Elbow Method vs Silhoette Method
 The main difference between them is in Elbow method we only consider the InterCluster distance however in Silhoette method we consider both Intra and Inter cluster differnece.
 

1b) Experimention with different cluster initialisation methods [k-means++, forgy ("random" in sklearn)]. (init parameter in KMeans class) 


1c) Visualization of the dataset to depict the clusters formed. Leveraging the methods like PCA to reduce the data to 2-3 dimensions and visualize using scatter plots. Color the points according to the clusters (you can use T-SNE or any other matplotlib method)


## Part 2:

Implementation of Hierarchical clustering (agglomerative) on the same dataset.

2a) Visualize a dendogram and find out the optimal number of clusters with the help of Dendogram. 

****Procedure to find the optimal number of clusters using dendogram

In the dendrogram locate the greatest vertical difference between nodes, and in the middle pass an horizontal line. 
The number of vertical lines intersecting it is the optimal number of clusters (when affinity is calculated using the method set in linkage)



2b) Implementation of Hierarchical clustering using: </br>
> i) Single linkage

> ii) Complete linkage

Visualization of the clusters obtained using these linkages and compare. 

### Single Linkage vs Complete Linkage

**Linkage criterion**: Single linkage measures the distance between the closest pair of points between two clusters, while complete linkage measures the distance between the farthest pair of points between two clusters. In contrast, Ward linkage measures the increase in sum of squared distances when merging two clusters. As a result, the three linkage criteria can result in different cluster shapes and sizes.
Sensitivity to outliers: Single linkage is sensitive to outliers, as a single point that is far away from the other points in a cluster can pull the entire cluster towards it. Complete linkage, on the other hand, is less sensitive to outliers as it considers the distance between the farthest pair of points. Ward linkage is less sensitive to outliers than single linkage but more sensitive than complete linkage.

**Number of clusters**: The number of clusters obtained using single and complete linkage can be different from the number of clusters obtained using Ward linkage. This is because single linkage tends to produce elongated clusters, while complete linkage tends to produce compact clusters. Ward linkage generally produces clusters of similar sizes and shapes.



## Part 3:

Implementation of kmeans to compress an image. In an original image each pixel has 3 8-bit integers, therefore the size of the image is **3 x height x width x 8**. 
Our task is to compress the image where it only comprises of **k** unique colors, where k = number of clusters formed by the algorithm where each pixel is a 3D datapoint.
Therefore the new compressed image can be stored in **k x 24 + width x height x b**. (b -> number of bits used to represent the integer *k*, since each pixel will have a color value from 0 to k-1). 
Now  task is to experiment with different values of k (atleast 3) and show the compressed image along with the value of data reduction (in terms of bits). 








