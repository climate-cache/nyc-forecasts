# Climate Cache: New York City - Forecasts

![weather workflow](https://github.com/climate-cache/nyc-forecasts/actions/workflows/nyc_14d_openmeteo.yml/badge.svg)

### A historical archive of hourly 14-day forecasts for New York City, powered by the free Open-Meteo API.

#### Data starts at: 2023-10-01 @ 05:00 EDT

#### Looking for historical weather data from the same source? Check out [Climate Cache: NYC Weather](https://github.com/climate-cache/nyc-weather)

## Data Notes
 The forecast for 2023-10-05 20:00 is a copy of 2023-10-05 19:00 until I can find the real one. That was before I was using GitHub Actions so it's somewhere on my computer.
### Formatting
GitHub Actions grabs data in a more efficient but less readable format, but some of the earlier data
was grabbed with a Python script so it's formatted normally. This shouldn't cause
any problems with analysis, but in case you're wondering why some
forecasts are half the size of others that's why. I'll eventually either convert all the data to the less readable format, or start
formatting all the incoming data.

### Source
Every hour using GitHub Actions, a 14-day hourly forecast *(336hrs)* is taken from open-meteo.com in JSON format and committed to this repository.

### Variables Recorded

| Variable                    | Description                              | Units                      |
|-----------------------------|------------------------------------------|----------------------------|
| `time`                      | Date of the weather record               | ISO8601 (2023-10-08T00:00) |
| `temperature_2m`            | Temperature at 2m/6ft above ground       | °F                         |
| `relative_humidity_2m`      | Relative humidity at 2m/6ft above ground | %                          |
| `dewpoint_2m`               | Dewpoint at 2m/6ft above ground          | °F                         |
| `apparent_temperature`      | Apparent temperature                     | °F                         |
| `precipitation_probability` | Probability of precipitation             | %                          |
| `rain`                      | Rainfall                                 | inches                     |
| `showers`                   | Showers                                  | inches                     |
| `snowfall`                  | Snowfall                                 | inches                     |
| `surface_pressure`          | Surface pressure                         | hPa                        |
| `cloudcover`                | Cloud cover                              | %                          |
| `windspeed_10m`             | Wind speed at 10m above ground           | mp/h                       |
| `winddirection_10m`         | Wind direction at 10m above ground       | °                          |
| `windgusts_10m`             | Wind gusts at 10m above ground           | mp/h                       |

### Sample JSON File:
#### Values cut for brevity, this shows hours 1 and 336, the real file has all 336
    
```json
{
    "latitude": 40.710335,
    "longitude": -73.99307,
    "generationtime_ms": 0.10597705841064453,
    "utc_offset_seconds": -14400,
    "timezone": "America/New_York",
    "timezone_abbreviation": "EDT",
    "elevation": 7.0,
    "hourly_units": {
        "time": "iso8601",
        "temperature_2m": "°F",
        "relativehumidity_2m": "%",
        "dewpoint_2m": "°F",
        "apparent_temperature": "°F",
        "precipitation_probability": "%",
        "rain": "inch",
        "showers": "inch",
        "snowfall": "inch",
        "surface_pressure": "hPa",
        "cloudcover": "%",
        "windspeed_10m": "mp/h",
        "winddirection_10m": "°",
        "windgusts_10m": "mp/h"
    },
    "hourly": {
        "time": [
            "2023-10-08T00:00",
            ...
            "2023-10-21T23:00"
        ],
        "temperature_2m": [
            52.1,
            ...
            53.2
        ],
        "relativehumidity_2m": [
            78,
            ...
            50
        ],
        "dewpoint_2m": [
            45.4,
            ...
            35.1
        ],
        "apparent_temperature": [
            46.8,
            ...
            45.4
        ],
        "precipitation_probability": [
            0,
            ...
            0
        ],
        "rain": [
            0.0,
            ...
            0.0
        ],
        "showers": [
            0.0,
            ...
            0.0
        ],
        "snowfall": [
            0.0,
            ...
            0.0
        ],
        "surface_pressure": [
            1002.8,
            ...
            1006.0
        ],
        "cloudcover": [
            0,
            ...
            99
        ],
        "windspeed_10m": [
            9.6,
            ...
            10.8
        ],
        "winddirection_10m": [
            259,
            ...
            249
        ],
        "windgusts_10m": [
            26.8,
            ...
            20.8
        ]
    }
}
```

###### Data in this repository is taken from the free public version of Open-Meteo's API, so all data falls under [Attribution 4.0 International (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/) according to [their website](https://open-meteo.com/en/license). Credit should go to Open-Meteo, any mention of this repo is optional.