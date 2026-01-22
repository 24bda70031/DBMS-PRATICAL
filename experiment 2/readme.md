# Experiment 2 – SQL SELECT Queries with Clauses

## Aim
To understand and implement SQL `SELECT` queries using clauses such as `WHERE`, `ORDER BY`, `GROUP BY`, and `HAVING` for efficient data retrieval and analysis.

## Objectives
- Practice writing SQL `SELECT` statements  
- Apply filtering conditions using the `WHERE` clause  
- Sort query results using `ORDER BY`  
- Group records using `GROUP BY`  
- Filter grouped data using the `HAVING` clause  
- Analyze data using aggregate functions like `COUNT()`, `SUM()`, `AVG()`, `MIN()`, and `MAX()`

## Software Requirements
- **PostgreSQL Database (pgAdmin)**

## Problem Description
An organization maintains an `EMPLOYEE` table with the following attributes:
- `emp_id` (NUMBER)
- `emp_name` (VARCHAR)
- `department` (VARCHAR)
- `salary` (NUMBER)
- `joining_date` (DATE)

The task is to:
1. Display department names and average salary of employees in each department  
2. Consider only employees with salary greater than 20,000  
3. Display only departments with average salary greater than 30,000  
4. Arrange the result in descending order of average salary

## I / O Analysis

### Database Design

#### Create Table: Students
```sql
CREATE TABLE Students (
    id NUMERIC(10,0) PRIMARY KEY,
    name VARCHAR(50),
    city VARCHAR(30),
    marks NUMERIC(10,0)
);
```

#### Insert Records
```sql
INSERT INTO Students VALUES (1, 'Aman', 'Mohali', 85);
INSERT INTO Students VALUES (2, 'Rohit', 'Mohali', 78);
INSERT INTO Students VALUES (3, 'Neha', 'Mohali', 92);
INSERT INTO Students VALUES (4, 'Simran', 'Amritsar', 88);
INSERT INTO Students VALUES (5, 'Karan', 'Amritsar', 75);
```
![Query Result](output/1.png)

## Group By and Aggregate Queries

```sql
SELECT CITY, COUNT(*) AS COUNT_STUDENTS
FROM STUDENTS
GROUP BY CITY;
```
![Query Result](output/2.png)

```sql
SELECT CITY, COUNT(ID) AS COUNT_STUDENTS
FROM STUDENTS
GROUP BY CITY;
```
![Query Result](output/3.png)

```sql
SELECT CITY, COUNT(ID) AS COUNT_STUDENTS
FROM STUDENTS
GROUP BY CITY
ORDER BY COUNT_STUDENTS ASC;
```
![Query Result](output/4.png)

```sql
SELECT CITY, COUNT(*) AS COUNT_STUDENTS
FROM STUDENTS
GROUP BY CITY
ORDER BY COUNT(*) ASC;
```
![Query Result](output/5.png)

```sql
SELECT CITY, COUNT(ID) AS COUNT_STUDENTS
FROM STUDENTS
GROUP BY CITY
HAVING COUNT(ID) >= 3;
```
![Query Result](output/6.png)

```sql
SELECT CITY, AVG(MARKS)::NUMERIC(10,2) AS AVERAGE_MARKS
FROM STUDENTS
GROUP BY CITY;
```
![Query Result](output/7.png)

```sql
SELECT CITY, SUM(MARKS)::NUMERIC(10,2) AS SUBMISSION_MARKS
FROM STUDENTS
GROUP BY CITY;
```
![Query Result](output/8.png)

```sql
SELECT CITY, MIN(MARKS)::NUMERIC(10,2) AS MINIMUM_MARKS
FROM STUDENTS
GROUP BY CITY;
```
![Query Result](output/9.png)

```sql
SELECT CITY, MAX(MARKS)::NUMERIC(10,2) AS MAXIMUM_MARKS
FROM STUDENTS
GROUP BY CITY;
```
![Query Result](output/10.png)


## SQL Clauses Used
- `WHERE`
- `GROUP BY`
- `HAVING`
- `ORDER BY`

## Learning Outcome
After completing this experiment, students will be able to:
- Filter records using the `WHERE` clause  
- Group records using `GROUP BY`  
- Apply conditions on grouped data using `HAVING`  
- Sort query results using `ORDER BY`

---
**Name:** Habis Prakash Deka
**UID:** 24BDA70031
