## deep-learning-challenge
# Using a neural network to predict the effectiveness of a foundation's grantees to influence grant decision-making

# Overview:
The purpose of this analysis is to predict which characteristics of a grantee organization will benefit from philanthropic funding. The aim is to help funders better use their grantmaking dollars by ensuring their grants go to grantees that will be successful in their charitable work. By creating a deep-learning neural network, I hope to analyze many characterstics of a grantee's grant to help grantmakers decide if they should fund an initiative.

# Results

<img width="1346" alt="image" src="https://github.com/dancab13/deep-learning-challenge/assets/147662348/bdaaa8b2-133c-474d-bef5-37c42818334c">
![The first rows of the dataset showing the features (including unnecessary ones) and the target variable](image.png

# Data Preprocessing:
    * The target variable for this model is historical data of whether or not a grantee was successful. This is the "IS SUCCESSFUL" column in the dataset, which is a binary choice of Y (yes) or N (no).
    * Most of the remaining data of the dataset serve as features for the model, or what the model will analyze to predict the target, or outcome, variable (if the grantee will likely to be successfull or not). These features include the type of grantee organization, the type of application, the amount of funds the grantee asked for in their application, the grantee's affiliation, the use case or field/type of work the grantee does, the income amount, special considerations, and status.
    * The variables that should be removed, as they are not targets nor features, are the grantees' name and EIN, which are unique to the grantee and therefore would not be classified with any other data in the set. Analyzing these data would not help predict future success, as it is likely (or certain) that future grantees will not share the same name or EIN. It may be possible to remove the STATUS variable because of the two possible options--1 or 0--the majority of these data are 1, with only a fraction being 0.
![STATUS value counts and percent](image-1.png)

# Compiling, Training, and Evaluating the Model:
    * For my first attempt at building the neural network, I used the number of features in the cleaned DataFrame as the number of neurons in the first layer. Specifically, there were 43 neurons.
    ** For the second layer, I doubled the number of neurons from the first layer, using 86.
    ** For the third and final layer, I tripled the neurons from the first layer, using 129.
    * I was not able to achieve the target model performance of 75%.
    * I made other attempts to increase my model performance by including more data and increasing the number of neurons and layers in my model and adjusting the number of epochs during testing. I also ran a Keras tuner to see if Keras could find the optimal model parameters.

# Summary: 
Ultimately, I was not able to meet or exceed the 75% accuracy threshold for my model, despite three attempts. I found that using more data without binning data from columns helped increase the accuracy. Also, using fewer epochs also helped increase the accuracy, especially at the start of testing. However, my accuracy barely made it past 74.45%. I believe this model is therefore inaccurate and I would not suggest using it to make predictions on grant recommendations.

A different model could use PCA to better normalize all of the data and lead to more accurate testing. Another possibility would be to use a branching method such as Random Forest to analyze the validity of the features used in testing. By better selecting the features for testing, it may be possible to exclude features with too much correlation, allowing for better classification and accuracy.

# About
This repo contains materials for the Module 21 challenge of the Columbia Data Analysis and Visualization boot camp (administered by edX). The repo contains this readme along with a Google Colab notebook file, two HDF5 files, and two image files. All code is my own and was adapted from boot camp class activities. Some code was from the boot camp's generative AI program.

