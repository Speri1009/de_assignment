# Holidays and Location mapping

This project fetches countries and holidays data from the website: https://holidayapi.com/
It uses **Kestra** for orchestration and **PostgreSQL** for storage.  
Each Kestra flow is scheduled and automated.

## Features

- Ingests data into multiple tables using scheduled flows.
- `location_datamart` flow creates a final table that maps holidays to the specified locations.

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
```

Folder location:
Use your git clone location in docker-compose.yml and appication.yml before running docker commands

Services:
Kestra: http://localhost:8080
pgadmin: http://localhost:8082

## Location_datamart

This table quickly gives you holidays per location id for the last 1 year.
For example

```
SELECT *
FROM public.locat_datamart
WHERE location_id = 'ab5df8c0-dfe7-4ca3-a9e4-c77f93e551a7'
```

## Architecture Diagram

![Location_datamart Flow Diagram](kestra-docker/flow.png)

## Future Scope for improvements

Store files such as subdivision codes and country-level location data in a cloud storage bucket (e.g., S3, GCS)
Use Terraform to securely manage API keys, database credentials, and other secrets.
