# Visualization and Modeling of Sales Prices
Perform data visualization on Features and Regression Models on Future Sale Prices of Items

**Santos A. Romero**

# Business Problem
Predicting future sales on specific items for supermarkets and grocery stores.

Trying to find which items sold more and finding any reason as to why.

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
>**SMALL OUTLET SIZE**
>- Tier 2s are always small, grocery stores are always small
>- Tier 1s are mostly small, Supermarket Type 1s are mostly small
>
>**MEDIUM OUTLET SIZE**
>- Tier 3s are mostly medium, Tier 1s are less likely but can be medium
>- Supermarket Type 2 & 3 are only medium, Type 1s are less likely but can be medium
>
>**HIGH OUTLET SIZE**
>- Tier 3s are the only highs
>- Supermarket Type 1s are the only highs

### Item_Weight
The Item_Weight column is missing slightly over ~17% of the data if I remove the columns with missing values I'd still have ~83% of the data with accurate values. Given the business problem (trying to predict future sales of specific items) I will opt to remove the rows with missing values in the Item_Weight column. Given that weight can influence price and amount purchased by customers in a grocery store setting, it is best to keep these values accurate and not impute estimations.

## Checked for inconsistencies in data.
- Standardized nomenclature to better organize data. Only necessary in Item_Fat_Content column.

# Visualizations
I compared multiple features for correlation and patterns with total outlet sales. Below is a comparison between items with low fat content vs regular fat content across all outlet types.

![Low Fat Content Sales](https://user-images.githubusercontent.com/112634963/228052570-9bca69c7-4c12-4909-a689-7a30a6d7a29d.png)
![Regular Fat Content sales](https://user-images.githubusercontent.com/112634963/228052587-d686f86b-1793-4b6f-b140-29c49fb2a40e.png)


Here we see a similar trend between low fat items and regular fat items and how much in sales they achieved across all grocery stores and supermarkets. Very few items made large amounts of sales individually.
Most items made from ₹0 to ₹4,000 but regular fat items do have a slightly greater median as well as a much greater top end where the highest selling low fat items peak at about ₹9,000 but for regular fat items it peaks at around ₹10,000.


# Conclusions Based on Visuals

Small outlets have the greatest selection of items, despite any individual item producing less sales than in medium and high outlets, it still produces the greatest amount of total sales overall simply out of the sheer volume of items. (₹8,779,049 in sales)

---
Medium outlets have the second largest selection of items, it also has more expensive items and items that can produce greater total sales individually than items in small outlets. It comes as a close second making a about ₹1,500,000 less than small outlets. (₹4,035,793 in sales)

---
High outlets have the smallest selection of items and produces the smallest total sales by a large margin than small and medium outlets. Despite have high value items than can consistenly make more sales individually than the other two outlet sizes, it produces a notable ~₹5,000,000 less in total sales than medium outlets and ~₹6,800,000 less than small outlets. (₹2,142,664 in sales)

---
Just based on what I found through my visualizations, what makes the most sales are the small outlets due to their massive variety of items. I also saw that despite there being much more low fat items, low fat items still had about the same amount of sales as regular fat items. So in order to get the greatest amount of sales an outlet must have a large variety of relatively low cost items while focusing more on regular fat items as they get the most sales. While if any low fat items are to be sold, they would need much more quantity and variety to get about the same amount of sales as regular fat items sold with lesser variety and lesser quantity.

# For Prediction Model

## Data Preparation
### Checked for duplicates
- None Found

### Checked for missing values
- Only two columns had missing values; Outlet_Size and Item_Weight
- I filled in the Outlet_Size feature missing values the same way as for the visualizations.
- I also removed the rows missing values in the Item_Weight feature exactly as I did for the visualizations.

## Model
I first tested a `Linear Regression` model.
>**R2**
>
>This model can only account for little more than 56% of the data. Which is not a good sign for a useful model as it only accounts for little more than half the data.
>
>**MAE / RMSE**
>
>Looking at the MAE and RMSE, they are about ₹200 to ₹300 apart. This means there aren't many large errors for RMSE to punish, but we still have an error margin of ~₹800 to ~₹1,100 from our models predictions to the actual reported total outlet sales of any given item. Which in the context of the " Item_Outlet_Sales " column, which is our target vector, that is a very large amount. In some cases, the model is potentially doubling the predicting sales of an item. So, despite the MAE and RMSE being seemingly close together, the actual values they hold are far too large for me to recommend this model.

Next I tested a `Random Forest Regression` Model.

>The Random Forest Regression model kept overfitting even after I made large adjustments. The closer I tried make the R2 scores for the Training data and Test data, the worse the score became. On the heatmap below, you can see there is very little correlation with any of the numerical columns. The categorical columns don't assist much in putting it all together, ultimately just creating too much noise for the Tree Regression Model to effectively work with other forms of data after fitting with the training data.
![Numeric Column Heatmap](https://user-images.githubusercontent.com/112634963/228395714-4f9578d6-0925-4b78-a752-2aed4138918e.png)

>I tested the model with reduced features to those only with reasonable correlations but that only made the model worse.

## Contact information
If there are any more questions or concerns regarding my data, feel free to contact me: saromerg@gmail.com
