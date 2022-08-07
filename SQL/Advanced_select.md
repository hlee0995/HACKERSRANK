|-------|-----|
| Column  | Type |
| A | INT   |
| B  | INT  |
| C  | INT |

q8, Write a query identifying the type of each record in the TRIANGLES table using its three side lengths. Output one of the following statements for each record in the table:

Equilateral: It's a triangle with  sides of equal length.
Isosceles: It's a triangle with  sides of equal length.
Scalene: It's a triangle with  sides of differing lengths.
Not A Triangle: The given values of A, B, and C don't form a triangle.

SELECT
Case 
    WHEN A + B <= C or B + C <= A or A + C <= B THEN 'Not A Triangle'
    WHEN A = B AND B = C THEN 'Equilateral'
    WHEN A = B OR B = C or A = C THEN 'Isosceles'
    ELSE 'Scalene'
End as column
from triangles;
