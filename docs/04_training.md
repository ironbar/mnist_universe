# Training

Artificial neural networks are typically trained using the gradient descent algorithm. This algorithm
modifies the model iteratively to minimize a loss function by computing the gradient of the loss
function and propagating it through the neural network.

The neural network and the loss function need to be differentiable if we want to use the gradient
descent algorithm. On the MNIST dataset we might be interested in maximizing the accuracy of the
model. However the accuracy function is not differentiable. So we have to use a proxy loss function
called cross-entropy loss with the hope that minimizing the cross-entropy loss will result in an increase
of the model accuracy.

This process is no different from function optimization. So what makes Deep Learning special?

- Deep Learning scales well with model size and dataset size. We can get better models just by training
  a bigger model on a bigger dataset.
- Deep Learning imposes some constraints in the model: the model should have multiple sequential layers. This imposes a bias towards hierarchical processing
- Deep Learning has benefited from the increase of computing power and the increase in dataset sizes

## How similar is this to human learning?

When humans are born they already have some innate capabilities. For example newborns have walking reflexes. In the other hand artificial neural networks are completely random at initialization, they have some inductive bias built in but no knowledge.

When a baby grows it learns in a completely unsupervised way. It learns to crawl, walk and talk just by trial and error and imitation. 

When a child learns to talk and understands language it starts to receive a much informative reward signal from his parents. 

We as humans experience time as it passes and we have memories. The typical NN do not have any notion of time nor memories. 

A child can interact with the world, this allows to test hypothesis and learn causality. However it seems that from data alone
is not possible to infer causality[^1].

[^1]: https://stats.stackexchange.com/questions/384330/is-causal-inference-only-from-data-possible
