
# MYSQL HACKER-RANK PROGRAM AND SOLUTION  FOR Basic Select



1)
**Revising the Select Query I**

Query all columns for all American cities in CITY with populations larger than 100,000. The CountryCode for America is USA.

Input Format

The CITY table is described as follows:

|  Field | Type |
|-------|-----|
| ID  | NUMBER |
| NAME | VARCHAR2(17)   |
| COUNTRY CODE  | VARCHAR2(3)  |
| DISTRICT |  VARCHAR2(20) |
| POPULATION | NUMBER |

**Solution**

```sql
  SELECT * FROM CITY WHERE COUNTRYCODE='USA' AND POPULATION>100000;
```


***
2)
**Revising the Select Query II**

Query the NAME field for all American cities in the CITY table with populations larger than 120000. The CountryCode for America is USA.

The CITY table is described as follows:

|  Field | Type |
|---|---|
| ID  | NUMBER |
| NAME | VARCHAR2(17)   |
| COUNTRY CODE  | VARCHAR2(3)  |
| DISTRICT |  VARCHAR2(20) |
| POPULATION | NUMBER |

**Solution**

```sql
SELECT NAME FROM CITY WHERE COUNTRYCODE='USA' AND POPULATION>120000;
```

***
3)

**Select All**

Query all columns (attributes) for every row in the CITY table.

The CITY table is described as follows:
|  Field | Type |
|---|---|
| ID  | NUMBER |
| NAME | VARCHAR2(17)   |
| COUNTRYCODE  | VARCHAR2(3)  |
| DISTRICT |  VARCHAR2(20) |
| POPULATION | NUMBER |

**Solution**

```sql
SELECT * FROM City;
```

***
4)

**Select By ID**

Query all columns for a city in CITY with the ID 1661.

The CITY table is described as follows:


|  Field | Type |
|---|---|
| ID  | NUMBER |
| NAME | VARCHAR2(17)   |
| COUNTRY CODE  | VARCHAR2(3)  |
| DISTRICT |  VARCHAR2(20) |
| POPULATION | NUMBER |

**Solution**

```sql
SELECT * FROM CITY WHERE ID=1661
```

***
5)

**Japanese Cities' Attributes**

Query all attributes of every Japanese city in the CITY table. The COUNTRYCODE for Japan is JPN.

The CITY table is described as follows:

|  Field | Type |
|---|---|
| ID  | NUMBER |
| NAME | VARCHAR2(17)   |
| COUNTRY CODE  | VARCHAR2(3)  |
| DISTRICT |  VARCHAR2(20) |
| POPULATION | NUMBER |

**Solution**
```sql
SELECT * FROM  CITY WHERE COUNTRYCODE='JPN';
```

***

6)

**Japanese Cities' Names**

Query the names of all the Japanese cities in the CITY table. The COUNTRYCODE for Japan is JPN.

The CITY table is described as follows:

|  Field | Type |
|---|---|
| ID  | NUMBER |
| NAME | VARCHAR2(17)   |
| COUNTRY CODE  | VARCHAR2(3)  |
| DISTRICT |  VARCHAR2(20) |
| POPULATION | NUMBER |

```SQL
SELECT NAME FROM CITY WHERE COUNTRYCODE='JPN'
```
***
7)

**Weather Observation Station 1**

Query a list of CITY and STATE from the STATION table.

The STATION table is described as follows:

|  Field | Type |
|---|---|
| ID  | NUMBER |
| CITY | VARCHAR2(21)   |
| STATE  | VARCHAR2(2)  |
| LAT_N |  NUMBER |
| LONG_W | NUMBER |

**Solution**

```sql
SELECT CITY,STATE FROM STATION;

```

***

8)

**Weather Observation Station 3**

Query a list of CITY names from STATION for cities that have an even ID number. Print the results in any order, but exclude duplicates from the answer.

The STATION table is described as follows:


|  Field | Type |
|---|---|
| ID  | NUMBER |
| CITY | VARCHAR2(21)   |
| STATE  | VARCHAR2(2)  |
| LAT_N |  NUMBER |
| LONG_W | NUMBER |

**Solution**

```SQL
SELECT DISTINCT  CITY FROM STATION WHERE (ID % 2)=0 ORDER BY CITY
```
***
9)

**SelectWeather Observation Station 4**

Find the difference between the total number of CITY entries in the table and the number of distinct CITY entries in the table.

The STATION table is described as follows:

|  Field | Type |
|---|---|
| ID  | NUMBER |
| CITY | VARCHAR2(21)   |
| STATE  | VARCHAR2(2)  |
| LAT_N |  NUMBER |
| LONG_W | NUMBER |

**Solution**

```sql
SELECT COUNT(CITY)-COUNT(DISTINCT CITY)FROM STATION;
```
***

10)

**Weather Observation Station 5**

Query the two cities in STATION with the shortest and longest CITY names, as well as their respective lengths (i.e.: number of characters in the name). If there is more than one smallest or largest city, choose the one that comes first when ordered alphabetically.

The STATION table is described as follows:
|  Field | Type |
|---|---|
| ID  | NUMBER |
| CITY | VARCHAR2(21)   |
| STATE  | VARCHAR2(2)  |
| LAT_N |  NUMBER |
| LONG_W | NUMBER |

**Solution**

```SQL
SELECT CITY,LENGTH(CITY)FROM STATION ORDER BY LENGTH(CITY),CITY LIMIT 1;
SELECT CITY,LENGTH(CITY)FROM STATION ORDER BY LENGTH(CITY) DESC,CITY LIMIT 1;

```
***

11)

**Weather Observation Station 6**

Query the list of CITY names starting with vowels (i.e., a, e, i, o, or u) from STATION. Your result cannot contain duplicates.

Input Format

The STATION table is described as follows:

|  Field | Type |
|---|---|
| ID  | NUMBER |
| CITY | VARCHAR2(21)   |
| STATE  | VARCHAR2(2)  |
| LAT_N |  NUMBER |
| LONG_W | NUMBER |

**Solution**

```sql
SELECT DISTINCT CITY FROM STATION WHERE CITY REGEXP '^[aeiouAEIOU]';

```
**OR**

```sql
SELECT DISTINCT CITY FROM STATION WHERE CITY LIKE 'a%' OR CITY LIKE 'e%' OR CITY LIKE 'i%' OR CITY LIKE 'o%' OR CITY LIKE 'U%';

```
**OR**

```SQL
SELECT CITY FROM STATION WHERE LEFT(CITY , 1) IN ('a','e','i','o','u')
```

***

12)

**Weather Observation Station 7**

Query the list of CITY names ending with vowels (a, e, i, o, u) from STATION. Your result cannot contain duplicates.

Input Format

The STATION table is described as follows:

|  Field | Type |
|---|---|
| ID  | NUMBER |
| CITY | VARCHAR2(21)   |
| STATE  | VARCHAR2(2)  |
| LAT_N |  NUMBER |
| LONG_W | NUMBER |

**Solution**

```SQL
SELECT DISTINCT CITY FROM STATION WHERE CITY LIKE '%a' OR  CITY LIKE '%e' OR  CITY LIKE '%i' OR  CITY LIKE '%o' OR  CITY LIKE '%u';
```

**OR**

```sql
SELECT DISTINCT CITY FROM STATION WHERE RIGHT(CITY,1) IN('a','e','i','o','u');
```
**OR**

```sql
SELECT DISTINCT CITY FROM STATION WHERE CITY REGEXP '[aeiouAEIOU]$';
```
***

13)

**Weather Observation Station 8**

Query the list of CITY names from STATION which have vowels (i.e., a, e, i, o, and u) as both their first and last characters. Your result cannot contain duplicates.

Input Format

The STATION table is described as follows:

|  Field | Type |
|---|---|
| ID  | NUMBER |
| CITY | VARCHAR2(21)   |
| STATE  | VARCHAR2(2)  |
| LAT_N |  NUMBER |
| LONG_W | NUMBER |

**Solution**

```sql
SELECT DISTINCT CITY FROM STATION WHERE (CITY LIKE 'a%' OR CITY LIKE 'e%' OR CITY LIKE 'i%' OR CITY LIKE 'o%' OR CITY LIKE 'u%')AND(CITY LIKE '%a' OR CITY LIKE '%e' OR CITY LIKE '%i' OR CITY LIKE '%o' OR CITY LIKE '%u');
```
**OR**

```SQL
SELECT DISTINCT CITY FROM STATION WHERE  LEFT(CITY,1) IN('a','e','i','o','u')AND RIGHT(CITY,1) IN('a','e','i','o','u');
```

**OR**

```SQL
SELECT DISTINCT CITY FROM STATION WHERE CITY REGEXP '^[aeiouAEIOU].*[aeiouAEIOU]$';

```

In this query, the REGEXP_LIKE function is used to match the CITY column against the specified regex pattern. The regex pattern '^[AEIOUaeiou].*[AEIOUaeiou]$' ensures that the CITY name starts with a vowel (either uppercase or lowercase) using ^[AEIOUaeiou], followed by any number of characters (.*), and ends with a vowel using [AEIOUaeiou]$. The ^ and $ symbols denote the start and end of the string, respectively.

The DISTINCT keyword is used to eliminate duplicate city names from the result.

Please note that the syntax for regular expressions and the function names may vary depending on the database system you are using. The example provided uses the REGEXP_LIKE function, which is commonly supported in databases such as Oracle and MySQL.

***

14)

**Weather Observation Station 9**

Query the list of CITY names from STATION that do not start with vowels. Your result cannot contain duplicates.

Input Format

The STATION table is described as follows:

|  Field | Type |
|---|---|
| ID  | NUMBER |
| CITY | VARCHAR2(21)   |
| STATE  | VARCHAR2(2)  |
| LAT_N |  NUMBER |
| LONG_W | NUMBER |


**Solution**

```SQL
SELECT DISTINCT CITY FROM STATION WHERE CITY NOT LIKE 'A%' AND  CITY NOT LIKE 'E%' AND  CITY NOT LIKE 'I%' AND  CITY NOT LIKE 'O%' AND CITY NOT LIKE 'U%';
```

**OR**

```SQL
SELECT DISTINCT CITY FROM STATION WHERE LEFT(CITY,1)NOT IN('a','e','i','o','u');
```

**OR**

```SQL
SELECT DISTINCT CITY FROM STATION WHERE CITY NOT REGEXP '^[aeiouAEIOU]';
```
**OR**

```SQL
SELECT DISTINCT CITY FROM STATION WHERE CITY  REGEXP '^[^aeiouAEIOU]';
```

The REGEXP keyword is used to perform a regular expression pattern match. The regular expression pattern used here is '^[^aeiouAEIOU]', which means we are looking for CITY names that do not start with any vowel (both lowercase and uppercase). The caret symbol (^) inside the square brackets means "not," and the lowercase and uppercase vowels inside the square brackets represent the vowels to exclude.

***
15)

**Weather Observation Station 10**

Query the list of CITY names from STATION that do not end with vowels. Your result cannot contain duplicates.

Input Format

The STATION table is described as follows:

|  Field | Type |
|---|---|
| ID  | NUMBER |
| CITY | VARCHAR2(21)   |
| STATE  | VARCHAR2(2)  |
| LAT_N |  NUMBER |
| LONG_W | NUMBER |

**Solution**

```SQL
SELECT DISTINCT CITY FROM STATION WHERE CITY NOT LIKE '%A' AND  CITY NOT LIKE '%E' AND  CITY NOT LIKE '%I' AND  CITY NOT LIKE '%O' AND CITY NOT LIKE '%U';
```

**OR**

```SQL
SELECT DISTINCT CITY FROM STATION WHERE RIGHT(CITY,1)NOT IN('a','e','i','o','u');
```

**OR**

```SQL
SELECT DISTINCT CITY FROM STATION WHERE CITY NOT REGEXP '[aeiouAEIOU]$';
```

**OR**

```SQL
SELECT DISTINCT CITY FROM STATION WHERE CITY  REGEXP '[^aeiouAEIOU]$';
```

The REGEXP keyword is used to perform a regular expression pattern match. The regular expression pattern used here is '[^aeiouAEIOU]$', which means we are looking for CITY names that do not start with any vowel (both lowercase and uppercase). The caret symbol (^) inside the square brackets means "not," and the lowercase and uppercase vowels inside the square brackets represent the vowels to exclude.

***
16)

**Weather Observation Station 11**

Query the list of CITY names from STATION that either do not start with vowels or do not end with vowels. Your result cannot contain duplicates.

Input Format

The STATION table is described as follows:

|  Field | Type |
|---|---|
| ID  | NUMBER |
| CITY | VARCHAR2(21)   |
| STATE  | VARCHAR2(2)  |
| LAT_N |  NUMBER |
| LONG_W | NUMBER |

**Solution**

```SQL
SELECT DISTINCT CITY FROM STATION WHERE (CITY NOT LIKE '%A' AND  CITY NOT LIKE '%E' AND  CITY NOT LIKE '%I' AND  CITY NOT LIKE '%O' AND CITY NOT LIKE '%U') OR (CITY NOT LIKE 'A%' AND  CITY NOT LIKE 'E%' AND  CITY NOT LIKE 'I%' AND  CITY NOT LIKE 'O%' AND CITY NOT LIKE 'U%') ;
```

**OR**

```SQL
SELECT DISTINCT CITY FROM STATION WHERE LEFT(CITY,1)NOT IN('a','e','i','o','u')OR RIGHT(CITY,1)NOT IN('a','e','i','o','u');
```

**OR**

```SQL
SELECT DISTINCT CITY FROM STATION WHERE CITY NOT REGEXP '^[aeiouAEIOU]' OR  CITY NOT REGEXP '[aeiouAEIOU]$';
```

**OR**

```SQL
SELECT DISTINCT CITY FROM STATION WHERE CITY  REGEXP '^[^aeiouAEIOU]' OR  CITY  REGEXP '[^aeiouAEIOU]$';
```

***

17)

**Higher Than 75 Marks**

Query the Name of any student in STUDENTS who scored higher than 75 Marks. Order your output by the last three characters of each name. If two or more students both have names ending in the same last three characters (i.e.: Bobby, Robby, etc.), secondary sort them by ascending ID.

Input Format

The STUDENTS table is described as follows:


|  Column | Type |
|---|---|
| ID  | INTEGER |
| NAME | STRING   |
| MARKS  | INTEGER  |


The Name column only contains uppercase (A-Z) and lowercase (a-z) letters.

Sample Input

|  ID | NAME | MARKS |
|---|---|----|
| 1  | ASHLEY | 81 | 
| 2 | SAMANTHA   | 75 |
| 4  | JULIA  |  76 |
| 3  | JULIA  |  84 |

Sample Output

Ashley
Julia
Belvet

Explanation

Only Ashley, Julia, and Belvet have Marks > 75. If you look at the last three characters of each of their names, there are no duplicates and 'ley' < 'lia' < 'vet'.


**Solution**

```SQL
SELECT Name FROM STUDENTS WHERE Marks>75 ORDER BY RIGHT(Name,3),ID;
```
***

18)

**Employee Names**

Write a query that prints a list of employee names (i.e.: the name attribute) from the Employee table in alphabetical order.

Input Format

The Employee table containing employee data for a company is described as follows:


|  Column | Type |
|---|---|
| employee_id  | INTEGER |
| name | STRING   |
| months | INTEGER  |
| salary | INTEGER |

where employee_id is an employee's ID number, name is their name, months is the total number of months they've been working for the company, and salary is their monthly salary.

Sample Input

|  employee_id | name | marks | salary  |
|---|---|----|-----|
| 12228 | Rose | 15 | 1968 |
| 33645 | Angela   | 1 | 3443 |
| 45692  | Frank  | 17  | 1608  |
| 56118  | Patrick  |  7 | 1345
| 59725 | Lisa | 11 | 2330 |
| 74197 | Kimberly   | 16 | 4372 |
| 78454  | Bonnie  |  8 | 1771 |
| 83565 | Michael |  6 | 2017
| 98607  | Todd  |  5 | 3396 |
| 99989 | Joe |  9 | 3573 |

Sample Output

Angela
Bonnie
Frank
Joe
Kimberly
Lisa
Michael
Patrick
Rose
Todd

```sql
SELECT NAME FROM EMPLOYEE ORDER BY NAME;  
```

***

19)

**Employee Salaries**

Write a query that prints a list of employee names (i.e.: the name attribute) for employees in Employee having a salary greater than  per month who have been employees for less than  months. Sort your result by ascending employee_id.

Input Format

The Employee table containing employee data for a company is described as follows:

|  Column | Type |
|---|---|
| employee_id  | INTEGER |
| name | STRING   |
| months | INTEGER  |
| salary | INTEGER |

where employee_id is an employee's ID number, name is their name, months is the total number of months they've been working for the company, and salary is the their monthly salary.

Sample Input

|  employee_id | name | marks | salary  |
|---|---|----|-----|
| 12228 | Rose | 15 | 1968 |
| 33645 | Angela   | 1 | 3443 |
| 45692  | Frank  | 17  | 1608  |
| 56118  | Patrick  |  7 | 1345
| 59725 | Lisa | 11 | 2330 |
| 74197 | Kimberly   | 16 | 4372 |
| 78454  | Bonnie  |  8 | 1771 |
| 83565 | Michael |  6 | 2017
| 98607  | Todd  |  5 | 3396 |
| 99989 | Joe |  9 | 3573 |

Sample Output

Angela
Michael
Todd
Joe

Explanation

Angela has been an employee for 1 month and earns $3443 per month.
Michael has been an employee for 6 months and earns $2017 per month.
Todd has been an employee for 5 months and earns $3396 per month.
Joe has been an employee for 9 months and earns $3573 per month.
We order our output by ascending employee_id.

**Solution**
```sql
SELECT NAME FROM EMPLOYEE WHERE SALARY > 2000  AND MONTHS < 10 ORDER BY EMPLOYEE_ID;  
```
***