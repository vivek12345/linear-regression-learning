# Linear Regression Learning - Google Colab Notebook

## Overview
This Google Colab notebook demonstrates the fundamentals of linear regression using Python. The project explores the relationship between performance length and tip amount, providing a hands-on introduction to regression analysis concepts.

## What You'll Learn
- **Linear Regression Basics**: Understanding how to fit a straight line to data points
- **Least Squares Method**: Using `np.polyfit()` to find the best-fit line
- **Error Analysis**: Calculating and visualizing prediction errors
- **Sum of Squares Error (SSE)**: Measuring model performance
- **Data Visualization**: Creating scatter plots with regression lines and error visualization

## Code Breakdown

### Data Fitting and Visualization
```python
# Fit a linear regression line using numpy's polyfit
m, b = np.polyfit(x_new, y_new, 1)  # Returns slope (m) and y-intercept (b)

# Plot the regression line
plt.plot(x_new, m*x_new+b, "-r")

# Plot the original data points
plt.scatter(x_new, y_new)
```

### Error Visualization
```python
# Draw vertical lines showing the error (residuals) for each data point
for i in range(len(x_new)):
  plt.plot([x_new[i], x_new[i]], [y_new[i], m*x_new[i]+b], "r--")
```

### Error Calculation
```python
# Calculate prediction errors (residuals)
errors = y_new - (m*x_new+b)

# Calculate Sum of Squares Error (SSE)
sse = np.sum(errors**2)
print(f'Sum of Squares of Errors (SSE): {sse}')
```

## Key Concepts Explained

### Linear Regression Equation
The line of best fit follows the equation: **y = mx + b**
- `m`: Slope of the line (rate of change)
- `b`: Y-intercept (value when x = 0)

### Sum of Squares Error (SSE)
SSE measures how well the regression line fits the data:
- **Lower SSE** = Better fit
- **Higher SSE** = Poorer fit
- Calculated as: SSE = Σ(actual - predicted)²

### Residuals
The vertical red dashed lines in the plot represent residuals - the difference between actual data points and predicted values from the regression line.

## Dataset
- **X-axis**: Performance Length (units: presumably minutes or hours)
- **Y-axis**: Tip Amount (units: presumably dollars)
- **Relationship**: Analyzing how performance duration affects tip amounts

## Requirements
```python
import numpy as np
import matplotlib.pyplot as plt
```

## How to Use
1. Open the notebook in Google Colab
2. Ensure you have your data loaded into `x_new` and `y_new` variables
3. Run each cell sequentially to see the regression analysis in action
4. Experiment with different datasets to see how the regression line and SSE change

## Learning Outcomes
After completing this notebook, you should understand:
- How linear regression finds the "best fit" line through data points
- The meaning and calculation of prediction errors
- How to interpret Sum of Squares Error as a measure of model quality
- Basic data visualization techniques for regression analysis

## Next Steps
Consider exploring:
- Multiple linear regression with more variables
- Polynomial regression for non-linear relationships
- R-squared values for model evaluation
- Cross-validation techniques
- Different regression algorithms (Ridge, Lasso, etc.)

---
*This notebook serves as an introduction to regression analysis concepts. For more advanced topics, consider exploring scikit-learn's regression modules.* 