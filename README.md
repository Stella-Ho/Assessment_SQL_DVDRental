# Assessment_SQL_DVDRental

## Overview


## Objective
- Create 10 SQL queries for DVD rental database
- Extract CSV result for each of the query
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
![ERD](https://github.com/Stella-Ho/Assessment_SQL_DVDRental/assets/141046828/e3d28a81-592f-43b7-9c77-7b240e0a0505)
