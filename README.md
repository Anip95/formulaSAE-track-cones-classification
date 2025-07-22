# formulaSAE-track-cones-classification

![Made with Python](https://img.shields.io/badge/Made%20with-Python-blue)


This project was developed for the *Machine Learning* course as part of my academic work as a master's degree student in Computer Engineering.

The assignment and the data were hosted on the Kaggle platform as a competition, owned by the University of Napoli "Federico II".

> *Important note about the data*: The dataset used in this project was provided through a private Kaggle competition hosted by the aforementioned university. Due to the competition's intellectual property rules, the data is not included in this repository.


# Project Overview


## The dataset

![](assets/formulaSAE.jpeg)

The dataset consists of features extracted from various frames of videos depicting different types of cones used in Formula SAE races.
These types are:
  - Big orange cones, delimiting the beginning and ending of the track 
  - Little orange cones, delimiting the finish area
  - Blue cones, delimiting the right border of the track
  - Yellow cones, delimiting the left border of the track

The aim of this project is to properly classify a specific cone detected by sensors given its extracted features.
A label is assigned to each type of cone, going from 1 to 4.

The datasets to train and test the model on are in the **csv** format.

## Model implementation

In the following picture 3 blocks can be seen and they show, respectively, all the libraries used, the loading of the dataset through *pandas* and the drop of columns that won't be used.

![](assets/2.png)


