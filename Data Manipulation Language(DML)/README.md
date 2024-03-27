# Data Manipulation Language(DML) Commands

## 1. DML Command
- Is used to query and manipulate database.
- Is used to
  - Insert record in a table
  - Retrieve information from table
  - Delete record from a table
- Command used are: **INSERT** **, UPDATE** **, DELETE** **, SELECT**

## SQL Commands:
### 1. INSERT
- Is used to add one or more rows in a table.
- The values are separated by commas and data types *char* and *date* is enclosed in apostrophes.
- The values must be entered in same order as they are defined.
- Syntax:
    ```sql
      INSERT into table_name VALUES(value1, value2,...)

      INSERT into table_name (column1, column2,...)
      VALUES(value1, value2,...)
    ```
- Example:
  ```sql
     INSERT into student VALUES(1,'ram','ktm',65.2)
  
     INSERT into student (roll, name, address, weight)
     VALUES(2,'sita','patan',55.5)

     INSERT into student(name, weight) VALUES('hari',75)

     INSERT into student VALUES(null,'gita','pokhara',null)

     INSERT into student
     VALUES(5,'rita,'dharan',56.5),(6,'hari','patan',59.8)
  ```
### 2. UPDATE
 - Is used to alter column values in a table.
 - Syntax:
   ```sql
      UPDATE table_name SET column1= value1,... WHERE condition
   ```
- Example:
  ```sql
     UPDATE employee SET e_address= 'pharping' where e_id= 1
  ```

### 3. DELETE
 - Is used to delete a table
 - Syntax:
   ```sql
      DELETE FROM table_name
   
      DELETE FROM table_name WHERE column1 = value1
   ```
- Example:
  ```sql
      DELETE FROM employee

      DELETE FROM employee where e_id = 1
  ```
  
### 4. SELECT
- Is used to retrieve information from a table.
- Is referred as querying a table.
- Can display either all columns in a table or only specific columns from a table.
- Syntax:
  - **Retrieve all rows from table**
    ```sql
       SELECT * FROM table_name
    ```
  - **Retrieve specific columns from table**
    ```sql
       SELECT column1, column2... FROM table_name
    ```
  - **Elimination of duplicates**
    ```sql
       SELECT DISTINCT column1, column2... FROM table_name
    ```
  - **Use of where clause**
    ```sql
       SELECT * FROM table_name WHERE condition
    ```
- Example:
  - **Retrieve all rows from table**
    ```sql
       SELECT * FROM employee
    ```
  - **Retrieve specific columns from table**
    ```sql
       SELECT e_name, e_address FROM employee
    ```
  - **Elimination of duplicates**
    ```sql
       SELECT DISTINCT e_address FROM employee
    ```
  - **Use of where clause**
    ```sql
       SELECT * FROM employee WHERE e_address = "kathmandu"
    ```
    ***
