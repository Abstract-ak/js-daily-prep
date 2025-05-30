# Weather Information Fetcher

A simple Node.js application that fetches weather information from the OpenWeatherMap API.

---

## **Project Overview**

This project retrieves weather data based on the city name provided by the user. It demonstrates working with external APIs, using the Axios library for HTTP requests, and setting up an Express.js server.

### **Features**

- Fetch real-time weather data (temperature, humidity, wind speed, and description).
- Error handling for invalid city names or API issues.
- Easy configuration using environment variables.

---

## **Prerequisites**

- Node.js installed on your system.
- Basic knowledge of JavaScript and Node.js.
- An API key from [OpenWeatherMap](https://openweathermap.org/).

---

## **Setup Instructions**

### **1. Clone the Repository**

```bash
git clone https://github.com/your-username/weather-fetcher.git
cd weather-fetcher
```

### **2. Install Dependencies**

```bash
npm install
```

### **3. Get an OpenWeatherMap API Key**

- Sign up at [OpenWeatherMap](https://openweathermap.org/).
- Generate an API key from your account dashboard.

### **4. Configure Environment Variables**

- Create a `.env` file in the project root:

```plaintext
OPENWEATHER_API_KEY=your_api_key_here
```

---

## **Project Structure**

```
weather-fetcher/
├── package.json
├── .env
├── app.js
```
