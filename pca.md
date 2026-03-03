---
layout: page
title: PCA
permalink: /pca/
---
<p style="text-align: justify;">
Principal Component Analysis (PCA) is a dimensionality reduction technique that transforms a large set of possibly correlated variables into a smaller set of uncorrelated components that capture most of the variation in the data. Instead of analyzing dozens of overlapping team statistics—such as points per game, field goal percentage, pace, turnovers, and defensive rating—PCA identifies underlying directions (principal components) that summarize the dominant patterns across those metrics. In the context of our NBA dataset, PCA helps simplify complex team performance profiles into a few interpretable dimensions, such as overall offensive strength or defensive efficiency, while retaining the majority of the information contained in the original variables. This makes it easier to visualize team differences, reduce noise before clustering, and understand which combinations of statistics explain the largest variation between teams and seasons.
</p>

## Cleaned Data for PCA
![PCA Clean Data](image/pca_clean.png)

Note that the nba team name feature gets dropped before performing PCA, this was just to double check that my preprocessing was behaving as expected and a general overview of the full dataset that this script was working with.

<p align="center">
  <strong>
    <a href="https://github.com/maxjwhite/csci5612ML-NBACode">PCA Script</a>
    &nbsp;|&nbsp;
    <a href="https://github.com/swar/nba_api">Link to Data</a>
  </strong>
</p>

---
## Visualizations

![2d](image/pca_2d.png)

![3d](image/pca_3d.png)

---
## Results

* How much information (what percentage ) remains in the 2D dataset. : **75.54%**  
![2d](image/pca_2d_var.png)

* How much information (what percentage ) remains in the 3D dataset. : **86.93%**  
![2d](image/pca_3d_var.png)

* How many dimensions do you need to have in your dataset (after using PCA) to retain at least 95% of the data. : **5 dimensions**

<p style="text-align: justify;">
In order to find this, we have to keep adding features in descending order of importance until we reach 95% of the variance retained. This requires some trial and error as well as first visualizing the importance of all of our principal components in order.
</p>

![2d](image/pca_num95.png)

* What are the top three eigenvalues of your data?  
![2d](image/pca_eigenvals.png)

<p style="text-align: justify;">
PCA allows for a reduction in our dimensionality whilst still preserving a majority of the variance within the dataset. By compiling our features in to our primary 3 principal components, we are able to retain a majority of the shape and clustering of our dataset. These reductions help us identify where strong performing NBA teams cluster without having to consider every single possible statistic in our dataset. Notice how with only 3 principal components, we are still able to explain 86.93% of the varaiation within out dataset, which means we can draw fairly accurate inferences in terms of the clustering of these principal components. These methods in turn help identify important features for further clustering methods which will supplement our findings above.
</p>

---

