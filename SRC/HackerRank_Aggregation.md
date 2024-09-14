# Revising Aggregations - The Count Function
---
Query a count of the number of cities in CITY having a Population larger than 100,000.

The CITY table is described as follows:

![Table](https://s3.amazonaws.com/hr-challenge-images/8137/1449729804-f21d187d0f-CITY.jpg)

```sql
Select Count(Name) From City
Where Population > 100000; 
```

# Revising Aggregations - The Sum Function
---
Query the total population of all cities in CITY where District is California.

```sql
Select Sum(Population) From City
Where District = 'California';
```

# Revising Aggregation - Averages
---
Query the average population of all cities in CITY where District is California.

```sql
Select Avg(Population) From City
Where District = 'California';
```

# Averages Population
---
Query the average population for all cities in CITY, rounded down to the nearest integer.

```sql
Select Round(Avg(Population),0) From City;
```

# Japan Population
---
Query the sum of the populations for all Japanese cities in CITY. The COUNTRYCODE for Japan is JPN.

```sql
Select Sum(Population) From City
Where  countryCode = 'JPN';
```

# Population Density Difference
---
Query the difference between the maximum and minimum populations in CITY.

```sql
Select Max(Population) - Min(Population) From City;
```

# The Blunder
---
Samantha was tasked with calculating the average monthly salaries for all employees in the EMPLOYEES table, but did not realize her keyboard's  key was broken until after completing the calculation. She wants your help finding the difference between her miscalculation (using salaries with any zeros removed), and the actual average salary.
Write a query calculating the amount of error (i.e.:Actual - miscalculated  average monthly salaries), and round it up to the next integer.

The EMPLOYEES table is described as follows:

![Table](https://s3.amazonaws.com/hr-challenge-images/12893/1443817108-adc2235c81-1.png)

Note: Salary is per month.

```sql
Select Ceil(Avg(Salary) - Avg(Replace(Salary,'0',''))) From Employees;
```

# Top Earners
---
We define an employee's total earnings to be their monthly salary * Months worked, and the maximum total earnings to be the maximum total earnings for any employee in the Employee table. Write a query to find the maximum total earnings for all employees as well as the total number of employees who have maximum total earnings. Then print these values as 2 space-separated integers.

The Employee table containing employee data for a company is described as follows:

![Table](https://s3.amazonaws.com/hr-challenge-images/19629/1458557872-4396838885-ScreenShot2016-03-21at4.27.13PM.png)

```sql
Select Max(Months * Salary) As Total_Earning, Count(*) From Employee
Where (Months * Salary) = (Select Max(Months * Salary) From Employee);
```

# Weather Observation Station 2
---
Query the following two values from the STATION table:
1. The sum of all values in LAT_N rounded to a scale of 2 decimal places.
2. The sum of all values in LONG_W rounded to a scale of 2 decimal places.

The STATION table is described as follows:

![Table](https://s3.amazonaws.com/hr-challenge-images/9336/1449345840-5f0a551030-Station.jpg)

```sql
Select Round(Sum(Lat_N),2), Round(Sum(Long_W),2) From Station;
```

# Weather Obervation Station 13
---
Query the sum of Northern Latitudes (LAT_N) from STATION having values greater than 38.7880 and less than 137.2345. Truncate your answer to 4 decimal places.

```sql
Select Round(Sum(Lat_N),4) From Station
Where Lat_N > 38.7880 And Lat_N < 137.2345;
```

# Weather Obervation Station 14
---
Query the greatest value of the Northern Latitudes (LAT_N) from STATION that is less than 137.2345. Truncate your answer to 4 decimal places.

```sql
Select Round(Lat_N,4) From Station 
Where Lat_N < 137.2345
Order By Lat_N Desc
Limit 1;
```

# Weather Observation Sation 15
---
Query the Western Longitude (LONG_W) for the largest Northern Latitude (LAT_N) in STATION that is less than 137.2345. Round your answer to 4 decimal places.

```sql
Select Round(Long_W,4) From Station
Where Lat_N = (Select Lat_N From Station 
               Where Lat_N < 137.2345 
               Order By Lat_N Desc 
               Limit 1);
```

# Weather Observation Station 16
---
Query the smallest Northern Latitude (LAT_N) from STATION that is greater than 38.7780. Round your answer to 4 decimal places.

```sql
Select Round(Lat_N,4) From Station
Where Lat_N = (Select Lat_N From Station 
               Where Lat_N > 38.7780 
               Order By Lat_N Asc 
               Limit 1);
```

# Weather Observation Station 17
---
Query the Western Longitude (LONG_W)where the smallest Northern Latitude (LAT_N) in STATION is greater than 38.7780. Round your answer to 4 decimal places.

```sql
Select Round(Long_W,4) From Station
Where Lat_N = (Select Lat_N From Station 
               Where Lat_N > 38.7780 
               Order By Lat_N Asc 
               Limit 1);
```

# Weather Observation Station 18
---
Consider P<Sub.1</Sub>(a,b) and P<Sub>2</Sub>(c,d) to be two points on a 2D plane.

 - a happens to equal the minimum value in Northern Latitude (LAT_N in STATION).
 - b happens to equal the minimum value in Western Longitude (LONG_W in STATION).
 - c happens to equal the maximum value in Northern Latitude (LAT_N in STATION).
 - d happens to equal the maximum value in Western Longitude (LONG_W in STATION).
Query the Manhattan Distance between points P<Sub>1</Sub> and P<Sub>2</Sub> and round it to a scale of  decimal places.

```sql

```
# Weather Observation Station 19
---
```sql

```
# Weather Observation Station 20
---
```sql

```
# 
---
```sql

```
