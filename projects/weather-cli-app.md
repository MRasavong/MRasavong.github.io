---
layout: project
type: project
image: img/micromouse/micromouse-square.jpg
title: "Weather Forecast CLI Application"
date: July 2023
published: true
labels:
  - JavaScript
  - HTML
  - CSS
  - Git
summary: "I developed a full-stack command-line interface application using Node.js to display real-time weather forecasts for
over 200,000 cities"
---

Using the OpenWeatherMap API, I implemented temperatures in Celsius and Fahrenheit, cloud coverage, visibility, humidity, atmospheric pressure, precipitation, and wind.

This was a personal project meant to help me learn full-stack development.

Here is some code that illustrates how I fetched data from the OpenWeatherMap API:

```cpp
app.post('/', function(req, res) {

    // Get city name passed in the form
    let city = req.body.city;

    // Use the city name to fetch data
    // Use the API_KEY in the '.env' file
    let url = `http://api.openweathermap.org/data/2.5/weather?q=${city}&units=metric&appid=${apiKey}`;
```

You can learn more at the [GitHub repository](https://github.com/MRasavong/weather-cli-app).
