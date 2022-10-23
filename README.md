# Navigating APIs Using Python
This project demostrates use of APIs in two examples:
1. WeatherPy - Generates scatter plots and linear regression models for weather in cities at different latitudes
2. VacationPy - Generates a heatmap of potential vacation locations based on humidity and places a marker to an available hotel in a city meeting ideal weather criteria.
## Imported Python Libraries
* matplotlib.pyplot
* pandas
* requests
* scipy.stats
* pprint
* datetime
* citipy
* os
* gmaps
## Datasets and APIs
### WeatherPy
* citipy - identify cities based on nearby latitude and longitude values
* [Open Weather Map](https://openweathermap.org/api)
### VacationPy
* cities_weather.csv - generated in WeatherPy program
* [gmaps](https://pypi.org/project/gmaps/)
* [Google Maps - Nearby Search](https://developers.google.com/maps/documentation/places/web-service/search-nearby)
## Analysis and Results
### WeatherPy
* On each run, this code generates a new list of cities for weather analysis
* 1500 random lat/long coordinates are tested to find the nearest cities using the citipy library
* The Open Weather Map API provides current weather info for each unique city
#### Summary of results
* 653 unique cities found through citipy
* 608 of 653 cities had current weather data available to be plotted as shown below
* Max Temperature vs Latitude - There is a strong correlation (r-values: -0.87, 0.74) between city latitude and the max temperature in both hemispheres. The max temperature steadily decreases (negative correlation) going from latitudes of 0 to 90 in the Northern Hemisphere (slope = -0.85), while it increases (positive correlation) going from a latitude of -90 to 0 in the Southern Hemisphere (0.59).

![temp_scatterplot](WeatherPy\output_data\lat_max_temp.png)
![temp_north](WeatherPy\output_data\north_lat_max_temp.png)
![temp_south](WeatherPy\output_data\south_lat_max_temp.png)

* Humidity vs Latitude - There is a weak correlation (r-values: 0.19, 0.18) between city latitude and humidity in either hemisphere.

![humidity_scatterplot](WeatherPy\output_data\lat_humidity.png)
![humidity_north](WeatherPy\output_data\north_lat_humidity.png)
![humidity_south](WeatherPy\output_data\south_lat_humidity.png)

* Cloudiness vs Latitude - There is a weak correlation (r-values: 0.15, 0.08) between city latitude and humidity in either hemisphere.

![clouds_scatterplot](WeatherPy\output_data\lat_clouds.png)
![clouds_north](WeatherPy\output_data\north_lat_clouds.png)
![clouds_south](WeatherPy\output_data\south_lat_clouds.png)

* Wind Speed vs Latitude - There is a weak correlation (r-values: 0.25, 0.28) between city latitude and humidity in either hemisphere.

![wind_scatterplot](WeatherPy\output_data\lat_wind.png)
![wind_north](WeatherPy\output_data\north_lat_wind.png)
![wind_south](WeatherPy\output_data\south_lat_wind.png)
### VacationPy
* A heatmap of cities assessed in WeatherPy was generated using the gmaps API
* 9 of 608 cities assessed in WeatherPy met ideal conditions for a vacation location (max temp is between 70 and 80 F, wind speed is less than 10, and cloudiness is 0%)
* The Google Maps API nearby search function identified a hotel in each of the 9 cities short-listed for vacation
* Map markers and hotel info were added to the original heatmap:

![hotel markers](VacationPy\output_data\hotel_locations.png)
