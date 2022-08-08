|  Column | Type |
|-------|-----|
| A | INT   |
| B  | INT  |
| C  | INT |

q1, Write a query identifying the type of each record in the TRIANGLES table using its three side lengths. Output one of the following statements for each record in the table:

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
End as Result
from triangles;

|  Column | Type |
|-------|-----|
| NAME | String   |
| OCCUPATION  | String |


q2, Generate the following two result sets:

Query an alphabetically ordered list of all names in OCCUPATIONS, immediately followed by the first letter of each profession as a parenthetical (i.e.: enclosed in parentheses). For example: AnActorName(A), ADoctorName(D), AProfessorName(P), and ASingerName(S).
Query the number of ocurrences of each occupation in OCCUPATIONS. Sort the occurrences in ascending order, and output them in the following format:

There are a total of [occupation_count] [occupation]s.
where [occupation_count] is the number of occurrences of an occupation in OCCUPATIONS and [occupation] is the lowercase occupation name. If more than one Occupation has the same [occupation_count], they should be ordered alphabetically.

Note: There will be at least two entries in the table for each type of occupation.







You are given a table, BST, containing two columns: N and P, where N represents the value of a node in Binary Tree, and P is the parent of N.

Write a query to find the node type of Binary Tree ordered by the value of the node. Output one of the following for each node:

Root: If node is root node.
Leaf: If node is leaf node.
Inner: If node is neither root nor leaf node.


|  Column | Type |
|-------|-----|
| N | String   |
| P  | String |

SELECT CASE
WHEN P IS NULL THEN CONCAT(N, ' Root')
WHEN N IN (SELECT Distinct p FROM BST) THEN CONCAT(N,' Inner')
ELSE CONCAT (N, ' Leaf')
END
from BST
order by N asc;
