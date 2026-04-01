---
layout: page
title: Naive Bayes
permalink: /naive_bayes/
---

<p style="text-align: justify;">
Naive Bayes is a classification model which assigns probabilities to data points which measure the likelihood of that data point belonging to a particular class. This model is based on the conditional probability formula or 'Bayes Theorem' which calculates the probability of a certain event given another related event is seen to be true. An example of this would be: what is the probability of it raining today given there are clouds in the sky. What naive means in this case is that the model is assuming that all features are independent of one another which drastically simplifies the computations necessary to assign probabilities, but the trade off is that by relying on this assumption, you have to ensure that there are not highly correlated or dependent features in the dataset. This model is typically used for spam message detection and sentiment analysis and there are several different variations which allow for a broad range of applications. For instance: Guassian NB is used for continuous numerical data and also relies on the assumption that the data is normally distributed, and Multinomial NB is more suited for discrete count based data. Additionally, there is also the Bernoulli NB which is used for binary features and Categorical NB which is used for discrete non binary categories. 
</p>

<p style="text-align: justify;">
In the case of this project where a majority of the data is continuous, it would be most appropriate to apply Guassian NB, but there may be applications for the other types. This process is just about exploring multiple different methods and comparing/contrasting the performance of them all in order to find the best fit.
</p>

---
## Data Prep

All models and methods require specific data formats. Supervised modeling requires first that you have labeled data. Next, it requires that you split your data into a Training Set (to train/build) the model, and a Testing Set to test the accuracy of your model.  Prepare data for Naïve Bayes analyses. You must code and run multinomial Naive Bayes. In addition, choose any two other different Naive Bayes flavors (such as Bernoullli, categorical, etc.)   (LINK to data you prepare) Include screen images of the dataframes you plan to use. Remember, you may have different dataframe data types depending on the flavor of NB you choose. Be clear and transparent.  Also include information and a small image of the Training Set and Testing sets and why they are (and must be) disjoint.

---
## Code
<p align="center">
  <strong>
    <a href="https://github.com/maxjwhite/csci5612ML-NBACode">NB Script</a>
    &nbsp;|&nbsp;
    <a href="https://github.com/swar/nba_api">Link to Data</a>
  </strong>
</p>

---
## Results
Creatively and clearly discuss, compare, illustrate, describe, and visualize the results. Include confusion matrices and the accuracies. 

---
## Conclusions
What did you learn (and/or what can you predict here) that pertains to your topic?
