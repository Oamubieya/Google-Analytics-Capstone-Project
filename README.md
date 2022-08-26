# Google-Analytics-Capstone-Project

This repository contains an analysis completed for the capstone project of the Google Data Analytics Certificate course.

In this case study I used the data from a fictional bike rental company, Cyclistic, to try and determine the main differences between annual members and casual rider.  I will showcase he full process of cleaning, analyzing and visualizing the data, along with my final suggestions and summary of the data.

## The Data

To analyze Cyclystics historical trip data I used the previous 12 months of Cyclystic trip data pulled from [divvy trip database](https://divvy-tripdata.s3.amazonaws.com/index.html).

## Process

The tools I used to analyze the data were Excel, SQL and Tableau.

### Excel

I used this for the initial cleaning and the processing of the individual .csv files. I also added two more columns, ride_length and day_of_week, in order to gather more insights into our analysis. When creating the ride_length column I was able to find rows where the time started_at was later than the time ended_at and was able to delete those rows.
