---
layout: post
title:      "No free lunch: Logistic Regression vs. Random Forest"
date:       2020-12-02 19:05:12 +0000
permalink:  no_free_lunch_logistic_regression_vs_random_forest
---


In Data Science, there is the no-free-lunch theorem for supervised algorithms: no one algorithm is the go-to optimal performer; if one algorithm outperforms another in one metric, it will lose in another. When it comes to using Logistic Regression or Random Forest to perform classification, this is very much the case. Therefore, one is better off selecting the optimal algorithm based on their unique circumstances. Below I explain both algorithms and their respective advantages and disadvatages so you can come to your own conclusion on which would be most fitting for your data science problem.

**Random Forest:**
* Random forest is a learning algorithm which is ensemble-based, meaning it learns from a collection of uncorrelated decision trees
* It is built off of bootstrap data, which is resampled with replacement to reduce variance 
* The root or top node corresponds to the best predictor variable 
* The top node is recursively split at a series of decision nodes, until the terminal decision node is reached
* At each decision node, the features are split into two branches and this process is repeated until the leaf nodes are reached, which is used to make the final prediction
* To determine which feature to split on at each node, entropy - which measures the homogeneity of the subset data - is computed, where if the split results in the labels being all the same (either all 1's or all 0's), then entropy = zero; otherwise, if the labels are heterogeneous, entropy = 1
* The difference between the entropy prior to the split (e.g. parent node) and after the split (e.g. child node) is performed on each feature and the one which yields the highest difference in entropies is the most useful in segmenting the class labels by providing the greatest information gain (a method for quantifying how important an input attribute in the model is)
* To make regression predictions, the terminal leaf nodes of multiple trees are averaged, and for classification predictions, the majority of votes is used

**RFC Advantages**
* It reduces overfitting in decision trees and helps improve accuracy
* It is flexible for both classification and regression problems
* It works well with both categorical and continuous values

**RFC Disadvantages**
* It requires a lot of computational power and resources as it builds numerous trees to combine their outputs 
* It requires a lot of time for training as it combines a lot of decision trees to determine the class
* Due to the ensemble of decision trees, it also suffers interpretability and fails to determine the significance of each variable


**Logistic Regression:**
* Logistic regression makes assumptions such as independence, normal distribution and constant variance between the features and target
* A logistic transformation is applied to the target to yield a continuous probability distribution between 0 and 1 (this is the log of the odds of being classified in the ith group of a binary or multi-class response)
* The model observes whether a 1 unit +/- in a feature yields a +/- in the predicted log odds of the target, while holding all other features constant
* The objective is to use gradient descent optimization to find a set of feature weights where the log loss is minimized, and you approach 1 for the probability of being close to the actual value
* The user can choose how the features are weighted to emphasize those with a more significant predicting ability 

**LR Advantages:**
* Logistic regression is easy to implement, interpret, and very efficient to train
* It can easily extend to multiple classes (multinomial regression) 
* It can interpret model coefficients as indicators of feature importance

**LR Disadvantages:**
* Logistic Regression requires average or no multicollinearity between independent variables
* If the number of observations is lesser than the number of features, Logistic Regression should not be used, otherwise, it may lead to overfitting
* It assumed linearity between the dependent variable and the independent variables; non-linear problems can’t be solved with logistic regression because it has a linear decision surface. Linearly separable data is rarely found in real-world scenarios



