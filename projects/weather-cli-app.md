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

Here is some code that illustrates how we read values from the line sensors:

```cpp
byte ADCRead(byte ch)
{
    word value;
    ADC1SC1 = ch;
    while (ADC1SC1_COCO != 1)
    {   // wait until ADC conversion is completed   
    }
    return ADC1RL;  // lower 8-bit value out of 10-bit data from the ADC
}
```

You can learn more at the [GitHub repository](https://github.com/MRasavong/weather-cli-app).
