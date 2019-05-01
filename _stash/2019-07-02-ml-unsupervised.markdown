---
layout: post
mathjax: true
title: "Intro to Machine Learning V"
excerpt: "Can my Computer Learn on its Own?"
date: 2019-03-02
categories:
  - edu_bank
background-image: edu_imgs/ml.png
---

## <u>Unsupervised Learning</u> Computer learning for themselves

Most ML problems stem from one of these three methods:
	1. **Regression**: The search for a good model to explain the relationship between dependent and independent variables. We went over this in the first post in this series with the example of predicting house price given square footage and number of bedrooms.
	2. **Classification**: The search for a model that differentiates between 2 or more distinct classes. We went over this in our logistic regression post when deciding if a photo was of a hot dog or not.
	3. **Clustering**: Grouping together data points to represent the data

So far, we’ve looked at Regression and **Supervised Learning**, where we provide the model with the “truth,” so it can learn what variables respond to it. We've told the computer we are looking for pictures of hotdogs, and so it learned to find the difference between hot dogs and non-hot dogs. In this way, we provided the computer the labels it needed to learn the answer to the problem.

But Machine Learning allows us to also use **Unsupervised Learning**, where we provide a model with **unlabeled data**, data is only a collection of explanatory variables with no response variable.

Essentially, our model will investigate the data and figure out what’s important!

A good example of unsupervised learning is clustering. Let’s imagine we run a grocery store, and want to see what kinds of customers are coming in. Based on their purchases, can we group together similar people?

As you can see from how the problem is phrased we don’t know what the answer actually is. Unlike the housing price example, we couldn’t tell the model how many types of shopper there are, or what they would look like. This is exactly why we would rely on an unsupervised learning approach to solve this problem

One common clustering algorithm is called **K-Means Clustering**. This algorithm attempts to take the data and split it into K number of groups and builds these groups by minimizing the distance between points in the same group. You can visualize this by imaging points in 3D space, and the algorithms tries to group data points that are close to each other. We can say this mathematically:

$$
W(C_p) = \frac{1}{|C_p|}\sum_{j∈C_p}(\vec{x_i}-\vec{x_j})^2
$$

Which is a long hairy formula saying that:

_for each cluster Cp, minimize the mean squared distance between every point_

The algorithm starts out by randomly assigning every point and slowing building groups that have smaller and smaller distances (variance).

Very similarly we can use **K-Medoids Clustering**, which is the same thinking as K-means except we use median distance instead of mean.

Now, choosing K is oftentimes more Art than Science. There is no one agreed formula for picking it, so we have to rely on picking what makes sense for the problem. For our shopping example, does it make business sense to have only 2 types of shoppers? To have 10,000 shoppers? Here, we can play with K on a case by case basis.

If using our domain knowledge doesn’t answer what K should be, we can also use the **Elbow Method**, where we plot the $$R^2$$ value for every K and pick the K that is at the “elbow,” where the variance explained starts to flatten out as we increase the number of clusters. This is where the increase in explanatory power of each cluster diminishes. This is obviously a subjective measure.

    <Scree Plot for Elbow>

There are quite a lot of different methods used to strengthen/modify our clustering, like Hierarchical Clustering and Silhouette Coefficients, but these are honestly just modifications to the core concepts of clustering and unsupervised learning mentioned above. This post was simply to get a taste of what clustering is, and what sorts of problems can be solved with unsupervised learning.

### Recap
1. Clustering, like K-Means, is the process of grouping similar data points together
2. Unsupervised Learning is a way to have your computer find important patterns in unlabeled data
