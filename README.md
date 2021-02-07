# UCF Data Bootcamp Homework 6

# Python API Homework - What's the Weather Like?

## Background

Whether financial, political, or social -- data's true power lies in its ability to answer questions definitively. So let's take what you've learned about Python requests, APIs, and JSON traversals to answer a fundamental question: "What's the weather like as we approach the equator?"

Now, we know what you may be thinking: _"Duh. It gets hotter..."_

But, if pressed, how would you **prove** it?

![Equator](Images/equatorsign.png)


## Part I - WeatherPy

In this example, we created a Python script to visualize the weather of 500+ cities across the world of varying distance from the equator. To accomplish this, we used a [simple Python library](https://pypi.python.org/pypi/citipy), the [OpenWeatherMap API](https://openweathermap.org/api), and a little common sense to create a representative model of weather across world cities.

The first requirement is to create a series of scatter plots to showcase the following relationships:

* Temperature (F) vs. Latitude
* Humidity (%) vs. Latitude
* Cloudiness (%) vs. Latitude
* Wind Speed (mph) vs. Latitude

After each plot, add a sentence or two explaining what the code is analyzing.

The second requirement is to run linear regression on each relationship. This time, separate the plots into Northern Hemisphere (greater than or equal to 0 degrees latitude) and Southern Hemisphere (less than 0 degrees latitude):

* Northern Hemisphere - Temperature (F) vs. Latitude
* Southern Hemisphere - Temperature (F) vs. Latitude
* Northern Hemisphere - Humidity (%) vs. Latitude
* Southern Hemisphere - Humidity (%) vs. Latitude
* Northern Hemisphere - Cloudiness (%) vs. Latitude
* Southern Hemisphere - Cloudiness (%) vs. Latitude
* Northern Hemisphere - Wind Speed (mph) vs. Latitude
* Southern Hemisphere - Wind Speed (mph) vs. Latitude

After each pair of plots, take the time to explain what the linear regression is modeling. For example, describe any relationships you notice and any other analysis you may have.

Your final notebook must:

* Randomly select **at least** 500 unique (non-repeat) cities based on latitude and longitude.
* Perform a weather check on each of the cities using a series of successive API calls.
* Include a print log of each city as it's being processed with the city number and city name.
* Save a CSV of all retrieved data and a PNG image for each scatter plot.

### Part II - VacationPy

Now let's use your skills in working with weather data to plan future vacations. Use jupyter-gmaps and the Google Places API for this part of the assignment.

* **Note:** Remember that any API usage beyond the $200 credit will be charged to your personal account. You can set quotas and limits to your daily requests to be sure you can't be charged. Check out [Google Maps Platform Billing](https://developers.google.com/maps/billing/gmp-billing#monitor-and-restrict-consumption) and [Manage your cost of use](https://developers.google.com/maps/documentation/javascript/usage-and-billing#set-caps) for more information.

* **Note:** if you having trouble displaying the maps, try running `jupyter nbextension enable --py gmaps` in your environment and retry.

To complete this part of the assignment,you will need to do the following:

* Create a heat map that displays the humidity for every city from Part I.

  ![heatmap](Images/heatmap.png)

* Narrow down the DataFrame to find your ideal weather condition. For example:

  * A max temperature lower than 80 degrees but higher than 70.

  * Wind speed less than 10 mph.

  * Zero cloudiness.

  * Drop any rows that don't contain all three conditions. You want to be sure the weather is ideal.

  * **Note:** Feel free to adjust to your specifications but be sure to limit the number of rows returned by your API requests to a reasonable number.

* Using Google Places API to find the first hotel for each city located within 5000 meters of your coordinates.

* Plot the hotels on top of the humidity heatmap with each pin containing the **Hotel Name**, **City**, and **Country**.

  ![hotel map](Images/hotel_map.png)
  
  ### Files
  
  Note: You will find two versions of the WeatherPy jupyter notebook under the WeatherPy folder.  WeatherPy-Citypy uses the citypy library to get the
  random city names, while WeatherPy creates the city list by randomly selecting from `openweather.com`'s own list of cities.

```
+<Project Top>
|   .gitignore - Git ignore file
|   README.md - This file
|   
+---Images
|       equatorsign.png - Documentation image
|       heatmap.png - Heatmap produced in part 2
|       hotel_map.png - Heatmap  + Layers for part 2
|       
+---VacationPy
|      config.py - Stores keys, not pushed to Github
|      VacationPy.ipynb  - Jupyter notebook for part 2.
|           
\---WeatherPy
       01_Temp_Vs_Latitudes.png - Image produced in part 1
       02_Humidity_Vs_Latitudes.png - Image produced in part 1
       03_Cloudiness_Vs_Latitudes.png - Image produced in part 1
       04_Wind_Speed_Vs_Latitudes.png - Image produced in part 1
       05_Temp_Vs_Latitudes_Multi.png - Image produced in part 1
       06_Humid_Vs_Latitudes_Multi.png - Image produced in part 1
       07_Cloud_Vs_Latitudes_Multi.png - Image produced in part 1
       08_Wind_Vs_Latitudes_Multi.png - Image produced in part 1
       city.list.json - Json file with list of cities from openweather.com
       config.py - Stores keys, not pushed to Github
       countryCodes.json - Json file with country codes, names 
       WeatherPy.ipynb - Jupyter notebook for part 1
	   WeatherPy-Citypy.ipynb - Jupyter notebook for part 1, using the citipy library.
       weather_data.csv - Output file with weather data from openweather.com
```

To view the completed notebooks, just open them in Jupyter notebook or access them from the Github repository.