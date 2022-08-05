Weather Observation Station 3


|  Field | Type |
|-------|-----|
| ID  | NUMBER |
| NAME | VARCHAR2(17)   |
| COUNTRY CODE  | VARCHAR2(3)  |
| DISTRICT |  VARCHAR2(20) |
| POPULATION | NUMBER |


Q1, Query a list of CITY names from STATION for cities that have an even ID number. Print the results in any order, but exclude duplicates from the answer.
The STATION table is described as follows:

SELECT DISTINCT CITY

FROM STATION

WHERE mod(id,2) = 0;

Q2, Find the difference between the total number of CITY entries in the table and the number of distinct CITY entries in the table.
The STATION table is described as follows:

SELECT COUNT(CITY) - COUNT(DISTINCT CITY)
FROM STATION;



