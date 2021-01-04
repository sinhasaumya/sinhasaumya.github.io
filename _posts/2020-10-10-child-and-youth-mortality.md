---
date: 2020-10-10
excerpt: "Data wrangling of UNICEF's Child and Youth Mortality data"
header: ~
tags:
  - pre-processing
  - child-mortality
  - youth-mortality
title: "Child and Youth Mortality - Data Wrangling"
---

The study of child and youth mortality are key to improving survival and well-being globally. United Nations International Children’s Emergency Fund (UNICEF) reports that if each country had a single source of high quality data covering the last few decades, reporting on child and youth mortality levels and trends would be straightforward. However, as this is not the case, United Nations Inter-agency Group for Child Mortality Estimation (UN IGME) compiled all available national-level data on child mortality and applied a statistical model to estimate unavailable or low-quality mortality data. The child and youth mortality data is made available by UNICEF in the form of mortality rate and number of deaths in 193 countries from 1990 to 2019 in September 2020 on its data website. The same, as named below, are chosen for wrangling. 
1. Mortality rates among children and youth, ages 5 to 24 years, and 
2. Number of deaths among children and youth, ages 5 to 24 years  

The datasets were accessed [here](https://data.unicef.org/topic/child-survival/child-and-youth-mortality-age-5-24/) and the data wrangling process and results are available on [RPubs](https://rpubs.com/saumyasinha/678260).  

In order to prepare this data for analysis, the following steps were taken -
1. Read mortality rate data
2. Prepare mortality rate data -
	2.1 read different age groups in different data frames
	2.2 add age group to each data frame
	2.3 combine data of all age groups in single data frame
	2.4 rename necessary columns
	2.5 change data type where necessary
	2.6 tidy up data - convert from wide to long format
	2.7 clean up year column
3. Prepare deaths data -
	3.1 read different age groups in different data frames
	3.2 add age group to each data frame
	3.3 combine data of all age groups in single data frame
	3.4 rename necessary columns
	3.5 change data type where necessary
	3.6 tidy up data - convert from wide to long format
	3.7 clean up year column
4. Merge mortality rate and deaths data frames to create single data frame
5. Scan for missing values, special values and obvious errors and treat them
6. Scan for outliers in numeric columns and treat them
7. Mutate new column YOY mortality rate change %
8. Apply transformations on mortality rate and deaths to convert them to approximate normal and remove right skew  

These steps tidy up the data and the clean data can now be analysed.