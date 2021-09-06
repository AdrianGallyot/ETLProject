Overview

This will develop a Global Temperature analysis database.   

This ETL project will look too arrange the temperate variance data for the last 50 years through to 2020 for all nations, as well as a collection of the average temperature of all major cities since 1995 to understand the effects of global warming.

Extract:

The raw data sets were both in CSV format

city_temperature.csv contains the average temperature for all major 
Environment_Temperature_change.csv contains temperature variance and standard dev data for all major cities from 1961-2020

Weather API - to get all the current temperature data for all cities from the above list


Transform:

City_temperature will be cleaned up to remove blank columns, creation of date column based on the Day, month and Year value provided, and removal of year value that are outliers (200, 201)

Environment_temperature.csv will be filtered to extract temperate change and standard deviation into two seperate tables.

Creation of Element, Month and EnvArea tables based on the relationships.


Use the City_temperature.csv to create three new tables with unique values for Cities, Countries and Regions.


Using this distinct city table list, I will then use this a source for the OpenWeather API to get the Latitude and current temperature values for the CurrentCityWeather table

Using the above City dataset will then be used in a Python Notebook file to query the OpenWeather API to get the current temperature for all cities and store in a new table

Load: 

TemperatureDataDB Creation in postgres

With the following final tables:

Cities
CityTemp
Countries
CurrentCityWeather
Element
EnvArea
Month
Regions
Std_Dev
TempVar

These two datasets were selected in understanding the effects of climate change and to establish patterns in temperature.
