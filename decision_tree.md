---
layout: page
title: Decision Tree
permalink: /decision_tree/
---

<img src="{{ site.baseurl }}/image/dt.png"
     alt="Wide-angle view of a professional basketball game"
     style="float: right; width: 45%; margin: 0 0 20px 25px; border-radius: 10px;">
<p style="text-align: justify;">
Decision Trees (DT) is a type of supervised learning model used for classification and regression. Supervised learning simply means that when we train our models, there are labels attached to the data which are essentially targets or classifications. These models work by breaking the data into subsets based on certain features where each break essentially becomes a new branch and each branch end becomes a node or leaf, making up a decision tree. A brief example using data on clothes: first split breaks into tops and bottoms, each leaf of this (top / bottom) then breaks again into (short / long). This simple tree now classifies clothes from unlabaled objects into short sleeve, long sleeve, shorts, and pants. But how does the model determine where these splits are made? 
</p>


<img src="{{ site.baseurl }}/image/dt_pure.png"
     alt="Wide-angle view of a professional basketball game"
     style="float: left; width: 45%; margin: 0 0 20px 25px; border-radius: 10px;">
<p style="text-align: justify;">
In order to make the best splits in the data, DTs use purity scores such as Gini and Entropy, which measure how mixed the classes are within each node. For example, the top node might contain four classes: t-shirt, sweater, tank top, and hoodie. Each possible split is evaluated using Information Gain, which calculates how much the split reduces uncertainty or disorder in the node. The split that maximizes Information Gain is chosen, creating child nodes that are more “pure” and better separated by class. Decision Trees can theoretically grow infinitely because you can continue splitting nodes or pick new thresholds for continuous features, producing countless possible tree structures. In practice, constraints like maximum depth, minimum samples per leaf, or pruning are applied to prevent overfitting and ensure the tree generalizes well to new data.
</p>

---
## Data Prep
(b) Data Prep. Prepare data for use with decision tree modeling. LINK to the sample of data. Also include information and a small image of the Training Set and Testing set and explain how you created them and why they are (and must be) disjoint. It is fine to use (and link to) the same data that you used from multinomial Naive Bayes above. 

---
## Code
<p align="center">
  <strong>
    <a href="https://github.com/maxjwhite/csci5612ML-NBACode">Decision Tree Script</a>
    &nbsp;|&nbsp;
    <a href="https://github.com/swar/nba_api">Link to Data</a>
  </strong>
</p>

---
## Results
(d) Results. Discuss, illustrate, describe, and visualize the results. Include the confusion matrix and the accuracy. Create and include at least three different trees with difference root nodes (you think about how to do this) and other difference (up to you). 

---
# Conclusions
(e) Conclusions. What did you learn (and/or what can you predict here) that pertains to your topic?
