# Revising the Select Query I
---
Query all columns for all American cities in the CITY table with populations larger than 100000. The CountryCode for America is USA. The CITY table is described as follows:

![Table](https://github.com/SatyamKeshri0/Images/blob/main/images/1.jpg?raw=true)

```sql
SELECT * FROM City WHERE CountryCode = 'USA' AND Population > 100000;
'''

# Revising the Select Query II
---
Query the NAME field for all American cities in the CITY table with populations larger than 120000. The CountryCode for America is USA.

'''sql
Select Name from City Where Population > 120000 AND CountryCode='USA'
