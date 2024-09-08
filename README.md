# CSST102-3B

# Linear Regression Model Implementation Report

## Objective
The objective of this lab activity was to build a linear regression model from the ground up to forecast home values based on a few parameters, including age, square footage, number of bedrooms, and proximity to the city center. After processing the given dataset, a model was created, trained, and its effectiveness assessed.

[View the dataset and code here](https://colab.research.google.com/drive/1ygtO0Ijz314ImwuoSxgEDfEq9OIhIfJq?usp=sharing)


---

## 1. Data Preprocessing
Size (sqft), Bedrooms, Age, Proximity to Downtown (miles), and Price (the objective variable) were the five columns that made up the dataset. Among the preprocessing actions were:

1. The dataset is being loaded into a Pandas DataFrame so that its contents may be examined.
2. Checking for missing values: No missing values were found in the dataset, indicating that no additional imputation was required.
3. **Normalizing the features**: In order to guarantee that each feature contributed equally to the model, normalization was required because the features (size, bedrooms, age, and proximity) were on various scales. To scale all features between 0 and 1, `MinMaxScaler` was utilized in this process.

---

## 2. Model Execution
The least squares method was used to create the linear regression model from scratch. The goal of this method is to minimize the sum of squared discrepancies between the expected and actual target values to determine the ideal parameters (slope and intercept). The procedure that was followed was:

1. Including a bias term (a one-column) to take the intercept into consideration.
2. Using the normal equation to derive the model parameters:

   \[
   (X^T X)^{-1} X^T y = w
   \]
   
   where the goal vector is \( y \) and the feature matrix is \( X \).

3. **The parameters that emerged**:
   - **Intercept**: 244,993.29
   - **Slopes** (each characteristic):
     - Area (square feet): 959,235.99
     - Bedrooms: 18,944.81
     - Age: -20,826.23
     - Distance from the center: -28,740.32

---

## 3. Model Training
Two sets of the dataset were created: **training (80%)** and **testing (20%)**. The least squares method was utilized to train the linear regression model after its splitting. Finding the ideal values for the intercept and slopes—which show how the independent variables and the target variable relate to one another—was a key component of the training.

To assess the model's performance, predictions were made on the training and testing sets after it had been trained.

---

## 4. Model Assessment
The **Mean Squared Error (MSE)**, which calculates the average squared difference between actual and predicted values, was used to evaluate the model. The model fits the data better the lower the MSE.

- **Training MSE**: 61,257,971,1112.05
- **Test MSE**: 79,891,617,362.29

The model appears to generalize quite well, although it could be enhanced with more advanced approaches or feature engineering, as indicated by the somewhat greater mean square error on the test data.

Additionally, a regression diagram was created to show the correlation between actual and projected home prices. A good fit was indicated by the regression line, which demonstrated that the model followed the overall trend of the data.

---

## 5. Conclusion 
Without the use of pre-built libraries like Scikit-learn, a basic linear regression model was successfully developed from scratch in this lab assignment. With a comparatively low error rate, the model was able to forecast property prices based on the features supplied. The following deductions were made:

- **Model Fit**: The association between the price of a house and its size, number of bedrooms, age, and proximity to the downtown area was successfully captured by the linear regression model.
- **Feature Importance**: As anticipated, age and proximity to downtown had a negative impact on the price, while house size had the most favorable influence.
- **Limitations**: By incorporating more pertinent features, managing non-linearity, and experimenting with more sophisticated regression methods, the model could be enhanced.

---

## Difficulties Faced
1. **Feature Scaling**: Normalizing the feature values helped to ensure that each feature contributed evenly to the model, which was one of the challenges faced.
2. **Overfitting**: On the test set, the model's error was somewhat greater, suggesting a potential overfit. Using regularization techniques or collecting more varied data could fix this.
3. **Manual Implementation**: To ensure accurate calculations while implementing linear regression manually using the normal equation, careful handling of matrix operations was necessary, particularly when adding the intercept term.

---

Overall, this exercise strengthened comprehension of the principles underlying linear regression and gave useful practice creating and assessing machine learning models from scratch. The model's performance on increasingly complicated datasets can be improved with additional advancements and sophisticated methodologies.
