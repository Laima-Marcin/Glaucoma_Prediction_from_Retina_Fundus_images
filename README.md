# IBM Advanced Data Science - my capstone project
**Predicting Glaucoma occurance from retina fundus images**

I invite you to see my project presentation on the link below:
https://www.youtube.com/watch?v=vaLwW3Q-shY

USE CASE AND DATASET

Use case:
* Classifying retinal fundus images as glaucoma or nonglaucoma (normal)
* Training a model to classify retinal fundus images from a dataset of labelled images

Dataset:
* ORIGA-light: An Online Retinal Fundus Image Database for Glaucoma Analysis and Research
This Database consists of 650 images (including 168 glaucomatous images and 482 randomly selected nonglaucoma images) from SiMES study. 
Each image is segmented and annotated by trained professionals from Singapore Eye Research Institute. 

	- Images downloaded from Kaggle open data source  
	https://www.kaggle.com/sshikamaru/glaucoma-detection
  
CSV file provides file names, CDR (cut to disk ratio) and classification of Glaucoma negative(a) or positive(b)

* If CDR ≥ 0.65, the image is Glaucoma positive.
* If CDR <0.65, the image is Glaucoma negative.

SOLUTION AND RESULTS

Shuffled the dataset (650 jpeg images in total) and split into 
* Training (520 images of which 134 Glaucoma positive and 386 Glaucoma negative)
* Validation (130 images of which 34 Glaucoma positive and 96 Glaucoma negative).

Best results with deep learning model - Convolutional Neural Network (CNN) in Keras, TensorFlow.
* Batch size: 64
* Number of Epochs: 20
* Architecture: Convolution layers followed by dense layers
* Optimizer: Adam
* Test loss: sparse categorical crossentropy 2.0893890133e-05
* Accuracy on test data: 93.83%

We tried 2 machine learning models:
* SVM (support vector machine), accuracy on test data: 71.53%
* Random Forest, accuracy on test data: 93.50%

INITIAL DATA EXPLORATION

DATASET:
* 650 images (jpeg) saved into labelled input folder Fundus_Train_Val_Data
* Image size from 192KB – 437KB
* Image dimensions 3072 x 2048 pixels
* Resolution 96 dpi
* Bit depth 24
* RGB color model

DATA CLEANSING AND FEATURES CREATION
* Resize images to 512 x 512 pixels
* Convert images to objects
* Image segmentation using Gaussian filter
* Plot preprocessed Green channel and smoothed histogram Green channel
* Plot preprocessed Red channel and smoothed histogram Red channel
* Covert images to grey scale
* Morphological segmentation for defining optic disc from Green channel and optic cup from Red channel

MODEL EVALUATION
Best results with deep learning model 
* Convolutional Neural Network (CNN) in Keras, TensorFlow.  Accuracy on test data: 93.83%
* SVM (support vector machine), accuracy on test data: 71.53%
* Random Forest, accuracy on test data: 93.50%

SUMMARY
Descent model with a reasonable computing need for training (both Random Forest and CNN)
Very limited overfit based on our test data 

Further steps:
* Build deeper network with more adaptive learning (Adam first then SGD + momentum for instance)
* Try different deep learning models (Resnet50, U-net)
* Try extracting more features from the image (veins, fovea, pigmentation, hemorrhage)
* Optical Coherence Tomography (OCT) is a non-invasive imaging technique that allows eye care professionals to measure the thickness and health of the retina’s multiple layers.




