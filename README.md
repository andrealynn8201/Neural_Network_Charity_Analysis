# Neural Network Charity Analysis
## Overview
The purpose of this analysis was to create a binary classifier that is capable of predicting whether applicants will be successful if funded by Alphabet Soup. 

## Results
### Data Preprocessing
* Variables that are considered the targets
  * Is_Successful column (indicates money was used successfully)
* Variables that are considedred the features
  * Application_Type, Affiliation, Classification, Use_Case, Organization, Status, Income_Amt, Special_Considerations, Ask_Amt, Is_Successful
  * Name was also a feature in the 3rd Optimization attempt

* What variables were removed (not targets or features)
  * EIN and Name for the initial build and for optimization attempts 1 and 2
  * EIN only for Optimization attempt 3

### Compiling, Training, and Evaluating the Model
* Neurons, Layers, and Activation Functions
  * Input Layer had the length of x_train (number of features)
  * Hidden Layer 1 had 80 neurons with a relu Activation Function
  * Hidden Layer 2 had 30 neurons with a relu Activation Function
  *  Output Layer used a sigmoid Activation Function

* Activation function for hidden layers chosen was relu, because it was ideal for nonlinear input data
  * Sigmoid chosen for Output Layer as it is ideal for binary classification
  * Layer 1 neurons was determined to be 80, or approximately twice the input features
  * Layer 2 neurons was determine to be 40, or approximately 1 times the input features making the total 3 times the input features

### Model performance
The initial performance was 72.6%, and the mode performance after optimization was 78% as seen below:
![Screen Shot 2022-07-21 at 6 41 29 PM](https://user-images.githubusercontent.com/93801125/180332981-8bfdb91e-1923-413f-aa31-4fe91fb0f0d7.png)
![Screen Shot 2022-07-21 at 6 42 18 PM](https://user-images.githubusercontent.com/93801125/180332987-2e2923d7-be54-457f-a2c6-c76b69bd8432.png)


The steps taken to increase performance, was first, adding a third hidden layer which increased the number of epochs to 150.  Second attempt, I dropped the columns 'Affiliation' and 'Organization' and again, set the number of epochs to 150. Last attempt, I kept the 'Name' column and separated it into buckets, using <10 as the value for other.


## Summary
Even though an above 75% accuracy was met, it's not recommended to drop the 'Name' column as it can skew the model. If a name keeps repeating, the applicant is likely to be well established and a reliable client which isn't always the case.

I would recommend using Random Forest Classifier as an alternative method. It excels at handling outliers as well as nonlinear data. The weak learner algorithms utilized in the Random Forest Classifier combines their output when making a final classification. This can be very powerful when choosing methods.
