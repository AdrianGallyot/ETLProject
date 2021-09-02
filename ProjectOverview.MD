Overview

Global Temperature and plastic pollution data collection    

This ETL project will look too arrange the temperate variance data for the last 50 years through to 2020 for all nations, as well as a collection of the average temperature of all major cities since 1995 to understand the effects of global warming.

The main two datasets will consist of Maximum temperature data for all major cities and coutries for the given time frames

Extract:

The raw data sets were both in CSV format

city_temperature.csv contains the average temperature for all major 
Environment_Temperature_change.csv contains temperature variance and standard dev data for all major cities from 1961-2020

Weather API - to get all the current temperature data for all cities from the above list


Transform:

City_temperature will be cleaned up to remove blank columns, creation of date column based on the Day, month and Year value provided, and removal of year value that are outliers (200, 201)

Environment_temperature.csv will be filtered to extract temperate change and standard deviation into two seperate tables.  Will also remove all the following quarterly and year grouped data (Dec–Jan–Feb,Dec–Jan–Feb,Mar–Apr–May
Mar–Apr–May
Jun–Jul–Aug
Jun–Jul–Aug
Sep–Oct–Nov
Sep–Oct–Nov
Meteorological year
Meteorological year)

A distinct city, Country table will be formed from the City_temperate dataset will be created.

Using the above City dataset will then be used in a Python Notebook file to query the OpenWeather API to get the current temperature for all cities and store in a new table

Load: 

TemperatureDataDB Creation in postgres

With the following final tables:

CitiesList
CityTemp
CityTempChange
CityTempStandardDev
CurrentCityData