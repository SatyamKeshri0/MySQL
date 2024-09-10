# Types of Trinagles
---
Write a query identifying the type of each record in the TRIANGLES table using its three side lengths. Output one of the following statements for each record in the table:
Equilateral: It's a triangle with  sides of equal length.
Isosceles: It's a triangle with  sides of equal length.
Scalene: It's a triangle with  sides of differing lengths.
Not A Triangle: The given values of A, B, and C don't form a triangle. 

The TRIANGLES table is described as follows:

![Table](https://s3.amazonaws.com/hr-challenge-images/12887/1443815629-ac2a843fb7-1.png)

Each row in the table denotes the lengths of each of a triangle's three sides.

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

The OCCUPATIONS table is described as follows:

![Table](https://s3.amazonaws.com/hr-challenge-images/12889/1443816414-2a465532e7-1.png)

Occupation will only contain one of the following values: Doctor, Professor, Singer or Actor.

```sql
Select 
Concat(Name, '(', substr(Occupation,1,1), ')' )
From Occupations 
As OccupationName
Order By Name;
Select 
Concat('There are a total of ', Count(Occupation), ' ', Lower(Occupation), 's.')
From Occupations
Group By Occupation
Order by Count(Occupation), Occupation ASC;
```

# Occupations
---
Pivot the Occupation column in OCCUPATIONS so that each Name is sorted alphabetically and displayed underneath its corresponding Occupation. The output column headers should be Doctor, Professor, Singer, and Actor, respectively.

Note: Print NULL when there are no more names corresponding to an occupation.

The OCCUPATIONS table is described as follows:

![Table](https://s3.amazonaws.com/hr-challenge-images/12889/1443816414-2a465532e7-1.png)

Occupation will only contain one of the following values: Doctor, Professor, Singer or Actor.

```sql

Set @Row_Num = 0;
Set @Current_Occup = '';

Select 
Max(Case When Occupation = 'Doctor' Then Name End) As Doctor,
Max(Case When Occupation = 'Professor' Then Name End) As Professor,
Max(Case When Occupation = 'Singer' Then Name End) As Singer,
Max(Case When Occupation = 'Actor' Then Name End) As Actor
From
(
Select Name, Occupation,
@Row_Num := If(@Current_Occup = Occupation, @Row_Num + 1, 1)
As Row_Num,
@Current_Occup := Occupation
From Occupations
Order By Occupation, Name
) 
As RN
Group By Row_Num
Order By Row_Num;
```

# Binary Tree Nodes
---
You are given a table, BST, containing two columns: N and P, where N represents the value of a node in Binary Tree, and P is the parent of N.

![Table](https://s3.amazonaws.com/hr-challenge-images/12888/1443818507-5095ab9853-1.png)

Write a query to find the node type of Binary Tree ordered by the value of the node. Output one of the following for each node:

Root: If node is root node.
Leaf: If node is leaf node.
Inner: If node is neither root nor leaf node.

```sql
Select N,
Case
When P Is NULL Then 'Root'
When N In (Select P From BST) Then 'Inner'
Else 'Leaf'
End
From BST
Order By N;
```

# New Companies
---
Amber's conglomerate corporation just acquired some new companies. Each of the companies follows this hierarchy:

![Table](https://s3.amazonaws.com/hr-challenge-images/19505/1458531031-249df3ae87-ScreenShot2016-03-21at8.59.56AM.png)

Given the table schemas below, write a query to print the company_code, founder name, total number of lead managers, total number of senior managers, total number of managers, and total number of employees. Order your output by ascending company_code.

Note:

The tables may contain duplicate records.
The company_code is string, so the sorting should not be numeric. For example, if the company_codes are C_1, C_2, and C_10, then the ascending company_codes will be C_1, C_10, and C_2.

The following tables contain company data:

Company: The company_code is the code of the company and founder is the founder of the company.

![Table](https://s3.amazonaws.com/hr-challenge-images/19505/1458531125-deb0a57ae1-ScreenShot2016-03-21at8.50.04AM.png)

Lead_Manager: The lead_manager_code is the code of the lead manager, and the company_code is the code of the working company.

![Table](https://s3.amazonaws.com/hr-challenge-images/19505/1458534960-2c6d764e3c-ScreenShot2016-03-21at8.50.12AM.png)

Senior_Manager: The senior_manager_code is the code of the senior manager, the lead_manager_code is the code of its lead manager, and the company_code is the code of the working company.

![Table](https://s3.amazonaws.com/hr-challenge-images/19505/1458534973-6548194998-ScreenShot2016-03-21at8.50.21AM.png)

Manager: The manager_code is the code of the manager, the senior_manager_code is the code of its senior manager, the lead_manager_code is the code of its lead manager, and the company_code is the code of the working company.

![Table](https://s3.amazonaws.com/hr-challenge-images/19505/1458534988-7fc0af46ce-ScreenShot2016-03-21at8.50.29AM.png)

Employee: The employee_code is the code of the employee, the manager_code is the code of its manager, the senior_manager_code is the code of its senior manager, the lead_manager_code is the code of its lead manager, and the company_code is the code of the working company.

![Table](https://s3.amazonaws.com/hr-challenge-images/19505/1458535002-d47f63cbb4-ScreenShot2016-03-21at8.50.41AM.png)

```sql

```

# 
---
```sql

```
