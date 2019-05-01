---
layout: post
mathjax: true
title: "Intro to Machine Learning II"
excerpt: "How can I Accurately Predict the Future? (pt.1)"
date: 2019-03-02
categories:
  - edu_bank
background-image: edu_imgs/ml.png
---

## <u>Validation:</u> Accurately predicting the future

The goal of Machine Learning is to build a model that best understands our problem. We want out model to be able to not just describe the data we have the best, but to also predict future values we get. A good mantra about ML captures this:

>Unlike classical mathematics and stats, ML is about reducing the error in _tomorrow’s_ data, no today’s. A model is only good if it can be generalized for future data and predictions.

But how can we figure out if our model predicts future data well when I don’t have future data? The answer lies in Validation.

**Validation** is the practice of splitting the data we have into subsets, training the model on one of those subsets, and testing the model on the other(s). The assumption here is that we can treat the unseen test set as future data, and therefore can see if our model is good at predicting on data it wasn’t trained on. And you don’t have to wait to collect future data to see if your model is effective!

There are a few forms of validation, but for now let’s look at the straight forward **Validation Set Approach**, where we randomly split the data into 2 separate subsets, a **training set** and a **test set**. As the names imply we train the model on the training set and test the model on the testing set.

Now that we have two data sets, we have two different errors: **training error** and **testing error**. Even with two error values, the goal is still to minimize error… this time minimize the error in two different datasets.

A model that has high training error and testing error is called **underfitting**—clearly the model isn’t a strong fit. A model that has low training error but high testing is called **overfitting**—the model only does well because it found some weird quirk with the training data (or simply "memorized" the data it was shown to pretend it was accurate) and won’t do very well with any other data. The next post will be all about how to combat overfitting.

### K-Fold Cross-Validation & LOOCV

Another form of validation is called **K-Fold Cross-Validation**, where you split the data into K equal subsets, called folds, and train K models on all subsets except 1. Then you pick the best model. In this way, you can train on 80-90% of data and actually get more consistently strong results than just using a one validation set.

You can also use **Leave-One-Out Cross-Validation (LOOCV)**, which is the same logic as K-Folds but you build training/test sets with all the data except one data point, which you use as the test set, and then train as many models as there are data points. While this is time consuming and computationally expensive, it will have the lowest _variance_, a term addressed in the next section.

Validation sets are great at helping you be more accurate in future predictions, but there are still some drawbacks. First, if your data isn’t large enough to accurately represent what future data will look like, your model may still perform poorly. Also, if you’re missing a few key variables in your model that actually matter to predictions, your model can at best overfit and at worst underfit—but will never learn to truly “understand” the data.

This section dealt with how to set up your data to help best predict the future. The next post will help you set up your learning process to help best predict the future.

**Recap**
1.	Machine Learning is about predicting the future as best as possible.
2.	Validation helps us feel more confident about our model's predictions by demonstrating if the model actually understands the data it is being shown
