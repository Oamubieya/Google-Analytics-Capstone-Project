# Google-Analytics-Capstone-Project

This repository contains an analysis completed for the capstone project of the Google Data Analytics Certificate course.

In this case study I used the data from a fictional bike rental company, Cyclistic, to try and determine the main differences between annual members and casual rider.  I will showcase he full process of cleaning, analyzing and visualizing the data, along with my final suggestions and summary of the data.

## The Data

To analyze Cyclystics historical trip data I used the previous 12 months of Cyclystic trip data pulled from [divvy trip database](https://divvy-tripdata.s3.amazonaws.com/index.html).

## Process

The tools I used to analyze the data were Excel, SQL and Tableau.

### Excel

I used this for the initial cleaning and the processing of the individual .csv files. I also added two more columns, ride_length and day_of_week, in order to gather more insights into our analysis. When creating the ride_length column I was able to find rows where the time started_at was later than the time ended_at and was able to delete those rows.

### SQL

Since the dataset was too large to work on in excel I imported the twelve CSV files into SQL and merged them into a single file called divvy_trip_data_merged. In total there are 5,723,387 rows. No duplicates or other errors were found in the data. Due to the large amount of units I opted to delete rows with null values in start_station_name and end_station_name leaving a total of 4,641,279 rows.

>SELECT * 
FROM `divvy_trips.divvy_trip_data_2021_04`
UNION ALL
SELECT * 
FROM `divvy_trips.divvy_trip_data_2021_05`
UNION ALL
SELECT * 
FROM `divvy_trips.divvy_trip_data_2021_06`
UNION ALL
SELECT * 
FROM `divvy_trips.divvy_trip_data_2021_07`
UNION ALL
SELECT * 
FROM `divvy_trips.divvy_trip_data_2021_08`
UNION ALL
SELECT * 
FROM `divvy_trips.divvy_trip_data_2021_09`
UNION ALL
SELECT * 
FROM `divvy_trips.divvy_trip_data_2021_10`
UNION ALL
SELECT * 
FROM `divvy_trips.divvy_trip_data_2021_11`
UNION ALL
SELECT * 
FROM `divvy_trips.divvy_trip_data_2021_12`
UNION ALL
SELECT * 
FROM `divvy_trips.divvy_trip_data_2022_01`
UNION ALL
SELECT * 
FROM `divvy_trips.divvy_trip_data_2022_02`
UNION ALL
SELECT * 
FROM `divvy_trips.divvy_trip_data_2022_03`

### Tableau

I used this to create visualizations about the information gathered through analysis. All of which can be viewed [here](https://public.tableau.com/app/profile/olabanji.amubieya/viz/CaseStudyBikeShareAnalysis_16513350695540/Top10StartStation_1)

## Analysis

*Through my analysis I found that of the 4,641,279 trips members accounted for 2,596,985 trips (55.95%) and casual members accounted for 2,044,294 trips (44.05%).
