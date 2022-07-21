<<<<<<< HEAD
# Image segmantation -- Unet, using Keras

---

## Overview

### Data

The data was obtained from UAV image scans on the NCAT test track.


This model was trained with 1089 images including augmented images.


You can find it in folder data/road-aug.

### Data augmentation

For data augmentation I use a module called ImageDataGenerator in keras.preprocessing.image to perform vertical shifts, flips, and brightness changes to the images, and the labeled images.

See aug.ipynb.


### Model

![img/u-net-architecture.png](img/u-net-architecture.png)

This deep neural network is implemented with Keras functional API, which makes it extremely easy to experiment with different interesting architectures.

Output from the network is a 256*256 which represents mask that should be learned. Sigmoid activation function
makes sure that mask pixels are in \[0, 1\] range.

### Training

The model is trained for 80 epochs.

After 80 epochs, calculated accuracy is about 0.88.

Loss function for the training is sparse categorical crossentropy.


---

## Tensorboard
You can visualize in real time the train and test losses, the weights and gradients, along with the model predictions with tensorboard:

`tensorboard –logdir logs/`



## How to use

### Dependencies

This tutorial depends on the following libraries:

* Tensorflow
* Keras >= 1.0

This code should be compatible with Python versions 2.7-3.5.

### Running the model

To run the model run:

Unet.ipynd

You will see the predicted results of test image in results

### Evaluating your results

To evaluate your results run:
eval.ipynd
The output will give you precision, recall, and F1-score of each image, as well as the average precision, recall, F1-score of the entire dataset.


### Results

![img/0label.png](img/0label.png)

![img/0truth.png](img/0truth.png)


=======
# Image-Segmentation-
Developed an automated convoluted neural network with Keras used to segment images in 9 different highway related classes. Uses a modified version of U-Net architecture and tested with UAV scanned images.
>>>>>>> fd79346fbacf63eb170dd84e601d323d5739d5fd
