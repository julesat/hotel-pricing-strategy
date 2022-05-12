## Business Fundamentals Project:
Hotel Pricing Optimization Strategy

### Abstract

Hotels have faced historic challenges in the past few years, but companies’ ability to make use of available data may mitigate some of the financial burden. In this project I investigated recent hotel booking data, looked for evidence that revenue could be further optimized, and introduce a dynamic pricing solution path for a hotel company.

### Design

#### Business Problem:
The travel industry was hit heavily by the pandemic, [shrinking by 42%](https://www.ustravel.org/toolkit/covid-19-travel-industry-research) from 2019 to 2020. At the same time, hotels have faced increasing competition from Airbnb. Faced with rapidly-changing economic conditions, and in competition with flexible short-term Airbnb rentals, hotels have an opportunity to implement dynamic pricing to their advantage.
	Although dynamic pricing systems are already commonplace in the hotel industry, there is still a gap between [available and adopted methodology](https://www.sciencedirect.com/science/article/abs/pii/S0261517719300627). My goal for this project is to support a small to medium-sized hotel company with optimizing revenue as travel patterns begin to recover. 
  
#### Impact Hypothesis:
Dynamic pricing will add a competitive advantage to a medium-sized hotel, increasing revenue with low overhead.	

#### Solution Paths:

Possible alternative paths to increase revenue include:
- forecasting meals, special requests etc to more accurately manage staff hours and food service orders
- customer segmentation for targeted marketing 
- static pricing based on Airbnb & other hotel rates, plus client’s historical bookings data
      
Proposed solution path:
- create a model of revenue based on historical data, to predict revenue using the current pricing strategy, taking into account booking features such as room type, time of year, meals, number of guests, length of stay, and market segment
- experiment with a range of product prices around the historical average, generating data to model price elasticity of demand
- include price elasticity in the regression model to optimize dynamic price recommendations

#### Measures of Success:

Technical:

For the two modeling steps, I would compare error and R2 scores across a few different ML models, but a reasonable option might be a boosted tree regressor with a squared error loss function.

Non-technical:

The implementation would be successful if revenue increases over the predicted value – realistically we can aim for a [5-10%](https://www.mckinsey.com/industries/retail/our-insights/how-retailers-can-drive-profitable-growth-through-dynamic-pricing) sustainable increase in revenue.

#### Risks and Assumptions:
	
It will be important to include constraints on price optimization, factoring in costs, hotel capacity, and reasonable rates. There is a risk of customer dissatisfaction if the variation in rates is too large, but dynamic pricing is generally accepted in the airline and hotel industries. It is also necessary to be cautious about segmenting rates in any way that risks discrimination in pricing.

The project timeline includes collecting more data to determine the price elasticity of demand for the hotel rooms, which involves the exploitation vs. exploration tradeoff. While collecting data, the company may lose out on available revenue, but the experiments could be brief and separated in time to avoid impacting future sales. 

### Data

I downloaded a Kaggle dataset (originally published in [Data in Brief](https://www.sciencedirect.com/science/article/pii/S2352340918315191)) of historical hotel booking data from slightly more than two years from two hotels in Lisbon, Portugal, as a stand-in for more recent data that would be shared by a hotel client. Filtered down to uncanceled bookings, this dataset contained over 70,000 rows representing individual bookings, and 32 columns representing the reservation type, date, lead time of booking, and other features that applied to the hotel room and stay. 

For analysis, I restricted the date range to two years (August 2015 - 2017) that seemed to be unaffected by the limits of the data collection time window. 
  
### Tools

To explore the data and design a solution path, I first used SQL to filter out canceled bookings, and added date columns. In Excel, I added a column for an exploratory look at pricing data with seasonal effects subtracted. I used Python/pandas to calculate the number of guests present on each day, and did most of the exploratory visualizations in Tableau.

### Communication

The results of exploratory analysis will be presented in a slide deck and shared on a [Tableau dashboard](https://public.tableau.com/views/Hotelbookings_16468721857690/EDA).
