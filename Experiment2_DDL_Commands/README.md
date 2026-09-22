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
--
<img width="1118" height="441" alt="image" src="https://github.com/user-attachments/assets/fa8e4198-0339-4926-aae1-5a891079eca0" />


```sql
INSERT INTO Products (Name, Category, Price, Stock)
VALUES
('Smartphone', 'Electronics', 800, 150),
('Headphones', 'Accessories', 200, 300);
```

**Output:**

<img width="1259" height="457" alt="image" src="https://github.com/user-attachments/assets/f326bd13-7446-4972-886c-310238267c4f" />


**Question 2**
---
<img width="976" height="436" alt="image" src="https://github.com/user-attachments/assets/6925f6ad-3001-4725-8b59-b0f2a99f4cd6" />


```sql
INSERT INTO Customers (CustomerID,Name,Address,City,ZipCode) VALUES
(302,"Laura Croft","456 Elm St","Seattle",98101),
(303,"Bruce Wayne","789 Oak St","Gotham",10001);
```

**Output:**

<img width="1212" height="510" alt="image" src="https://github.com/user-attachments/assets/3a0138d4-707b-45a8-9701-10833b643e9b" />


**Question 3**
---
<img width="1200" height="463" alt="image" src="https://github.com/user-attachments/assets/68fa0ada-c267-41d9-9b1c-49792b9c507c" />


```sql
CREATE TABLE Bonuses (
    BonusID INTEGER PRIMARY KEY,
    EmployeeID INTEGER,
    BonusAmount REAL CHECK(BonusAmount > 0),
    BonusDate DATE,
    Reason TEXT NOT NULL,
    FOREIGN KEY(EmployeeID) REFERENCES Employees(EmployeeID)
);
```

**Output:**

<img width="1215" height="414" alt="image" src="https://github.com/user-attachments/assets/a2ddec35-e865-45ff-a59f-066b70de788e" />

**Question 4**
---
<img width="1214" height="453" alt="image" src="https://github.com/user-attachments/assets/0e7ca2d6-f19e-4f39-b67a-ff90cb9eb25a" />


```sql
CREATE TABLE Products (
    ProductID INTEGER PRIMARY KEY,
    ProductName TEXT UNIQUE NOT NULL,
    Price REAL CHECK(Price > 0),
    StockQuantity INTEGER CHECK(StockQuantity >= 0)
);
```

**Output:**

<img width="1198" height="406" alt="image" src="https://github.com/user-attachments/assets/223f5f22-29b4-43c5-8bcd-4fa5eb92fd9e" />

**Question 5**
---

<img width="925" height="403" alt="image" src="https://github.com/user-attachments/assets/d64956a3-79b8-46dc-9883-5ff2d51d117a" />

```sql
CREATE TABLE Products (
    ProductID INTEGER PRIMARY KEY,
    ProductName TEXT NOT NULL,
    Price REAL CHECK(Price > 0),
    Stock INTEGER CHECK(Stock >= 0)
);
```

**Output:**

<img width="1180" height="402" alt="image" src="https://github.com/user-attachments/assets/d957def1-ede5-48f2-a30e-2f33634d6200" />


**Question 6**
---
<img width="1220" height="419" alt="image" src="https://github.com/user-attachments/assets/08531b56-0acc-4ea0-b7fe-4b9a37ed8fa3" />

```sql
CREATE TABLE Invoices 
(
    InvoiceID INTEGER PRIMARY KEY,
    InvoiceDate DATE,
    DueDate Date CHECK (DueDate > InvoiceDate),
    Amount REAL CHECK(Amount > 0)
);
```

**Output:**

<img width="1254" height="405" alt="image" src="https://github.com/user-attachments/assets/e81fcba0-104d-4883-880d-ec6f32d84aa0" />

**Question 7**
---
<img width="1178" height="465" alt="image" src="https://github.com/user-attachments/assets/a061160e-60af-4aea-a8f4-2ea792364430" />

```sql
CREATE TABLE Locations 
(
    LocationID INTEGER,
    LocationName TEXT,
    Address TEXT
);
```

**Output:**

<img width="1203" height="510" alt="image" src="https://github.com/user-attachments/assets/20e56195-c191-4859-bed6-e2c7d1ba90fa" />

**Question 8**
---
<img width="1146" height="399" alt="image" src="https://github.com/user-attachments/assets/9923a28c-b4bc-41f4-b4fe-2341b7b6fea6" />


```sql
INSERT INTO Books (ISBN, Title, Author, Publisher, YearPublished)
SELECT ISBN, Title, Author, Publisher, YearPublished
FROM Out_of_print_books;
```

**Output:**

<img width="1170" height="420" alt="image" src="https://github.com/user-attachments/assets/93934a17-e612-423d-bf56-d88d9dbe25f1" />

**Question 9**
---
<img width="1190" height="440" alt="image" src="https://github.com/user-attachments/assets/e7407cef-717d-4483-8ae8-4f7d7d60e68f" />


```sql
ALTER TABLE Student_details
ADD COLUMN email TEXT NOT NULL DEFAULT 'Invalid';
```

**Output:**
<img width="1218" height="368" alt="image" src="https://github.com/user-attachments/assets/fff54f47-f576-4ab4-a62b-54c1161e85ad" />


**Question 10**
---
<img width="1192" height="547" alt="image" src="https://github.com/user-attachments/assets/e4edebe6-d2d6-4dfb-a68f-fc862edca2c3" />


```sql
ALTER TABLE Companies
RENAME COLUMN name TO first_name;

ALTER TABLE Companies
ADD COLUMN mobilenumber number;

ALTER TABLE Companies
ADD COLUMN DOB Date;
```

**Output:**

<img width="1181" height="516" alt="image" src="https://github.com/user-attachments/assets/221a49f8-1044-4651-af58-186afc7966e4" />


## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.
