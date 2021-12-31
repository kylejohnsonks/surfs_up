# Surfs Up Overview

The purpose of this analysis is the help the board determine if the range of temperatures in Oahu throughut the year will be conducive to a successful surf and ice cream shop.  We will examine the daily temperatures June and December for all the years availbale in the data set, 2010 thru 2017.  Although omitted for readability, all temperatures are in degrees Farenheit.

# Results
To retrieve the data for this analysis we first reflected the tables from hawaii.sqlite, saved references to each table and created a Session with the sqlite database.  We then queried the Measurement table, using the extract function from sqlalchemy, for all resutls for june.  The resuslts of the query were converted to a list and then a pandas DataFrame to generate summary statistics.  The same approach was repeated with December.  The results are below.

![June](/Resources/JuneTemps.png)  ![Dec](/Resources/DecTemps.png)<br>

- The average temperature in June is warmer than December by almost 4 degrees (74.9 and 71.0 respectively).
- December's lowest temperature is 8 degrees cooler than June's, 56 and 64 respectively.
- While the high temperatures in June and December are similar, 85 and 83 respectively, December temperatures are more variable with a standared deviatoion of 3.75 vs 3.26 degrees in June.

# Summary
 
We assume that warmer days will lead to more surfing and ice cream consumption leading to higher sales.  Althought it is true that the weather in Decemer is slighly cooler and more vairable than June, the results show that the weather in December is fairly siliar to the weather in June from a board perspective.  There will likely be fewer good weather days in December, but there will still be many good days for surfing and ice cream.  

We can refine and imporove the comparsion between the two months in a number of ways.  

- We can assume that days with a lot of rain will not be good for sales, and that precipition data exists in the measurments table.  We can query thata data to produce pereiption resutls that are similar to what we have produced for temperature.
- We can define a mininum temperature and maximum, perhpas 0, rainfall which constitute a 'good' day.  We can then querey the data and count the good days in June vs December for each station over the eight available years.  
- Our surf shop will likely be on the beach at sea level.  The location and elevation of the each weather station is differnt.  We can use that data and perform a new querey with the results restriced to stations that are representative of our locaiton.
