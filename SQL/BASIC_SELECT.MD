Weather Observation Station 3


|  Field | Type |
|-------|-----|
| ID  | NUMBER |
| NAME | VARCHAR2(17)   |
| COUNTRY CODE  | VARCHAR2(3)  |
| DISTRICT |  VARCHAR2(20) |
| POPULATION | NUMBER |


Q1, Query a list of CITY names from STATION for cities that have an even ID number. Print the results in any order, but exclude duplicates from the answer.


SELECT DISTINCT CITY

FROM STATION

WHERE mod(id,2) = 0;

Q2, Find the difference between the total number of CITY entries in the table and the number of distinct CITY entries in the table.


SELECT COUNT(CITY) - COUNT(DISTINCT CITY)
FROM STATION;

Q3, Query the two cities in STATION with the shortest and longest CITY names, as well as their respective lengths (i.e.: number of characters in the name). If there is more than one smallest or largest city, choose the one that comes first when ordered alphabetically.


select city c, length(city) l
from   station
order by l desc, c asc
limit 1;

select city c, length(city) l
from   station
order by l asc, c asc
limit 1;

Q4, Query the list of CITY names starting with vowels (i.e., a, e, i, o, or u) from STATION. Your result cannot contain duplicates.

SELECT DISTINCT CITY FROM STATION WHERE CITY LIKE 'A%' OR CITY LIKE 'E%' OR CITY LIKE 'I%' OR CITY LIKE 'O%' OR CITY LIKE 'U%';

OR 

SELECT CITY
FROM STATION
WHERE CITY Like '[AEIOU]%';

|  Field | Type |
|-------|-----|
| Column  | Type |
| ID | INT   |
| NAME  |STR  |
| MARKS | INT |



