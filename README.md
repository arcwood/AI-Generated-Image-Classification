# AI-Generated-Image-Classification
## Problem Statement
With the advent of generative AI, it has become increasingly difficult to separate real data from AI-generated content. The goal of this project is to develop a model that can accurately identify fake photos created by AI. The model aims to contribute to the development of more secure and reliable online services by detecting and mitigating identity fraud.
## Dataset Used
The training and evaluation dataset utilized in this project is called the "[140k Real and Fake Faces](https://www.kaggle.com/datasets/xhlulu/140k-real-and-fake-faces)" dataset. Due to computational constraints related to image processing, a subset of 20,000 images from the test data of the aforementioned dataset was employed. The dataset encompasses a mixture of genuine and fabricated images, each labeled accordingly.
## Building Model
  ### Data Pre-processing
    - The dataset contained two folders corresponding to real and fake images.
    - The images were loaded from these folders and assigned a label based on their folder name.
    - Seperate arrays were then constructed consisting of images and labels.
  ### Model Architecture
    - The Resnet50 pre-trained model was used as the base model, with the pre-trained weights initialized from the "ImageNet" dataset.
    - After the last layer of the Resnet50 model a GlobalAveragePooling2D layer was added, followed by a Dense(256) with activation = Relu.
    - The last layer consists of the two classes with activation = softmax
  ### Model Training
    - The Model was trained on 10000 training images which were split into training and validation data.
    - The model was trained using the training set and evaluated on the validation set.
    - The Adam optimizer and binary cross-entropy loss function were used during training.
    - The Model was trained on 10 epochs with a Batch Size of 250.
  ### Model Evaluation
    - The Model gave an accuracy of 0.98 on training and 0.86 on validation data.
    - It was then tested on 1000 images from testing images, resulting in an accuracy of 0.85
