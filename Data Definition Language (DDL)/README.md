# Data Definition Language(DQL) Commands

## 1. DDL Command
- Is used to communicate with database.
- Is used to
  - Create an object
  - Alter the structure of object
  - To drop the object created
- Command used are: **SELECT** **, ALTER** **, DROP** **, TRUNCATE**

## 2. Constraint
- Constraint are the rules or definition that governs the operations in the data. Constraints can be done at the column level or at the table level depending upon the requirement.
- Three types of constraints
  - Integrity Constraint
    - NOT NULL Constraint
    - NULL Constraint
    - UNIQUE Constraint
  - Entity Constraint (Primary Key)
  - Referential Constraint (Foreign key)
  -  CREATE TABLE table_name(
      Column_name1 data_type,
      Column_name2 data_type,

## SQL Commands:
### 1. CREATE TABLE
- Is used to create a table.
- Syntax:
    ```sql
      CREATE TABLE table_name
      (
      Column_name1 data_type,
      Column_name2 data_type,
      .......................
      .......................
      )
    ```
- Example:
  ```sql
     CREATE TABLE student
     (
      St_roll int,
      St_name varchar(50),
      St_address varchar(50)
     )
  ```
### 2. ALTER TABLE
- Is used to add, delete, or modify columns in a table.
- Syntax:
  - **To add a column in a table**
    ```sql
       ALTER TABLE table_name
       ADD column_name data_type
    ```
  - **To delete a column in a table**
    ```sql
       ALTER TABLE table_name
       DROP COLUMN column_name 
    ```
  - **To change data type of column in a table**
    ```sql
       ALTER TABLE table_name
       ALTER COLUMN column_name data_type
    ```
- Example:
  - **To add a column in a table**
    ```sql
       ALTER TABLE student
       ADD email varchar(50)
    ```
  - **To delete a column in a table**
    ```sql
       ALTER TABLE student
       DROP COLUMN email
    ```
  - **To change data type of column in a table**
    ```sql
       ALTER TABLE student
       ALTER COLUMN name char(10)
    ```

### 3. DROP TABLE
 - Is used to delete a table
 - Syntax:
   ```sql
      DROP TABLE table_name
   ```
- Example:
  ```sql
  DROP TABLE student
  ```
### 4. TRUNCATE TABLE 
- Is used to delete records of table retaining the table structure.
- Syntax:
  ```sql
     TRUNCATE TABLE table_name
  ```
- Example:
  ```sql
     TRUNCATE TABLE student
  ```
## Constriants
### NOT NULL
- Enforce a field to always have value
- Example:
  ```sql
  CREATE TABLE teacher
  (
  T_id int NOT NULL,
  T_name varchar(50) NOT NULL,
  T_address varchar(50),
  T_email varchar(25)
  )
  ```
### UNIQUE
- Ensures that information in column for each record is unique.
- Example 1:
  ```sql
  CREATE TABLE teacher
  (
  T_id int NOT NULL UNIQUE,
  T_name varchar(50) NOT NULL,
  T_address varchar(50),
  T_email varchar(25)
  )
  ```
- Example 2:
  ```sql
  CREATE TABLE teacher
  (
  T_id int NOT NULL,
  T_name varchar(50) NOT NULL,
  T_address varchar(50),
  T_email varchar(25)
  CONSTRAINT u_nid UNIQUE (T_id, T_name)
  )
  ```
- Example 3:
  ```sql
  ALTER TABLE teacher
  ADD UNIQUE (T_id)
  )
  ```
- Example 4:
  ```sql
  ALTER TABLE teacher
  ADD CONSTRAINT u_nid UNIQUE (T_id, T_name)
  ```
- Example 5:
  ```sql
  ALTER TABLE teacher
  DROP CONSTRAINT u_nid
  ```
### PRIMARY KEY
- Uniquely identifies each record in a table.
- Cannot contain NULL values.
- Example 1:
  ```sql
  CREATE TABLE teacher
  (
  T_id int PRIMARY KEY,
  T_name varchar(50) NOT NULL,
  T_address varchar(50),
  T_email varchar(25)
  )
  ```
- Example 2:
  ```sql
  CREATE TABLE teacher
  (
  T_id int,
  T_name varchar(50) NOT NULL,
  T_address varchar(50),
  T_email varchar(25)
  CONSTRAINT pk_nid PRIMARY KEY (T_id, T_name)
  )
  ```
- Example 3:
  ```sql
  ALTER TABLE teacher
  ADD PRIMARY KEY (T_id)
  )
  ```
- Example 4:
  ```sql
  ALTER TABLE teacher
  ADD CONSTRAINT pk_nid PRIMARY KEY (T_id, T_name)
  ```
- Example 5:
  ```sql
  ALTER TABLE teacher
  DROP CONSTRAINT pk_nid
  ```
### FOREIGN KEY  
- Points to Primary Key of another table
- Example 1:
  ```sql
  CREATE TABLE teacher
  (
  T_id int PRIMARY KEY,
  T_name varchar(50) NOT NULL,
  T_address varchar(50),
  T_email varchar(25)
  D_id int FOREIGN KEY REFERENCES department(D_id)
  )
  ```
- Example 2:
  ```sql
  CREATE TABLE teacher
  (
  T_id int PRIMARY KEY,
  D_id int,
  T_name varchar(50) NOT NULL,
  T_address varchar(50),
  T_email varchar(25)
  CONSTRAINT fk_td FOREIGN KEY(D_id) REFERENCES department(D_id)
  )
  ```
- Example 3:
  ```sql
  ALTER TABLE teacher
  ADD FOREIGN KEY (D_id) REFERENCES department(D_id)
  )
  ```
- Example 4:
  ```sql
  ALTER TABLE teacher
  ADD CONSTRAINT fk_td FOREIGN KEY(D_id) REFERENCES department(D_id)
  ```
- Example 5:
  ```sql
  ALTER TABLE teacher
  DROP CONSTRAINT fk_td
  ```
### CHECK
- Allows only a particular range of values.
- Example 1:
  ```sql
  CREATE TABLE teacher
  (
  T_id int NOT NULL CHECK (T_id>0),
  T_name varchar(50) NOT NULL,
  T_address varchar(50),
  T_email varchar(25)
  )
  ```
- Example 2:
  ```sql
  CREATE TABLE teacher
  (
  T_id int NOT NULL,
  T_name varchar(50) NOT NULL,
  T_address varchar(50),
  T_email varchar(25)
  CONSTRAINT chk_teacher CHECK (T_id>0 AND T_address = 'kathmandu')
  )
  ```
- Example 3:
  ```sql
  ALTER TABLE teacher
  ADD CHECK (T_id>0)
  )
  ```
- Example 4:
  ```sql
  ALTER TABLE teacher
  ADD CONSTRAINT chk_teacher CHECK (T_id>0 AND T_address = 'kathmandu')
  ```
- Example 5:
  ```sql
  ALTER TABLE teacher
  DROP CONSTRAINT chk_teacher
  ```
  ***
