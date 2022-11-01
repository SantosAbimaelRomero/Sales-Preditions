# Visualization and Modeling of Sales Prices
Perform data visualization on Features and Regression Models on Future Sale Prices of Items

**Santos A. Romero**

# Business Problem
Predicting future sales on specific items for supermarkets and grocery stores.

# Data
Big Mart Sales Predictions data
https://datahack.analyticsvidhya.com/contest/practice-problem-big-mart-sales-iii/

# Methods
For Predictive Model
- Checked for duplicates
- Checked for missing values
> - Used SimpleImputer for numerical values
> - Found patterns to manually impute values for categorical columns
- Removed Certain Columns
> Certain columns were not useful and would only clutter my predictive model with noise.
For the Visualization /Presentationfile
- Checked for duplicates
- Checked for missing values
> - Found patterns to manually impute values for categorical columns
> - Dropped Numerical Column as was not needed for Visualizations
- Checked for inconsistencies in data.
> - Renamed certain values so organize data

# Visualizations
I compared multiple features for correlation and patterns with total outlet sales.

![Distribution of Sales by Outlet Size](https://user-images.githubusercontent.com/112634963/199135169-b4dc908f-2737-4980-9fcb-86df17a47955.png)

![Distribution of Sales by Item Fat Content](https://user-images.githubusercontent.com/112634963/199135215-6c09dbd6-aea5-40a5-bea8-f69ae8e6f29a.png)

Most features I visualized with total outlet sales display the same pattern of a high count of items making relatively low total sales, with fewer
and fewer items making significant sales individually.


# Model
For the predictive model I recommend a `Linear Regression` model.

My reasoning resides on how it performed against a Random Tree Regression Model.
The Random Tree Regression model kept overfitting even after I made adjustments by a significant margin.
The closer I tried make the R2 scores for the Training data and Test data, the worse the score had to get.
On the heatmap in my Predictions file you can see there is very little correlation with any of the numerical columns
The categorical columns don't assist much in putting it all together, ultimately just creating too much noise for the 
Tree Regression Model to effectively work with other forms of data.

The linear regression model managed to keep the R2 scores close together and overall higher than when the same was 
accomplished with the Tree Regression Model.

## Contact information
If there are any more questions or concerns regarding my data, feel free to contact me: saromerg@gmail.com
