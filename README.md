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

![unnamed-chunk-8-2](https://user-images.githubusercontent.com/81647911/212739176-ef77c144-8425-4b6a-8014-86c2d2c321e4.png)

Permutation test result for Morning (06:00 - 11:59)  vs. Evening (18:00 - 23:59) :[1] 2e-04

![unnamed-chunk-8-3](https://user-images.githubusercontent.com/81647911/212739285-18b1780e-e878-49dd-ac7f-a7db32aa1b54.png)

Permutation test result for Morning (06:00 - 11:59)  vs. Night (24:00 - 05:59) :[1] 0.0012

![unnamed-chunk-8-4](https://user-images.githubusercontent.com/81647911/212739290-e6d2b7bb-d774-4ed2-820b-ccd06cf5b625.png)

Permutation test result for Afternoon (12:00 - 17:59)  vs. Evening (18:00 - 23:59) :[1] 2e-04

![unnamed-chunk-8-5](https://user-images.githubusercontent.com/81647911/212739304-b55c5db3-5152-43d9-b37a-fdb95a49d893.png)

Permutation test result for Afternoon (12:00 - 17:59)  vs. Evening (18:00 - 23:59) :[1] 2e-04

![unnamed-chunk-8-6](https://user-images.githubusercontent.com/81647911/212739311-e202d6c2-98d0-44b4-aee6-23cad559181a.png)

Permutation test result for Evening (18:00 - 23:59)  vs. Night (24:00 - 05:59) :[1] 2e-04

Accoridng to the above test results, we can determine from the graphs that the simulated mean is normally distributed around 0. The observed values are distant from the generated distribution, indicating that we seldom attain an observed mean when randomly classifying different kinds throughout the day. All of our P-values are as low as 2e-04 = 0.0002, however one exchange instance involving morning and evening varies from the others with a higher P-value = 0.0012. We could infer that there is a significant difference between the means of departure delays for the different time periods of the day since the P-values are all less than 5%, therefore we reject the null hypothesis and endorse the alternative hypothesis.

### 2. Is there a relationship between departure delays and the time of year?

![unnamed-chunk-10-1](https://user-images.githubusercontent.com/81647911/212740107-6d9636f1-5ff6-4a0a-8d1a-2ed810cd5db1.png)

![time of the year](https://user-images.githubusercontent.com/81647911/212740402-77d02700-f044-4fcb-b3a1-8089ca978c7a.png)

With the statistics from the flightsUA data, which are Fall 14531, Spring 14828, Summer 15016, and Winter 13604, we can see from the bar diagram above that there is nearly the same numbers of flights during each season, with the exception of winter. Next we can use boxplot to show us more direct comparison for all seasons.

![unnamed-chunk-12-1](https://user-images.githubusercontent.com/81647911/212740114-00ab45ff-62d3-487e-95c2-f28be9ff43c3.png)

The graph demonstrates that there are anomalies in every season. The median, for instance, is around zero in the summer and winter and somewhat lower in the fall and spring. Therefore, compared to summer and winter, we have more early departures in the fall and spring. We can use the permutation test to see whether there is a relationship between departure delays and the season. Let’s assume that the mean value of departure delays is the same for all cases. Another theory is that there are variations at different times of the year. Next, we will run permutation test and then use histograms show us the result as below.

![unnamed-chunk-13-1](https://user-images.githubusercontent.com/81647911/212740123-7317e080-e267-4a0f-9e2a-0cf542e2f142.png)

Permutation test result for Fall (Sep - Nov)  vs. Spring (Mar - May) :[1] 2e-04

![unnamed-chunk-13-2](https://user-images.githubusercontent.com/81647911/212740556-b4fdaf02-45af-44e4-9291-f73461167f00.png)

Permutation test result for Fall (Sep - Nov)  vs. Summer (Jun - Aug) :[1] 2e-04

![unnamed-chunk-13-3](https://user-images.githubusercontent.com/81647911/212740561-73ec5a02-ddc2-47f3-8865-5290ff2bff5f.png)

Permutation test result for Fall (Sep - Nov)  vs. Winter (Dec - Feb) :[1] 2e-04

![unnamed-chunk-13-4](https://user-images.githubusercontent.com/81647911/212740562-0bb4e755-253b-49f4-bbc2-1899ecb479bb.png)

Permutation test result for Spring (Mar - May)  vs. Summer (Jun - Aug) :[1] 2e-04

![unnamed-chunk-13-5](https://user-images.githubusercontent.com/81647911/212740567-0f048c87-763a-4472-b987-bae57b2e6e1c.png)

Permutation test result for Spring (Mar - May)  vs. Winter (Dec - Feb) :[1] 0.0076

![unnamed-chunk-13-6](https://user-images.githubusercontent.com/81647911/212740889-738a4298-f26e-4579-8347-7524e4c47d90.png)

Permutation test result for Summer (Jun - Aug)  vs. Winter (Dec - Feb) :[1] 2e-04

We can determine from the graphs that the simulated mean is normally distributed around 0. The observed values are distant from the generated distribution, indicating that we seldom attain an observed mean when randomly classifying different season throughout the year. All of our P-values are as low as 2e-04 = 0.0002, however one exchange instance involving Spring and Winter varies from the others with a higher P-value = 0.0078. We could infer that there is a significant difference between the means of departure delays for the different time periods of the year since the P-values are all less than 5%, therefore we reject the null hypothesis and endorse the alternative hypothesis.

### 3. Does the visibility affect departure delay?

![unnamed-chunk-17-1](https://user-images.githubusercontent.com/81647911/212740892-629d2d5c-c539-4bed-b5db-5a2614a9a1b0.png)

We can observe from the graphs above that the average departure delay time increase with the lower visibility. This demonstrates how weather conditions like visibility affect flights in New York City. Next we will calculate the permutation test result as well as the low visibility and high visibility.

Permutation test result: [1] 1e-04

Low visibility mean result: [1] 11.74591

High visibility mean result: [1] 17.89801

The observed values indicating that we observed the permutation test mean result 1e-04 = 0.0001, and the mean between Low visibility and High visibility are 11.74591 and 17.89801. We could infer that there is a significant difference between the means of departure delays for the different visibility, since the P-values are all less than 5%, therefore we reject the null hypothesis and endorse the alternative hypothesis.

### 4. Does the wind speed affect departure delay?

![unnamed-chunk-21-1](https://user-images.githubusercontent.com/81647911/212740893-4c7add27-39e4-48de-aed5-94e27048fe28.png)

Here, we can observe from grouped base on the grouped wind speeds and calculated the average departure delay time for each wind speed value (since only specific wind speed values were observed in the dataset, it is actually a continuous variable). The graph above shows that as the wind speed increases, a small increase in the average departure delay time occurs. Next we will calculate the permutation test result as well as the low wind speeds and high wind speeds.

Permutation test result: [1] 0.3839

Low wind speed standard deviation result: [1] 36.39903

High wind speed standard deviation result: [1] 34.79615

The observed values indicating that we observed the permutation test standard deviation result 0.385, and the standard deviation between Low wind speed and High wind speed are 36.39903 and 34.79615. We could infer that there is not statistically significant, since the P-values are all greater than 5% which indicating the difference between the standard deviation of departure delays for the different wind speed.

### 5. Does the weather temperature affect departure delay?

![unnamed-chunk-24-1](https://user-images.githubusercontent.com/81647911/212740895-3c7f7fab-5f96-4557-91e9-092c91b53f65.png)

We can observe from the graphs above that the average departure delay time increase with the temperature increase. This demonstrates how weather conditions like visibility affect flights in New York City. Next we will calculate the permutation test result as well as the low temperature and high temperature.

Permutation test result: [1] 1e-04

Low temperature mean result: [1] 15.82985

High temperature mean result: [1] 10.10027

The observed values indicating that we observed the permutation test mean result 1e-04 = 0.0001, and the mean between Low temperature and High temperature are 15.82985 and 10.10027. We could infer that there is a significant difference between the means of departure delays for the different visibility, since the P-values are all less than 5%, therefore we reject the null hypothesis and endorse the alternative hypothesis.

### 6. Does the precipitation affect departure delay?

![unnamed-chunk-27-1](https://user-images.githubusercontent.com/81647911/212740896-0f91f420-4aa3-48f3-bf49-e2b706536417.png)

We can observe from the graphs above that the average departure delay time increase with the precipitation increase. This demonstrates how weather conditions like precipitation affect flights in New York City. Next we will calculate the permutation test result as well as the low precipitation and high precipitation.

Permutation test result: [1] 1e-04

Low precipitation median result: [1] 9

High precipitation median result: [1] 0

The observed values indicate that we observed the permutation test median result 1e-04 = 0.0001, and the mean between Low precipitation and High precipitation are 9 and 0. We could infer that there is a significant difference between the median of departure delays for the different precipitation, since the P-values are all less than 5%, therefore we reject the null hypothesis and endorse the alternative hypothesis.
