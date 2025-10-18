## UN Data Exploration Bonus Bonus Questions

This set of exercises is designed to give you a chance to try out even more advanced features of the pandas library.
These exercises will be using the gdp_le DataFrame that you created for the regular exercises, meaning that it will have columns for Country, Year, GDP_Per_Capita, Continent, and Life_Expectancy.

1. In this question, we'll compare life expectancy by decade.  
	a. Start by creating a decade column using the pandas [cut function](https://pandas.pydata.org/docs/reference/api/pandas.cut.html).    
	b. Then use the pivot_table method to calculate the median life expectancy by continent by decade.    
	c. Use .loc to select the median life expectancy for Asia in the 2000s. Hint: you may need to inspect the decade indicator.    
	d. Create a seaborn heatmap of median life expectancy for each continent over time using the pivot table you created in part b.  

2. In this question, you'll assign a rank based on GDP Per Capita.  
	a. For each year, create a column gdp_rank that ranks countries by GDP per capita (highest GDP = rank 1).  
	b. Using your rank column, find the top 5 ranked countries for GDP for the years 1990, 2000, 2010, and 2020.  
	c. Using the pivot method, reshape the data from the pervious part to get a table with one row per year and one column per rank. Why doesn't pivot_table work here?  
	d. Identify the top 3 countries whose GDP rank improved the most from 2000 to 2010. Find the countries, their ranks in 2000 and 2010, and the change in ranks.  
	e. Filter to 2010. Assign each country to a GDP quintile using pd.qcut. Then compute the median life expectancy for each quintile in 2010.  

3. In this question, we'll look for countries that had a lot of volatility in their gdp per capita.
	a. First, for each country, find the 3-year rolling average and 3-year rolling standard deviation of GDP per capita.  
	b. Because there is a wide range of GDP per capita values, just looking at standard deviation may not be the best way to assess variability. Instead, we can use the [coefficient of variation](https://en.wikipedia.org/wiki/Coefficient_of_variation). Calculate the rolling coefficient of variation by dividing the rolling standard deviation by the rolling mean.  
	c. Which countries have experienced the highest volativility, on the basis of the coefficient of variation?  

4. Finally, we'll look at how the life expectancy of a country compares to the life expectancy of other countries in their same continent.  
	a. Create a new column life_expectancy_category that classifies each country-year as:    
		* “Low” if life expectancy is in the bottom third of life expectancies for that continent in that year  
		* “Medium” if life expectancy is in the middle third of life expectancies for that continent in that year  
		* “High” if life expectancy is in the top third of life expectancies for that continent in that year  
	b. Ethiopia was in the low category in 1996 but by 2018 had made it into the High category. How many countries have gone from a Low category to a High category in a later year? How many have gone from a High category to a Low category in a later year?  