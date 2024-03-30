# Inbuilt Functions
- Function is a block of codes that accept zero or more arguments and returns one or more results.
- Function can be classified into *single row functions* and *group functions*.

## Single row Functions:
- Returns only one value for every row queries in table.
- Can appear in select command and can also be included in where clause.
- Eg. Numeric functions, character functions.
  
## Group Functions:
- Returns a result based on group of rows.
  
## SQL Commands:

### 1. Numeric functions

| Command      | Query                     | Output     |
|--------------|---------------------------|------------|
| Abs(n)       | Select abs(-10)           | 10         |
| Ceil(n)      | Select ceil(55.67)        | 56         |
| Floor(n)     | Select floor(100.2)       | 100        |
| Exp(n)       | Select exp(4)             | 54.59      |
| Power(m,n)   | Select power(4,2)         | 16         |
| Mod(m,n)     | Select mod(10,3)          | 1          |
| Sqrt(n)      | Select sqrt(16)           | 4          |
| Round(m,n)   | Select round(100.256,2)   | 100.26     |


### 2. Character functions

| Command                      | Query                               | Output     |
|------------------------------|-------------------------------------|------------|
| Lower(char)                  | Select lower('HELLO')               | hello      |
| Upper(char)                  | Select upper('hello')               | HELLO      |
| Ltrim(char_exp)              | Select ltrim(' beit')               | beit       |
| Rtrim(char_exp)              | Select rtrim('beit ')               | beit       |
| Replace(SE,SP,SR)            | Select replace('hello','ll','xx')   | hexxo      |
| Substring(exp,start,length)  | Select substring('hello',2,3)       | ell        |

### 3. Count functions
- **COUNT(*)** : counts all, inclusive of duplicates and null values
  - Select count(*) from employee
- **COUNT(col_name)** : avoids null value
  - Select count(salary) form employee
- **COUNT(distinct col_name)** : avoids repeated and null values
  - Select count(distinct salary) from employee
    
### 4. Group functions
- AVG()
  - Select avg(salary) from employee
- MAX()
  - Select max(salary) from employee
- MIN()
  - Select min(salary) from employee
- SUM()
  - Select sum(salary) from employee
    
### GROUP BY clause
- Allows us to use simultaneous column name and group functions.
- Use in conjuction with the aggregate functions to group the result-set by one or more columns.
- Eg.
   - Select max(salary),job from employee group by job

## HAVING clause
- Use to specify conditions on rows retrieved by using **group by** clause.
- Added to SQL because the WHERE keyword could not be used with aggregate functions.
- Eg.
  - Select max(salary),job from employee group by job having count(*)>=2
    
***
