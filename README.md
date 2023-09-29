# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png)  Project 2 - Singapore Housing Data and Kaggle Challenge
---
### Introduction & Problem Statement

The Housing Development Board (HDB) flat is a cornerstone of the Authentic Singaporean Experience (for [78% of us](https://www.singstat.gov.sg/find-data/search-by-theme/households/households/latest-data)). While many of us purchase flats directly from HDB through the Build-to-Order (BTO) exercise, there are some factors which will lead to many others purchasing an HDB flat on the resale market instead.

Because a home purchase is typically the most expensive item that many of us purchase in our lives, it is really important that we pay the right amount for the house, as overpaying for a home can cost us a lot of money, typically in the tens of thousands, or hundreds of thousands of dollars.

However, housing prices are determined by a myriad of factors, and it can get very confusing to understand what is the right value to offer for a home. So, this project will aim to address the issue of predicting the resale value of a house.

The problem statement is:
**<center>Can we accurately predict the resale value of a Housing Development Board (HDB) flat based on various housing-related data?</center>**

The ideal outcome is to provide home buyers with relevant information to understand the drivers of flat resale value, in order to make good home valuation decisions when looking to buy resale flats. This will be done by running a linear regression model with the dependent variable being the resale price of the flat, and the independent variables being the various factors that affect the resale price of the flat.

Success of the model will be determined by the Root Mean Square Error of the model. The lower the RMSE, the better it is at predicting the resale price of a flat given the factors.

The primary audience will be home buyers, and the secondary audience will be housing agents who usually assist and advise home buyers with deciding on the price to offer to the home seller.

---

### Data Dictionary

This dataset contains the data of HDB resale flat transactions from the year 2012 to 2021.

| No. | Column                    | Description                                                                     |
|-----|---------------------------|---------------------------------------------------------------------------------|
| 1   | resale_price              | The property's sale price in Singapore dollars                                  |
| 2   | Tranc_YearMonth           | Year and month of the resale transaction, e.g. 2015-02                          |
| 3   | town                      | HDB township where the flat is located, e.g. BUKIT MERAH                        |
| 4   | flat_type                 | Type of the resale flat unit, e.g. 3 ROOM                                       |
| 5   | block                     | Block number of the resale flat, e.g. 454                                       |
| 6   | street_name               | Street name where the resale flat resides, e.g. TAMPINES ST 42                  |
| 7   | storey_range              | Floor level (range) of the resale flat unit, e.g. 07 TO 09                      |
| 8   | floor_area_sqm            | Floor area of the resale flat unit in square metres                             |
| 9   | flat_model                | HDB model of the resale flat, e.g. Multi Generation                             |
| 10  | lease_commence_date       | Commencement year of the flat unit's 99-year lease                              |
| 11  | Tranc_Year                | Year of resale transaction                                                      |
| 12  | Tranc_Month               | Month of resale transaction                                                     |
| 13  | mid_storey                | Median value of storey_range                                                    |
| 14  | lower                     | Lower value of storey_range                                                     |
| 15  | upper                     | Upper value of storey_range                                                     |
| 16  | mid                       | Middle value of storey_range                                                    |
| 17  | full_flat_type            | Combination of flat_type and flat_model                                         |
| 18  | address                   | Combination of block and street_name                                            |
| 19  | floor_area_sqft           | Floor area of the resale flat unit in square feet                               |
| 20  | hdb_age                   | Number of years from lease_commence_date to present year                        |
| 21  | max_floor_lvl             | Highest floor of the resale flat                                                |
| 22  | year_completed            | Year which construction was completed for resale flat                           |
| 23  | residential               | Boolean value if resale flat has residential units in the same block            |
| 24  | commercial                | Boolean value if resale flat has commercial units in the same block             |
| 25  | market_hawker             | Boolean value if resale flat has a market or hawker centre in the same block    |
| 26  | multistorey_carpark       | Boolean value if resale flat has a multistorey carpark in the same block        |
| 27  | precinct_pavilion         | Boolean value if resale flat has a pavilion in the same block                   |
| 28  | total_dwelling_units      | Total number of residential dwelling units in the resale flat                   |
| 29  | 1room_sold                | Number of 1-room residential units in the resale flat                           |
| 30  | 2room_sold                | Number of 2-room residential units in the resale flat                           |
| 31  | 3room_sold                | Number of 3-room residential units in the resale flat                           |
| 32  | 4room_sold                | Number of 4-room residential units in the resale flat                           |
| 33  | 5room_sold                | Number of 5-room residential units in the resale flat                           |
| 34  | exec_sold                 | Number of executive type residential units in the resale flat block             |
| 35  | multigen_sold             | Number of multi-generational type residential units in the resale flat block    |
| 36  | studio_apartment_sold     | Number of studio apartment type residential units in the resale flat block      |
| 37  | 1room_rental              | Number of 1-room rental residential units in the resale flat block              |
| 38  | 2room_rental              | Number of 2-room rental residential units in the resale flat block              |
| 39  | 3room_rental              | Number of 3-room rental residential units in the resale flat block              |
| 40  | other_room_rental         | Number of "other" type rental residential units in the resale flat block        |
| 41  | postal                    | Postal code of the resale flat block                                            |
| 42  | Latitude                  | Latitude based on postal code                                                   |
| 43  | Longitude                 | Longitude based on postal code                                                  |
| 44  | planning_area             | Government planning area that the flat is located                               |
| 45  | Mall_Nearest_Distance     | Distance (in metres) to the nearest mall                                        |
| 46  | Mall_Within_500m          | Number of malls within 500 metres                                               |
| 47  | Mall_Within_1km           | Number of malls within 1 kilometre                                              |
| 48  | Mall_Within_2km           | Number of malls within 2 kilometres                                             |
| 49  | Hawker_Nearest_Distance   | Distance (in metres) to the nearest hawker centre                               |
| 50  | Hawker_Within_500m        | Number of hawker centres within 500 metres                                      |
| 51  | Hawker_Within_1km         | Number of hawker centres within 1 kilometre                                     |
| 52  | Hawker_Within_2km         | Number of hawker centres within 2 kilometres                                    |
| 53  | hawker_food_stalls        | Number of hawker food stalls in the nearest hawker centre                       |
| 54  | hawker_market_stalls      | Number of hawker and market stalls in the nearest hawker centre                 |
| 55  | mrt_nearest_distance      | Distance (in metres) to the nearest MRT station                                 |
| 56  | mrt_name                  | Name of the nearest MRT station                                                 |
| 57  | bus_interchange           | Boolean value if the nearest MRT station is also a bus interchange              |
| 58  | mrt_interchange           | Boolean value if the nearest MRT station is a train interchange station         |
| 59  | mrt_latitude              | Latitude (in decimal degrees) of the the nearest MRT station                    |
| 60  | mrt_longitude             | Longitude (in decimal degrees) of the nearest MRT station                       |
| 61  | bus_stop_nearest_distance | Distance (in metres) to the nearest bus stop                                    |
| 62  | bus_stop_name             | Name of the nearest bus stop                                                    |
| 63  | bus_stop_latitude         | Latitude (in decimal degrees) of the the nearest bus stop                       |
| 64  | bus_stop_longitude        | Longitude (in decimal degrees) of the nearest bus stop                          |
| 65  | pri_sch_nearest_distance  | Distance (in metres) to the nearest primary school                              |
| 66  | pri_sch_name              | Name of the nearest primary school                                              |
| 67  | vacancy                   | Number of vacancies in the nearest primary school                               |
| 68  | pri_sch_affiliation       | Boolean value if the nearest primary school has a secondary school affiliation  |
| 69  | pri_sch_latitude          | Latitude (in decimal degrees) of the the nearest primary school                 |
| 70  | pri_sch_longitude         | Longitude (in decimal degrees) of the nearest primary school                    |
| 71  | sec_sch_nearest_dist      | Distance (in metres) to the nearest secondary school                            |
| 72  | sec_sch_name              | Name of the nearest secondary school                                            |
| 73  | cutoff_point              | PSLE cutoff point of the nearest secondary school                               |
| 74  | affiliation               | Boolean value if the nearest secondary school has an primary school affiliation |
| 75  | sec_sch_latitude          | Latitude (in decimal degrees) of the the nearest secondary school               |
| 76  | sec_sch_longitude         | Longitude (in decimal degrees) of the nearest secondary school                  |


---

### Methodology

Our methodology is as follows:
1. Cleaning of Data
    1. Handling of null values
    2. Handling duplicated values
    3. Handling data type errors
    4. Handling other data issues
3. Selecting Relevant Features
    1. Creating relevant features
    2. Dropping irrelevant features
5. Initial Modeling and Review
    1. Modeling using Linear Regression
    2. Review of performance
7. Further Feature Selection
    1. Dropping more features based on multicollinearity and relevance
9. Creating Production Model and Evaluation
    1. Modeling using Linear Regression
    2. Modeling using Ridge Regression
    3. Modeling using Lasso Regression
    4. Evaluation of models, choosing of best model for submission

---

### Model Evaluation

We can say that all the models performed quite well, with R2 values around 0.90 and 0.91. Additionally, the difference between the train and test R2 values are small, less than 0.01. The difference between the train and test Root Mean Square Error values are small too. The results are as follows:

| Regression Type            | Train R2 | Test R2 | Root Mean Square Error |
|----------------------------|----------|---------|------------------------|
| Baseline Linear Regression | 0.909    | 0.909   | 43,304.10              |
| Ridge Regression           | 0.909    | 0.909   | 43,319.07              |
| Lasso Regression           | 0.899    | 0.898   | 45,636.67              |


Overall, the baseline linear regression model has the best performance in terms of R2 score and Root Mean Squared Error. Regularisation did not enhance the baseline's predictive performance. When it comes to the submission to Kaggle, I will be using the linear regression.

---

### Recommendations and Next Steps

Overall, we managed to create a strong model with an R2 value of 0.91, which means that 91% of the variation of the resale price of an HDB house can be explained by our model. Also, our Root Mean Square Error is approximately 43,000. This means that on average, our predicted price can vary from the actual price by $43,000.

Based on the heatmap in the previous notebook, we found five main characteristics of an HDB house that would affect its resale value the most.
1. Size of the house - The larger the size of the house, the more expensive it is.
2. The storey of the house - The higher the storey of the house, the more expensive it is.
3. The age of the house when sold - The older the house is when sold, the cheaper it is.
4. Commercial - If the resale flat does not have commercial units in the same block, it is more expensive.
5. Its distance from the nearest MRT station - The nearer it is to an MRT station, the more expensive it is.

While there are many Singapore-specific columns, the 5 that we identified appear to be able to be generalised to other cities and countries as well. 

Going back to the problem statement:
**<center>Can we accurately predict the resale value of a Housing Development Board (HDB) flat based on various housing-related data?</center>**

I'd say that this model can reasonably predict the resale value of a HDB flat, with an error margin of approximately $43,000 on average. 

For our next steps, I'd recommend using this model as a baseline for us to build solutions for our primary and secondary audience (ie. home buyers and housing agents). 

For example, for home buyers who are interested to find out the suggested resale price for a house they are interested to buy, we can have them fill up a form to describe the details of the house they are looking to buy. By filling up the form, it gives us the values for the different independent variables (eg. town, age of house, size of house) that we can put into the model to come up with a suggested price. This suggested price, along with the RMSE, can allow home buyers to decide on the price they would like to offer to the home seller. For example, a desperate buyer can offer a price at the high end of the range, while a buyer who is looking for a bargain can offer a price at the low end of the range. After all, the buying and selling of resale flats is still a very human process.