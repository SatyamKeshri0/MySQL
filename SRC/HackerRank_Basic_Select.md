# Revising the Select Query I
---
Query all columns for all American cities in the CITY table with populations larger than 100000. The CountryCode for America is USA.

The CITY table is described as follows:

![Table](https://s3.amazonaws.com/hr-challenge-images/8137/1449729804-f21d187d0f-CITY.jpg)

```sql
SELECT * FROM City WHERE CountryCode = 'USA' AND Population > 100000;
```

# Revising the Select Query II
---
Query the NAME field for all American cities in the CITY table with populations larger than 120000. The CountryCode for America is USA.

```sql
Select Name from City Where Population > 120000 AND CountryCode='USA';
```

# Select All 
---
Query all columns (attributes) for every row in the CITY table.

```sql
Select * from CITY;
```

# Select By ID
---
Query all columns for a city in CITY with the ID 1661.

```sql
Select * from CITY 
where ID = 1661;
```

# Japanese Cities' Attributes
---
Query all attributes of every Japanese city in the CITY table. The COUNTRYCODE for Japan is JPN.

```sql
Select * from CITY
Where COUNTRYCODE = 'JPN';
```

# Japanese Cities Names
---
Query the names of all the Japanese cities in the CITY table. The COUNTRYCODE for Japan is JPN.

```sql
Select NAME from CITY
Where COUNTRYCODE = 'JPN';
```

# Weather Observation Station 1
---
Query a list of CITY and STATE from the STATION table.

The STATION table is described as follows:

![TABLE](https://s3.amazonaws.com/hr-challenge-images/9336/1449345840-5f0a551030-Station.jpg)

```sql
Select CITY, STATE from STATION;
```

# Weather Obervation Station 3
---
Query a list of CITY names from STATION for cities that have an even ID number. Print the results in any order, but exclude duplicates from the answer.

```sql
Select Distinct CITY from STATION
Where Mod(ID,2) = 0; 
```

# Weather Observation Station 4
---
Find the difference between the total number of CITY entries in the table and the number of distinct CITY entries in the table.

```sql
Select Count(CITY) - Count(Distinct(CITY)) from Station;
```

# Weather Observation Station 5
---
Query the two cities in STATION with the shortest and longest CITY names, as well as their respective lengths (i.e.: number of characters in the name). If there is more than one smallest or largest city, choose the one that comes first when ordered alphabetically.

```sql
(Select City, Length(City) from Station
Order By Length(City) ASC, City ASC Limit 1)
UNION
(Select City, Length(City) from Station
Order By Length(city) DESC, City ASC limit 1);
```

# Weather Observation Station 6
---
Query the list of CITY names starting with vowels (i.e., a, e, i, o, or u) from STATION. Your result cannot contain duplicates.

```sql
Select Distinct City from Station
Where Lower(Substr(City,1,1)) in ('a','e','i','o','u');
```

# Weather Observation Station 7
---
Query the list of CITY names ending with vowels (a, e, i, o, u) from STATION. Your result cannot contain duplicates.

```sql
Select Distinct City from Station
Where lower(substr(City,-1,1)) in ('a','e','i','o','u');
```

# Weather Observation Station 8
---
Query the list of CITY names from STATION which have vowels (i.e., a, e, i, o, and u) as both their first and last characters. Your result cannot contain duplicates.

```sql
Select Distinct City from Station
Where lower(substr(City,1,1)) in ('a','e','i','o','u')
And lower(substr(City,-1,1)) in ('a','e','i','o','u');
```

# Weather Observation Station 9
---
Query the list of CITY names from STATION that do not start with vowels. Your result cannot contain duplicates.

```sql
Select Distinct City from Station
Where lower(substr(City,1,1)) not in ('a','e','i','o','u');
```

# Werather Observation Station 10
---
Query the list of CITY names from STATION that do not end with vowels. Your result cannot contain duplicates.

```sql
Select Distinct City from Station
Where lower(substr(City,-1,1)) not in ('a','e','i','o','u');
```

# Weather Observation Station 11
---
Query the list of CITY names from STATION that either do not start with vowels or do not end with vowels. Your result cannot contain duplicates.

```sql
Select Distinct City from Station
Where lower(substr(City,1,1)) not in ('a','e','i','o','u')
Or lower(substr(City,-1,1)) not in ('a','e','i','o','u');
```

# Weather Observation Station 12
---
Query the list of CITY names from STATION that do not start with vowels and do not end with vowels. Your result cannot contain duplicates.

```sql
Select Distinct City from Station
Where lower(substr(City,1,1)) not in ('a','e','i','o','u')
And lower(substr(City,-1,1)) not in ('a','e','i','o','u');
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
