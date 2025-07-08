# My Tasker projects

Please feel free to use and modify any of these projects as you see fit! If you find a bug, please [submit an issue in this repository](https://github.com/aarosmit/tasker-tasks/issues). If you make a project better, [submit an issue](https://github.com/aarosmit/tasker-tasks/issues) and I can try to incorporate your changes!

**Downloads are available on the [Releases page](https://github.com/aarosmit/tasker-tasks/releases) or through the TaskerNet links below!**

## Will it rain? ([TaskerNet](https://taskernet.com/shares/?user=AS35m8khgdlKUqH3A8l4hlHzPyAboljs64wgsYvPkKDEqLLboSV5qMXLNUBUw9IhDk0LzL0%3D&id=Project%3AWill+it+rain%3F))

  - This project notifies you of any precipitation within the next hour for your current location.
    - Every five minutes, it fetches your location and then a weather forecast for that location using [OpenWeatherMap's OneCall API 3.0](https://openweathermap.org/api/one-call-3).
    - It supports liquid and solid states of precipitation, which are based on the temperature of your current location (e.g. if temp < 32, then "snow"). I have chosen the terms "rain" and "snow" to identify these two forms of precipitation.
    - It classifies the intensity of the precipitation (light, moderate, heavy) using the parameters from [this website](https://www.baranidesign.com/faq-articles/2020/1/19/rain-rate-intensity-classification).
    - The notifications it returns have two primary states:
      - If it is currently raining/snowing, the notification will let you know when the rain is expected to stop or if it will continue for the next hour.
      - If rain/snow is expected within the next hour, the notification will let you know when the rain/snow will start.
    - If no rain/snow is expected, no notification will be produced and remaining notifications will be cleared.
    - Tapping the notification will open the weather app you define under the "open-weather" task.
  - Prerequisites
    - **You must sign up and get an API key at [OpenWeatherMap](https://openweathermap.org/api).** Make sure it is the OneCall API 3.0. You get 1,000 free calls per day, so just don't set your profile frequency faster than one activation every two minutes or so.
      - **Save your API key under a variable named "%OpenWeatherAPI".**
    - **This relies on OpenWeatherMap's "minutely" forecast, which is not available in every location** (but seems to have good coverage across the contiguous US and Europe). The task will flash a message if this is the case or if the HTTP Request to the API fails.
  - Inspiration
    - Dark Sky once had an app for Android that would send you helpful alerts letting you know when rain would be starting/stopping. This project simply tries to mimic that. (But for free.)
