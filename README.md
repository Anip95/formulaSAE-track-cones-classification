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

### Libraries and first operations

In the following picture 3 blocks can be seen and they show, respectively, all the libraries used, the loading of the dataset through *pandas* and the drop of columns that won't be used.
Also, the first two rows of the csv file can be seen, which give an idea of how the dataset is structured.

![](assets/2.png)

Next, the dataset was split in training set, validation set and test set, following a **80 (75-25) - 20** rule, meaning that 80% of the training set got split into 75%-25%.

![](assets/3.png)

A class imbalance was noticed. In particular, **class 1** only had **927 samples** and **class 3** only had **916**. Thus, the SMOTE technique was used to oversample the minority classes.

![](assets/4.png)

### Training procedure

Before training the model, both input features and target labels needed to be converted into a format compatible with Keras.

The pipeline that performs the aforementioned operations is the following:

  - The training and validation Pandas dataframes got coverted into NumPy arrays because Keras expects inputs as arrays;
  - Encoding of the validation labels into integers via LabelEncoder;
  - Application of one-hot encoding through get_dummies. This produces a NumPy array, needed for training with the categorical_crossentropy loss metric;
  - Application of the same encoding to the training labels.

![](assets/5.png)

