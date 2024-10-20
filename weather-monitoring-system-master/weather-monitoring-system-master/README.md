##### **README.md (Weather Monitoring System)**

# Weather Monitoring System

## Overview
This project is a real-time weather monitoring system that retrieves weather data from the OpenWeatherMap API. It allows users to fetch weather data for different cities and customize the data returned (e.g., exclude minutely, hourly data).

## Features
- Fetch real-time weather data for specific cities.
- Customize data exclusions (minutely, hourly, daily).
- Supports metric, imperial, and standard units for temperature.

## Technologies Used
- **Java 17**
- **Spring Boot 3.3.4**
- **OpenWeatherMap API**
- **RestTemplate** for making HTTP requests
- **Spring Scheduling** (for future features)

## How to Run

1. Clone this repository:
   ```bash
   git clone https://github.com/khanshaif9102/weather-monitoring-system.git
   ```
2. Get your OpenWeatherMap API key:
   - Sign up at OpenWeatherMap to get your free API key.
3. Update the application.properties file located in src/main/resources with your API key:
   ```
   weather.api.url=https://api.openweathermap.org/data/2.5/weather?q={city}&appid={key}
   weather.api.key=your_openweathermap_api_key
   ```
4. Run the application:
   ```
   mvn spring-boot:run
   ```
5. The application will be available at http://localhost:8080

# API Endpoints
## Get Weather by City:
- GET /api/weather?city={city_name}
- Example: /api/weather?city=London,uk
- Response: Current weather data for the specified city.

# Example API Response
```
{
  "coord": {
    "lon": -0.1257,
    "lat": 51.5085
  },
  "weather": [
    {
      "id": 500,
      "main": "Rain",
      "description": "light rain",
      "icon": "10d"
    }
  ],
  "main": {
    "temp": 280.32,
    "feels_like": 278.34,
    "temp_min": 279.15,
    "temp_max": 281.15,
    "pressure": 1012,
    "humidity": 81
  },
  "wind": {
    "speed": 4.12,
    "deg": 240
  },
  "clouds": {
    "all": 90
  },
  "name": "London",
  "cod": 200
}
```

# Future Improvements
- Add weather alerts for specific thresholds (e.g., temperature over 35°C).
- Store historical weather data for trend analysis.
