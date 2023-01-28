# Data

The model sees pairs of images and labels during training. For example it receives an image of a handwritten 0 and a label indicating that it is a 0.

Thus the model only has access to a very limited subset of the universe. It does not have access to letters, animals, sounds...
Also the images are grayscale, the numbers are centered... The dataset has many particular characteristics that will influence how
well the model generalizes to new data.

Also the model will not experience any **notion of time**. When a human is learning the numbers there is a time continuity on the senses inputs. 
By contrary the inputs to the model change randomly: there is no relation between the image the model receives at one step and the next.

In general a dataset is a biased and partial subset of the real world. A model trained on a dataset will learn the particularities of the dataset and because of that the performance of the model will be lower when being evaluated on a dataset with different biases.

## Real data is noisy

In an ideal world all the samples in a dataset will have correct labels. That is hardly the case in
the real world. It is likely that even the famous MNIST dataset has wrong labels: for example an image
of a one labelled as a seven.

This can happen both for human errors or for ambiguity in the definition of the problem. If the handwriting
is not clear we could misclassify a seven by a one, or a nine by a four.

A model with enough capacity trained on noisy data could achieve perfect accuracy by memorizing the errors.
This makes the learning process harder because there are contradictions in the dataset. In those cases
taking time to clean the dataset will usually pay off. There is a data-centric movement championed by Andrew Ng
that places the focus on the data instead of the model.
