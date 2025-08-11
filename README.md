# SQL Joins Task – Customers & Orders

## Objective

Learn and demonstrate how to use SQL JOINs (INNER, LEFT, RIGHT, FULL) to combine data from two related tables: **Customers** and **Orders**.

---

## Table Structure

### Customers

| Column       | Type          |
|--------------|---------------|
| CustomerID   | INT (PK)      |
| CustomerName | VARCHAR(100)  |
| City         | VARCHAR(50)   |

### Orders

| Column     | Type            |
|------------|-----------------|
| OrderID    | INT (PK)        |
| OrderDate  | DATE            |
| CustomerID | INT (FK)        |
| Amount     | DECIMAL(10, 2)  |

---

## Sample Data

### Customers

| CustomerID | CustomerName | City        |
|------------|--------------|-------------|
| 1          | Prasad        | Vijayawada    |
| 2          | Ravi          | Hyderabad |


### Orders

| OrderID | OrderDate   | CustomerID | Amount |
|---------|-------------|------------|--------|
| 101     | 2025-08-01  | 1          | 25000.00 |
| 102     | 2025-08-02  | 2          | 2500.00 |


---

## 🔄 SQL JOIN Examples

### 🔸 INNER JOIN

Returns only matching rows from both tables.

```sql
select Customers.CustomerName, Orders.OrderID, Orders.Amount FROM Customers INNER JOIN Orders ON Customers.CustomerID = Orders.CustomerID;
select Customers.CustomerName, Orders.OrderID, Orders.Amount FROM Customers LEFT JOIN Orders ON Customers.CustomerID = Orders.CustomerID;
select Customers.CustomerName, Orders.OrderID, Orders.Amount FROM Customers RIGHT JOIN Orders ON Customers.CustomerID = Orders.CustomerID;
select Customers.CustomerName, Orders.OrderID, Orders.Amount FROM Customers LEFT JOIN Orders ON Customers.CustomerID = Orders.CustomerID UNION SELECT Customers.CustomerName, Orders.OrderID, Orders.Amount FROM Customers RIGHT JOIN Orders ON Customers.CustomerID = Orders.CustomerID;
