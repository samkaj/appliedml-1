# Programming assigment 1

Group 5: Samuel Kajava and Torbjörn Livén

## Task 1

When running the classifiers inlcuded in the examples from the assignment description, gradient boosting performed best of the bunch. We concluded this by comparing the aggregated results from each classifier.

To explain the gradient boosting classifier, we first discuss the concept of gradient boosting. Boosting is a method where you train a model several times while iteratively trying to correct the previous iteration. This process is described as a way of combining weak learners into strong ones [[1]](https://en.wikipedia.org/wiki/Boosting_(machine_learning)). Gradient boosting utilizes this concept by training each model to minmize the loss function first, followed by training a new model to minimize the gradient. This process successively adds predicitions to the ensemble. These predictions are done by regression trees and return the final predictions once the `criterion` hyperparameter is met. In our case, we used the default `friedman_mse` which measures the quality of the iteration by looking at "the mean squared error with improvement score by Friedman" [[2]](https://scikit-learn.org/stable/modules/generated/sklearn.ensemble.GradientBoostingClassifier.html).

## Task 2

After trying out some different max-depths, the best one we got was a max-depth of 7, with an accuracy of `0.9178403755868545`.

For the tree visualization, a max-depth of 3 was selected.
![image](./task2.svg)

<p align='center'>
<b>Fig:</b> Decision tree produced by Graphviz with <code>max_depth=3</code>.
</p>

## Task 3

The regression model we chose and got the best score with, was the MLPRegressor. Which after some fine-tuning achieved a negative mse of `-0.0006478530592890497`.
The hyperparameters we set were: 
`learning_rate_init=0.03`
`max_iter=15000`
`hidden_layer_size=(200,10)`
we also set `early_stopping=True`

## Task 4

Considering the data generating function we want a regression tree to predict the output from the input. We dont want to simply classify
the data into two classes, we want a value.


Nothing happens if we give it a bigger depth, the graph is only 1 node deep. 
We trained a tree regression model with `max_depth=6` and achieved a negative mse of `-0.2806332424585957`
 In the plot, we can see that the model is overfitting on the training set. The evalutation on the test set keeps improving until
around `max_depth=6`, then the evaluation score really starts to diverge and we can see that it overfits on the training data because it gets better at the training set, but worse on the test set.
![training vs testing](task4.png)