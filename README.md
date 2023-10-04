# Project Name
> Melanoma Detection Using CNN


## Table of Contents
* [General Info](#general-information)
* [Conclusions](#conclusions)
* [Technologies Used](#technologies-used)

<!-- You can include any other section that is pertinent to your problem -->

## General Information
- Project: Melanoma Detection To build a CNN based model which can accurately detect melanoma. Melanoma is a type of cancer that can be deadly if not detected early. It accounts for 75% of skin cancer deaths. A solution that can evaluate images and alert dermatologists about the presence of melanoma has the potential to reduce a lot of manual effort needed in diagnosis.

- The dataset consists of 2357 images of malignant and benign oncological diseases, which were formed from the International Skin Imaging Collaboration (ISIC). All images were sorted according to the classification taken with ISIC, and all subsets were divided into the same number of images, with the exception of melanomas and moles, whose images are slightly dominant.

The data set contains the following diseases:

- Actinic keratosis 
- Basal cell carcinoma 
- Dermatofibroma 
- Melanoma 
- Nevus 
- Pigmented benign keratosis 
- Seborrheic keratosis 
- Squamous cell carcinoma 
- Vascular lesion


<!-- You don't have to answer all the questions - just the ones relevant to your project. -->

## Conclusions
### The first Model

- The input to the network is an image of dimensions (180, 180, 3). The first two layers have 32 channels of a 3*3 filter size and the same padding.

- Then after a max pool layer of stride (2, 2),

- Then a convolution layer of 32 filter size and filter size (3, 3). This is followed by a max-pooling layer of stride (2, 2)

- Then a convolution layer of filter size (3, 3) and 64 filters.This is followed by a max-pooling layer of stride (2, 2)

- Then a convolution layer of filter size (3, 3) and 64 filters.This is followed by a max-pooling layer of stride (2, 2)

- Then We flatten this output. After this there is a fully connected layer. fully connected layer is used to implement softmax function to classify 9 classes. All the hidden layers use ReLU as its activation function. ReLU is more computationally efficient because it results in faster learning and it also decreases the likelihood of vanishing gradient problems.

#### Key Observations:
*   The training and validation accuracy are 66% and  50% respectively. Validation accuracy is much lesser than training accuracy.
*   The difference in training and validation accuracy shows the clear case of model overfitting.
*   The training accuracy increases with increase in epochs.
*   The validation accuracy is stable at first and decreases with increase in epochs.
*   The Validation loss follows the training loss around 10 epochs and then validation loss increases and training loss further decreases with number of epochs.

### Model Revision with Data Augmentation:

- Problem Identification Uneven dataset: The training dataset the distribution of image are uneven. seborrheic keratosis:77; squamous cell carcinoma:181; vascular lesion:139; actinic keratosis:114. The samples in above cases are very less in comparison to the other cases. So we need to increase the samples in each case. we attempt to use **DATA AUGMENTATION** tecbhnique

### After Data Augmentation:

#### Key Observations:

* The training accuracy and validation accuracy are almost equal. They follow similar trends, Although the training accuracy 52% and validation accuracy 51% has decreased. The problem of overfitting has been addressed with data augmentation as both accuracies almost follow each other.

But we have the decreased accuracies which needs to be addressed.

### With Model Augmentor

This is the final model created by adding more images. 500+ images to each dataset. With Augmentor we increased the number of samples by 500 in each of the classes. This make the difference in ratio less and between each each class.

#### Final Model Observations:

* The accuracy of test set is 90%
* Accuracy of validation dats set is 84%
* Here we went for some extra epochs to try if the model gets improved. But,  the model tends to increase the overfitting once we have extra epochs.
* The model with the above accuracy shows an increased performace of the model when we get a class balanced training data.
* As we can see from the model performace on the augmented data.

<!-- You don't have to answer all the questions - just the ones relevant to your project. -->


## Technologies Used
- Google Colab
- Python
- Tensorflow

<!-- As the libraries versions keep on changing, it is recommended to mention the version of library used in this project -->

## Contact
Created by [@vkarkera] - feel free to contact me!


<!-- Optional -->
<!-- ## License -->
<!-- This project is open source and available under the [... License](). -->

<!-- You don't have to include all sections - just the one's relevant to your project -->
