# To run the application locally in Docker:

1) Create a `.env` file in the `flask_weather_service` folder and add your OpenWeatherMap API key:
    OPENWEATHER_API_KEY="here_is_your_apikey_in_doublequotes"

2) Install Docker Desktop on your computer and make sure it is running.

3) Open a terminal (or Command Prompt) and navigate to the `flask_weather_service` folder (project root):
    cd (project_root)/flask_weather_service

4) Build the Docker image using the following command:
    docker build -t flask-weather-service .

5) Run the Docker container with the following command:
    docker run -p 5000:5000 flask-weather-service

6) The app should now be running inside the Docker container and accessible at port 5000 on your local machine. 
   You can use the microservice via browser or other tools (like `curl`) by accessing localhost at port 5000.
   For example:
       http://localhost:5000/weather?city=tampere


# The API's used in the app
1) OpenWeatherMap Geocoding API
    - for fetching the latitude and longitude of the user-given cityname

2) OpenWeatherMap Current weather data API
    - for fetching the most recent measured weather data from the user determined location