# Data

The model sees pairs of images and labels during training. For example it receives an image of a handwritten 0 and a label indicating that it is a 0.

Thus the model only has access to a very limited subset of the universe. It does not have access to letters, animals, sounds...  
The dataset has many particular characteristics that will influence how well the model generalizes to new data. For example the images are grayscale, the numbers are centered...

Also the model will not experience any **notion of time**. When a human is learning the numbers there is a time continuity on the senses inputs. If I see some numbers on a book those numbers won't change. I will be able
to see them from different perspectives, distances and orientations.  
By contrary the inputs to the model change randomly: there is no relation between the image the model receives at one step and the next.

In general a dataset is a biased and partial subset of the real world. A model trained on a dataset will learn the particularities of the dataset and because of that the performance of the model will be lower when being evaluated on a different dataset (with different biases).

## Train, validation and test data

It is very common on machine learnig to partition the data on three disjoint subsets that are called train, validation and test.

- **train**: this is the data that the model will use to "learn", to fit its parameters. We can evaluate the model
  on this train data but this evaluation will have a very weak relation to the performance of the model with new data.
  Neural network models can have an arbitrary capacity and are able to memorize the train set and achieve a perfect score.
- **validation**: while training or at the end of the train we will evaluate our model on the validation data. This evaluation
  will be a more faithfull representation of how the model works with new data. We can use the validation score to guide the
  optimization of the hyperparameters of the model. However since we are doing multiple evaluations on the validation set there
  is information flowing to the model and we could not trust the validation score after many evaluations.
- **test**: when we have optimized the model using the validation scores then we could use the test to have a real estimation of how
  the model will work with new data.
  
This process has some similarities to how a student prepares for a exam. The training set would be the books, video and other learning resources. The validation set would be exams from previous years. The real exam of that year would be the test set.
If the student does a previous years' exam more than one time the score obtained on the following evaluations won't be a good estimator of the score on the real exam.

## Real data is noisy

In an ideal world all the samples in a dataset will have correct labels. That is hardly the case in
the real world. It is likely that even the famous MNIST dataset has wrong labels[^1]: for example an image
of a one labelled as a seven.

This can happen both for human errors or for ambiguity in the definition of the problem. If the handwriting
is not clear we could misclassify a seven by a one, or a nine by a four.

A model with enough capacity trained on noisy data could achieve perfect accuracy by memorizing the errors.
This makes the learning process harder because there are contradictions in the dataset. In those cases
taking time to clean the dataset will usually pay off. There is a data-centric movement championed by Andrew Ng
that places the focus on the data instead of the model.

[^1]: Even the MNIST dataset, assumed to be error-free and benchmarked in tens of thousands of peer-reviewed ML publications, contains 15 (human-validated) label errors in the test set. [https://l7.curtisnorthcutt.com/label-errors](https://l7.curtisnorthcutt.com/label-errors)
