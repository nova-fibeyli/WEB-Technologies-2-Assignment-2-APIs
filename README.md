# Weather & News Web Application

## Overview
This is a web application that displays real-time **weather information** and **latest news**. The backend is powered by **Express.js**, and the frontend is built using **HTML, JavaScript, and Bootstrap**. The application also includes:

- **Geolocation and Mapping**: Uses **Leaflet.js** to visually showcase the location of cities based on latitude and longitude. Users can view their current location on an interactive map.
- **Weather API**: Fetches real-time weather updates from **OpenWeatherAPI**, displaying temperature, humidity, wind speed, and weather conditions.
- **News API**: Retrieves the latest news headlines using **NewsAPI.ai** to provide up-to-date information relevant to the user's location.
- **Fact API**: (Optional) Fetches interesting facts about the city or country to enhance user engagement.

---

## Installation Guide
### **1. Prerequisites**
Ensure you have the following installed:
- [Node.js](https://nodejs.org/) (v14+ recommended)
- [npm](https://www.npmjs.com/) (comes with Node.js)
- A text editor (VS Code recommended)
- PowerShell or Command Prompt

### **2. Setup Instructions**
1. **Extract the Project**:
   ```powershell
   cd C:\ass2
   ```
2. **Install dependencies**:
   ```powershell
   npm install
   ```
3. **Set up `.env` file** (Create manually in `C:\ass2\` if not present):
   ```plaintext
   OPENWEATHER_API_KEY=your_openweather_api_key
   NEWS_API_AI_KEY=your_newsapi_ai_key
   ```
4. **Run the server**:
   ```powershell
   node server.js
   ```
5. **Access the Web App**:
   Open **[http://localhost:3000](http://localhost:3000)** in your browser.

---

## API Endpoints & Usage

### **1. Get Weather Data**
#### **Endpoint:**
```
GET /api/weather?city=CityName
```
#### **Example Request:**
```
http://localhost:3000/api/weather?city=Astana
```
#### **Response Format (JSON):**
```json
{
  "coord": {"lon": 71.446, "lat": 51.1801},
  "weather": [{"main": "Clouds", "description": "overcast clouds", "icon": "04n"}],
  "main": {"temp": -7.03, "feels_like": -10.64, "pressure": 1027, "humidity": 93},
  "wind": {"speed": 2, "deg": 190},
  "clouds": {"all": 100},
  "name": "Nur-Sultan"
}
```

---

### **2. Get News Articles**
#### **Endpoint:**
```
GET /api/news
```
#### **Example Request:**
```
http://localhost:3000/api/news
```
#### **Response Format (JSON):**
```json
{
  "articles": [
    {
      "title": "Breaking News Headline",
      "description": "Short news summary.",
      "url": "https://newsapi.ai/article-link",
      "source": "NewsAPI.ai"
    }
  ]
}
```

---

### **3. Get City Facts (Optional)**
#### **Endpoint:**
```
GET /api/facts?city=CityName
```
#### **Example Request:**
```
http://localhost:3000/api/facts?city=Astana
```
#### **Response Format (JSON):**
```json
{
  "city": "Astana",
  "country": "Kazakhstan",
  "fact": "Astana was renamed back to its original name in 2022."
}
```

---

## Frontend Features
- **Weather Section**: Displays city temperature, weather condition, wind speed, humidity, and pressure.
- **News Section**: Lists the latest news articles with clickable links.
- **Map**: Uses **Leaflet.js** to display a map based on user location.
- **City Facts**: Provides interesting facts about the selected city or country.

---

## Troubleshooting
### **1. Missing Dependencies?**
Run:
```powershell
npm install
```

### **2. API Not Working?**
- Ensure your `.env` file has valid API keys.
- Restart the server:
  ```powershell
  node server.js
  ```

### **3. Port Already in Use?**
Find and kill the process using port 3000:
```powershell
netstat -ano | findstr :3000
```
Then:
```powershell
taskkill /PID <PID> /F
```
Restart the server after this.

---

## License
This project is open-source and can be used freely.

