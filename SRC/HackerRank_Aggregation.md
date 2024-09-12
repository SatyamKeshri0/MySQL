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

```

# 
---
```sql

```

# 
---
```sql

```

# 
---
```sql

```

# 
---
```sql

```

# 
---
```sql

```

# 
---
```sql

```
