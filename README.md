# Ames Housing Price Prediction 

## Problem Statement 
In perspective of the home-sellers, we would find comfort in knowing that the potential price for resale is aligned with the market pricing (perhaps better). Using regression analysis, we will attempt to find out the important features that would impact sale prices. This prediction model aims to help home-sellers to maximise the return of investment by fulfilling home-buyers checklist and provide home-sellers a glimpse on what is priority features that can affect the housing price in Ames City. 

--

## Background on Ames City

Ames is a city located in Iowa, United States. In 2020, it has been recorded as the 8th largest city in United States [(Population Review, 2021)](https://worldpopulationreview.com/us-cities/ames-ia-population). 

The population growth has grown steadily to 66,772 in 2021 with about 37% of the population are workers employed in the city [City of Ames, 2019](https://www.cityofames.org/home/showdocument?id=49889). The strategic geography of the state between Intersection I35 and one of US primary east-west highway, Route 30  maintains as economic driver for the city. Route 69 (US primary north-south highway) as well as Union Pacific Railroad (cross-country line) also passes through Ames. It is thriving with businesses like 3M, Barilla, Becker Underwood and more [(City of Ames, 2021)](https://www.cityofames.org/about-ames/about-ames). The city has also increased in population due to the rise of enrollment in Iowa State University (34% increase over the past decade) with potential for more tenancy in this city.

Ames City is also known as the home of Iowa State University. According to the financial report in 2017, top employers in the city is Iowa State University [(Annual Report, 2017)](http://www.cityofames.org/home/showdocument?id=41596). This stablity and resilience is proven in the recession in 2008, Ames as been regarded as one of the 15 cities that has outdone themselves despite the uncertainty [(Bloomberg, 2015)](https://www.bloomberg.com/news/articles/2015-06-22/here-are-the-15-cities-that-have-done-the-best-and-the-worst-since-the-recession). 

--

## Data Dictionary 

|Feature|Type|Dataset|Description|
|---|---|---|---|
|ms_zoning|object|train & test|General zoning classification of the sale| 
|lot_frontage|float| train & test | Linear feet of street connected to property|
|street|object| train & test | type of road access to property|
|land_contour|object| train & test | Flatness of property|
|overall_qual|int| train & test | Rates the overall material and finish of the house (Rating from 1-10)|
|roof_matl|object| train & test | Roof material|
|exterior_1st|object| train & test | Exterior covering on house|
|mas_vnr_type|object| train & test | Masonry veneer type|
|mas_vnr_area|float| train & test | Masonry veneer area|
|foundation|object| train & test | Type of foundation of the house|
|bsmt_qual|int| train & test | Basement height (Rating from 0 - 6)|
|bsmt_exposure|int| train & test | Walkout or garden level walls (Rating from 0-4)|
|bsmtfin_sf_1|float| train & test | Type 1 finished in square feet|
|heating|object| train & test | Type of heating in the house|
|heating_qc|int| train & test | Heating quality or condition|
|central_air|object| train & test | Central air condition (Y or N)|
|gr_liv_area|int| train & test | Above ground living area square feet|
|full_bath|int| train & test | Full bathrooms above ground|
|fireplace_qu|int| train & test | Fireplace quality (Rating from 0-5)|
|garage_type|object| train & test | Garage location|
|garage_finish|int| train & test | Interior finish of the garage (Rating from 0-3))|
|garage_area|float| train & test | Size of garage in square feet|
|wood_deck_sf|int| train & test | Wood deck area in square feet|
|open_porch_sf|int| train & test | Open porch area in square feet|
|sale_type|object| train & test | Type of sale|
|saleprice|int| train & test | Sale price in $|
|age_built|int| train & test | Age of the house since it was built|
|age_remod|int| train & test | Age of the house since it was modified|
|total_sf|float| train & test | Total square feet of the house|
|open_lot|bool| train & test | Location of the house with 3 side frontage|
|common_lot|bool| train & test | Location of the house with 2 side frontage |
|closed_lot|bool| train & test | Location of the house in cul de sac|
|near_park|bool| train & test | Proximity of house near and adjacent to off-site features |
|near_road|bool| train & test | Proximity of house near and adjacent to feeder and arterial street | 

--

## Analysis

3 regression models is trained for the housing saleprice prediction - Linear Regression, Ridge Regression and Lasso Regression. After  
The linear regression model shows a relatively close prediction for the test set. The scores are slightly below the training score, and close to the cross valuation score suggesting an overfitted model. However, the error are average of 3% difference

The LR Train RMSE is \\$25,793 at a much higher given the average saleprices is \\$18,382. This difference is price is attributed from the outliers of highly priced units within the neighborhood.
The residual errors are minimal when predicting houses below \\$400,000. It predicts 
For houses with higher values at \\$600,000 the prediction model undervalues at least \\$150,000, making it unsuitable to predict high valued units. 

In the technical evaluation of this linear regression prediction model, it is predicting with RMSE \\$29,494 (Kaggle Submission) comapred to \\$25,793 during the training set in the model. Nonetheless, it would be better improved with more datas of houses sold above \\$400,000. This existing model is localised for Ames City and further calibration would be required as different region may have different requirements on the housing needs and/or features. 

--


## Conclusion and Recommendation

After modelling of the features affecting the house pricing in Ames city, we find the folowwing top 5 features that adds monetary value in the saleprice. 
1. Wood Shingles Roofing Material
2. House Location near park / other facilities
3. Masonry Veneer with Stone Material 
4. Garages preferred for Built-In 
5. Foundation of the house with Slab 

Meanwhile, features that hurt the valuation of the housing in summary in below list. 
1. Heating System by hot water or steam heating
2. Exterior material made of ply wood, hard board, vinyl sliding, wood sliding 
3. Location of unit exposed on 3 sides.

With these findings, homesellers are able to evaluate their current housing features and make necessary judgement whether to improve some features to bump the final selling price. We recommend several potential upgrades for the homesellers to upgrade / change their existing roofing material to wood shingles. With the modification \\$450 price per square are only, but a huge valuation bump to \\$$77,289. Another easy feature upgrade recommendation would be changing heating systems for example electric heating. It low costs, effective and minimal renovation required. This is especially important change for homesellers existing unit which are hot water/heating heating system. 

Other renovation feature change that home sellers can consider to do is upgrading the exterior materials to cement boards or brick face. Plywood, hard board, vinyl sliding and wood sliding are not in favour. However the negative price impact are close to $8,000. Homesellers can evaluate the necessity for this cost opportunity before making decisions. 

Additional feature that can bump the saleprice is having a wood deck. For every square feet of wood deck built, there is a \\$1,869 rise to the saleprice. Homesellers can evaluate if their existing units are able to accomodation sufficient space for an additional wood deck without compromising other features. 

