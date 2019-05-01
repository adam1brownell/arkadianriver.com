---
layout: post
mathjax: true
title: "Intro to Machine Learning IV"
excerpt: "How can I Accurately Predict the Future? (pt.2)"
date: 2019-03-02
categories:
  - edu_bank
background-image: edu_imgs/ml.png
---

## <u>Accuracy:</u> Predicting the Future

In the first post we looked at linear regression, which fits a linear (straight) line to the data. This time around, we will explore logistic regression, which fits a funny looking line to the data:

      <logistic line>

**Logistic regression** outputs values between 0 and 1, which is really helpful when dealing with problems that have a yes/no answers—using the classic Silicon Valley example, classifying if a picture is a hot dog or not a hot dog.

Despite including the word “regression”, Logistic Regression is most often used for classification, where we use ML to determine which class an input belongs to. To find the link between linear and logistic regression, we have to do some basic math manipulation:

<center> 1. Odds of something happening:</center>

$$
 \frac{p(x)}{1-p(x)}
$$

<center> 2. Set this probability as what we want our line to model:</center>

$$
 \frac{p(x)}{1-p(x)} = B_0 + B_1x + ...
$$

<center> 3. Take the log of each side:</center>

$$
 log(\frac{p(x)}{1-p(x)}) = log(B_0 + B_1x + ...)
$$

$$
 p(x) = \frac{e^{B_0 + B_1x + ...}}{1 + e^{B_0 + B_1x + ...}}
$$

This transformation changes our straight line (linear regression) into our s-curve line (logistic regression)!

Logistic Regression outputs numbers between 0 and 1, with each extreme representing our two classes—in our case, hot dogs or not hot dogs. We want our model to output an answer as close as possible to it’s actual value, called the likelihood. **Probability**, a term people are more familiar with, describes future events _before_ data is available. **Likelihood**, on the other hand, fits parameters of a model _after_ data is available.
  - Probability: Before a coin flip, you could say, "The probability of flipping a heads in the future is..."
  - Likelihood: After a coin flip, you could say, "The likelihood that the previous flip was a head was..."

If we can predict the output correctly every time, the likelihood $$l(B_0,B_1)$$ would be equal to 1. With this in mind, we want to increase our likelihood as much as possible, which can be done by maximizing the **Likelihood Function**:

$$
\sum_{i=1}^n[y_iln(p(x_i)) + (1 - y_i)ln(1-p(x_i))]
$$

Yes, it's a scary formula at first. But don't panic! If you look at it long enough, you can see how this simple says:
 - sum up the probability of event ($$y_i$$) occurring TIMES
 - our guess at how likely it is to happen ($$ln(p(x_i))$$) PLUS
 - the probability of the event not happening ($$1-y_i$$) TIMES
 - our guess at how likely it is to _not_ happen ($$ln1 - (p(x_i))$$)

Which makes a lot of sense!

The $$R^2$$ value we used for linear regression unfortunately does not work for logistic regression, but we still want to be able to compare models to each other. So we can use **McFadden Pseudo R2** instead:

$$
R^2_{MCF} = 1 - \frac{ln(L_M)}{ln(L_0)}
$$

Where:
- $$L_M$$ is the likelihood of your models
- $$L_0$$ is the likelihood of a model built with only $$B_0$$ (the intercept)

\*This value doesn’t capture the variance explained by the model like regular R2, but rather the improvement in variance in comparison to our “Null Model” $$L_0$$

The hotdog classification problem is called **Binary Classification** since there are just two classes, but we can build a classification model for any number of classes

### Accuracy
 Accuracy is a lot harder to pin down than you may think. Imagine if of all the photos we have for our Hot Dog/Not Hot Dog model, only 20% of the photos are of hot dogs—which could definitively happen since there are a lot of foods that aren’t hot dogs. We tell our model to “maximize accuracy”, meaning to guess correctly about as many photos as possible. It COULD learn what a hot dog looks like and how its different from other foods…

… or it could just guess “not hot dog” for every single photo. If it did this, it would get an accuracy of ~80%, since 80% of the time it’s looking at not a hot dog. Even with a high accuracy score, our model could be a total dud. How can we make sure our model “knows” something? *

  \*I’m just going to avoid the controversial can of words that is “what is knowing” and just explain alternative accuracy metrics ok pls don’t yell at me

We can check accuracy of our model by setting thresholds that line up with our training data, and introducing a few new vocab words.

A **Threshold** is the arbitrary line we/our model draws on it’s predictions to decide whether to predict a 0 (not hot dog) or 1. Common sense says we should use 0.5 as a threshold, since that is how rounding typically woks, but you can change this number and change how accurate your model is.

Let’s draw our threshold at 0.5:

      <Log line with a threshold, with segments drawn for FN TP TN FP>

- A **True Positive (TP)** is when our model predicts Hot Dog and it is a Hot Dog
- A **False Positive (FP)** is when our model predicts Hot Dog and it is not a Hot Dog
- A **True Negative (TN)** is when our model predicts not Hot Dog and it is not a Hot Dog
- A **False Negative (FN)** is when our model predicts not Hot Dog and is a Hot Dog

    \*If you recall an intro stats class you've taken, FP is called Type 1 Error and FN is called Type 2 Error

We can describe our classification accuracy using a confusion matrix:

    <binary confusion matrix>

First, I would like to say that confusion matrix is an awesome term. A lot of times math and stats nerds don’t have a lot of creativity when it comes to names, but confusion matrix had a good PR person behind it.

The above confusion matrix is for a binary classification, but you can imagine more cells for more classes. The rows are the ground truth / actual answers, and the columns are predicted values. If you haven’t already noticed, the cells running diagonally from top left to bottom right represent when our model guessed correctly, and all the other cells are when our model was wrong.

**Accuracy**, as we normally think about it, is how many we got right over how many chances we got, or:

$$
Accuracy = \frac{TP + TN}{TP + TN + FP +FN}
$$

But there are other, more informative accuracy metrics. Let's use the previous example-- our model _only_ guesses Not Hot Dog, and since 80% of all the photos are not hot dogs, our accuracy is 80%. Not bad, right?

- **Recall**, also called **True Positive Rate (TPR)**, is our model’s ability to predict Hot Dog when it is actually a hot dog. Defined as $$\frac{TP}{TP + FN}$$. For our model that only guesses Not Hot Dog, this value would be 0%. Not great.

- **Precision** is our model’s ability to be right when it guessing Hot Dog—when it predicts hot dog, what are the chances it is actually a Hot dog? Defined as $$\frac{TP}{TP + FP}$$. For our dud model, this would also be 0%.

- **F1 Score** is an accuracy metric for the relationship between Precision and Recall, defined:

$$
F1 = 2 * \frac{Precision*Recall}{Precision + Recall}
$$

The reason we have multiple different accuracy metrics is because we may have different definitions of what “accuracy” means:

- Sometimes, we may want to maximize Recall—Imagine if we are the coast guard and deciding if we should close a beach because a shark may be nearby (Shark = 1, no Shark = 0). The consequences of closing the beach when there isn’t a shark (False Positive) is very small, maybe a few complaints. The consequences of keeping the beach open when there really is a shark (False Negative) could be very very bad

      <Jaws>

- 	Sometimes, we want to maximize Precision—Imagine if we are in charge of a large hedge fund deciding what to invest in. (Good investment = 1, Bad Investment = 0). The consequences of missing a few good investments (False Negative) is not as costly as spending a huge amount of money on a bad investment (False Positive).

These are more extreme cases, but I’m sure you can think up plenty of other examples. For those binary classification problems that fall somewhere in the middle, using F1 Score is a good metric to maximize.

Other accuracy metrics to consider:

- **Correct Rejection Rate**, also called **True Negative Rate (TNR)**, is our model’s ability to be right when it guessing Not Hot Dog: $$\frac{TN}{TN + FP}
- **False Alarm Rat**e, also called **False Positive Rate (FPR)**, is how often our model guesses Hot Dog incorrectly

When I say “you can maximize ___ accuracy metric” I mean that you can change the threshold of your classification model from the traditional 0.5 to some other number that increases that specific metric. Since each metric relies on increasing different metrics, each metric will have a different maximum threshold. The best/most thorough way to figure out the max threshold is to programmatically test every threshold and see which has the max value

We can also visual our binary classification accuracy with an **ROC Curve**. An ROC Curve models the TPR as FPR increases:

    <ROC Curve>

The higher the **area under the curve (AUC)** the better the model fit. An AUC of 1 is perfect, and an AUC of 0.5 means the model is just guessing (or has the same accuracy of someone randomly guessing)

### Recap
1. Logistic Regression can be used for binary classification
2. Accuracy is more than just guessing correctly, and depends on how you want to measure it
