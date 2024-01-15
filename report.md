# Programming assigment 1

Group 5: Samuel Kajava and Torbjörn Livén

## Task 1

When running the classifiers inlcuded in the examples from the assignment description, gradient boosting performed best of the bunch. We concluded this by comparing the aggregated results from each classifier.

To explain the gradient boosting classifier, we first discuss the concept of gradient boosting. Boosting is a method where you train a model several times while iteratively trying to correct the previous iteration. This process is described as a way of combining weak learners into strong ones [[1]](https://en.wikipedia.org/wiki/Boosting_(machine_learning)). Gradient boosting utilizes this concept by training each model to minmize the loss function first, followed by training a new model to minimize the gradient. This process successively adds predicitions to the ensemble. These predictions are done by regression trees and return the final predictions once the `criterion` hyperparameter is met. In our case, we used the default `friedman_mse` which measures the quality of the iteration by looking at "the mean squared error with improvement score by Friedman" [[2]](https://scikit-learn.org/stable/modules/generated/sklearn.ensemble.GradientBoostingClassifier.html).
