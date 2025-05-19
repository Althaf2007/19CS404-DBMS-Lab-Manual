# Experiment 2: DDL Commands

## AIM
To study and implement DDL commands and different types of constraints.

## THEORY

### 1. CREATE
Used to create a new relation (table).

**Syntax:**
```sql
CREATE TABLE (
  field_1 data_type(size),
  field_2 data_type(size),
  ...
);
```
### 2. ALTER
Used to add, modify, drop, or rename fields in an existing relation.
(a) ADD
```sql
ALTER TABLE std ADD (Address CHAR(10));
```
(b) MODIFY
```sql
ALTER TABLE relation_name MODIFY (field_1 new_data_type(size));
```
(c) DROP
```sql
ALTER TABLE relation_name DROP COLUMN field_name;
```
(d) RENAME
```sql
ALTER TABLE relation_name RENAME COLUMN old_field_name TO new_field_name;
```
### 3. DROP TABLE
Used to permanently delete the structure and data of a table.
```sql
DROP TABLE relation_name;
```
### 4. RENAME
Used to rename an existing database object.
```sql
RENAME TABLE old_relation_name TO new_relation_name;
```
### CONSTRAINTS
Constraints are used to specify rules for the data in a table. If there is any violation between the constraint and the data action, the action is aborted by the constraint. It can be specified when the table is created (using CREATE TABLE) or after it is created (using ALTER TABLE).
### 1. NOT NULL
When a column is defined as NOT NULL, it becomes mandatory to enter a value in that column.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) NOT NULL
);
```
### 2. UNIQUE
Ensures that values in a column are unique.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) UNIQUE
);
```
### 3. CHECK
Specifies a condition that each row must satisfy.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) CHECK (logical_expression)
);
```
### 4. PRIMARY KEY
Used to uniquely identify each record in a table.
Properties:
Must contain unique values.
Cannot be null.
Should contain minimal fields.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) PRIMARY KEY
);
```
### 5. FOREIGN KEY
Used to reference the primary key of another table.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size),
  FOREIGN KEY (column_name) REFERENCES other_table(column)
);
```
### 6. DEFAULT
Used to insert a default value into a column if no value is specified.

Syntax:
```sql
CREATE TABLE Table_Name (
  col_name1 data_type,
  col_name2 data_type,
  col_name3 data_type DEFAULT 'default_value'
);
```

**Question 1**
![1](https://github.com/user-attachments/assets/89903b03-48ca-45a7-a337-9b8131d2c86a)

```sql
insert into Products(Name,Category,price,Stock)
values("Smartphone","Electronics",800,150),
("Headphones","Accessories",200,300);
```

**Output:**
![1 o](https://github.com/user-attachments/assets/77001c2e-4910-49ed-837a-bc6b7db51715)

**Question 2**
![2](https://github.com/user-attachments/assets/6bba4576-2100-4737-846b-3eedc5adee12)

```sql
 create table item(
item_id varchar(50) primary key,item_desc varchar(50) not null,
rate int not null,icom_id char(4),foreign key(icom_id)
references company(com_id) on update set null on delete set null);
```
**Output:**
![2 0](https://github.com/user-attachments/assets/0301bca1-f05f-44d3-8bcc-0da4d06e008a)

**Question 3**
![3](https://github.com/user-attachments/assets/55cc29d4-faf0-40da-b00e-251bd85836b6)

```sql
create table Department(
DepartmentID int primary key,
DepartmentName varchar(50) UNIQUE NOT NULL,
Location varchar(100));
```

**Output:**
![3 o](https://github.com/user-attachments/assets/33d99b12-ed9e-4e8d-a86c-62c3514a31e9)

**Question 4**
![4](https://github.com/user-attachments/assets/2f440e97-c8de-4da4-a654-2a4e7ff2012f)

```sql
create table jobs(
job_id int,
job_title varchar(50) default "",
min_salary int default 8000,max_salary int);create table jobs(
job_id int,
job_title varchar(50) default "",
min_salary int default 8000,max_salary int);
```

**Output:**
![4 o](https://github.com/user-attachments/assets/bb3d038b-73f6-42cc-887e-689699abd9ca)

**Question 5**
![5](https://github.com/user-attachments/assets/3f8d01c9-375f-452e-a819-18e089a40670)

```sql
alter table Employees add column Date_of_joi Date;
alter table employees rename column job_title to Designation;
```

**Output:**
![5 o](https://github.com/user-attachments/assets/5003fa2b-e185-408d-8587-f144688bc0a2)

**Question 6**

![6](https://github.com/user-attachments/assets/37da834d-5076-41bf-9639-bda333dd2440)

```sql
insert into Products(ProductID,ProductName,Price,Stock)
select ProductID,ProductName,Price,Stock from Discontinued_products;
```

**Output:**
![6 o](https://github.com/user-attachments/assets/19e7738a-3b07-4585-9538-c93f05021982)

**Question 7**
![7](https://github.com/user-attachments/assets/1b6923b4-c211-41df-8688-538b00b8850e)

```sql
alter table Companies add column designation varchar(50);
alter table Companies add column net_salary number;
```

**Output:**
![7 o](https://github.com/user-attachments/assets/48cc1e52-b2fe-4bee-ba7b-7168b16674a5)

**Question 8**
![8](https://github.com/user-attachments/assets/c9615ae7-96f9-4438-baa7-c74b28d170e5)

```sql
create table item(item_id varchar(50) primary key,item_desc varchar(50) not null,
rate int not null,icom_id char(4),
foreign key(icom_id) references company(com_id) on update cascade on delete cascade);
```

**Output:**

![8 o](https://github.com/user-attachments/assets/77c45098-4442-4ecc-9a9e-ea4691a765bb)

**Question 9**

![9](https://github.com/user-attachments/assets/577e4532-9084-485a-bea2-53f0289b0fa1)

```sql
insert into Student_details(RollNo,Name,Gender) values(204,"Samuel Black","M");
```

**Output:**

![9 o](https://github.com/user-attachments/assets/9ba15757-3d03-493e-ad6c-ae569ebfba6f)

**Question 10**

![10](https://github.com/user-attachments/assets/f141c0cc-073b-4ddc-b4ae-3a9af7047a10)

```sql
create table Customers(CustomerID INTEGER,Name TEXT,Email TEXT,JoinDate DATETIME);
```

**Output:**

![10 o](https://github.com/user-attachments/assets/b99a95a7-5678-4814-8939-dd6c15639382)

## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.
