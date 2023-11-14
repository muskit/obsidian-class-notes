# Clustering
or **categorizing/grouping data**
- the process will typically group objects that are **similar**
- how clustering is done will generally be subjective
- *cluster* - a group

Our goal is to find clusters that have...
- high intra-cluster similarity: degree of closeness of objs in the same cluster
- low inter-cluster similarity: similarity between different clusters

Clusters are used to...
- help marketers discover distinct groups for targeted ads
- identify areas of similar land use
- identify groups of houses by type, value, location, etc.

## Measuring similarity
The "distance" (dissimilarity) between two objects $A$ and $B$ is denoted by $D(A,B)$
- lower = more similar

Literal distance between 2 points can be used

**Properties of $D(A,B)$**  
Symmetry
- $D(A,B) = D(B,A)$
Constancy of Self-Similarity
- $D(A,A)=0$
Positivity (Separation)
- $D(A,B)=0\ \text{if}\ A=B$
Triangular Inequality
- $\text{if}\ A \leq B \leq C\ \text{, then}\ D(A,B) \leq D(A,C) + D(B,C)$

## Approaching Clustering
**Centroid-based**  
- K-Means: partition into $k$ distinct clusters based on **distance to the centroid of a cluster**
**Connectivity-based**  
- build **nested** clusters

### Hard & Soft Clustering
Hard
- a data item belongs to **exactly one** cluster
- more common, easier
Soft
- a data item can belong to multiple clusters
- ie. sneakers is both *shoes* and *sports apparel*

### Dendogram
a **bottom-up** approach for nested clustering
- start with an object, work our way up to progressively abstract and classify it
- ie. animal/plant classification

### K-means clustering
1. Determine $k$ (number of clusters)
2. Initialize centroid points (likely randomly)
3. Calculate distances btwn points and centroids, adjust centroid points as needed
4. Adjust centroids to be the **center** of given clusters by re-partitioning data points
5. Repeat 2-4 until **convergence** is achieved, where
	- centroid points don't change significantly
	- data points cannot be moved in re-partitioning