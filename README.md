﻿# Tamil_Character_Recognition_Using_CNN

 **1. Abstract:**
Character recognition is developed for various patterns of handwritten or optical characters to be recognized digitally. There are many Tamil literatures in undigitized form. Using deep learning the undigitized Tamil literatures can be converted into readable format. Many researches were carried on character recognition using deep learning for languages like Arabic, Devanagari, Telugu, etc Due to the larger category set and confusion in similarities between handwritten characters Tamil character recognition is a challenge. Convolutional Neural Networks (CNN) are playing a vital role nowadays in every aspect of computer vision applications. In this paper we have used the state of the art CNN in recognizing handwritten Tamil characters. CNNs differ from traditional approach of Handwritten Tamil Character Recognition (HTCR) in extracting the features automatically. We have used an isolated handwritten Tamil character dataset developed by HP Labs India. In this paper, we propose a character recognition system for handwritten Tamil characters using deep learning. Here, VGG 16 approaches is carried out. The proposed work gives efficiency of 94.52% on our datasets. Keywords— Image processing, Character recognition, Deep learning, Convolution Neural Network, Visual Geometry Group (VGG16), Tamil handwritten characters.

**2. Introduction:**
Tamil is one of the ancient Indian languages which is predominantly used in Southern India, Srilanka and Malaysia. The speciality of Tamil language is every sound pronounced has a syllable in Tamil. The economy of characters to represent a word is minimal in Tamil language. The smallest unit of Tamil script is syllable. These syllabic units of Tamil script has 12 vowels, 18 consonants and a special character (Ayudha Ezhuthu, ஃ). The combination of vowels and consonants make a total of 216 compound characters, thus a total of 247 characters. There are 5 borrowed consonants from Sanskrit, which when combined with vowels would yield another 60 compound characters so as to make a total of 307 characters. The complete Tamil character set can be represented by combinations of 156 distinct characters. For example, கௌ (pronounced as kow) can be represented by combining ’,’க’,’ள’. 
Handwritten Character Recognition (HCR) is of two forms: online and offline. Online method converts the tip movements (strokes) of digital pen to a list of coordinates, whereas offline method uses characters as scanned images. The challenging part of handwritten character recognition is the variations in the writing patterns of individuals. Even the same person handwriting can vary at different times. Traditional machine learning approaches were used for an offline HCR for a long time. A typical machine learning way of handwritten character recognition would be pre-processing, segmenting, extracting the features and classifying. An offline HCR system is first trained with the set of characters (as scanned images) and later when a new character image is given as input, the system should be able to recognize it accurately. HCR has shown its usefulness in many applications such as sorting of mails in post offices, bank check reading, digitization of legacy documents and legal documents and handwritten document/form conversions.
 Digitization of a handwritten document involves various operations such as conversion of color or greyscale image to binary image, extraction of the foreground text from background texture (if any), noise removal, separation of the individual lines, segmentation of words in each line, segmentation of the characters in every word and recognition of the isolated characters. However, this work involves only the isolated offline handwritten Tamil characters recognition using deep learning approach. 
For Tamil, HPLabs, India have developed a dataset named ‘hpl-tamil-iso-char’ for 156 classes of Tamil characters which was used by very few. In (Vijayaraghavan and Sra, 2014), only 34 classes were used. In (Bhattacharya et al., 2007) though all the classes were used, they used a grouping method. Shanthi and Duraiswamy (2010) created their own dataset and was able to recognize only 34 classes. This work will set the benchmark for HTCR for all the 156 classes using deep learning methods. The objective of our work is to set a benchmark for Tamil character dataset of HPLabs.

**3. Convolutional Neural Networks:**
Convolution Neural Network is a special type of neural network used effectively for image recognition and classification. By implementing these techniques, we recognize the handwritten Tamil characters. Convolution layer differ with a neural network in a way that, not every pixel (a neuron) is connected to the next layer with a weight and bias, but the entire image is split as small regions (say a n x n matrix) and weights and bias are applied over it. These weights and bias are referred to as filters or kernels which when convoluted with every small region in the input image would yield feature maps. These filters are the simple ‘features’ that is searched in the input image in the convolution layer. The number of parameters required for this convolution operation would be minimal as the same filter is traversed over the entire image for a single feature. The number of filters, size of the local region, stride, and padding are the hyper parameters of convolution layer. Based on the size and genre of the input image, these hyper parameters could be tuned to achieve better results.
Pooling layer:
    In order to reduce the spatial dimension of the image as well as the number of parameters, thereby to reduce the computation, this pooling layer is used. This layer performs a fixed function over the input, hence no parameters are introduced. Different types of pooling are available such as average pooling, stochastic pooling, max pooling. Max pooling is the most commonly used pooling algorithm, in which an nxn window is slid across and down the input with a stride value s and for each position the maximum value in the nxn region is taken, thereby reducing the size of the input. This layer provides translational invariance such that even with a slight variation in the position would still be able to recognize the image. But the location information is lost as the size is reduced. 
Fully connected layer:
 In this layer the flattened output of the last pooling layer is fed as input to a fully connected layer. This layer behaves like a traditional neural network layer where every neuron of the previous layer is connected to the present layer. Hence, the number of parameters in this layer are higher compared to the convolution layer. This fully connected layer is connected to an output layer which is generally a classifier. 
Activation function:
 Different activation functions have been used across various architectures of convolution neural networks. Nonlinear activation functions such as ReLU, LReLU, PReLU, and Swish have proven better results when compared to the classic sigmoid or tangent functions. These nonlinear functions have helped in speeding up the training.
 
**4. Dataset:**
4.1 Isolated Handwritten Tamil Character Dataset:
•	This work uses the Isolated Handwritten Tamil Character dataset developed by HP Labs India. This dataset contains images of Handwritten images of Tamil vowels (or Uyir Eluthukkal). The Goal of this project is to build a model that predicts new handwritten tamil characters. 
•	This dataset contains approximately 500 isolated samples each of 156 Tamil “characters” (details) written by native Tamil writers including school children, university graduates, and adults from the cities of Bangalore, Karnataka, India and Salem, Tamil Nadu, India.
•	 The data was collected using HP Tablet PCs and is in standard UNIPEN format.
•	An offline version of the data is also available in the form of bi-level TIFF images, generated from the online data using simple piecewise linear interpolation with a constant thickening factor applied.
•	The data is available only for research use. Subsets of this dataset were used for the IWFHR 2006 Tamil Character Recognition Competition.
 
Fig:1 The above picture depicts the Isolated tamil characters.

**5. Proposed Methodology:**
The Goal of this project is to build a Convolutional Neural Network (CNN) model that predicts new handwritten tamil characters and classify them. The dataset used here is Isolated Handwritten Tamil Character dataset.


**6. Frameworks:**
•	Tensorflow v2 - A open sourced machine learning framework from Google.
•	Keras - A open sourced neural network library running on top of tensorflow.
•	scikit-learn – It is a free software machine learning library for the Python.

**6.1 Process flow:**
1.	Importing Libraries
2.	Preparing the Dataset
3.	Preparing the pixel data
4.	Data Pre-processing methods
5.	Building the model
6.	Training and evaluating the model

**1. Importing the Libraries:**
Here we are importing the required libraries for the kernel. The basic libraries that are required for the project are pandas, numpy, matplotlib, zipfile, os and re in order to perform the basic functions in the data importing and pre-processing.

**2. Preparing the Dataset:**
•	Adding the data provided from the Isolated Tamil Handwritten Tamil Character dataset. The data will be added to the kernel.
•	The basic OS library create a dictionary of mapped variable with the image file name is used to return a pandas Data Frame object from conversion of the image file.
•	Then selecting the label column and store it in category list which is used for the classification of the labelled image.
•	Visualizing the total number of data of each category using image show function. Then, we check for less populated values in the dataset.
•	That is done after extracting the dataset, which is uploaded in the form of zip file to a folder named shuffled.  
•	Reading and extracting all the data in the dataset and renaming the directory from data/shuffled to data/train.
•	Setting up the train path and thereby reading all the images in the dataset.

**3. Preparing the Pixel Data:**
Since the pixel values for each image in the dataset are Tamil characters in the range between black and white, or 0 and 255.
A good starting point is to normalize the pixel values of grayscale images, e.g. rescale them to the range [0,1] and set the fill_mode to nearest. This involves first converting the data type from unsigned integers to floats, then dividing the pixel values by the maximum value (255). The ImageDataGenerator() function below implements these behaviours and is provided with the pixel values for both the train and test datasets that will need to be scaled.

**4. Data pre-processing methods:**
	
Creating a DataFrame:
•	Creating a data frame that contains the image file names and its associated class.
•	Displaying the unique characters in the dataset using the category variable  
•	There are twelve vowels in Tamil, and there are twelve target values here ranging from 000 to 010 and the value 155..
•	We know that there are twelve classes, one for each character, but we don’t know which class maps to which character. So, lets print one image of each class, and use that to create a dictionary that maps the class with the Unicode value of that character.
Mapping class with Unicode String:
Creating a dictionary data frame, that maps the file name with the character's Unicode string which is labelled before using the file name data. 
Visualizing the distribution of data in the dataset:
•	The data is not evenly distributed among all classes, and class '155' has only one image associated with it in the dataset.
•	We remove the class due to insufficient data with the particular class ‘155’
•	Randomly visualizing all image datapoints of one of the class to get an intuitive understanding of the dataset.

**5. Building the Model:**
Using the Keras API to build the model hence We have a Tensorflow background. We import the Sequential Model from Keras and add Conv2D, Max Pooling, Flatten, Dropout, and Dense layers. Dropout layers fight with the overfitting by disregarding some of the neurons while training while Flatten layers flatten 2D arrays to 1D array before building the fully connected layers. 
There are 4 RELU (Rectified Linear Activation unit) which does BatchNormalization, MaxPool2D is doe with a pool size of (2,2), ad DropOut which has a value of 0.2. The size of image is 120 to 23 in the final layer  of Dense layer.
 
  Building a Deep Learning model with CNN:
Building up the model with different Sequential CNN layers so that it results with trainable and non-trainable parameters as:                 
Total Parameters	Trainable parameters	Non-trainable parameters
278,091	277,259	832

  Creating Callbacks:
A callback is an object that can perform actions at various stages of training (e.g. at the start or end of an epoch, before or after a single batch, to correct certain behaviours)
Visualizing validation vs Training accuracy and Loss:
Validation Accuracy:
In other words, the test (or testing) accuracy often refers to the validation accuracy, that is, the accuracy you calculate on the data set you do not use for training, but you use (during the training process) for validating (or "testing") the generalisation ability of your model or for "early stopping".
Validation Loss:
The validation loss indicates how well the model fits new data. "Validation loss" is the loss calculated on the validation set, when the data is split to train / validation / test sets using cross validation. The idea is that you have three, separate sets of data: one used for training the model (train), one for doing things like hyperparameter tuning, model selection (validation), and one used to make final check of the model (test).

The model didn’t overfit, and has reached convergence.
Validation Accuracy	Validation loss
97.33%
	0.109


**6. Training and evaluating the model:**
The image dimensions in this dataset vary by a significant amount. The standard deviation is really long. The image data should be regularized before feeding it into the neural network. From the summary above, 120x120 shape will be a better option.
Splitting the Data into Training and Validation Dataset:
	• We are segmenting the input data for training into two exclusive data namely, Train and Validation data sets. Train data is used to train the model whereas the validation data is used for cross verification of the model's accuracy and how well the model is generalized for the data other than training data. • 
  • Validation accuracy and loss will tell us the performance of the model for new data and it will show if there is overfitting or underfitting situation while model training.
	• Compiling and fitting the Model:
Setting up and fitting the model with the validation data, call backs, epoch  parameters with our train data. At epoch value 50,  the model is evaluated.
	• Creating Training and validation Image Data Generators
At the batch size 5 and epochs 50, resulted in 2399 validated image filenames belonging to
11 classes and 600 validated image filenames belonging to 11 classes.

Making Predictions:
We can use our saved model to make a prediction on new images. The model assumes that new images are grayscale, that they have been aligned so that one image contains one centered handwritten letter, and that the size of the image is square with the size.
Model Evaluation:
•	When this model is evaluated, the model has a validation accuracy of 97.33% at 50 epochs, which is not bad for such a small dataset.
•	Plotting up all the images and mapping the particular character with its corresponding image.

**7. Results and Discussions:**
A popular dataset called Isolated Tamil character dataset was taken to make predictions of handwritten tamil characters from 0 to 9. The dataset was cleaned, scaled, and shaped. Using TensorFlow, a CNN model was created and was eventually trained on the training dataset. Finally, predictions were made using the trained model. Through broad assessment utilizing a Isolated Tamil character dataset, the current work recommends the job of different hyper-boundaries. We additionally confirmed that tweaking of hyper-boundaries is fundamental in improving the presentation of CNN engineering. 

With respect to our study, CNN is a better option to be imparted to the model due to the following advantages:
•	The CNN will converge more faster on values 0 to 1 than 0 to 255. So we divide every value by 255 to scale the data from [0.. 255] to [0..1]. 
•	It helps the model to better learning of features by decreasing computational complexities if we have data that scales bigger.
•	CNN uses bigger pre-trained models, K-Fold Cross Optimization, CutMix to aug-ment your images, MixUp to augment your images and Ensemble learning methods to improve the efficiency.
•	The weights are smaller and shared — less wasteful, easier to train than MLP and more effective too. They can also go deeper. Layers are sparsely connected rather than fully connected.



