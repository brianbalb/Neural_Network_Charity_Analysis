# Neural_Network_Charity_Analysis

## Tools/Software
* Python 3.7
* pandas 1.2.4
* sklearn 0.24.1
* tensorflow 2.5.0
* Data: charity_data.csv

## Overview
As requested by client, the purpose of creating a binary classifier capable of predicting applicant's success rate if funded by Alphabet Soup. The Data is preprocessed, a NNM (Neurnal Network Model) is compiled, trained and evaluated. An attempt to optimize the model by increasing the accuracy to 75% or higher. 

## Results
1. Data Preprocessing

* Read charity_data.csv file to a Pandas DataFrame, 
* The "EIN" and "NAME" columns were dropped from the dataset. (These identification columns did not contain any valuable information)
* Columns with more than 10 unique values, such as the "CLASSIFICATION" and "APPLICATION_TYPE" columns, have had their rare categorical variables binned into a new "other" column.
* A list of categorical variables is generated and is then encoded using OneHotEncoder. These encoded variable names are added to a new dataframe. 
* After merging the one-hot encoded features, the originals are dropped.

The variable considered the target for this model is "IS_SUCCESSFUL," all other variables in the dataframe are considered features. The numerical variables are standardized using Scikit-Learn’s StandardScaler module.

2. Compiling, Training, and Evaluating the Model

* A deep learning model is designed to to create a binary classification model that can predict if an "Alphabet Soup" funded organization will be successful based on the features in the dataset.
* Rectified Linear Unit (ReLU) is used as the activation function for both the first and second hidden layers. 
* For the output layer, a sigmoid activation function is used. 
* While training the model, a callback saves the model's weights every 5 epochs. 
* After training, the model's Loss and Accuracy values are evaluated. 
* Although an accuracy of 72.67% is somewhat high, it is decided to optimize the model to 75% or higher.

Optimization Attempt 1

* In the first attempt to optimize this model, the number of neurons in the hidden layers were increased. 
* This had a negligible effect on the model's accuracy. 
* The number of neurons is reverted back to their original levels for the other optimization attempts.

Optimization Attempt 2

* In the second attempt, a third hidden layer was added to the model with 4 neurons. 
* This change slightly reduced the model's accuracy. 
* The number of epochs were also reduced to 40 (Down from 50 epochs). 
* This third layer is deleted due to it's negative effect.

Optimization Attempt 3

* In the third attempt, the activation function in the second hidden layer is changed to a tanh function. 
* This change also reduced the models accuracy. 
* It can be inferred that the activation function that best suits this model is ReLu.

## Summary
*None of the optimization attempts in this analysis were able to produce a model with a predictive accuracy level of 75% or higher. The following methods were attempted:*

* Add an additional hidden layer.
* Add more neurons to a hidden layer.
* Use different activation functions.
* Decrease the number of epochs in the training.
* The number of neurons in the hidden layers may need to be adjusted, this results why this model did not reach the targeted predictive accuracy level of 75%. 
* The number of epochs during trainiing may need to be increased. The input data may have outliers or variables that are confusing the model.

1. Deep Learning model in this binary classifiication project, it may be preferable to use a Random Forest Classifier. Random Forest Classifiers are much simpler to setup and can be trained in a matter of seconds compared to a binary classifier. 

2. The predictive accuracy level of these two models would most likely be similar. For its ease of implementation and applicability to this situation. 

Ultimatly it is recommended to use a Random Forest Classifier for future development on this project.
