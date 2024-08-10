### Capstone: Food Demand Forecasting

**Niranjan Dhomse**

#### Executive summary
A meal delivery company which operates in multiple cities via various fulfillment centers for dispatching meal orders to their customers. The client wants you to help these centers with demand forecasting for upcoming weeks so that these centers will plan the stock of raw materials accordingly.

#### Rationale
Without proper demand forecasting processes in place, it can be nearly impossible to have the right amount of stock on hand at any given time.
A food delivery service has to deal with a lot of perishable raw materials which makes it all the more important for such a company to accurately forecast daily and weekly demand.
Too much inventory in the warehouse means more risk of wastage, and not enough could lead to out-of-stocks

#### Research Question
Given the historical data of demand for a product-center combination (Weeks: 1 to 145), the task is to predict the demand for the next 10 weeks (Weeks: 146-155) for the center-meal combinations in the test set.

#### Data Sources
Analytics Vidhya runs hackathons for various ML problems. This data is sourced from their site: 
[Food Demand Forecasting](https://datahack.analyticsvidhya.com/contest/genpact-machine-learning-hackathon-1/#ProblemStatement) 

The input data contains the following:
* Historical data of demand for a product-center combination (Weeks: 1 to 145)
* Product(Meal) features such as category, sub-category, current price and discount
* Information for fulfillment center like center area, city information etc.

#### Methodology

* Time Series techniques using sktime, LinearRegression, XGBoost, Random Forest

#### Results / Findings

* The number of orders distribution is very right skewed. Which means we found a number of outliers with large number of orders. Although the max number of orders is 24299, less than 0.75% of the instances have values > 2000, the median value is only 136 and 75% of the values are 324 or less
* Beverages category orders comprise 28% of all occurrences and is at least 4x the other categories
* Even though 57% of the order occurrences are from TYPE_A centers, TYPE_B generates more orders on average
* Lower prices clearly attract more orders
* Thai cuisine has about 25% more meal options than other cuisines. However, Italian cuisine seems to be more popular and generates the highest number of orders on average
* Emailer and Homepage promos result in 3x orders on average
* Larger Op Areas generate larger number of orders on average


#### Next steps and recommendations

Recommend working with the business and tech team to look at `skforecast` and `sktime` frameworks and perhaps the `Prophet` model to figure out how the models could be trained on a hierarchical multi-series dataset and forecast using all the available features in the dataset
From business perspective, following recommendations could help the business grow its orders,
* Leveraging the emailer and homepage promos
* Further including looking at other modes/channels of advertising 
* Review and publicize any discounts and promotions that will reduce the prices for the consumers
* Review what is making the TYPE_B centers generate higher orders and implement for other center types
* Review what is making the Italian cuisine offerings generate higher orders and see if some elements could be enhanced for other cuisines. Also, review the possibility of enhancing the Italian menu further


#### Outline of project
* Work done for the complete analysis including statistics, observations, and visualizations available in:

- [Jupiter Notebook used](https://github.com/ndhomse/food-demand-forecasting/blob/main/notebook/Food-Demand-Forecasting.ipynb)
- Detailed presentation of the project can be found at [Project Presentation](https://github.com/ndhomse/food-demand-forecasting/blob/main/presentation/Food-Demand-Forecasting-Report.pdf)

