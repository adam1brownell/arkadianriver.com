---
layout: post
mathjax: true
title: "Intro to Machine Learning III"
excerpt: "How can I Prevent Overfitting?"
date: 2019-03-02
categories:
  - edu_bank
background-image: edu_imgs/ml.png
---

## <u>Regularization:</u> Fighting Overfitting

**Overfitting** is a Machine Learning engineer’s nightmare. It’s what keeps us up at night.

It’s when your model captures the noise in your data instead of what is actually important, and “learns” how to essentially replicate the data you have. This means that it performs really well when you’re training it, but horribly when you’re testing it.

How can I prevent this horrible thing from happening?!

To understand overfitting and the methods to combat it (**regularization**) we have to understand a few underlying principles

### Bias vs. Variance
**Bias** is how far our estimates are from the true value
**Variance** is the spread of our estimates

The best visual for this is a dartboard.

        <dart board visual>

You would have low bias if your shots were generally around bullseye, and high bias if they were centered around the edge of the board (or if you missed the board entirely)

You would have low variance if your shots were all in the same area, and high variance if they were all over the place.

In Machine Learning, a model with high bias would have coefficients that, on average, were very different from true coefficients. A model with high variance will have coefficients that are very sensitive to small changes in the data. Typically, the more complex the model, the lower the bias and the higher the variance.

For the model we just learned about in the first post, Linear regression guarantees low bias, since we optimize for the model that minimizes error, but does not guarantee low variance due to potential multicollinearity.

There are two ways to solve this variance problem in ML models:
- Subset Selection: Simplify our model using fewer variables
- Regularization: Shrink coefficient estimates

### Subset Selection
We can reduce variance by using fewer variables. This can be accomplished in a few different ways:

- **Forward Stepwise Selection**: We start with a model with 1 variable, and pick the one that the best $$R^2$$ statistic. Then we add another variable, and continue the until either we run out of variables or the $$R^2$$ does not increase (or doesn’t increase enough).

- **Backward Stepwise Selection**: We start with a model with every variable, and remove one variable at a time and pick the model with the best $$R^2$$ statistic. We continue this process until we end up with 1 variable or removing any variable greatly reduces the $$R^2$$ statistic.

While subset selection works, it is computationally slow—especially when building models that have thousands of variables. Most modern ML engineers use regularization instead.

### Regularization

We can also prevent overfitting by modifying the loss function itself—meaning that a model is only a stronger version if it can withstand penalties procured by regularization terms. The regularization methods mentioned below all contain λ, which controls the influence of the regularization term on the loss function; the higher the lambda value, the greater the effect. When λ= 0, the regularization term has no effect. When λ is too high, this can lead to severe underfitting since it has too large of an impact on the loss function.

**Ridge Regression** performs **L2 Regularization**, meaning that it penalizes a model for having very large coefficients:

$$
λ \sum_{j=1}^j \hat{B}^2_j
$$

Where:
- $$\hat{B}_j$$ is the coefficient of term j.

This is a valuable form of regularization because it ensures the model doesn’t rely completely on only a few features, and explores relationship found throughout the dataset. This results in a model that has many coefficients that are very small, but non that are zero.

**LASSO Method** performs **L1 Regularization**, meaning that it penalizes the number of number of coefficients used:

$$
λ \sum_{j=1}^j |\hat{B}_j|
$$

Where:
- $$\hat{B}_j$$ is the coefficient of term j.

This is a valuable form of regularization because it reduces the complexity of the model by removing unnecessary variables. This variable removal is done by setting unnecessary variable coefficient’s to 0.

**Elastic Net** is a mix of both L1 and L2 regularization, which provides the positives of both LASSO and Ridge regression.

### Recap
1. The Bias-Variance trade-off is key to understanding overfitting
2. Intelligently creating subsets of variables can help reduce overfitting
3. Adding a regularization term to your loss function can help systematically prevent overfitting
