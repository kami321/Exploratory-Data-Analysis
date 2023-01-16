# Exploratory-Data-Analysis

Author: Yinhui(Kami) Yang

## Introduction of the Data

Flight delays might cause a lot of inconvenience. Customers would not want to waste precious vocation or work time by waiting for hours at a busy airport. That is the purpose for this exploratory data analysis on this United Airlines (carrier code UA) dataset. The main focus is to improve both efficiency and customer satisfaction.

In this study, I would find out what causes departure/arrival delays. Are delays growing better or worse with different time of the day? Is there a relationship between departure delays and the time of year? Does the visibility, wind speed, weather temperature, and precipitation affect airplane ability to arrive on time?

## Background Information on the datasets

The nycflights13 package contains on-time information data for all flights that departed NYC (i.e. JFK, LGA or EWR) in the year of 2013.

Goal: To use exploratory data analysis methods that we have been studying, and permutation tests, to analyze departure delays with a unique carriers United Airlines (carrier code UA)

### 1. Are delays growing better or worse with different time of the day?

![unnamed-chunk-6-1](https://user-images.githubusercontent.com/81647911/212738780-23f6bf4b-da65-4e14-bfee-7e3974e93834.png)

The data is skewed to the right, with a mean departure delay of roughly 10 minutes. We can also notice some negative numbers, which signify both early departures and exceptionally long departure delays.

![unnamed-chunk-7-1](https://user-images.githubusercontent.com/81647911/212738865-04605ec6-3012-4e18-b199-963bbb013989.png)

We can observe from the above boxplots that the median departure delay is nearly the same for all times of the day, which is around 0 with some outliers. The IQR in the evening is higher. So we could see there is early departures are more common in the morning and at night. To investigate if there is a relationship between departure delays and time of day, we will do two-sided permutation tests. The null hypothesis is that there is no difference in departure delays. The alternative theory is that there is a genuine difference between different times of the day. Next, we will run permutation test and then use histograms show us the result as below.

![unnamed-chunk-8-1](https://user-images.githubusercontent.com/81647911/212739002-045d350e-565a-4637-9dce-749387ff1e13.png)

Permutation test result for Morning (06:00 - 11:59)  vs. Afternoon (12:00 - 17:59) :[1] 2e-04

