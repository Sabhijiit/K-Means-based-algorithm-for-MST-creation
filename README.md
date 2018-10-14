# K-Means-based algorithm for MST creation

This project contains the code for "KMST+: A K-Means++-Based Minimum Spanning Tree Algorithm" implemented on a test dataset "drinking_fountains".

Link to the research paper: https://link.springer.com/chapter/10.1007/978-981-10-8968-8_10

The steps for the algorithm are as follows:

* Input: Graph of X;
* Output: Approximate MST of X;

1) Apply Divide and Conquer using K-Means++ on X to produce the K MSTs.
    * Divide step: Apply K-means++ to partition dataset of N points into √N clusters
    * Conquer step: Construct an MST for each subset separately using the Kruskal’s algorithm.
2)  Apply Combine Algorithm on the K MSTs to produce the first approximate MST, MST1, and the MST of subset centers, MSTcen.
3)  Apply Split-and-Merge on MSTcen and X to generate the secondary approximate MST, MST2. This is called the refinement stage.
4)  Merge MST1 and MST2 into a graph G.
5)  Apply an exact MST algorithm on G, and the final approximate MST is achieved.
