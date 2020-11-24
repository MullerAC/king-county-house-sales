# King County House Sales Linear Regression
Linear Regression Modeling on King County House Sales data

### Group Members
- Andrew Muller
- Asher Khan

## Business Case
We will predict how much a house should be sold for in order to determine whether a house on the market is being underpriced or overpriced. Our clients are homeowners looking to sell their house, but do not know how much to sell their house for.

## Data Analysis
We were given information on the column in the column_names.md file. After turning all the data into numerical data types, we handle any NaN values and create a few new features: 'yr_since_renovation', 'yr_since_built', and 'renovated'. We then drop unneeded features: 'view', 'sqft_above', 'sqft_living15', 'sqft_lot15', and 'date'.

With the data cleaned, we start to analyze it. Scatter plots of each variable against our target, price, show which of our variables have obvious linear relationships. Insignificant relationships will be taken care of when we start looking at the p-values of our coefficients, so they don't need to be handled now. This also makes clearer which variables are categorical and which are continuous.
![scatterplots](/figures/scatter-plots.png)

Histograms show us that none of our variables are normally distributed. None of them are, so we will need to log transform them later.
![histograms](/figures/histogram-plots.png)

We look at colinear features using a heatmap and decide to remove the 'yr_built', 'yr_renovated', 'price', 'yr_sold', and 'yr_since_renovation' columns.
![heatmap](/figures/heatmap-before.png)

## Model
Our baseline model had the following metrics:
- R2 of 0.821
- adjusted R2 of 0.820
- Train RMSE of 157156
- Test RMSE of 139700
- 81 significant features (p-value < 0.05)
- 103 features total

![baseline-qq](figures/baseline-qq-plot.png)

To improve on our model, we took the folowing steps:
- dropped colinear features ()
- removed outliers from our datasets
- log transformed applicable continuous features
- eliminated insignificant features (p-value < 0.05)

Our final model has the following metrics:
- R2 of 0.857
- adjusted R2 of 0.856
- Train RMSE of 103086
- Test RMSE of 99701
- 90 significant features (p-value < 0.05)
- 90 features total

![final-qq](figures/final-qq-plot.png)

We also performed cross-validation and constructed a residuals plot to verify that our final model is accurate.
![final-residuals](figures/final-residuals-plot.png)

## Conclusions
todo
