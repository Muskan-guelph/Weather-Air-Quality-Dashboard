# 🌦️ Weather & Air Quality Dashboard

## Overview
This Power BI dashboard provides a **real-time view of weather conditions and air quality** for multiple cities. It combines environmental indicators with forecast trends, offering an interactive way to monitor climate and pollution data.

## Features
- **Current Weather:** Temperature, humidity, wind speed, pressure, visibility, and UV index.
- **7-Day Forecast:** Line chart showing upcoming daily temperatures.
- **Air Quality Index (AQI):** Tracks PM10, PM2.5, SO₂, NO₂, O₃, and CO levels with health classification.
- **Sunrise & Sunset:** Automatically adjusts by city.
- **Chance of Rain:** Daily precipitation probability in bar chart format.
- **Multi-City Comparison:** View data side by side (Mississauga, Mumbai, Surat).

## Data Sources
- Weather API (real-time & forecast data)
- Air Quality API (pollutant-level data)

## Key Metrics
- Current Temperature & Weather Status
- Humidity, Wind Speed, Visibility, Pressure
- Sunrise & Sunset Times
- AQI Index & Pollutant Breakdown
- Rain Probability (%)

## DAX Queries (Samples)
```DAX
AQI Category = 
SWITCH(
    TRUE(),
    'air_quality'[AQI] <= 50, "Good",
    'air_quality'[AQI] <= 100, "Moderate",
    'air_quality'[AQI] <= 150, "Unhealthy for Sensitive",
    'air_quality'[AQI] <= 200, "Unhealthy",
    'air_quality'[AQI] <= 300, "Very Unhealthy",
    "Hazardous"
)

FeelsLikeTemp = 
'weather_data'[Temperature] - 
( (100 - 'weather_data'[Humidity]) / 5 )
```
## Project Insights
- ** Offers a holistic view of weather and pollution for health, travel, and planning decisions.
- ** Visual storytelling: temperature trends, pollutant breakdown, and rain chance highlight patterns clearly.
- ** Scalable for adding more cities or integrating historical trends.

## Screenshots
### Dashboard Overview
![Dashboard Overview](https://github.com/Muskan-guelph/Weather-Air-Quality-Dashboard/blob/main/Assets/Report/Dashboard.png?raw=true)

## Download
[Download the Power BI report](Weather Dashboard.pbix)
## Contact
For any questions or collaboration, please contact 
[Muskan Manwani](mailto:mmanwani@uoguelph.ca).
