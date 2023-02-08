# DWD_Weather_Data_2023

## Prerequisite

pip install wetterdienst
import(wetterdienst)

## Introduction

This project explores the use of weather data in sales forecasts. Weather data can play an important role in accurately predicting sales, as various weather conditions can impact consumer behavior. The project focuses on daily weather data from Germany, with a particular emphasis on the variables of sunshine, temperature, and rainfall. The data is extracted from the Wetterdienst library (API Deutscher Wetterdienst) using the wetterdienst Python library. The project outlines the steps for obtaining and using the weather data, including the creation of monthly weather scores, the selection of weather stations, and the construction of weather classes for each state in Germany. The project concludes with an example of how the weather data can be used to create machine learning features for sales forecasts.

## Background

Weather data has been found to be benefitial in the e-commerce forecasting context.

From Steinker et al. (2017):

"We find that sunshine, temperature, and rain have a significant impact on daily sales, particularly in the summer, on weekends, and on days with extreme weather. Using weather forecasts, we have significantly improved sales forecast accuracy. We find that including weather data in the sales forecast model can lead to fewer sales forecast errors, reducing them by, on average, 8.6% to 12.2% and up to 50.6% on summer weekends."

## Weather Scores

**Rationale**

To make the different months more comparable, I compute relative weather classes, which I refer to as scores. More specifically, I build monthly deciles using data from 2015 to 2022. The weather score expresses the relative classification of a weather parameter on 1 day compared with all of the days in that month across the 15-year estimation sample.

Three main featuers from DWD API: precipitation_height	sunshine_duration	temperature_air_mean_200

**Feature Engeneering**

Temperature: scale 1-10 for each month average
Sunshine: convert into hours /3600
Percipitation: One class for no rain; 9 for rest

## States and Station IDs

There are thousands of weather stations in Germany. I selected 16 in each state. Lastly, I calculated the average of the 16 states to construct weather classes for Germany. 


## References
Steinker, S., Hoberg, K., & Thonemann, U. W. (2017). The value of weather information for e‐commerce operations. Production and Operations Management, 26(10), 1854-1874.

Wetterdienst liberary
https://pypi.org/project/wetterdienst/
