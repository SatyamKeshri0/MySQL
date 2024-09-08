# Types of Trinagles
---
Write a query identifying the type of each record in the TRIANGLES table using its three side lengths. Output one of the following statements for each record in the table:
Equilateral: It's a triangle with  sides of equal length.
Isosceles: It's a triangle with  sides of equal length.
Scalene: It's a triangle with  sides of differing lengths.
Not A Triangle: The given values of A, B, and C don't form a triangle.

The TRIANGLES table is described as follows:

![Table](https://s3.amazonaws.com/hr-challenge-images/12887/1443815629-ac2a843fb7-1.png)

```sql
Select 
Case
    When (A + B <= C) Or (A + C <= B) Or (B + C <= A) Then 'Not A Triangle'
    When (A = B) And (B = C) Then 'Equilateral'
    When (A = B) Or (B = C) Or (C = A) Then 'Isosceles'
    Else 'Scalene'
    End
From Triangles;
```

# The PADS
---
Generate the following two result sets:

1. Query an alphabetically ordered list of all names in OCCUPATIONS, immediately followed by the first letter of each profession as a parenthetical (i.e.: enclosed in parentheses). For example: AnActorName(A), ADoctorName(D), AProfessorName(P), and ASingerName(S).
2. Query the number of ocurrences of each occupation in OCCUPATIONS. Sort the occurrences in ascending order, and output them in the following format:
```Text
There are a total of [occupation_count] [occupation]s.
```
where [occupation_count] is the number of occurrences of an occupation in OCCUPATIONS and [occupation] is the lowercase occupation name. If more than one Occupation has the same [occupation_count], they should be ordered alphabetically.
Note: There will be at least two entries in the table for each type of occupation.

```sql

```

# Occupations
---
```sql

```

# Binary Tree Nodes
---
```sql

```

# New Companies
---
```sql

```

# 
---
```sql

```
