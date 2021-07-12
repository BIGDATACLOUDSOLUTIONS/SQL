Table: `Logs`

```
+-------------+---------+
| Column Name | Type    |
+-------------+---------+
| id          | int     |
| num         | varchar |
+-------------+---------+
id is the primary key for this table.
```

Write an SQL query to find all numbers that appear at least three times consecutively.

Return the result table in any order.

The query result format is in the following example:

```
Logs table:
+----+-----+
| Id | Num |
+----+-----+
| 1  | 1   |
| 2  | 1   |
| 3  | 1   |
| 4  | 2   |
| 5  | 1   |
| 6  | 2   |
| 7  | 2   |
+----+-----+

Result table:
+-----------------+
| ConsecutiveNums |
+-----------------+
| 1               |
+-----------------+
1 is the only number that appears consecutively for at least three times.

```

<!--
## Solution
```text
Create table If Not Exists Person (Id int, Email varchar(255))
Truncate table Person
insert into Person (Id, Email) values ('1', 'a@b.com')
insert into Person (Id, Email) values ('2', 'c@d.com')
insert into Person (Id, Email) values ('3', 'a@b.com')
insert into Employee (Id, Name, Salary, ManagerId) values ('4', 'Max', '90000', 'None')
insert into Logs (Id, Num) values ('5', '1')
insert into Logs (Id, Num) values ('6', '2')
insert into Logs (Id, Num) values ('7', '2')


SELECT distinct num as ConsecutiveNums
from
(SELECT NUM,(CASE WHEN NUM = LEAD(NUM,1) OVER (ORDER BY ID) 
           AND NUM = LEAD(NUM,2) OVER (ORDER BY ID) THEN 'Y'
        ELSE 'N'
        END) AS Consecutiveind
FROM LOGS)
WHERE Consecutiveind = 'Y'
```
-->

