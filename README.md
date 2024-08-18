# Flight Delays and Cancellations Analysis

This project aims to analyze flight delays and cancellations in the Pacific Northwest, using two datasets containing flight and weather information. The analysis focuses on identifying the most affected airlines and routes, as well as examining the impact of wind gusts on departure delays.

## Project Overview

The project leverages data analysis techniques to uncover insights about flight delays and cancellations. The primary objectives include:

- Identifying the airlines and routes most affected by flight delays.
- Examining the impact of wind gusts on departure delays for the SEA (Seattle) and PDX (Portland) airports.
- Visualizing the results to highlight key findings.

## Datasets

The analysis is based on two datasets:

### 1. flights2022.csv: 
Contains flight information for the year 2022.
### 2. flights_weather2022.csv:
Contains weather data corresponding to the flights.

### Columns in flights_weather2022.csv

- year, month, day
- dep_time, sched_dep_time, dep_delay
- arr_time, sched_arr_time, arr_delay
- carrier, flight, tailnum
- origin, dest, air_time, distance
- hour, minute, airline, route
- temp, dewp, humid, wind_dir, wind_speed, wind_gust
- precip, pressure, visib

### Columns in flights2022.csv

- year, month, day
- dep_time, sched_dep_time, dep_delay
- arr_time, sched_arr_time, arr_delay
- carrier, flight, tailnum
- origin, dest, air_time, distance
- hour, minute, time_hour, airline

## Analysis Steps

### 1. Data Loading

The data from both CSV files is loaded into Pandas DataFrames for analysis. The `flights_weather` DataFrame is enhanced with a `route` column, created by combining the origin and destination airports.

### 2. Delays and Cancellations Analysis

#### For Routes:
- **Average Departure Delay**: Calculated for each route.
- **Number of Cancellations**: Determined by counting the instances where `dep_delay` is `NaN`.

#### For Airlines:
- **Average Departure Delay**: Calculated for each airline.
- **Number of Cancellations**: Determined by counting the instances where `dep_delay` is `NaN`.

### 3. Visualization

Two bar graphs are generated:
- **Top 9 Routes with Most Cancellations**: Highlights the routes with the highest number of cancellations.
- **Top 9 Airlines with Longest Departure Delays**: Shows the airlines with the highest average departure delays.

### 4. Wind Gusts Impact

The analysis checks whether wind gusts of 10 mph or more result in larger average departure delays for SEA and PDX airports. The result is stored in a boolean variable `wind_response`.

## Results

### Routes Delays and Cancellations:
- The DataFrame `routes_delays_cancels` shows the average delays and number of cancellations for each route.
### Airlines Delays and Cancellations:
The DataFrame `airlines_delays_cancels` shows the average delays and number of cancellations for each airline.
### Wind Impact:
 The boolean `wind_response` indicates whether wind gusts of 10+ mph cause higher delays at SEA and PDX.

## Conclusion

This project provides insights into the factors affecting flight delays and cancellations in the Pacific Northwest. The analysis reveals the most affected airlines and routes, and shows how wind gusts can impact departure delays at major airports.

## Dependencies

- Python 3.x
- Pandas
- Matplotlib
