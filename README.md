Project Overview
This repository contains a Python application that performs traffic sign recognition using a Convolutional Neural Network (CNN). The application provides a simple PyQt5-based graphical user interface with three main functions:

Training: Trains a CNN from scratch on a labeled traffic-sign dataset.

Browse Image: Allows the user to select an input image from their local file system to be classified.

Classify: Loads the trained model from disk, processes the selected image, and displays the predicted sign name in the GUI.

Under the hood, we use Keras (with a TensorFlow backend) to build and train a CNN that takes RGB traffic sign images (resized to 30×30 pixels) and outputs a probability distribution over 43 possible sign classes (from the German Traffic Sign Recognition Benchmark [GTSRB] dataset).

Features
Interactive GUI (PyQt5):

Browse Image: Select any .png, .jpg, .jpeg, or .bmp image from disk.

Training: Trigger model training on the prepared dataset and view progress in the console.

Classify: Load a pre-trained .h5 model file and predict the class of a newly selected image.

Result Display: The recognized class name appears in a read-only text box.

Custom CNN Architecture (Keras):

Two stacks of Conv2D → Conv2D → MaxPool → Dropout

A Flatten layer followed by a Dense(256) + Dropout

Final Dense layer with Softmax activation over 43 classes

Training Visualization (Matplotlib):

Saves plots of training/validation accuracy (Accuracy1.png) and loss (Loss1.png) to disk.

Model Persistence:

Saves the trained model to my_model_new.h5.

During classification, loads my_model.h5 (or my_model_new.h5 if retrained).

