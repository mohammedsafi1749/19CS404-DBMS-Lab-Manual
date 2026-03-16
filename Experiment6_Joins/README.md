# Experiment 6: Joins

## AIM
To study and implement different types of joins.

## THEORY

SQL Joins are used to combine records from two or more tables based on a related column.

### 1. INNER JOIN
Returns records with matching values in both tables.

**Syntax:**
```sql
SELECT columns
FROM table1
INNER JOIN table2
ON table1.column = table2.column;
```

### 2. LEFT JOIN
Returns all records from the left table, and matched records from the right.

**Syntax:**

```sql
SELECT columns
FROM table1
LEFT JOIN table2
ON table1.column = table2.column;
```
### 3. RIGHT JOIN
Returns all records from the right table, and matched records from the left.

**Syntax:**

```sql
SELECT columns
FROM table1
RIGHT JOIN table2
ON table1.column = table2.column;
```
### 4. FULL OUTER JOIN
Returns all records when there is a match in either left or right table.

**Syntax:**

```sql
SELECT columns
FROM table1
FULL OUTER JOIN table2
ON table1.column = table2.column;
```

**Question 1**
--
<img width="826" height="611" alt="image" src="https://github.com/user-attachments/assets/b43f7f67-8825-4690-90fe-820aa7793eab" />


```
SELECT n.*
FROM nurses n
INNER JOIN departments d
ON n.department_id=d.department_id
WHERE d.department_name="Pediatrics"

```

**Output:**

<img width="826" height="424" alt="image" src="https://github.com/user-attachments/assets/c3d2abfc-4219-4ecf-a14a-67bc54e3fd49" />

**Question 2**
---
<img width="826" height="928" alt="image" src="https://github.com/user-attachments/assets/d9c6182f-891e-4a5e-883d-955ab00ca17e" />

```
SELECT
    s.name AS Salesman,
    c.cust_name,
    c.city
FROM salesman s
JOIN customer c
ON s.city=c.city
```

**Output:**

<img width="826" height="658" alt="image" src="https://github.com/user-attachments/assets/6cacddbe-aaab-4699-be49-095267b164fe" />

**Question 3**
---
<img width="826" height="985" alt="image" src="https://github.com/user-attachments/assets/5ef044f3-4d2e-48ef-8f49-87dfc5447a5e" />

```
SELECT
    c.cust_name,
    c.city,
    o.ord_no,
    o.ord_date,
    o.purch_amt AS "Order Amount",
    s.name,
    s.commission
FROM customer c
LEFT OUTER JOIN orders o ON c.customer_id=o.customer_id
LEFT OUTER JOIN salesman s ON c.salesman_id=s.salesman_id
```

**Output:**

<img width="826" height="1021" alt="image" src="https://github.com/user-attachments/assets/2a70eb9f-1598-4f45-943d-4a19a696bb0a" />

**Question 4**
---
<img width="826" height="794" alt="image" src="https://github.com/user-attachments/assets/4c369e9d-59f8-435d-9f0d-73d84470ff52" />

```
SELECT 
    p.admission_date,
    s.surgery_date
FROM patients p
INNER JOIN surgeries s
ON p.patient_id=s.patient_id
```

**Output:**

<img width="826" height="635" alt="image" src="https://github.com/user-attachments/assets/b1cabd79-30ef-4a9b-83d9-8488ef0b4c90" />


**Question 5**
---
<img width="826" height="977" alt="image" src="https://github.com/user-attachments/assets/c8134087-7f1e-47da-8742-244248dd9f2d" />


```
SELECT
    c.cust_name,
    c.city,
    o.ord_no,
    o.ord_date,
    o.purch_amt AS "Order Amount"
FROM customer c
LEFT OUTER JOIN orders o
ON c.customer_id=o.customer_id
ORDER BY o.ord_date
```

**Output:**

<img width="826" height="951" alt="image" src="https://github.com/user-attachments/assets/02b0519e-e877-43ae-907a-543b93cb76bc" />

**Question 6**
---
<img width="826" height="655" alt="image" src="https://github.com/user-attachments/assets/d3fa6e7e-76c6-43df-82a6-0eb1b3c6bdb5" />

```
SELECT p.*,d.specialization AS "doctor_specialization"
FROM patients p
INNER JOIN doctors d
ON p.doctor_id=d.doctor_id
```

**Output:**

<img width="826" height="354" alt="image" src="https://github.com/user-attachments/assets/5456054e-3582-447f-98e2-0e984610872c" />

**Question 7**
---
<img width="826" height="422" alt="image" src="https://github.com/user-attachments/assets/73457f6b-76e1-4520-bca9-29e233c9bc12" />

```
SELECT p.*
FROM patients p
INNER JOIN test_results t
ON p.patient_id=t.patient_id
WHERE test_date BETWEEN '2024-03-01' AND '2024-03-31'
```

**Output:**

<img width="826" height="285" alt="image" src="https://github.com/user-attachments/assets/5735b72f-3284-4a7b-abf7-1c95a7674fbd" />

**Question 8**
---
<img width="826" height="686" alt="image" src="https://github.com/user-attachments/assets/a9d589e0-10b3-4db1-99f4-8fdf99c8502f" />

```
SELECT
    c.cust_name AS "Customer Name",
    c.city,
    s.name AS Salesman,
    s.city,
    s.commission
FROM customer c
JOIN salesman s
ON c.salesman_id=s.salesman_id
WHERE s.city<>c.city AND s.commission>0.12
```

**Output:**

<img width="826" height="628" alt="image" src="https://github.com/user-attachments/assets/6d681851-8bfd-4aa5-9beb-9effc20edb4a" />

**Question 9**
---
<img width="826" height="469" alt="image" src="https://github.com/user-attachments/assets/2fa4c6d4-b0c3-414c-b11f-309e55dbfcff" />

```
SELECT
    c.cust_name,
    s.name
FROM customer c
LEFT JOIN salesman s
ON c.salesman_id=s.salesman_id
WHERE c.city=s.city
```

**Output:**

<img width="826" height="571" alt="image" src="https://github.com/user-attachments/assets/dfc8a464-8e5a-40a8-a24a-abe455137c33" />

**Question 10**
---
<img width="826" height="729" alt="image" src="https://github.com/user-attachments/assets/6ecf27f1-523b-40aa-b154-b1a258fab9d2" />

```
SELECT 
    c.cust_name,
    s.commission
FROM customer c
LEFT JOIN salesman s
ON c.salesman_id=s.salesman_id
```

**Output:**

[](url)<img width="826" height="875" alt="image" src="https://github.com/user-attachments/assets/1b1b8ae3-f660-4a22-863d-ef1331c311a2" />


## RESULT
Thus, the SQL queries to implement different types of joins have been executed successfully.
