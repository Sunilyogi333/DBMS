# Data Query Language(DQL) Command

## DQL Command
- Is used to query database.
- Is used to retrieve information from table
- Command used is: **SELECT**

## SQL Command:
### 1. SELECT
- Is used to retrive information from a table.
- Is referred as querying a table.
- Can display either all columns in a table or only specific columns from a table
- **WHERE** clause is used with **SELECT** to filter records.
- Syntax:
  - **Retrieve all rows from table** <br>
      ```sql
      Select * FROM table_name
      ```
  - **Retrieve specific columns from table** <br>
      ```sql
      Select column1, column2,... FROM table_name
      ```
  - **Elimination of duplicates** <br>
      ```sql
      Select DISTINCT column1,... FROM table_name
      ```
  - **Use of where clause** <br>
      ```sql
      Select * FROM table_name WHERE condition
      ```

## Operators in WHERE Clause

| Operator  | Description                       |
|-----------|-----------------------------------|
| =         | Equal                             |
| <>        | Not Equal                         |
| >         | Greater Than                      |
| <         | Less Than                         |
| >=        | Greater Than or Equal             |
| <=        | Less Than or Equal                |
| BETWEEN   | Between an inclusive range        |
| LIKE      | Search for pattern                |
| IN        | To specify multiple possible values for a column |



## SQL AND & OR Operator
- **AND** operator displays a records if both the ifrst condition AND the second condition are true.
- **OR** operator displays a records if either the first condition or the second condition is true.
- **AND** & **OR** operator can also be combined.
- Syntax:
  ```sql
  SELECT * FROM table_name WHERE column1 = Value1 AND column2 = Value2
  
  SELECT * FROM table_name WHERE column1 = Value1 OR column2 = Value2
  
  SELECT * FROM table_name WHERE column1 = Value1 AND (column2 = Value2 OR column3 = Value3)
  ```
  
## SQL LIKE Operator

- Is used to search for specific pattern in a column
- Syntax:
  ```sql
  SELECT * FROM table_name WHERE columnname LIKE pattern
  ```

## SQL Wildcard characters
- Are used to substitute for any other character(s) in a string.
- Are used with the SQL **LIKE** Operator
- Wildcards are:
  
| Wildcard                   | Description                                                        |
|----------------------------|--------------------------------------------------------------------|
| %                          | Substitute for zero or more characters                             |
| _                          | Substitute for a single character                                  |
| [charlist]                 | Sets and ranges of characters to match                             |
| [^charlist] or [!charlist] | Matches only characters NOT specified within brackets              |

### For Example
```sql
Select * FROM employee WHERE city LIKE '%s'
Select * FROM employee WHERE city LIKE 'F%'
Select * FROM employee WHERE city NOT LIKE 'A%'
Select * FROM employee WHERE city LIKE '%A%'
Select * FROM employee WHERE city LIKE 'ber%'
Select * FROM employee WHERE city LIKE '_erlin%'
Select * FROM employee WHERE city LIKE 'L_N_ON'
Select * FROM employee WHERE city LIKE '[bsp]%'
Select * FROM employee WHERE city LIKE '[a-e]'
Select * FROM employee WHERE city LIKE '[!bsp]%'
Select * FROM employee WHERE city NOT LIKE '[bsp]%'
```

## SQL IN Operator
- To specify multiple values in a **WHERE** clause
- Syntax:
  ```sql
   SELECT * FROM table_name WHERE column_name IN (value1, value2,.....)
  ```
- For Example:
  ```sql
  SELECT * FROM employee WHERE city IN ('LONDON','MUNICH')
  ```

## SQL BETWEEN Operator
- To select values within range
- Syntax:
  ```sql
  SELECT * FROM table_name WHERE column_name BETWEEN value1 and value2
  ```
- For Example
  ```sql
  SELECT * FROM employee WHERE Salary BETWEEN 4000 AND 6000
  SELECT * FROM employee WHERE Salary NOT BETWEEN 4000 AND 6000
  SELECT * FROM employee WHERE name BETWEEN 'A' AND 'M'
  SELECT * FROM employee WHERE name NOT BETWEEN 'A' AND 'M'
  SELECT * FROM employee WHERE (Salary BETWEEN 4000 AND 6000) AND eid NOT IN (1,2,3)
  ```
  
- *In some databases, BETWEEN selects fields that are between and excluding the test values.*
- *In other databases, BETWEEN Selects fields that are between and including test values.*
- *And in other database, BETWEEN select fields between the test values, including the first test value and excluding the last test value.*

## SQL ORDER BY Operator
- To sort the result set by one or more columns.
- Sorts records in ascending order by default.
- Syntax:
  ```sql
  SELECT * FROM table_name ORDER BY column_name ASC

  SELECT * FROM table_name ORDER BY column_name DESC
  ```
## SQL FUNCTION
- SQL has many built in functions
  - For performing calculations on data.

 | Function | Description                                      |
 |----------|--------------------------------------------------|
 | AVG()    | Returns the average value of a numeric column    |
 | COUNT()  | Returns the number of rows                       |
 | MAX()    | Returns the largest value of a selected column   |
 | MIN()    | Returns the smallest value of a selected column  |
 | SUM()    | Returns the total sum of a numeric column        |
 | UPPER()  | Converts the value of a field to uppercase       |
 | LOWER()  | Converts the value of a field to lowercase       |
 | SQRT()   | Used to find the square root of a number         |
 | CONCAT() | Used to concatenate two strings into one         |
 | RAND()   | Used to produce random numbers between 0 and 1   |

 - **Syntax**
   ```sql
   SELECT AVG(column_name) FROM table_name

   SELECT COUNT(column_name) FROM table_name
   SELECT COUNT(*) FROM table_name

   SELECT MAX(column_name) FROM table_name

   SELECT MIN(column_name) FROM table_name

   SELECT SUM(column_name) FROM table_name

   SELECT UPPER(column_name) FROM table_name

   SELECT LOWER(column_name) FROM table_name

   SELECT SQRT(column_name) FROM table_name

   SELECT CONCAT(coL1,col2) FROM table_name

   SELECT * FROM table_name ORDER BY RAND()
   ```
   
## GROUP BY and HAVING Clause
 - used to divide the rows in table into groups
 - used with SQL aggregate functions like SUM(), AVG() etc.
 - For example:
     ```sql
     SELECT job, MAX(Salary) FROM employee GROUP BY job;

     SELECT job, MAX(Salary) FROM empoyee GROUP BY job HAVING MAX(Salary) > 6000;
     
     SELECT department, COUNT(*) AS num_employees FROM employee WHERE salary > 5000 GROUP BY department;

     SELECT job, AVG(Salary) AS avg_salary FROM employee GROUP BY job HAVING COUNT(*) > 3;

     SELECT department, SUM(Salary) AS total_salary FROM employee GROUP BY department HAVING SUM(Salary) > 100000;
     ```
     
   ***
   

