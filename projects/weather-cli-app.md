---
layout: project
type: project
image: img/weather-cli-app-square.png
title: "Weather Forecast CLI Application"
date: 2023
published: true
labels:
  - JavaScript
  - Node.js
  - HTML
  - CSS
  - GitHub
summary: "A full-stack command-line interface application that displays real-time weather forecasts for over 200,000 cities."
---
<img class="img-fluid" src="../img/weather-cli-app-full.png">

During the summer, I decided to take advantage of the break I was given to improve my programming skills. Previously, I had only taken introductory ICS courses in Java, where code would simply take place within an IDE and be printed to the console. While these courses taught me valuable computer science concepts such as binary trees and sorting algorithms, I was curious about how to develop an application with an interactable user interface and real-time outputs. Thus, in July, I created a weather application in JavaScript and Node.js that runs directly from the command line. Using the OpenWeatherMap API, I implemented temperatures in Celsius and Fahrenheit, cloud coverage, visibility, humidity, atmospheric pressure, precipitation, and wind.

This was a personal project meant to help me learn full-stack development. It was the first time I was coding outside of an academic environment and I was thrilled to finally see my code out in public. Not having to worry about grading was a plus.

Below is an example of the code I used to retrieve data from the OpenWeatherMap API and set up my output:

```
let place = `${weather.name}, ${weather.sys.country}`,
    /* Calculate the current timezone using the data fetched*/
    weatherTimezone =
        `${new Date(weather.dt * 1000 - (weather.timezone * 1000))}`;
let weatherTemp = `${weather.main.temp}`,
    weatherPressure = `${weather.main.pressure}`,
    /* Fetch the weather icon and its size using the icon data*/
    weatherIcon =
        `http://openweathermap.org/img/wn/${weather.weather[0].icon}@2x.png`,
    weatherDescription = `${weather.weather[0].description}`,
    humidity = `${weather.main.humidity}`, clouds = `${weather.clouds.all}`,
    visibility = `${weather.visibility}`, main = `${weather.weather[0].main}`,
    weatherFahrenheit;
weatherFahrenheit = ((weatherTemp * 9 / 5) + 32);
```

To create the application, I first had to learn about web development. I started by creating an account with the Odin Project and completed several lessons, with the most valuable being how to commit repositories to GitHub. I also took the time to run a virtual machine on my laptop and download Linux, which has a far more functional base terminal (bash) than Windows (cmd). While Windows is still my main operating system, I have dual-booted Manjaro to my laptop since then and occasionally use its terminal to code. I look forward to learning more about front-end programming in ICS 314.

You can learn more at the [GitHub repository](https://github.com/MRasavong/weather-cli-app).
