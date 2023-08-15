# Weather Image Classification

In this project, our goal is to create an image classifier that can categorise various weather images.  Traditional methods rely on human observations which can a take a long time and are prone to errors. Weather classification is very useful, for example, in development of self-driving cars, smart transportation systems, and outdoor vision systems. Given an input image, this image classifier will be quick to predict the weather.

## Folder Structure
```
dataset/

Code/
├─ Data_preparation.R
├─ Training.Rmd

README.md

```

## Dataset

Dataset used in this project can be found at https://www.kaggle.com/datasets/jehanbhathena/weather-dataset?resource=download

Dataset contains labeled 6862 images of different types of weather.

The weather dataset is split into 11 folders, one for each class, with each named after the class of images it contains. i.e. all 'rain' images must be in weather/rain/.

Our original dataset folder structure will look this.

<img width="728" alt="folders" src="https://github.com/ACM40960/project-Neha-0994/assets/118282077/de518152-3d63-48ed-ae89-a035f07ccf18">

Inside these folder contains images of that particular weather. For example, lightning folder will contain below images.

<img width="647" alt="lightning" src="https://github.com/ACM40960/project-Neha-0994/assets/118282077/eff60ef3-6d39-437d-b140-42eedd3ff49c">

## Install packages

You need to have following packages installed prior running the code in RStudio.
* install.packages("keras") - For training CNN model
* install.packages("ggplot2) - To plot the learning curves
* install.packages("grDevices") - To Plot accuracy and loss

## Data preparation

We must split the dataset into train, validation and test prior training the model. We will split the original dataset into folders like train, test and validation. Each of these 3 folders will contain the weather categories folders similar to original dataset folder.

File Data_preprocessing.R will split the folders into train, test and validation folder. Our new dataset will look like this.

<img width="317" alt="division" src="https://github.com/ACM40960/project-Neha-0994/assets/118282077/8666fc0b-e0e3-436f-9091-b3d2719fa965">

## CNN Model

Image classifier is build using Convolutional Neural Network (CNN). We have build a baseline CNN model followed by 2 CNN models with different configurations. Confusion matrix is used to check the precision, recall and F-1 score of these 3 models. These 3 are used as a metric to understand the performance of the model.

## Usage

* Run Data_preprocessing.R file to split the dataset into train , test and validation folders.

* Run Training.Rmd file to train the models. Make sure the path is correctly specified in your code.





