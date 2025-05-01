# Holidays and Location mapping

This project fetches countries and holidays data from the website: https://holidayapi.com/
Kestra and postgres is used for this project
Each flow in Kestra is automated to run based on the schedule.

## Features

- The ingestion flows ingest all the data into mutiple tables
- location_datamart flow inserts the final table that maps holidays with locations provided

## Installation

```bash
# Example:
git clone git@github.com:Speri1009/de_assignment.git
cd project
brew install colima
brew install docker docker-compose
colima start
docker-compose pull
docker-compose up
docker-compose down
Kestra: http://localhost:8080
pgadmin: http://localhost:8082
```

## Location_datamart

This table quickly give you holidays per location id for the last 1 year
Example

```
SELECT *
FROM public.locat_datamart
WHERE location_id = 'ab5df8c0-dfe7-4ca3-a9e4-c77f93e551a7'
```
