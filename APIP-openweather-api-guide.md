# OpenWeather API Documentation

This document provides a quick-start guide to using the OpenWeather API to retrieve current weather data for a specified city.

## Overview

The OpenWeather API allows developers to access real-time weather data for cities around the world. This guide focuses on the **Current Weather Data API**, which returns temperature, humidity, wind speed, and other metrics.

## Base URL

```
https://api.openweathermap.org/data/2.5/weather
```

## Authentication

You must register for an API key at [OpenWeather](https://openweathermap.org/api). Include this key as a query parameter in each request.

### Example:

```
https://api.openweathermap.org/data/2.5/weather?q=London&appid=YOUR_API_KEY
```

## Parameters

| Parameter | Type   | Required | Description                        |
|-----------|--------|----------|------------------------------------|
| `q`       | string | Yes      | City name (e.g., `London`)         |
| `appid`   | string | Yes      | Your unique API key                |
| `units`   | string | No       | Units of measurement (metric/imperial) |

## Sample Request

```
GET /data/2.5/weather?q=New York&units=metric&appid=YOUR_API_KEY
```

## Sample JSON Response

```json
{
  "weather": [
    {
      "description": "clear sky"
    }
  ],
  "main": {
    "temp": 25.6,
    "humidity": 40
  },
  "wind": {
    "speed": 4.1
  },
  "name": "New York"
}
```

## Error Handling

| Code | Message                 | Description                          |
|------|-------------------------|--------------------------------------|
| 401  | Invalid API key         | Check if your API key is correct     |
| 404  | City not found          | Ensure the city name is spelled right|
| 429  | Too many requests       | You’ve exceeded your request limit   |

## Best Practices

- Always check for null or missing values in the response.
- Use `units=metric` or `imperial` for readable temperature.
- Cache frequent requests to avoid rate limits.
- Monitor your API usage through the OpenWeather dashboard.

## Resources

- [Official Documentation](https://openweathermap.org/current)
- [API Key Signup](https://home.openweathermap.org/users/sign_up)