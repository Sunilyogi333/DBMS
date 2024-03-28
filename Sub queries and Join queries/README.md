
# Sub queries and Join queries

## Sub queries
- Sub query or inner query or nested query is a query within another SQL query and embedded within WHERE clause.
- Sub query returns data that will be used in main query as a condition to further restrict data to be retrieved.
- Sub queries can be used with the SELECT, INSERT, UPDATE, and DELETE statements along with the operators like =, <, >, >=, <=, IN BETWEEN etc.
- The SQL Joins clause is used to combine records from two or more tables in a database.

## SQL Commands:
### 1. Sub query with SELECT statement
- Syntax:
    ```sql
       SELECT column_name FROM table_name
       WHERE column_name OPERATOR
       (SELECT column_name FROM table_name WHERE...)
    ```
- Example:
  ```sql
     SELECT * FROM customer
     WHERE cid IN (SELECT cid FROM customer WHERE salary > 10000)
  ```
### 2. Sub query with INSERT statement
- Syntax:
    ```sql
       INSERT INTO table_name(column_name)
       SELECT column_name FROM table_name
       [WHERE VALUE OPERATOR]
    ```
- Example:
     ```sql
       INSERT INTO cutomer1
       SELECT * FROM customer
       WHERE cid IN (SELECT cid FROM customer)
    ```
     
    ```sql
       INSERT INTO employee(name)
       SELECT name FROM employee
    ```
### 3. Sub query with UPDATE statement
- Syntax:
   ```sql
      UPDATE table
      SET column_name = new value
      [WHERE OPERATOR VALUE]
      (SELECT column_name FROM table_name WHERE...)
   ```
- Example:
  ```sql
     UPDATE customer
     SET salary = salary* 0.25
     WHERE age IN (SELECT age FROM customer1 WHERE age >=27)
  ```
### 4. Sub query with DELETE statement
- Syntax:
  ```sql
     DELETE FROM table_name
     [WHERE OPERATOR VALUE]
     (SELECT column_name FROM table_name WHERE...)
  ```
- Example:
  ```sql
     DELETE FROM customer WHERE age IN (SELECT age FROM customer1 WHERE age > 27)
  ```
  
## JOIN
- A JOIN is a means for combining fields from two tables by using values common to each.
- SQL JOIN types:
  - INNER JOIN
    - Returns rows when there is a match in both tables.
  - LEFT JOIN
    - Returns all ross from the left table, even if there are no matches in the right table.
  - RIGHT JOIN
    - Returns all rows from the right table, even if there are not matches in the left table.
  - INNER JOIN
    - Returns rows when there is a match in one of the tables.
      
## SQL Commands:
### 1. INNER JOIN
- Syntax:
  ```sql
     SELECT table1.column1, table2.column2,...
     FROM table1
     INNER JOIN table2
     ON table1.common_field = table2.common_field;
  ```
- Example:
  ```sql
     SELECT cid, name, amount, date
     FROM customer
     INNER JOIN order
     ON customer.cid = order.cid;
  ```
### 2. LEFT JOIN
- Syntax:
  ```sql
     SELECT table1.column1, table2.column2,...
     FROM table1
     LEFT JOIN table2
     ON table1.common_field = table2.common_field;
  ```
- Example:
  ```sql
     SELECT cid, name, amount, date
     FROM customer
     LEFT JOIN order
     ON customer.cid = order.cid;
  ```
### 3. RIGHT JOIN
- Syntax:
  ```sql
     SELECT table1.column1, table2.column2,...
     FROM table1
     RIGHT JOIN table2
     ON table1.common_field = table2.common_field;
  ```
- Example:
  ```sql
     SELECT cid, name, amount, date
     FROM customer
     RIGHT JOIN order
     ON customer.cid = order.cid;
  ```
### 4. FULL JOIN
- Syntax:
  ```sql
     SELECT table1.column1, table2.column2,...
     FROM table1
     FULL JOIN table2
     ON table1.common_field = table2.common_field;
  ```
- Example:
  ```sql
     SELECT cid, name, amount, date
     FROM customer
     FULL JOIN order
     ON customer.cid = order.cid;
  ```


