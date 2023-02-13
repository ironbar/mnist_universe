# Artificial Intelligence

We have seen how a typical AI training looks like. We already have a trained model: is this model intelligent?

That model is performing some operation (classifying handwritten digits) that we do with our brains.
Thus the model is emulating a tiny process of our brain and we could say that it is somehow intelligent.

But in the other hand the model is just a mathematical function. It can only do a very specialized task.

## [On the Measure of Intelligence](https://arxiv.org/abs/1911.01547)

> The intelligence of a system is a measure of its skill-acquisition efficiency over a scope of tasks, with respect to priors, experience, and generalization difficulty.

Chollet takes away the focus on skill (how good a model is on Go, chess, image classification…) and puts the focus on skill-acquisition efficiency. It says that if a task is fixed it it possible to buy arbitrary levels of skill given unlimited priors or unlimited training data. It argues that training on more data does not make the system more intelligent.

> Adding ever more data to a local-generalization learning system is certainly a fair strategy if one’s end goal is skill on the task considered, but it will not lead to generalization beyond the data the system has seen

This seems true in the case of MNIST. If we extend the dataset by searching for more images for each category is very likely that we are going to improve the skill of the system but it won't be more intelligent.

However I'm not sure if this holds for Large Language Models. They are trained with a very general objetive: to predict the next word. It seems that to solve that task the model needs to develop many abilities. In the Palm paper they say that if they scale the model and the data they see emerging capabilities in the model. 

Thus according to the definition of Chollet a model trained on MNIST dataset is no intelligent. It does not have any adaptation capacity and it only knows to recognize digits. When presented with any other task it will completely fail.

## Generalization

Let's think if the model will generalize to new data.

### Color data

The model will likely work well with color images if they are previously transformed to gray scale. 

However it will likely fail when using images with white background (contrary to the black background seen during training)
We should use data augmentation if we expect to find inverted images on production.

*The model is only going to work well on data that has similar properties to the train set.*

### New symbols

It is very likely that the model will missclassify new symbols that were not present on the train dataset.
