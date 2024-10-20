
# Real-Time Weather Monitoring

## Overview

**Real-Time Weather Monitoring** is a Spring Boot-based application that retrieves and displays real-time weather data for various cities using the OpenWeatherMap API. It allows users to fetch current weather information with options to customize the returned data (e.g., exclude minutely, hourly data) and supports multiple units for temperature measurement.

## Features

- Fetch real-time weather data for specific cities.
- Customize data exclusions (e.g., minutely, hourly, daily data).
- Supports metric, imperial, and standard units for temperature.
- Easy-to-use REST API for getting weather updates.

## Technologies Used

- **Java 17**
- **Spring Boot 3.3.4**
- **OpenWeatherMap API**
- **RestTemplate** for making HTTP requests
- **Spring Scheduling** (for future enhancements)

## How to Run

1. **Clone this repository:**

   ```bash
   git clone https://github.com/Aryan13242/Real-Time-Weather-Monitoring.git
   ```

2. **Get your OpenWeatherMap API key:**

   Sign up at [OpenWeatherMap](https://home.openweathermap.org/users/sign_up) to get your free API key.

3. **Update the `application.properties` file** located in `src/main/resources` with your API key:

   ```properties
   weather.api.url=https://api.openweathermap.org/data/2.5/weather?q={city}&appid={key}
   weather.api.key=your_openweathermap_api_key
   ```

4. **Run the application:**

   ```bash
   mvn spring-boot:run
   ```

5. The application will be available at:  
   **http://localhost:8080**

## API Endpoints

### Get Weather by City:

- **Endpoint:** `GET /api/weather?city={city_name}`
- **Example:** `/api/weather?city=London,uk`
- **Response:** Current weather data for the specified city.

### Example API Response:

```json
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

## Future Improvements

- Add weather alerts for specific thresholds (e.g., temperature over 35°C).
- Schedule automatic weather updates at regular intervals.
- Implement caching for frequently requested cities to reduce API calls.
