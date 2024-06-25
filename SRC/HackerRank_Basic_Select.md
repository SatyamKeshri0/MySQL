#Revising the Select Query I
---
Query all columns for all American cities in the CITY table with populations larger than 100000. The CountryCode for America is USA.
The CITY table is described as follows:

<-- ![table][https://raw.githubusercontent.com/SatyamKeshri0/Images/main/images/1.jpg?token=GHSAT0AAAAAACUB6SYKSL4EMMGF6XRDTJ3AZT2X5AA] -->

'''
Select * from City
Where CountryCode = 'USA' 
AND Population > 100000;
