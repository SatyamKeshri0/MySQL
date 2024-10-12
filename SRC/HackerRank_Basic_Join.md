# Population Census
---
Given the CITY and COUNTRY tables, query the sum of the populations of all cities where the CONTINENT is 'Asia'.

Note: CITY.CountryCode and COUNTRY.Code are matching key columns.

The CITY and COUNTRY tables are described as follows:

![Table1](https://s3.amazonaws.com/hr-challenge-images/8137/1449729804-f21d187d0f-CITY.jpg)

![Table2](https://s3.amazonaws.com/hr-challenge-images/8342/1449769013-e54ce90480-Country.jpg)

```sql
Select Sum(City.Population) From City 
Inner Join Country On City.CountryCode = Country.Code
Where Continent = 'Asia';
```

# African Cities
---
Given the CITY and COUNTRY tables, query the names of all cities where the CONTINENT is 'Africa'.

Note: CITY.CountryCode and COUNTRY.Code are matching key columns.

```sql
Select City.Name From City
Inner Join Country On City.CountryCode = Country.Code
Where Continent = 'Africa';
```

# Average Population of Each Continent
---
Given the CITY and COUNTRY tables, query the names of all the continents (COUNTRY.Continent) and their respective average city populations (CITY.Population) rounded down to the nearest integer.

Note: CITY.CountryCode and COUNTRY.Code are matching key columns.

```sql
Select Country.Continent, Floor(Avg(City.Population)) From City
Inner Join Country On City.CountryCode = Country.Code
Group By Country.Continent;
```

# The Report
---
You are given two tables: Students and Grades. Students contains three columns ID, Name and Marks.

![Table1](https://s3.amazonaws.com/hr-challenge-images/12891/1443818166-a5c852caa0-1.png)

Grades contains the following data:
![Table2](https://s3.amazonaws.com/hr-challenge-images/12891/1443818137-69b76d805c-2.png)

Ketty gives Eve a task to generate a report containing three columns: Name, Grade and Mark. Ketty doesn't want the NAMES of those students who received a grade lower than 8. The report must be in descending order by grade -- i.e. higher grades are entered first. If there is more than one student with the same grade (8-10) assigned to them, order those particular students by their name alphabetically. Finally, if the grade is lower than 8, use "NULL" as their name and list them by their grades in descending order. If there is more than one student with the same grade (1-7) assigned to them, order those particular students by their marks in ascending order.

Write a query to help Eve.
Note
Print "NULL"  as the name if the grade is less than 8.

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

