# Python Convolutional Neural Network (CNN) for Fruit Classification
This is a simple project that generates a randomized json output with configurable attributes and key-value data. It uses a command-line interface.

## Introduction
This project leverages existing libraries to develop an image Classifier that can correctly identify different types of fruit. 
The dataset consists of four classes: Apple only, Banana only, Orange only, and a mix of fruits. 
The objective is to train a Convolutional Neural Network (CNN) model and employ various techniques to improve its accuracy. In this folder you will find four items:

    • `Report.docx` documents the experiments, results, and insights gained during the process of enhancing the performance of the fruit image classifier.
    • `FruitClassifier.ipynb`: A Jupyter notebook that supports this report and shows all experiments conducted.
    • `ML_Proj_Data` folder: A folder which contains the different types of training data utilized, as well as best-performing models (having test accuracy of 0.98% and 0.93% respectively).
    • `FruitClassifier-Sandbox.ipynb`: A Jupyter notebook which integrates the numerous variables that tweaked and used in this project, that can be experimented with.

## Base Model
The CNN model layer setup consists of several convolutional layers followed by max pooling layers, a global average pooling layer, a dense layer, and a final dense layer for classification. 
Random seeds were fixed to a value of 42 to maintain consistency across all runs of the training model.
For the model fitting process, the batch size was fixed to 10. Early stopping was implemented to monitor accuracy.

## Data Preprocessing: Edge Mapping and Channels
Four types of channel-based modification were carried out:

    1. Changing the image to grayscale, in the interest of reducing dimension count and increasing training speed. This modification is named “Grayscale” in the first parameter of var_aug (augmentation variant).
    2. Extracting a canny map from the image, in the interest of increased training speed in addition to edge recognition. This modification is named “Canny”.
    3. Compressing the alpha layers of images that had 4 channels(RGBA) into 3 channels (RGB) to white, in order to reduce dimensionality while simultaneously capturing the base features. This modification is named “RGB”.
    4. Compressing the alpha layers as with modification 3), then extracting the canny map and appending it to the fourth channel to provide the model with additional features to learn from. This modification is named “RGBcanny”.
    
Please refer to the codes in 6. Data Preprocessing: Edge Mapping and Channels in Jupter Notebook for the details. 
