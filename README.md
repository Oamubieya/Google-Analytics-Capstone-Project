# Cyclistic Bike Share Data Analysis
## Scenario

You are a junior data analyst working in the marketing analyst team at Cyclistic, a bike-share company in Chicago. The director of marketing believes the company’s future success depends on maximizing the number of annual memberships. Therefore, your team wants to understand how casual riders and annual members use Cyclistic bikes differently. From these insights, your team will design a new marketing strategy to convert casual riders into annual members. But first, Cyclistic executives must approve your recommendations, so they must be backed up with compelling data insights and professional data visualizations.

## Ask

1. How do annual members and casual riders use Cyclistic bikes differently?
2. Why would casual riders buy Cyclistic annual memberships?
3. How can Cyclistic use digital media to influence casual riders to become members?

## The Data

To analyze Cyclystics historical trip data I used the previous 12 months of Cyclystic trip data (04/2021 - 03/2022) pulled from [divvy trip database](https://divvy-tripdata.s3.amazonaws.com/index.html). These datasets contain the following 13 columns.

![download](https://user-images.githubusercontent.com/105673465/186822412-807f4511-3e11-40fd-aa87-8970215e2fc0.png)

## Process

The tools I used to analyze the data were Excel, SQL and Tableau.

### Excel

In order to process the data from the datasets I did the initial cleaning of the individual .csv files in excel. To gather more information for analysis I also added two more columns, ride_length and day_of_week. After creating the ride_length column I was able to find conflicting rows where the time started_at was later than the time ended_at. For a proper analysis these rows were deleted.

### SQL

Since the dataset was too large to work on in excel I imported the twelve CSV files into Bigquery and merged them into a single file called divvy_trip_data_merged. In total there are 5,723,387 rows. No duplicates or other errors were found in the data. Due to the large amount of units I opted to delete rows with null values in start_station_name and end_station_name leaving a total of 4,641,279 rows.
```TSQL
-- Merging the 12 datasets into one table for better usability
SELECT * 
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
```

### Tableau

I used this to create visualizations about the information gathered through analysis. All of which can be viewed [here](https://public.tableau.com/app/profile/olabanji.amubieya/viz/CaseStudyBikeShareAnalysis_16513350695540/Top10StartStation_1)

## Analysis

* I found that of the 4,641,279 trips members accounted for 2,596,985 trips (55.95%) and casual members accounted for 2,044,294 trips (44.05%).
![download](https://user-images.githubusercontent.com/105673465/186812991-fc5c8fc9-ad9f-4e58-8a19-3c27600b3a1c.png)

* The average length of a trip for all cyclics was 21.36 minutes, 32.05 for casuals and 12.94 for members.
![download](https://user-images.githubusercontent.com/105673465/186813008-04f72dd0-b3c8-4432-9889-70aadcfa203c.png)

* Of the three bike types, classic bikes were used by the majority of both casuals and members.
![download](https://user-images.githubusercontent.com/105673465/186813027-b84d373e-d46b-4f55-822e-1024b63930de.png)

* July and August are the months with the most rides with July being the highest for casuals and August the highest for members. January and February are the months with the least amount of rides for everyone.
![download](https://user-images.githubusercontent.com/105673465/186813055-8d4505bb-1137-419c-be05-7dde5611a769.png)

* Weekends are the most popular ride times for casual riders while weekdays are the most popular for members.
![download](https://user-images.githubusercontent.com/105673465/186813067-70ddd363-a843-4af5-9b05-8f4bd9a7c3e9.png)

* The most popular stations for casual riders are 
![download](https://user-images.githubusercontent.com/105673465/186812667-df1ffd17-e27c-489c-a912-fff61c3a36bd.png)

* The most popular stations for members are
![download](https://user-images.githubusercontent.com/105673465/186812732-ee250cdb-d4df-4dc9-9ce8-b8f9802026c7.png)


## Conclusion

Based on the findings of this analysis these are my top recommendations.

* When looking at the data casual riders ride more on the weekend. In order to appeal to casual riders, I would suggest adding promotions or discounts targeting lower rates for weekday rides. I would place these promotional messages at the top 10 start and end stations for casuals in order to reach the largest proportion of casuals.

* Casual riders spend on average spend twice as much time riding their bikes than members. I would provide posters or messages at stations to show how much money could be saved in the long run by becoming a member rather than paying per trip or duration.
