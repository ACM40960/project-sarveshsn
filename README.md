# Weather Image Classification

Weather Image Classification holds significant significance in the realms of meteorology and computer vision, offering far-reaching implications that span a diverse array of activities, including weather forecasting, environmental monitoring, and disaster preparedness. The prevailing techniques predominantly hinge on human interpretations, a factor that can potentially introduce inaccuracies and uncertainties. This underscores the pressing need for more advanced methodologies.

As a solution, the integration of Convolutional Neural Networks (CNNs) into weather image classification has emerged as a robust and pragmatic approach. In this project, our primary objective is to develop an image classifier capable of categorizing diverse weather images. Traditional methods often rely on human observations, a process that can be time-consuming and susceptible to errors. The importance of accurate weather classification is underscored by its relevance in the development of self-driving vehicles, intelligent transportation systems, and outdoor vision systems. With the aid of this image classifier, predictions about the prevailing weather conditions can be rapidly and accurately made based on input images. This marks a significant advancement over traditional approaches, enhancing both efficiency and accuracy.

## Folder Structure
```
dataset/

Code/
├─ Data_preparation.R
├─ Training.Rmd

README.md

```
## Installing R and RStudio

1. Install R:

R is a programming language and software environment used for statistical computing and graphics.

  Visit the official R website: https://cran.r-project.org/
  Click on the "Download R" link at the top of the page.
  Select your operating system (Windows, macOS, or Linux) and download the appropriate installer.
  Run the downloaded installer and follow the on-screen instructions to install R.

2. Install RStudio:

RStudio is an integrated development environment (IDE) specifically designed for R.

  Visit the official RStudio website: https://www.rstudio.com/
  Click on the "Products" menu and select "RStudio Desktop."
  Choose the "Free" version, which is sufficient for most users.
  Download the appropriate installer for your operating system (Windows, macOS, or Linux).
  Run the downloaded installer and follow the on-screen instructions to install RStudio.

## Prerequisite

You need to have following packages installed prior to running the code in RStudio. You can run this code in the RStudio script/console. 
```
install.packages("jpeg") #For loading pictures
install.packages("reticulate")  #To integrate Python code and libraries into your R environment if not done exclusively.
install.packages("keras")  #For training CNN model
install.packages("ggplot2) #To plot the learning curves
install.packages("grDevices")  #To Plot accuracy and loss

```
Import the above packages by running the following code - 
```
library(jpeg)
library(reticulate)
library(keras)
library(ggplot2)
library(grDevices)
```

## Dataset

Dataset used in this project can be found at https://www.kaggle.com/datasets/jehanbhathena/weather-dataset?resource=download

Dataset contains labeled 6862 images of different types of weather.

The weather dataset is split into 11 folders, one for each class, with each named after the class of images it contains. i.e. all 'rain' images must be in weather/rain/.

Our original dataset folder structure will look like this.

![filesssnip](https://github.com/ACM40960/project-sarveshsn/assets/93898181/58f280d9-026f-4d17-af6d-12efcb32e78e)

Inside these folder contains images of that particular weather. For example, lightning folder will contain below images.

<img width="647" alt="lightning" src="https://github.com/ACM40960/project-Neha-0994/assets/118282077/eff60ef3-6d39-437d-b140-42eedd3ff49c">


## Data preparation

We must split the dataset into train, validation and test prior training the model. We have split the original dataset into folders like train, test and validation. Each of these 3 folders will contain the 11 different weather class folders. The train, testn and validation split is 80-10-10 respectively. 

Running file Data_preprocessing.R will split the folders into train, test and validation folder. Our new dataset will look like this.

![filesssnip2](https://github.com/ACM40960/project-sarveshsn/assets/93898181/cf0f2425-6036-485f-90eb-3a2c2aa67edd)


## CNN Model

Image classifier is built using Convolutional Neural Network (CNN). We have built a baseline CNN model followed by 2 CNN models with different configurations. Confusion matrix is used to check the precision, recall and F-1 score of these 3 models. These 3 are used as metrics to understand the performance of the model.

CNN Model 1

•	Architecture: Model 1 (our base model) is CNN with 4 convolution layers and 4 max-pooling layers then followed by 2 fully connected layers. The first convolution layer is set with 32 filters and a 3 × 3 kernel with strides 1 (default). Next 3 convolution layers are set with 64 and 128 filters with 3 × 3 kernels. The fully connected layer uses 512 units and ReLU activation function.
•	Hyperparameters: Learning rate -0.0001 using optimizer - RMSProp

![Model1](https://github.com/ACM40960/project-sarveshsn/assets/93898181/d0cdb497-7e19-44fe-b9f5-3cba198e6e3e)

CNN Model 2

•	Architecture: Four pairs of convolutional layers followed by max-pooling layers.The number of filters increases with depth (64, 128, 256, 512). Additional use of batch normalization and dropout for regularization. Flattening layer followed by two dense (fully connected) layers.
•	Hyperparameters: Learning Rate: 0.001 (using Adam optimizer).	Batch normalization applied after each convolutional and dense layer. Dropout: 0.25 applied after each max-pooling layer and 0.5 after the first dense layer.

![Model2](https://github.com/ACM40960/project-sarveshsn/assets/93898181/c843c5b1-88d1-4648-a2f9-866fa65545cb)

CNN Model 3 

Model 3 is structurally similar to Model 2, but with the added benefit of data augmentation during training.
The additional data augmented images look like this - 

![Data aug](https://github.com/ACM40960/project-sarveshsn/assets/93898181/a22537cd-c2a9-4e49-9f9a-c62d487289d9)




## Usage

* Run Data_preprocessing.R file to split the dataset into train , test and validation folders.

* Run Training.Rmd file to train the models. Make sure the path is correctly specified in your code.





