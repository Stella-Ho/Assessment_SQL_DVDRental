# Assessment_SQL_DVDRental <img src="https://github.com/Stella-Ho/Assessment_SQL_DVDRental/blob/6adb6504f4cf14326be437e4a50e84d2896f8824/DVD_photo.png" width="50"> 


## Overview
In this project, it used POSTGRESQL database and extracted 10 SQL queries and 10 result file ".CSV" for these queries for DVD Rental database. It's also listed out all the table and created ERD which showed in below section.

## Objective
The objective of this research is to analyze DVD Rental data, based on the data analysis, we have more insight on the customers usage by category or amount as well as consolidate data by different criteria to see the analysis of rental duration, film length, top actor and customers status etc.

- Install POSTGRESQL-ver.15.3 and PGADMIN4-ver.7.3 and run DVD rental dataset file ".TAR"
- Create 10 SQL queries for DVD rental database
- Extract CSV result for each of the query
- Create Github repository to store the results
- DVD Rental SQL Analysis

## Database
There are 15 tables in the database as below.
```
SELECT table_name
FROM information_schema.tables
WHERE table_type='BASE TABLE'
AND table_schema='public';
```
actor; store; address; category; city; country; customer; film_actor; film_category; inventory; language; rental; staff; payment; film


## Entity Relationship Diagram (ERD)
ERD visualizes the relationships between all entities which link up customers identity with DVD rental details in a database.

<img src="https://github.com/Stella-Ho/Assessment_SQL_DVDRental/assets/141046828/e3d28a81-592f-43b7-9c77-7b240e0a0505" width="800">

## DVD Rental SQL Analysis
Click [Here](https://github.com/Stella-Ho/Assessment_SQL_DVDRental/blob/6adb6504f4cf14326be437e4a50e84d2896f8824/SQL_Analysis.md)
