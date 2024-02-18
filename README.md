# DM-HW-1
 install the `pandas`, `numpy`, `sickitlearn', and `matplotlib` Python packages if you haven't already, as they are required to run this code:

A few notes about the code:
1. It starts with importing necessary libraries.
2. Loads CSV files into Pandas DataFrames.
3. Creates subsets of the training dataset and saves new CSV files.
4. Defines a function `compute_mse` to compute the training and test MSE.
5. Loops through the datasets, computes MSE for a range of lambda values, and plots the results.
6. Prints the best lambda values for each dataset.
7. Cross-validates to find the best lambda using KFold.
8. Plots the cross-validation MSE.

9. 
1. **Imports:**
   - `numpy` as `np`: Used for numerical operations.
   - `pandas` as `pd`: Used for data manipulation and reading/writing files.
   - `matplotlib.pyplot` as `plt`: Used for creating plots.
   - `Ridge` from `sklearn.linear_model`: Ridge regression model from scikit-learn.
   - `mean_squared_error` from `sklearn.metrics`: Used to calculate MSE.
   - `KFold` from `sklearn.model_selection`: Used for cross-validation.

2. **Loading CSV Files into DataFrames:**
   - Three training datasets and three test datasets are loaded from provided CSV files into pandas DataFrames.

3. **Creating Subsets of the Third Training Dataset:**
   - Training subsets of sizes 50, 100, and 150 are created from the third training dataset (`train-1000-100.csv`), which are then written back out to CSV files.

4. **Reloading Newly Created Datasets:**
   - These new subsets (CSV files) are then reloaded into DataFrames and appended to the list of training datasets.

5. **Defining a Function to Compute MSEs:**
   - A function `compute_mse` is defined to fit a Ridge regression model for a range of lambda values (regularization strengths) and to compute the MSE on both a training set and a test set.

6. **Plotting MSEs and Finding the Best Lambda Value:**
   - For each pair of training and test datasets, the function computes and stores the MSEs. These MSEs are plotted as a function of the regularization parameter lambda.
   - The best lambda value (the one that leads to the lowest MSE on the test set) is recorded for each dataset.

7. **Cross-Validation for Optimal Lambda Selection:**
   - Cross-validation with `KFold` (5 splits) is implemented to find a more robust estimate of the optimal lambda value for selected datasets.
   - The MSEs from cross-validation are plotted as a function of lambda.

**Key Points:**

- Ridge regression is used to prevent overfitting by adding a penalty proportional to the square of the magnitude of coefficients (L2 penalty). The `alpha` parameter in Ridge indicates the strength of this penalty.
- The code compares both training and test MSEs for different datasets, which allows for evaluation of how the model generalizes to unseen data.
- Cross-validation is used to estimate the model's performance more reliably by dividing the dataset into training and validation subsets multiple times.
- The mean squared error is used as a performance metric, representing the average of squared differences between the predicted values and actual values.
