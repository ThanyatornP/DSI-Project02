# Project 2 - Ames Housing Data and Kaggle Challenge

Project2 - Ames Housing Data and Kaggle Challenge which use a data provided to create a regression model that predicts the price of houses in Ames, Iowa.

### The problem statement is
As a real estate agency based in Ames, in order to help the client (house owner) to estimate their house price decied features to do with their house to increase value of the house:
'If you want to sell your own house, which features could increase the values of your house and which features could drop the values of your house'

### Data Dictionary
Data dictionary of final to 20 features is here

Data dictionary for the final set of features.

| Features              |type         |Description                                                          |
| ---                   |---          |---                                                                  |
| grlivarea             |integer      |Above grade (ground) living area square feet                         |
| overallqual           |integer      |Overall material and finish quality (Scale 1-10)                     |
| bsmtfinsf1            |float        |Basement Type 1 finished square feet                                 |
| yearbuilt             |integer      |Original construction date                                           |
| exterqual             |object       |Exterior material quality (Excellent,Good,Average/Typical,Fair,Poor) |
| kitchenqual           |object       |Kitchen quality (Excellent,Good,Average/Typical,Fair,Poor)           |                                                          
| neighborhood_NridgHt  |object       |Physical locations within Ames city limits (Northridge Heights)      |
| totalbsmtsf           |integer      |Total square feet of basement area                                   |
| garagearea            |integer      |Size of garage in square feet                                        |
| lotarea               |integer      |Lot size in square feet                                              |
| fireplacequ           |object       |Fireplace quality (Excellent,Good,Average/Typical,Fair,Poor)         |
| bsmtexposure          |object       |Walkout or garden level basement walls                               |
| functional            |object       |Home functionality rating                                            |
| saletype_New          |object       |Type of sale (Home just constructed and sold)                        |
| neighborhood_NoRidge  |object       |Physical locations within Ames city limits (Northridge)              |
| 1stflrsf              |integer      |First Floor square feet                                              |
| bldgtype_1Fam         |object       |Type of dwelling (Single-family Detached)                            |
| overallcond           |integer      |Overall condition rating (Scale 1-10)                                |
| yearremod/add	        |integer      |Remodel date (same as construction date if no remodeling or additions)|
| landcontour_HLS       |object       |Flatness of the property (Significant slope from side to side)       |
    
Full data dictionary for the original Ames dataset [here](https://www.kaggle.com/c/dsi-us-6-project-2-regression-challenge/data).


### Model Selection
In this project we used linear regession, ridge regession, lasso regression and elasticnet regression to find best R2 CV score and RSEM, by select a differenct features to compared score of each model.

Lasso regression of model 6 features has the best R2 CV score yet at 91.36%. With 120 non-zero coefficients features now, which it is too complex to explain.
So we have increase alpha to 1500 to decrese features to 47,which it is now more ideal and easy to explain featues that relevant to stakeholders. Ideally we would always want to have a model that is complex enough to fit all the points but still having enough simplicity to explain your model.

### Analysis and Recommendation
In Model 6, lasso regression model was selected as its had best prediction value on house price in AMES out perform other linear regression models.  

As model 6 got better score at this point with R2 score of 0.9138145738322001 and RSME in test data on kaggle is 28588.51095.  

with R2 cossvalidation score at 91.38%

This showing that thai model can predict the house price +- around $28000

As of lasso was able to reveal which features affect sale price the most.

Therefore, for the purpose of having a simpler and more easily interpretable model, the top 20 predictors will be used for the interpret the model which are:

| Features | coef |
| --- | --- |
| grlivarea | 18389.231190 |
| overallqual | 13801.084197 |
| bsmtfinsf1 | 7977.693521 |
| yearbuilt | 5681.509935 |
| exterqual | 5645.198910|
| kitchenqual | 4870.495420 |
| neighborhood_NridgHt | 4569.173849 |
| totalbsmtsf | 3841.539208 |
| garagearea | 3728.459323 |
| lotarea | 3206.535611 |
| fireplacequ | 2841.643622 |
| bsmtexposure | 2750.224952 |
| functional | 1925.715326 |
| saletype_New | 2623.424833|
| neighborhood_NoRidge | 2617.704679 |
| 1stflrsf | 2048.731244 |
| bldgtype_1Fam | 2016.998752 |
| overallcond | 1985.514504 |
| yearremod/add	| 1944.957227 |
| landcontour_HLS | 1795.868018 |


### Recommendation to steakholders

##### In conclusion the factors the reslut to house price that owner should consider: 
<ul>
    <li>Above ground living area</li>
    <li>Size of garage</li>
    <li>Size of the basement</li>
    <li>Quality of overall condition </li>
    <li>House in the area of Northridge Heights is likely to have a good price</li>
    <li>Age of the house</li>
    <li>Size of the basement</li>
    <li>Lot size </li>
    <li>property has significant slope from side to side </li>
    <li>Basement with good exposure </li>
    <li>New constructed house appears to have better sale price</li>
    <li>house with family Detached</li>
</ul> 

##### Value added to the house:  
<ul>
    <li>Renovate kitchen </li>
    <li>Renovate external area of the house</li>
    <li>Renovate basement finished area (if exist)</li>
    <li>Quality of overall condition </li>
    <li>House in the area of Northridge Heights is likely to have a good price</li>
    <li>Renovate fire place (if exist)</li>
    <li>Quality of overall condition </li>
    <li>House in the area of Northridge Heights is likely to have a good price</li>
    <li>Improve home functional quality</li>
</ul> 
