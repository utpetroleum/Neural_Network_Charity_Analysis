# Neural_Network_Charity_Analysis

## Overview of Project

### Purpose

The purpose of this project is to use machine learning and neural networks to create a binary classifier that is capable of predicting whether applicants will be successful if funded by Alphabet Soup. The datasets provided in CSV format has more than 34,000 organizations that have received funding from Alphabet Soup over the years. Within this dataset are a number of columns that capture metadata about each organization, such as the following:

    * EIN and NAME—Identification columns

    * APPLICATION_TYPE—Alphabet Soup application type

    * AFFILIATION—Affiliated sector of industry

    * CLASSIFICATION—Government organization classification

    * USE_CASE—Use case for funding

    * ORGANIZATION—Organization type

    * STATUS—Active status

    * INCOME_AMT—Income classification

    * SPECIAL_CONSIDERATIONS—Special consideration for application

    * ASK_AMT—Funding amount requested

    * IS_SUCCESSFUL—Was the money used effectively

## Results

    * Data Preprocessing

        * What variable(s) are considered the target(s) for your model?

![Target](https://user-images.githubusercontent.com/92401000/156908158-4fd75422-1071-4549-bb1d-a6fc1a282cbf.PNG)

The column "IS_SUCCESSFUL" is the target variable.

        * What variable(s) are considered to be the features for your model?

![Features](https://user-images.githubusercontent.com/92401000/156908167-058cb50a-b03d-43ff-81bf-ee1caaf5701d.PNG)

The columns "APPLICATION_TYPE", "AFFILIATION", "CLASSIFICATION", "USE_CASE", "ORGANIZATION", "STATUS", "INCOME_AMT", "SPECIAL_CONSIDERATIONS", "ASK_AMT" are the feature variables. 

        * What variable(s) are neither targets nor features, and should be removed from the input data?

![EIN_NAME](https://user-images.githubusercontent.com/92401000/156908178-f3130d1d-5e88-43fa-8447-0dcd4b192f77.PNG)

The columns "EIN" and "NAME" are neither targets nor features, and removed from the input data.

    * Compiling, Training, and Evaluating the Model

        * How many neurons, layers, and activation functions did you select for your neural network model, and why?

![nn_summary](https://user-images.githubusercontent.com/92401000/156908185-ffa9e4a8-15ff-456d-a45c-af4085b6e59d.PNG)

We selected two hidden layers, 80 neurons for the first layer, 30 neurons for the second layer, and used "relu" activation functions for both. For the output layer, we used one neuron with a "sigmoid" activation function. 

After preprocessing the datasets, we ended up with 34,299 rows and 44 columns. Due to the complexity of the datasets, we needed to add an additional hidden layer and increased the number of neurons. We chose "relu" activation function for the hidden layers because it is ideal for looking at positive nonlinear input data for classification. We chose "sigmoid" activation function for the output layer because the values are normalized to a probability between 0 and 1, which is ideal for binary classification.

        * Were you able to achieve the target model performance?

![best_param](https://user-images.githubusercontent.com/92401000/156908255-03e773e0-4ab1-49b7-b96f-2c22a1a93833.PNG)

We were unable to achieve a target predictive accuracy higher than 75%. The highest predictive accuracy we achieved was 72.9%.

        * What steps did you take to try and increase model performance?

![optimzation](https://user-images.githubusercontent.com/92401000/156908204-0bacb3b7-7fad-4a3d-90b0-1a7694e11df8.PNG)

1. Attempt 1: We automated optimization by using Kerastuner. We created a function to run three different activation functions, run up to 100 neurons in the first hidden layer, and run up to 6 hidden layers with max of 100 neurons. 

2. Attempt 2: We ran three hidden layers using 15 neurons for the third layer. 

3. Attempt 3: We increased the neurons in the first hidden layer to 200, the second layer to 100, and the third layer to 50.

## Summary

Using the deep learning model, we were able to train the model with a 72.6% accuracy in predicting whether applicants will be successful or not if funded by Alphabet Soup. 

After three attempts to optimize the model, we were able to increase the model's accuracy to 72.9%.

We recommend using supervised learning random forest models. Random forest models can handle tabular data, which is appropriate for the data we are using. Also, random forest models can train large datasets and predict values quicker than deep learning models, in order words random forest models can achieve comparable predictive accuracy on large tabular data with less code and faster performance.
