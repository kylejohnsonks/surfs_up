# Surfs Up Overview

The purpose of this analysis is the help the board determine if the range of temperatures in Oahu throughout the year will be conducive to a successful surf and ice cream shop.  We will examine the daily temperatures June and December for all the years available in the data set, 2010 thru 2017.  Although omitted for readability, all temperatures are in degrees Fahrenheit.

# Results
To retrieve the data for this analysis we first reflected the tables from hawaii.sqlite, saved references to each table and created a Session with the sqlite database.  We then queried the Measurement table, using the extract function from sqlalchemy, for all results for June.  The results of the query were converted to a list and then a pandas DataFrame to generate summary statistics.  The same approach was repeated with December and both are displayed below.

![June](/Resources/JuneTemps.png)  ![Dec](/Resources/DecTemps.png)<br>

- The average temperature in June is warmer than December by almost 4 degrees (74.9 and 71.0 respectively).
- December's lowest temperature is 8 degrees cooler than June's, 56 and 64 respectively.
- While the high temperatures in June and December are similar, 85 and 83 respectively, December temperatures are more variable with a standard deviation of 3.75 vs 3.26 degrees in June.

# Summary
 
We assume that warmer days will lead to more surfing and ice cream consumption leading to higher sales.  Although it is true that the weather in December is somewhat cooler and more variable than June, the results show that the weather in December is fairly similar to the weather in June from a board perspective.  There will likely be fewer good weather days in December, but there will still be many good days for surfing and ice cream.  

We can refine and improve the comparison between the two months in a number of ways.  

- We can assume that days with a lot of rain will not be good for sales.  The precipitation data exists in the measurements table.  We can query that data to produce precipitation results that are similar to what we have produced for temperature.
- We can define a minimum temperature and maximum, perhaps 0, rainfall which constitute a 'good' day.  We can then query the data and count the good days in June vs December for each station over the eight available years.  
- Our surf shop will likely be on the beach at sea level.  The location and elevation of the each weather station is different.  We can use that data and perform a new query with the results restricted to stations that are representative of our location.
