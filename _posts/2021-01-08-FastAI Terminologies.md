For this post, I thought it'll be nice to collate dictionary of common terms in AI that I'll probably use in the future (and forget). I had quite a bit of trouble remembering what each term means. Hopefully this  will be useful for anyone that is trying to learn AI. 

## Common Terms
| acronym        |actual term | explanation   |      
|:------------- |:-------------|:-------------|
|dls |dataloaders| fastAI's module to split datasets into mini-batches. gradient is updated after every batch (rather than every epoch)|
|ds  |dataset| tuple of inputs and labels |
|bs | batch size| size of each mini-batch|
|lr | learning rate| size of each step to update the parameters after each mini-batch|
|loss function| | a function to calculate a value of how well/badly the model is doing (*varies with every mini-batch*). *eg. CrossEntropy for classification, RMSE for regression*|
|L1 norm| mean absolute difference| fancy term for taking the mean of the *absolute value* of differences|
|L2 norm| root mean squared error/RMSE| fancy term for taking the mean of the *square* of differences and then take the *square root*|
|metric | | another function to calculate a value of how well/badly the model is doing **on the validation set** (*may not vary with every mini-batch*), *eg accuracy/precision/recall for classification, RMSE for regression*|
> difference between loss function and metric: loss function is sensitive to minute changes. Therefore, it is the function we use to calculate gradient. However, at the end of the day, the metric is what we are looking out for (practical significance).

## Deep Learning Models
| acronym        |actual term | explanation   |      
|:------------- |:-------------|:-------------|
|CNN | convolutional neural network| a type of neural network that works particularly well for computer vision tasks|
|RNN| recurrent neural network| a type of neural network that works particularly well for natural language processing tasks|
|collaborative filtering| |a type of neural network that works particularly well for tablular data|

## Neural Network Vocab
| acronym        |actual term | explanation   |      
|:------------- |:-------------|:-------------|
|epoch| | one complete pass through the training data|
|transfer learning| |using a pretrained model as the base, and training for a few more epochs to solve a ML problem that is new to the pretrained model|
|activations|| numbers that are calculated (both by linear and nonlinear layers)|
|parameters|| numbers that are randomly initialized, and optimized (that is, the numbers that define the model)|
|GD | gradient descent| taking a step in the directions **opposite** to the graidents to make the model more accurate|
|SGD | stochastic gradient descent| GD but taking a step after every mini-batch instead of every epoch. The pro is that weights can be updated more frequently, especially if the dataset is huge|
|nonlinearity| | something that helps to add complexity to the model to help it generalise for any tasks(*as proposed in the **universal approximation theorem** *)
|activation function| |a function in the final layer that returns the dependent variables as values between 0-1. *eg. sigmoid for binary classification, softmax is the multi-category equivalent of sigmoid*|
|y_range| |the range of values of the dependent variable (*applicable to regression problems*)|
|vocab| |list of all the possible levels of dependent variable (*applicable to classification problems*)|
|tensor| | fancy term for arrays of differet dimensions |
|ReLU | rectified linear unit | fancy term for a nonlinearity function that returns 0 for negative numbers and unchaged for postive numbers |
>There are other nonlinearities other than ReLU, such as leaky ReLU, but that is not a parameter to change on the model to model basis


## Tabular Model Vocab
|term | explanation   |      
|:-------------|:-------------|
|latent factors|factors that are hidden in the data that affect the dependent variable|
|embedding|fancy term for the computational shortcut for doing matrix multiplication without a one-hot encoded matrix|
> Note: due to the nature of tabular data, often times, ensembling techniques such as random forest works equally well. Better yet, try combining random forest with a neural network!

## RNN Model Vocab
|actual term | explanation   |      
|:-------------|:-------------|
|self-supervised learning| training a model using labels that are embedded in the independent variable, rather than requiring external labels. For instance, training a model to predict the next word in a text|
|corpus| all the words in the dataset|
|tokenization| convert dataset into list of words/characters/substrings aka vocab|
|numericalisation| convert each word in the vocab into a number corresponding to it's index|

## Fine-tuning Vocab
| acronym        |actual term | explanation   |      
|:------------- |:-------------|:-------------|
|mixed-precision training| | used less precise floating point numbers to speed up training and require less memory|
|normalise| |helps with the training process. Transforms variables into values with mean of 0 and a standard deviation of 1. Normalization becomes especially important when using pretrained models|
|lr_finder| learning rate finder| super handy tool for finding the optimal learning rate instead of randomly trying different learning rates|
|fit_one_cycle||different layers of the model are trained with different learning rates|
|progressive resizing| | gradually using larger and larger images as you train|
|tta | test time augmentation | during inference or validation, creating multiple versions of each image, using data augmentation, and then taking the average or maximum of the predictions for each augmented version of the image. *Note:  It does not change the time required to train at all, but will increase the amount of time required for validation or inference by the number of test-time-augmented images requested*|
|cbs|callbacks|callbacks are used in fastai to inject custom behavior in the training loop (like a learning rate schedule, or training in mixed precision)|
|L2 regularization/wd | weight decay | fancy term for adding the sum of all the weights square to your loss function. It encourage the weights to be as small as possible|
|mixup||creating new data by overlaying different proortions of existing data on top of each other. Useful when you don't have much data and don't have a pretrained model that was trained on data similar to your dataset. Can be extended to NLP models too|
|label smoothing||multi-category classification: replace all our 1s with a number a bit less than 1, and our 0s by a number a bit more than 0, and then train. By encouraging your model to be less confident, label smoothing will make your training more robust, even if there is mislabeled data.|
> mixup and label smoothing often requires more epochs to see significant improvements.

That's alot of terms. I think I'll call it a day.
