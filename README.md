# Northwind-SQL-Queries
# 📊 Northwind SQL Queries

This project contains SQL queries written and executed on the *Northwind database* using *SQL Server Management Studio (SSMS)*.  
The goal is to practice *joins, aggregate functions, grouping, and filtering* with real dataset examples.

---

## 🚀 Queries Implemented

### 1. Orders with Customer Names
Show order details with customer company names.

```sql
SELECT o.OrderID, c.CompanyName, o.OrderDate
FROM Orders o
INNER JOIN Customers c ON o.CustomerID = c
### 1. **Average Order Amount per customer**
SELECT 
    o.CustomerID,
    AVG(od.UnitPrice * od.Quantity) AS AvgOrderAmount
FROM Orders o
JOIN [Order Details] od ON o.OrderID = od.OrderID
GROUP BY o.CustomerID;
Customer with more than 10 order
SELECT CustomerID
FROM Orders
GROUP BY CustomerID
HAVING COUNT(OrderID) > 10;
