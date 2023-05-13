# Machine Learning techniques

## Regularization

Regularization techniques impose some inductive bias to the models. We apply some priors with the believe that they will guide the model to find a simpler solution that will generalize better

- L1 regularization induces sparsity in the model, drives some of the weights to be zero
- L2 regularization favours smaller weights over big weights
- Dropout forces the model to be able to work with dead neurons. This favours the learning of robust features.

## Early stopping

When using early stopping we will stop the training if the validation loss does not improve. It's a simple way to avoid overfitting to the train set.
