# surfs_up #

#Overview of the Analysis#

I have a great business idea: create a surf and ice cream shop in Oahu Hawaii, but I need capitol to do so. I found a potential investor: W. Avy, a businessman and avid surfer, and presented the plan to him. He loves the idea, but is hesitant to invest in it because a similar venture in the past went out of business due to bad weather. He asked that I run some data that he has compiled about the precipitation on the island of Oahu, (hawaii.sqlite). 

The data compiled spans dates between 2016 and 2020. For the purpose of my initial analysis I looked at data over the course of a year. Remembering that W. Avy said his favorite surf experience was on August 23, 2017, I used that as my start date and explored the data through the first anniversary of that date. I received the precipitation scores for the year and put them into a DataFrame. Then I sorted the DataFrame in chronological order. Lastly, I plotted the results.

![percipitation_plot](https://github.com/JovanHumphrey/surfs_up/blob/main/percipitation_plot.PNG)

I also provided W. Avy with some statistics about the precipitation over the course of a year. It was obvious from this data that aside from some outlier days, the rain on Oahu was rarely over an inch, and shouldn't be enough to rain-out our surf shop.

![percipitation_summary](https://github.com/JovanHumphrey/surfs_up/blob/main/percipitation_summary.PNG)

After our meeting W. Avy asked that I investigate how many weather stations provided the weather information. His concern was that perhaps we didn't have enough weather stations collecting data to trust the results. To put his mind at ease I added a count function to the data to count the number of stations, and then ran an additional query to see how active the stations were.

![stations_count](https://github.com/JovanHumphrey/surfs_up/blob/main/stations_count.PNG)

I discovered that station USC00519281 was the most active so I decided to do a temperature analysis on that location. Using additional queries I was able to determine that over the course of a year the lowest temperature was recorded as 54 degrees, with a max of 85, and an average of 71.7 degrees. I visualized that data as well. I created a histogram for the temperature observations ("tobs") with 12 bins. If we count the frequencies of tobs we can see that over 300 days of the year were 65 degrees or higher. Perfect surfing temperature!

![Station_Tobs](https://github.com/JovanHumphrey/surfs_up/blob/main/Station_Tobs.PNG)

Lastly, I used Flask to display my results in webpages, with routes for each result. I did that so that W. Avy's board of directors could easily access the results for themselves without Python.

##Purpose of Analysis##

W. Avy was thrilled with the results but asked that I dive deeper into the temperatures of June and December to ensure that the surf and ice cream shop would be sustainable year-round. Using the same data source as before I ran analysis for the months of June and December. I ran a query to create a list of observed temperatures in June and then ran a summary statistic on the results. I then repeated the same steps for December.

#Results#

![June](https://github.com/JovanHumphrey/surfs_up/blob/main/June.PNG)
![Dec](https://github.com/JovanHumphrey/surfs_up/blob/main/Dec.PNG)

##Differences Between June and December Temperatures##

Please note a few imporatant details about these summary results:

1. June never saw days under the mid-60s.
2. The highest recorded temperatures in each month were about the same although,
3. the days in June trended warmer across the board.

#Summary#

Overall, I would say that the variance between temperatures in June and December aren't so drastic as to expect the business to lose money in the winter. In a given year the temperature and rain on Oahu should be even enough to prevent the shop from being rained-out. That said I would recommend a couple more queries to be sure.

##Additional Queries##

I would create a query to compare rainfall between the two months. It could be that while the temperatures don't differ very much, the rainfall could. Combined with lower average temperatures, higher precipitation scores in December could cause a more significant dip in business than the current data suggests. 

Secondly, though looking at temperature and precipitation data that spans a year is very useful, I recommend that we use the data source for all it's worth and run queries for the entire duration of the observed data. This would allow us to get averages over the span of 4 years and tell us if our sample year was anomalous.

Lastly, the weather stations haven't provided data about wind. This data is crucial in determining the best surfing environment, and different times of year could easily see a range of waves, not to mention that wind can make cool temperatures and rain less pleasant. Because the dataset doesn't provide this information, I recommend additional research.
