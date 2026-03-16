# Experiment 3: DML Commands

## AIM
To study and implement DML (Data Manipulation Language) commands.

## THEORY

### 1. INSERT INTO
Used to add records into a relation.
These are three type of INSERT INTO queries which are as
A)Inserting a single record
**Syntax (Single Row):**
```sql
INSERT INTO table_name (field_1, field_2, ...) VALUES (value_1, value_2, ...);
```
**Syntax (Multiple Rows):**
```sql
INSERT INTO table_name (field_1, field_2, ...) VALUES
(value_1, value_2, ...),
(value_3, value_4, ...);
```
**Syntax (Insert from another table):**
```sql
INSERT INTO table_name SELECT * FROM other_table WHERE condition;
```
### 2. UPDATE
Used to modify records in a relation.
Syntax:
```sql
UPDATE table_name SET column1 = value1, column2 = value2 WHERE condition;
```
### 3. DELETE
Used to delete records from a relation.
**Syntax (All rows):**
```sql
DELETE FROM table_name;
```
**Syntax (Specific condition):**
```sql
DELETE FROM table_name WHERE condition;
```
### 4. SELECT
Used to retrieve records from a table.
**Syntax:**
```sql
SELECT column1, column2 FROM table_name WHERE condition;
```
**Question 1**

<img width="600" height="583" alt="image" src="https://github.com/user-attachments/assets/f484bdba-c3d9-4bdc-82e9-5c568a08dde4" />


```
SELECT
    id,
    value1,
    ABS(value1) AS 'absolute_value'
FROM Calculations
```

**Output:**

<img width="1235" height="326" alt="image" src="https://github.com/user-attachments/assets/1aff34ed-dd47-418e-b582-807020141963" />


**Question 2**

<img width="600" height="583" alt="image" src="https://github.com/user-attachments/assets/21110155-a7f9-4eef-a5a3-bd821a65092a" />


```
UPDATE Employees
SET SALARY=SALARY*2
WHERE DEPARTMENT_ID=20 AND JOB_ID LIKE "%MAN"
```

**Output:**

<img width="1234" height="491" alt="image" src="https://github.com/user-attachments/assets/d7da9afe-d409-494e-b905-11a6149a5143" />


**Question 3**

<img width="600" height="583" alt="image" src="https://github.com/user-attachments/assets/b48aaae1-b864-462c-9809-cdfc5ac4078f" />


```
UPDATE Employees
SET EMAIL='not available',COMMISSION_PCT=0.55
WHERE DEPARTMENT_ID=110
```

**Output:**

<img width="1238" height="441" alt="image" src="https://github.com/user-attachments/assets/f8847417-24b5-4076-85b0-fafd75d67443" />


**Question 4**

<img width="600" height="583" alt="image" src="https://github.com/user-attachments/assets/373b9361-533d-4152-873f-bd7273da1fdf" />


```
UPDATE products
SET product_name='Grapefruit'
WHERE product_id=4
```

**Output:**

<img width="1242" height="327" alt="image" src="https://github.com/user-attachments/assets/bcf8d031-4cf1-4ff1-bc5b-03fbe5a5d9e0" />


**Question 5**

<img width="600" height="583" alt="image" src="https://github.com/user-attachments/assets/4b475ce3-b374-4700-a046-2bcabcf1fb75" />


```
SELECT
    id,
    value2,
    CASE
        WHEN value2<10 THEN 'Small'
        WHEN value2>=10 AND value2<=50 THEN 'Medium'
        WHEN value2>50 THEN 'Large'
    END AS size_category
FROM Calculations
```

**Output:**

<img width="1227" height="1013" alt="image" src="https://github.com/user-attachments/assets/0e790c4c-2600-474a-8e5f-7734d9c38800" />


**Question 6**

<img width="600" height="568" alt="image" src="https://github.com/user-attachments/assets/7a61b62c-00f8-4ffb-a820-cce7b9b20a38" />


```
SELECT 
    ename,
    hiredate,
    CASE strftime("%w",hiredate)
        WHEN '0' THEN 'Sunday'
        WHEN '1' THEN 'Monday'
        WHEN '2' THEN 'Tuesday'
        WHEN '3' THEN 'Wednesday'
        WHEN '4' THEN 'Thursday'
        WHEN '5' THEN 'Friday'
        WHEN '6' THEN 'Saturday'
    END AS day_of_week
FROM emp
```

**Output:**

<img width="1232" height="987" alt="image" src="https://github.com/user-attachments/assets/a1a297b4-394f-43c3-874b-c2cf5ac49849" />


**Question 7**

<img width="600" height="700" alt="image" src="https://github.com/user-attachments/assets/f0732bee-b8a7-4dc3-8e1a-316a48006466" />


```
SELECT * FROM customer
WHERE cust_name LIKE '%n'
```

**Output:**

<img width="1230" height="467" alt="image" src="https://github.com/user-attachments/assets/90bf6f7c-eceb-46db-8e61-ebf82c91c72b" />


**Question 8**

<img width="600" height="339" alt="image" src="https://github.com/user-attachments/assets/b30cc783-1e5b-45a1-9af2-51f2bf2944db" />


```
DELETE FROM Doctors
WHERE doctor_id=1
```

**Output:**

<img width="1240" height="495" alt="image" src="https://github.com/user-attachments/assets/3dca1d82-1629-4e30-85a1-3f4c33ca9af4" />


**Question 9**

<img width="600" height="694" alt="image" src="https://github.com/user-attachments/assets/f23b8a0c-0ceb-462d-9667-c8fc0a8bea63" />


```
SELECT
    product_id,
    original_price,
    discount_percentage,
    original_price*(1-discount_percentage) AS discounted_price
FROM Products
```

**Output:**

<img width="1236" height="481" alt="image" src="https://github.com/user-attachments/assets/5110a59c-1453-4339-bea0-ea3f6e4a5567" />


**Question 10**

<img width="600" height="311" alt="image" src="https://github.com/user-attachments/assets/74bfcb65-9051-4031-95a8-b4460438aee0" />


```
SELECT * FROM salesman
WHERE commission BETWEEN 0.12 AND 0.14
```


**Output:**

<img width="1232" height="446" alt="image" src="https://github.com/user-attachments/assets/466f80be-87ef-4e4e-afa5-fb1aa99be391" />


## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.
