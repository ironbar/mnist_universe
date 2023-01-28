# Model

An artificial neural network is just a parametric mathematical function. It receives some numbers as input and returns other numbers as input depending on the parameters of the function, which are typically called weights in the case of a neural network.

In the case for the MNIST dataset the model will receive as input the value of the pixels of the images, and it will output a 10d vector representing the probability of the image being any of the digits from 0 to 9.

The neural networks are typically structure in layers. Each layer has its own set of operations and parameters. Thus a neural network is a mathematical function that is created by composing smaller functions that we called layers.

TODO: add latex code showing composition of functions/layers

The space of all the possible neural networks is infinite.

The choice of the type of layers, numbers and connectivity between the layers is called the model architecture.
Through trial and error the AI community has found certain architectures that work well for some specific problems. For example there are architectures that work well for image classification, others work well for time-series prediction... (Although there is a recent trend where it seems that the Transformer architecture is taking over all the applications)

When we choose an architecture we are imposing some biases into the model. Those biases limit the capacity and expressivity of the model but if carefully chosen they will help the model to generalize better. For example convolutional layers apply the same filter over the whole image on a sliding window fashion. This bias implies that the position on a image won't be relevant to classify that object which makes sense.
In theory if we had an infinite stream of data we will let an unbiased model to learn the structure of the data without constraints. We will do this because bias can guide the learning process in a limited set of data, but they also impose limits on the model performance (because there is almost always an exception to each rule)
