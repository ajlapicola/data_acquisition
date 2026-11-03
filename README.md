# Fireball Energy and Atmospheric Characteristics

This project explores NASA/JPL CNEOS records of fireballs: unusually bright meteors detected by U.S. Government sensors.

## Research question

**Among reported fireballs, how are altitude at peak brightness and entry speed associated with estimated total radiated energy?**

The analysis is exploratory. It looks for patterns in the recorded events and does not test whether altitude or speed causes a fireball to release more energy.

## Data source

The data come from the [NASA/JPL CNEOS Fireball Data API](https://ssd-api.jpl.nasa.gov/doc/fireball.html). The API returns JSON records with fields such as date and time, latitude and longitude, altitude at peak brightness, estimated total radiated energy, estimated impact energy, and entry velocity components.

The collection request requires records to have location, altitude, and entry velocity components. It also requests the velocity fields. This filtering makes the records more useful for comparing the selected characteristics, but may reduce the number of observations. Check and report the final sample size and missing values in the analysis.

The database is not a complete catalog of all meteors or fireballs. CNEOS reports events detected by government sensors and notes that only the brightest fireballs are included. Findings should therefore be described as patterns among the reported records.

## Data and workflow

The project uses Python to:

1. Request fireball records from the API.
2. Check the HTTP response and convert the returned JSON fields and rows into a pandas DataFrame.
3. Save the original API records as `data/raw/fireballs_raw.csv`, when permitted and appropriate to include in the repository.
4. Read the saved data and convert the date and numeric columns to suitable pandas types.
5. Explore radiated energy in relation to altitude at peak brightness and entry speed. Entry speed can be calculated from the velocity components `vx`, `vy`, and `vz`.

The repository contains the Python collection, cleaning, and exploratory analysis code. Add or update the file names here as the project code is finalized.

## Related links

- [CNEOS Fireballs overview and data](https://cneos.jpl.nasa.gov/fireballs/intro.html)
- [Fireball Data API documentation](https://ssd-api.jpl.nasa.gov/doc/fireball.html)
- [JPL SSD/CNEOS API Fair Use Policy](https://ssd-api.jpl.nasa.gov/)

