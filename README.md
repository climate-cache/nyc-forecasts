# Climate Cache: New York City - Forecasts
#### 14-Day Hourly Forecasts - Archived Every 60 Minutes 
##### (Started @ 05:00 on 2023-10-01)

## Data Cleanliness
GitHub Actions grabs data in a more efficient but less readable format, but some of the earlier data
was grabbed with a Python script so it's formatted normally. This shouldn't cause
any problems with analysis, but in case you're wondering why some
forecasts are half the size of others that's why. I'll eventually either convert all the data to the less readable format, or start
formatting all the incoming data.

## Data Source
Every hour using GitHub Actions, a 14-day hourly forecast *(336hrs)* is taken from open-meteo.com in JSON format and committed to this repository.

###### Data in this repository is taken from the free public version of Open-Meteo's API, so all data falls under [Attribution 4.0 International (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/) according to [their website](https://open-meteo.com/en/license). Credit should go to Open-Meteo, any mention of this repo is optional.