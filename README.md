# Image segmantation 
### Data 
The data was obtained from UAV image scans on the NCAT test track. This model was trained
with 1089 images including augmented images.
### Data augmentation 
For data augmentation I use a module called ImageDataGenerator in <span class=GramE>keras.preprocessing</span>.image
to perform vertical shifts, flips, and brightness changes to the images, and
the labeled images. See <span class=GramE>aug.ipynb</span>. 
### Model 
This deep neural network is implemented with Keras functional API, which makes it
extremely easy to experiment with different interesting architectures. Output
from the network is a 256*256 which represents mask that should be learned.
Sigmoid activation function makes sure that mask pixels are in <span
class=GramE>\[</span>0, 1\] range. 
### Training 
The model is trained for 80 epochs. After 80 epochs, calculated accuracy is about 0.88. Loss function for
the training is sparse categorical crossentropy. 
## Tensorboard 
You can visualize in real time the train and test losses, the <span class=GramE>weights</span>
and gradients, along with the model predictions with tensorboard: `tensorboard logdir
logs/` 
## How to use 
### Dependencies 
This tutorial depends on the following
libraries: * Tensorflow * Keras &gt;= 1.0 This code should be compatible with
Python versions 2.7-3.5. 
### Running the model 
To run the model run: Unet.ipynd
You will see the predicted results of test image in results
### Evaluating your results 
To evaluate your results run: <span class=GramE>eval.ipynd</span> The
output will give you precision, recall, and F1-score of each image, as well as
the average precision, recall, F1-score of the entire dataset.
