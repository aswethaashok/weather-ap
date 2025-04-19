## WEATHER APP

Name: SWETHA A
Reg no: 212223220114

Build a Weather App using React


# Objective
Create a simple weather application using React that allows the user to enter a city name and view simulated weather data such as temperature, wind speed, and sky condition.

# Task Description
Develop a weather app that:

Accepts a city name from the user

Displays weather information (temperature, wind speed, sky condition) only for predefined cities

Shows an error message for cities not in the mock data

# Requirements
React functional component (WeatherApp)

Text input to enter city name

A button or "Enter" key to trigger search

Display of weather data (if city is valid)

Error message for invalid cities

Basic styling using external or inline CSS

# PROGRAM:
```
dev by: SWETHA A(212223220114)
```
```
index.js

import React from 'react';
import ReactDOM from 'react-dom/client';
import './App.css';
import WeatherApp from './App';

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(
  <React.StrictMode>
    <WeatherApp />
  </React.StrictMode>
);

App.js

import React, { useState } from 'react';
import './App.css';

const mockWeatherData = {
  "London": {
    location: "London, GB",
    temperature: "6.9 °C",
    humidity: "65%",
    conditions: "shower rain"
  },
  "New York": {
    location: "New York, US",
    temperature: "12.4 °C",
    humidity: "58%",
    conditions: "clear sky"
  },
  "Tokyo": {
    location: "Tokyo, JP",
    temperature: "18.2 °C",
    humidity: "70%",
    conditions: "scattered clouds"
  }
};

function WeatherApp() {
  const [city, setCity] = useState('');
  const [weather, setWeather] = useState(null);
  const [error, setError] = useState('');

  const handleSearch = () => {
    const input = city.trim();
    if (mockWeatherData[input]) {
      setWeather(mockWeatherData[input]);
      setError('');
    } else {
      setWeather(null);
      setError('City not found!');
    }
  };

  const handleKeyDown = (e) => {
    if (e.key === 'Enter') handleSearch();
  };

  return (
    <div className="container">
      <div className="left-panel">
        <h1>Your Weather</h1>
        <p>Current weather conditions in your city!</p>
        <img
          src="https://www.thebransinn.com/gallery-images/properties/7/5/9/1644927339_weather_1.jpg"
          alt="weather"
          className="weather-image"
        />
      </div>
      <div className="right-panel">
        <input
          type="text"
          placeholder="City..."
          value={city}
          onChange={(e) => setCity(e.target.value)}
          onKeyDown={handleKeyDown}
        />
        <button onClick={handleSearch}>Get Weather</button>

        {error && <p className="error">{error}</p>}

        {weather && (
          <div className="weather-data">
            <p><strong>Location:</strong> {weather.location}</p>
            <p><strong>Temperature:</strong> {weather.temperature}</p>
            <p><strong>Humidity:</strong> {weather.humidity}</p>
            <p><strong>Conditions:</strong> {weather.conditions}</p>
          </div>
        )}
      </div>
    </div>
  );
}

export default WeatherApp;

App.css

body {
  margin: 0;
  font-family: 'Segoe UI', sans-serif;
  background: linear-gradient(to right, #7bdff2, #b2f7ef, #eff7f6, #f7d6e0, #f2b5d4);
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
}

.container {
  display: flex;
  width: 80%;
  max-width: 900px;
  background: #1e1e1e;
  border-radius: 20px;
  overflow: hidden;
  box-shadow: 0 10px 30px rgba(0,0,0,0.3);
}

.left-panel {
  flex: 1;
  background-color: #a3e4f7;
  padding: 30px;
  text-align: center;
}

.left-panel h1 {
  font-size: 2.5rem;
  margin-bottom: 10px;
}

.left-panel p {
  font-size: 1.1rem;
}

.weather-image {
  width: 70%;
  margin-top: 20px;
}

.right-panel {
  flex: 1;
  padding: 30px;
  background-color: #1e1e1e;
  color: white;
}

input {
  width: 70%;
  padding: 10px;
  font-size: 1rem;
  border: none;
  border-bottom: 2px solid #00d1ff;
  background: transparent;
  color: white;
  margin-right: 10px;
}

input:focus {
  outline: none;
}

button {
  padding: 10px 15px;
  background-color: transparent;
  color: #00d1ff;
  border: 2px solid #00d1ff;
  cursor: pointer;
  font-weight: bold;
  border-radius: 5px;
}

.weather-data {
  margin-top: 20px;
}

.weather-data p {
  font-size: 1.1rem;
  border-bottom: 1px solid #00d1ff;
  padding: 5px 0;
}

.error {
  color: red;
  margin-top: 15px;
}

```

# OUTPUT

![Screenshot 2025-04-19 095055](https://github.com/user-attachments/assets/9683c801-fe4d-424a-bfa3-def48c0b437a)

![Screenshot 2025-04-19 095254](https://github.com/user-attachments/assets/9059b51f-a51f-451b-b1e5-d83a18fd20b4)


# RESULT
The giver task is implemented by reactor(Weather-app).
