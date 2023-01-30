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
- Deep Learning imposes some constraints in the model: the model should have multiple sequential layers
- Deep Learning has benefited from the increase of computing power and the increase in dataset sizes
