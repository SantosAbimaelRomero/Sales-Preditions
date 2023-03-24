# Visualization and Modeling of Sales Prices
Perform data visualization on Features and Regression Models on Future Sale Prices of Items

**Santos A. Romero**

# Business Problem
Predicting future sales on specific items for supermarkets and grocery stores.

Trying to find which items sold more than others and why.

# Data
Big Mart Sales Predictions data
https://datahack.analyticsvidhya.com/contest/practice-problem-big-mart-sales-iii/

# Methods For the Visualization / Presentation

## Checked for duplicates
- None Found

## Checked for missing values
- Only two columns had missing values; Outlet_Size and Item_Weight

### Outlet_Size
- Found patterns between "Outlet_Size"/"Outlet_Type"/"Outlet_Location_Type" columns detailed below which allowed me to accurately fill in missing values for the "Outlet_Size" column
>SMALL OUTLET SIZE
>- Tier 2s are always small, grocery stores are always small
>- Tier 1s are mostly small, Supermarket Type 1s are mostly small
>
>MEDIUM OUTLET SIZE
>- Tier 3s are mostly medium, Tier 1s are less likely but can be medium
>- Supermarket Type 2 & 3 are only medium, Type 1s are less likely but can be medium
>
>HIGH OUTLET SIZE
>- Tier 3s are the only highs
>- Supermarket Type 1s are the only highs

### Item_Weight
The Item_Weight column is missing slightly over ~17% of the data if I remove the columns with missing values I'd still have ~83% of the data with accurate values. Given the business problem (trying to predict future sales of specific items) I will opt to remove the rows with missing values in the Item_Weight column. Given that weight can influence price and amount purchased by customers in a grocery store setting, it is best to keep these values accurate and not impute estimations.

## Checked for inconsistencies in data.
- Standardized nomenclature to better organize data. Only necessary in Item_Fat_Content column.

# Methods For Predictive Model
Mostly Similar as I did for the presentation and visuals. (In Progress)
## Checked for duplicates
 None where found

## Checked for missing values
> - Used SimpleImputer for numerical values; instead of removing rows.
> - Found patterns to manually impute values for categorical columns
- Removed Certain Columns
> Certain columns were not useful and would only clutter my predictive model with noise.


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
