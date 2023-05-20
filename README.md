# Neural_Network_Charity_Analysis
## Overview of the Analysis
The purpose of this analysis is to assist AlphabetSoup's business team in predicting whether applicants will be successful if funded by AlphabetSoup. We will be doing this by creating a binary classifier with a provided dataset that contains more than 34,000 previous organizations that have received funding from Alphabet soup over the years.

## Results
### Data Processing
- Target Variable: IS_SUCCESSFUL

![Target Variable](https://github.com/Caracalla1081/Neural_Network_Charity_Analysis/blob/e743a6576c761b2f5b81a6777c9a90829f8a2895/Images/Target%20and%20Features%20Variables.png)

- Feature Variables: APPLICATION_TYPE, CLASSIFICATION, AFFILIATION, USE_CASE, INCOME_AMT, SPECIAL_CONSIDERATIONS, ASK_AMT

![Feature Variable](https://github.com/Caracalla1081/Neural_Network_Charity_Analysis/blob/e743a6576c761b2f5b81a6777c9a90829f8a2895/Images/Target%20and%20Features%20Variables%20DfHead.png)

- Removable Variables: EIN, NAME, STATUS, ORGANIZATION

![Neither Feature or Target Variable](https://github.com/Caracalla1081/Neural_Network_Charity_Analysis/blob/e743a6576c761b2f5b81a6777c9a90829f8a2895/Images/Neither%20Target%20or%20Feature%20Variables.png)

### Compiling, Training, and Evaluating the Model
- In my original model I used:
  - Neurons: 139 
  - Layers: 2
  - Activation Functions: 3(relu and sigmoid twice)
![Original Model](https://github.com/Caracalla1081/Neural_Network_Charity_Analysis/blob/e743a6576c761b2f5b81a6777c9a90829f8a2895/Images/Neurons_Layers_ActivationFunctions.png)

- I was not able to achieve the target model performance. My original model reached an accuracy of 47%
![Original Model Accuracy Score](https://github.com/Caracalla1081/Neural_Network_Charity_Analysis/blob/e743a6576c761b2f5b81a6777c9a90829f8a2895/Images/Original_Test_Model.png)

- Optimization Steps Taken:
  - Attempt One: Added a third hidden layer to the model
![Optimization Attempt One](https://github.com/Caracalla1081/Neural_Network_Charity_Analysis/blob/e743a6576c761b2f5b81a6777c9a90829f8a2895/Images/Model_Optimization_Try_1_Changes.png)
![Optimization Attempt One Results](https://github.com/Caracalla1081/Neural_Network_Charity_Analysis/blob/e743a6576c761b2f5b81a6777c9a90829f8a2895/Images/Model_Optimization_Try_1.png)

  - Attempt Two: Removed additional columns determined to be unnecessary (STATUS and ORGANIZATION)
                 This made it necessary to change the "number_input_features" to 38
 ![Optimization Attempt Two](https://github.com/Caracalla1081/Neural_Network_Charity_Analysis/blob/e743a6576c761b2f5b81a6777c9a90829f8a2895/Images/Model_Optimization_Try_2_Changes_1.png)
 ![Optimization Attempt Two 2](https://github.com/Caracalla1081/Neural_Network_Charity_Analysis/blob/e743a6576c761b2f5b81a6777c9a90829f8a2895/Images/Model_Optimization_Try_2_Changes_2.png)
 ![Optimization Attempt Two Results](https://github.com/Caracalla1081/Neural_Network_Charity_Analysis/blob/e743a6576c761b2f5b81a6777c9a90829f8a2895/Images/Model_Optimization_Try_2.png)

  - Attempt Three: Kept same "number_input_features" and columns from second attempt, but also added a third hidden layer to the model

    ![Optimization Attempt Three](https://github.com/Caracalla1081/Neural_Network_Charity_Analysis/blob/e743a6576c761b2f5b81a6777c9a90829f8a2895/Images/Model_Optimization_Try_3_Changes.png)
    ![Optimization Attempt Three Results](https://github.com/Caracalla1081/Neural_Network_Charity_Analysis/blob/e743a6576c761b2f5b81a6777c9a90829f8a2895/Images/Model_Optimization_Try_3.png)

## Summary
Overall my attempts at creating a binary model to predict a potential charities "IS_SUCCESSFUL" classification proved to be unsuccessul; only obtaining an accuracy score as high as 53% on my third and final attempt.

If I was to recommend using a different model I would try a logistic regression model. I would recommend this because it is my belief that this model is not on a level of complication to require a neural network, also since we are looking at data that be more easily classified if removing more arbitrary columns it would not over power the logistic regression model.
