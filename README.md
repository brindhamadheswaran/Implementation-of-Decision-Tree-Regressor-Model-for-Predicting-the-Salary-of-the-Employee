# Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee

## AIM:
To write a program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
```
1.Start the program and import the required Python libraries.
2.Create the dataset containing Position, Level, and Salary, and convert it into a DataFrame.
3.Select Level as the input (X) and Salary as the target/output (y).
4.Create and train a Decision Tree Regressor using the input and target data.
5.Predict salaries for the given levels and predict the salary for a new level such as 6.5.
6.Plot the results using a scatter plot for actual salaries and a line plot for predicted salaries.
7.Display the graph and predicted values, then stop the program.
```

## Program:
```
/*
Program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.
Developed by: BRINDHA.M
RegisterNumber:  212225060038
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
from sklearn.tree import DecisionTreeRegressor
# Step 1: Sample dataset

data = {
    'Position': ['Business Analyst', 'Junior Consultant', 'Senior Consultant',
                 'Manager', 'Country Manager', 'Region Manager',
                 'Partner', 'Senior Partner', 'C-level', 'CEO'],
    'Level': [1, 2, 3, 4, 5, 6, 7, 8, 9, 10],
    'Salary': [45000, 50000, 60000, 80000, 110000, 150000, 200000, 300000, 500000, 1000000]
}

df = pd.DataFrame(data)
# Step 2: Split features and target

X = df[['Level']]     # Feature (Level)
y = df['Salary']      # Target (Salary)

# Step 3: Create Decision Tree Regressor

regressor = DecisionTreeRegressor(random_state=42)
regressor.fit(X, y)
# Step 4: Predict salary for the dataset or new levels

y_pred = regressor.predict(X)
print("Predicted salaries:", y_pred)
# Example: predict salary for a new employee at level 6.5
level = np.array([[6.5]])
predicted_salary = regressor.predict(level)
print(f"Predicted Salary for level {level[0][0]}: {predicted_salary[0]}")

# Step 5: Visualize the results (High-resolution curve)
X_grid = np.arange(min(X.values), max(X.values)+0.01, 0.01)  # High-resolution for smoother curve
X_grid = X_grid.reshape(-1, 1)

plt.scatter(X, y, color='red', label='Actual Salary')
plt.plot(X_grid, regressor.predict(X_grid), color='blue', label='Decision Tree Prediction')
plt.title('Decision Tree Regression: Level vs Salary')
plt.xlabel('Level')
plt.ylabel('Salary')
plt.legend()
plt.show()
*/
```

## Output:
<img width="873" height="76" alt="image" src="https://github.com/user-attachments/assets/d074e530-fdb7-434a-81d8-7fb23b82a204" />
<img width="765" height="557" alt="image" src="https://github.com/user-attachments/assets/481826d8-0578-4dd4-85de-256c9b9197ba" />


## Result:
Thus the program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee is written and verified using python programming.
