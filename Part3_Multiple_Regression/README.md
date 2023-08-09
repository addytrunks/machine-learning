# Building a Model
1. ## All in
    **.** You know that all the variables are required to predict the target/variables 
    
    **.** You are forced to do that

    **.** Preparing for Backward Elimination

2. ## Backward Elimination
    **Step 1:** Select a significant level to stay in the model (_SL_=0.05)

    **Step 2:** Fit the full model with all possible predictors

    **Step 3:** Consider the predictor (dependent variables) with the highest P value. If _P_ > _SL_  go to **Step 4**

    **Step 4:** Remove the predictor

    **Step 5:** Fit the model without this variable

    Keep performing **Step 3** to **Step 5** until the point where the predictor with the highest P value is less than _SL_.

3. ## Forward Elimination
    **Step 1:** Select a significant level to stay in the model (_SL_=0.05)

    **Step 2:** Create a simple regression model for each independent variable. Select the one(regression model) with the lowest P value(of dependent variable).

    **Step 3:** Keeping the selected model, add extra predictors

    **Step 4:** The condition to add the extra predictor is that : _P_   < _SL_.

    Keep repeating this until the P value is greater than the Significant level.