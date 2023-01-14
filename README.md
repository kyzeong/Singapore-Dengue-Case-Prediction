# SG-DSIF-7 Project 4
# Group: 3
# Students name:
    1. Jance Ng
    2. Jin Min Wood
    3. Adrian Kong

### Problem Statement

Total number of Dengue cases from year 2017 to 2020 has increased from 2,767 to 35,266. Dengue fever is a mosquito-borne illness that occurs in tropical and subtropical areas of the world. Mild dengue fever causes a high fever and flu-like symptoms. The severe form of dengue fever, also called dengue hemorrhagic fever, can cause serious bleeding, a sudden drop in blood pressure (shock) and death.
As a part of the data science team in National Environmental Agency (NEA) Singapore, we are tasked to predict of dengue cases in Singapore so that NEA can decide when and where to perform vector control such as pesticide spraying. Besides prediction of dengue cases, we are also looking into the cost-benefit analysis of pesticide spraying to maximize the benefit and lower the cost.

---

### Assumptions

Aedes mosquitoes prefer to breed in clean, stagnant water such as flower vases, flower pot plates, roof gutters, earthen jars for water storage or decorative purposes, watering cans, and bamboo pole holders. Many of the breeding sites mentioned accumulate stagnant water easily especially when there it is raining. Therefore, the breeding of Aedes mosquitoes indirectly linked to th weather. Hypothetically, we could predict the number of dengue cases with weather data.

Besides weather data, we could also make use of Google trend in various search term to predict number of dengue cases. The logic behind this is people usually Google search the sypmtoms when they are suspecting they have any disease.

Based on the problem statement and assumptions, we will generate regression model to predict the number of dengue cases.

---

### Data

The data is collected from a few sources as listed below.

* Singapore daily climate historical data ([source](http://www.weather.gov.sg/climate-historical-daily/))
* Google trend of various search term ([source](https://trends.google.com/trends/explore?date=today%205-y&geo=SG&q=%2Fm%2F09wsg))
* Dengue clusters in Singapore ([source](https://outbreak.sgcharts.com/data))

---

### Data Dictionary

|Feature|Type|Dataset|Description|
|:---|:---|:---|:---|
|**date**|*datetime*|weather|Date when the records were taken| 
|**daily_rainfall_total**|*float*|weather|Total daily rainfall in mm|
|**highest_30_min_rainfall**|*float*|weather|Highest 30min rainfall in mm|
|**highest_60_min_rainfall**|*float*|weather|Highest 60min rainfall in mm|
|**highest_120_min_rainfall**|*float*|weather|Highest 120min rainfall in mm|
|**mean_temperature**|*float*|weather|Mean temperature in °C|
|**maximum_temperature**|*float*|weather|Maximum temperature in °C|
|**minimum_temperature**|*float*|weather|Minimum temperature in °C|
|**mean_wind_speed**|*float*|weather|Mean wind speed in km/h|
|**max_wind_speed**|*float*|weather|Maximum wind speed in km/h|
|**year**|*float*|weather|Year when the records were taken|
|**region**|*string*|weather|Region where the records were taken|
|**aedes**|*float*|google_trend|Number of searches in this term on Google|
|**dengue**|*float*|google_trend|Number of searches in this term on Google|
|**fever**|*float*|google_trend|Number of searches in this term on Google|
|**headache**|*float*|google_trend|Number of searches in this term on Google|
|**nosebleed**|*float*|google_trend|Number of searches in this term on Google|
|**vomit**|*float*|google_trend|Number of searches in this term on Google|

---

### Summary

After cleaning and merging the data from different sources into 1 dataset, we began the modelling. 

We fitted 4 different regression models: 
1. Linear Regression
2. Support Vector Regression
3. Random Forest Regression
4. XGBoost Regression

XGBoost is selected as our final model as this model outperforms the other models that we have tried. The XGBoost model attained the lowest RMSE (15.20) out of all the models and also outperformed the baseline model (RMSE = 28.92). 

---

### Conclusion
Historically, the top three estates with the most number of dengue cases are:
1. Chai Chee
2. Ang Mo Kio
3. Tai Seng


The factor that most likely to affect the number of dengue case are the regions. This could be due to the population density at the regions. For improvement in the future, we could possibly add in data on population density such that we are able to get the % of case/population of each region.  



Number of cases per fortnight to justify cost of fumigation = 25

---

### Recommendation
1.
2.
3. To engage fumigation service only when there are more than 25 cases per fortnight

