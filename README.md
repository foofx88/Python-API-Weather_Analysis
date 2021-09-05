<h3>Python API - Finding the Best Vacation Spots</h3>
<hr>

<h4>Part 1: Getting data and analyzing relationships</h4>
<p>Utilizing Python requests, APIs, and JSON traversals to answer a fundamental question: "What's the weather like as we approach the equator?"
<br>In order to answer this, Python script created to visualize the weather of 500+ cities across the world of varying distance from the equator. Used Python library - <a href="https://pypi.python.org/pypi/citipy">citipy and used request to obtain JSON from <a href="https://openweathermap.org/api">OpenWeather API</a> 
</p>

<p>Performed the following on the JSON data:</p>
<ul>
  <li>Used np.random to obtain a range of random latitude and longitude to form a lists of coordinates</li>
  <li>Feed the coordinates into citipy to get a list of city names </li>
  <li>The city names are then used to get weather data from OpenWeatherMap</li>
  <li>As there is a limit on the API key, a limiter of 50 is inplace</li>
  <li>Clean the data by removing a few outliers and export to CSV</li>
  <li>Plot the data and identify the correlation between Latitude and the required factors - Temperature, Humidity, Cloudiness, Wind Speed</li>
  <li>Ran linear regression on each relationship and seperate into Northern and Southern Hemisphere</li>
</ul>

<h4>Sample Snippets of Plots:</h4>
<img src="/WeatherPy/Output/lat_vs_cloud.png">
<img src="/WeatherPy/Output/lat_vs_temp.png">
<img src="/WeatherPy/Output/northlat_vs_humi.png">
<img src="/WeatherPy/Output/southlat_vs_humi.png">

See part 1's <a href="/WeatherPy/WeatherPy.ipynb">Jupyter Notebook</a>

<hr>
<h4>Part 2: Using the analysis to find the best facation spot</h4>
<p>Used the exported CSV to plot on Google Maps and generate a heatmap displaying the humidity for every city </p>
<p>Narrowed down the DataFrame to get the ideal weather condition:</p>
<ul>
  <li>A max temperature lower than 80 degrees but higher than 70</li>
  <li>Wind speed less than 10 mph</li>
  <li>Zero cloudiness</li>
</ul>
<p>Feed the ideal locations into Google Places API to find the first hotel within 5000 meters</p>
<p>Pin each hotel on the map</p>

Explore on how it is done on the <a href="/VacationPy/VacationPy.ipynb">Jupyter Notebook</a>
