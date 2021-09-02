# Data Science II - Machine Learning algorithms and techniques for Tabular data

Resources:

- Quick overview of ML: [Rémi Canard's Cheatsheet](https://remicnrd.github.io/the-machine-learning-cheatsheet/)
- Longer overview of ML (CS229 Cheat sheet): [Amidi's Cheatsheet](https://stanford.edu/~shervine/teaching/cs-229/)
- ML Course: [Stanford CS229](http://cs229.stanford.edu/) (aka Andrew Ng's Machine Learning course)
- ML "Bible": [Introduction to Statistical Learning](https://www.statlearning.com/)

General ML

- Describe a Machine Learning pipeline
- What's the difference between hypothesis, actual (observed) outputs, and predicted outputs?
- What does "linear" in linear models mean? How about non-linear?
- What is a Baseline model? Bayes error rate?
- Why do we need train-validation-test split? Is test set the same as validation set?
- When do we need (and not need) to normalize the data?
- How do we test/evaluate a model?
- What's the difference between loss function and evaluation metrics?
- Is "robust" the same as "not overfitting"?

Linear regression

- What's the equation (formulation) for linear regression? For 1 variable and multiple variables? For 1 sample and for several samples (a batch or dataset)?
- How do we optimize for linear regression?
- How do we include non-linear features in linear regression?
- How do we know which features are more important than others?
- L1 and L2 regularization

Logistic regression

- Compare Logistic regression and Linear regression
- What's the loss function used in Logistic regression? Can we use mean squared error (L2 loss) for logistic regression?

Naive-Bayes

- What is Naive-Bayes' formulation? What is the naive assumption?
- How do we optimize for Naive-Bayes

Support Vector Machine

- What are support vectors?
- How do we optimize for SVM?
- What's the difference between hard-margin and soft-margin SVM? Why do we need soft SVM?
- How do we make SVM learn non-linear features?
- How do we make SVM do regression?

Tree-based algorithms

- Decision tree, CART, Random forest

Boosting algorithms

- [XGBoost](https://xgboost.ai/)
- [CatBoost](https://catboost.ai/)
- [LightGBM](https://lightgbm.readthedocs.io/en/latest/)
