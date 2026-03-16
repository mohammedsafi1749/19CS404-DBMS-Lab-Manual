# Experiment 4: Aggregate Functions, Group By and Having Clause

## AIM
To study and implement aggregate functions, GROUP BY, and HAVING clause with suitable examples.

## THEORY

### Aggregate Functions
These perform calculations on a set of values and return a single value.

- **MIN()** – Smallest value  
- **MAX()** – Largest value  
- **COUNT()** – Number of rows  
# Experiment 4: Aggregate Functions, Group By and Having Clause

## AIM
To study and implement aggregate functions, GROUP BY, and HAVING clause with suitable examples.

## THEORY

### Aggregate Functions
These perform calculations on a set of values and return a single value.

- **MIN()** – Smallest value  
- **MAX()** – Largest value  
- **COUNT()** – Number of rows  
- **SUM()** – Total of values  
- **AVG()** – Average of values

**Syntax:**
```sql
SELECT AGG_FUNC(column_name) FROM table_name WHERE condition;
```
### GROUP BY
Groups records with the same values in specified columns.
**Syntax:**
```sql
SELECT column_name, AGG_FUNC(column_name)
FROM table_name
GROUP BY column_name;
```
### HAVING
Filters the grouped records based on aggregate conditions.
**Syntax:**
```sql
SELECT column_name, AGG_FUNC(column_name)
FROM table_name
GROUP BY column_name
HAVING condition;
```

**Question 1**
--
<img width="826" height="609" alt="image" src="https://github.com/user-attachments/assets/7718f70a-6163-4bce-b289-e49af2c26953" />


```
SELECT COUNT(*) AS COUNT
FROM customer
```

**Output:**

<img width="826" height="306" alt="image" src="https://github.com/user-attachments/assets/2417b626-cad6-45db-a37e-20080c6de47f" />


**Question 2**
---
<img width="826" height="568" alt="image" src="https://github.com/user-attachments/assets/b50849a7-8074-422d-b248-6fd00685d089" />


```
SELECT
    name,
    email,
    MIN(LENGTH(email)) AS min_email_length
FROM customer
```

**Output:**

<img width="826" height="298" alt="image" src="https://github.com/user-attachments/assets/dacae34c-f39d-425c-a697-a06cd393f8fc" />


**Question 3**
---
<img width="826" height="565" alt="image" src="https://github.com/user-attachments/assets/bad35cfe-0fd4-4a6e-99bd-57040fad46ee" />


```
SELECT COUNT(*) AS employees_count FROM employee
```

**Output:**

<img width="826" height="301" alt="image" src="https://github.com/user-attachments/assets/d2422b8f-dee5-4547-b480-50f43d2391e2" />


**Question 4**
---
<img width="826" height="740" alt="image" src="https://github.com/user-attachments/assets/ab1a7d73-7f36-47b3-ad97-9a4d0e0df97e" />


```
SELECT 
    strftime('%H',AppointmentDateTime) AS HourOfDay,
    COUNT(*) AS TotalAppointments
FROM Appointments
GROUP BY HourOfDay
ORDER BY HourOfDay
```

**Output:**

<img width="826" height="574" alt="image" src="https://github.com/user-attachments/assets/abf03ce2-1c09-4986-8f0f-6cfbd935329e" />


**Question 5**
---
<img width="1238" height="667" alt="image" src="https://github.com/user-attachments/assets/3a6f580b-9c86-489e-bb51-bbd21993f3eb" />


```
SELECT
    PatientID,
    COUNT(RecordID) AS TotalRecords
FROM MedicalRecords
GROUP BY PatientID
```

**Output:**

<img width="826" height="729" alt="image" src="https://github.com/user-attachments/assets/16543f43-43af-46a4-a4e3-bf9c350ada12" />


**Question 6**
---
<img width="826" height="649" alt="image" src="https://github.com/user-attachments/assets/989ea049-b1ec-4bb2-a569-8066d4a40b35" />


```
SELECT
    DoctorID,
    COUNT(AppointmentID) AS TotalAppointments
FROM Appointments
GROUP BY DoctorID
```

**Output:**

<img width="826" height="705" alt="image" src="https://github.com/user-attachments/assets/602fd688-e405-4b6b-b9fe-e97c357fa5b4" />


**Question 7**
---
<img width="826" height="565" alt="image" src="https://github.com/user-attachments/assets/d41acef6-7da4-44a3-8f5e-cfd6014d8d82" />


```
SELECT 
    jdate,
    AVG(workhour)
FROM employee1
GROUP BY jdate
HAVING AVG(workhour)<10
```

**Output:**

<img width="826" height="331" alt="image" src="https://github.com/user-attachments/assets/b2000ccc-b8a9-4f8c-b31f-941e3ca4f7bc" />

**Question 8**
---
<img width="826" height="624" alt="image" src="https://github.com/user-attachments/assets/ed6cb4b4-72fa-4816-a382-a59a303af571" />


```
SELECT 
    jdate,
    MIN(workhour)
FROM employee1
GROUP BY jdate
HAVING MIN(workhour)<10
```

**Output:**

<img width="826" height="453" alt="image" src="https://github.com/user-attachments/assets/cd441967-5140-4b76-a888-c81c125287d8" />

**Question 9**
---
<img width="826" height="581" alt="image" src="https://github.com/user-attachments/assets/15842de9-6df0-4378-aac4-1ee1bf92b911" />


```
SELECT
    (age/5)*5 AS age_group,
    SUM(salary)
FROM customer1
GROUP BY age_group
HAVING SUM(salary)>5000
```

**Output:**

<img width="826" height="355" alt="image" src="https://github.com/user-attachments/assets/1055627d-a9a4-4a78-9cc5-6c572a56188d" />

**Question 10**
---
<img width="826" height="578" alt="image" src="https://github.com/user-attachments/assets/f2b9198b-8c8c-42c0-9bfe-6ace39fba830" />


```
SELECT
    category_id,
    SUM(price) AS Total_Cost
FROM products
GROUP BY category_id
HAVING SUM(price)>50
```

**Output:**

<img width="826" height="327" alt="image" src="https://github.com/user-attachments/assets/40ca683e-7034-4963-9ea7-cf271e32c775" />


## RESULT
Thus, the SQL queries to implement aggregate functions, GROUP BY, and HAVING clause have been executed successfully.
