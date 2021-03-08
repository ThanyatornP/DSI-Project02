# Project 2 - Ames Housing Data and Kaggle Challenge

Project2 - Ames Housing Data and Kaggle Challenge which use a data provided to create a regression model that predicts the price of houses in Ames, Iowa.

### The problem statement is
As a real estate agency based in Ames, in order to help the client (house owner) to estimate their house price decied features to do with their house to increase value of the house:
'If you want to sell your own house, which features could increase the values of your house and which features could drop the values of your house'

### Data Dictionary
Data dictionary of final to 12 features is here:

| Features              |type         |Description                                                          |
| ---                   |---          |---                                                                  |
| grlivarea             |integer      |Above grade (ground) living area square feet                         |
| overallqual           |integer      |Overall material and finish quality (Scale 1-10)                     |
| bsmtfinsf1            |float        |Basement Type 1 finished square feet                                 |
| neighborhood_NridgHt  |object       |Physical locations within Ames city limits (Northridge Heights)      |
| exterqual             |object       |Exterior material quality (Excellent,Good,Average/Typical,Fair,Poor) |
| kitchenqual           |object       |Kitchen quality (Excellent,Good,Average/Typical,Fair,Poor)           |
| neighborhood_StoneBr  |object       |Physical locations within Ames city limits (Stone Brook)             |
| yearbuilt             |integer      |Original construction date                                           |
| garagearea            |integer      |Size of garage in square feet                                        |
| bldgtype_1Fam         |object       |Type of dwelling (Single-family Detached)                            |
| totalbsmtsf           |integer      |Total square feet of basement area                                   |
| saletype_New          |object       |Type of sale (Home just constructed and sold)                        |
| bsmtexposure          |object       |Walkout or garden level basement walls                               |
| miscfeature_Elev	    |object       |Miscellaneous feature not covered in other categories (Elevetor)     |
|roofmatl_ClyTile	    |object       |Roof material made with clay or tile                                 |
    
Full data dictionary for the original Ames housing price dataset [here](https://www.kaggle.com/c/dsi-us-6-project-2-regression-challenge/data).


### Model Selection
In this project we used linear regession, ridge regession, lasso regression and elasticnet regression to find best R2 CV score and RSEM, by select a differenct features to compared score of each model.

This model select features all features from data **without outliers**

As model 4 got lower R2 cross validation score and RMSE in train data compare with model 6 but at this point  model 4 shows that RMSE score in train data and test data in kaggle was closed together, which mean model 4 is not to be overfitted compare to model 6

| Model | Description | R2 CV Score | RMSE on train | RMSE on Kaggle |
| --- | --- | --- | --- | --- |
|Model1: Lasso| Numerical cleaned data with cofficient > 40% | 80.12% | 35108 | 33266 |
|Model2: Lasso| All numerical cleaned data| 80.71% | 34536 | 33425 |
|Model3: Lasso| Encoded and cleaned data with cofficient > 40% | 83.02% | 32453 | 33063 |
|Model4: Lasso| All encoded and cleaned data| 86.34% | 28785 | 27754 |
|Model5: Ridge| Encoded and cleaned data with cofficient > 40% | 85.62% | 25115 | 34358 |
|Model6: Lasso| All encoded and cleaned data| 91.34% | 28785 | 27808 |

### Analysis and Recommendation

In Model 4, lasso regression model was selected as its had best prediction value on house price in AMES shows in Kaggle out perform other linear regression models.  

After increased alpha ny 1500 to elimited the features, afterall we have got final 52 features (if count  same categorical as 1 features it will be final at 39 features) with RMSE in train data at 29403 and on Kaggle at 29377.

**This showing that the final model can predict the house price +- around $29000**

As of lasso was able to reveal which features affect sale price the most.

The validation set errors are then plotted against number of predictors. RMSE appears to stop decreasing significantly from 30 predictors onwards.  
Therefore, for the purpose of having a simpler and more easily interpretable model, look closer at 15 predictors onward RMSE tend to slightly decrese which the top 15 predictors will be used for the interpret the model which are:


|Features|Coefficient|
|---|---|
|grlivarea|3223.872588|
|overallqual|14035.774287|
|bsmtfinsf1|8729.217990|
|neighborhood_NridgHt	|7050.805490|
|exterqual	|6996.110155|
|kitchenqual	|5595.558339|
|neighborhood_StoneBr	|5021.050500|
|yearbuilt	|4839.733343|
|garagearea	|4799.303515|
|bldgtype_1Fam	|4738.694615|
|totalbsmtsf	|4677.522978|
|saletype_New	|4373.543453|
|bsmtexposure	|4130.057381|
|miscfeature_Elev	|-8993.741428|
|roofmatl_ClyTile	|-11156.215150|

![PJ2_RSMEbyFEATURES](https://user-images.githubusercontent.com/76549565/110248082-ebf38780-7fa1-11eb-9065-810ab4434ef4.png)

### Recommendation to steakholders

##### In conclusion the factors the result to house price that owner should consider: 
<ul>
    <li>Above ground living area</li>
    <li>Quality of overall condition </li>
    <li>Age of the house</li>
    <li>House in the area of Northridge Heights, Stone Brook are likely to have a good price</li>
    <li>Size of garage</li>
    <li>House with single family Detached</li>
    <li>Size of the basement</li>
    <li>New constructed house appears to have better sale price</li>
    <li>Size of the basement</li>
    <li>Lot size </li>
    <li>property has significant slope from side to side </li>
</ul> 

##### Value added to the house:  
<ul>
    <li>Renovate basement finished area (if exist)</li>
    <li>Renovate external area of the house</li>
    <li>Renovate kitchen </li>
    <li>Renovate basement with good exposure </li>
</ul> 
    
##### Thing that should avoid:  
<ul>
    <li>Clay or Tile roof material </li>
    <li>Elevator in the house</li>
</ul> 
