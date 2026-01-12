# SalesDB Database Overview

This document provides a concise understanding of the `SalesDB` database, including its schema, tables, and key relationships.

---

## Database: SalesDB

### Schema: Sales

`SalesDB` contains sales-related data, including customers, employees, products, and orders. The schema `Sales` is the main organizational structure.

### Tables Overview

#### 1. Customers

| Column     | Type        | Nullable | Description                              |
| ---------- | ----------- | -------- | ---------------------------------------- |
| CustomerID | int         | NO       | Unique ID for each customer              |
| FirstName  | varchar(50) | YES      | Customer's first name                    |
| LastName   | varchar(50) | YES      | Customer's last name                     |
| Country    | varchar(50) | YES      | Customer's country                       |
| Score      | int         | YES      | Customer score, e.g., loyalty or ranking |

**Notes:**

* Primary key: `CustomerID`
* Can join with `Orders` using `CustomerID`
---

#### 2. Employees

| Column     | Type        | Nullable | Description                      |
| ---------- | ----------- | -------- | -------------------------------- |
| EmployeeID | int         | NO       | Unique employee identifier       |
| FirstName  | varchar(50) | YES      | Employee first name              |
| LastName   | varchar(50) | YES      | Employee last name               |
| Department | varchar(50) | YES      | Department name                  |
| BirthDate  | date        | YES      | Date of birth                    |
| Gender     | char(1)     | YES      | M/F                              |
| Salary     | int         | YES      | Employee salary                  |
| ManagerID  | int         | YES      | References EmployeeID of manager |

**Notes:**

* Self-referencing relationship: `ManagerID` links to `EmployeeID`.
* Can join with `Orders` using `EmployeeID` as `SalesPersonID`

---

#### 3. Products

| Column    | Type        | Nullable | Description               |
| --------- | ----------- | -------- | ------------------------- |
| ProductID | int         | NO       | Unique product identifier |
| Product   | varchar(50) | YES      | Product name              |
| Category  | varchar(50) | YES      | Product category          |
| Price     | int         | YES      | Price of product          |

**Notes:**

* Join with `Orders` using `ProductID`
* Useful for sales aggregation by category or product

---

#### 4. Orders

| Column        | Type         | Nullable | Description                            |
| ------------- | ------------ | -------- | -------------------------------------- |
| OrderID       | int          | NO       | Unique order identifier                |
| ProductID     | int          | YES      | Product sold                           |
| CustomerID    | int          | YES      | Customer who bought the product        |
| SalesPersonID | int          | YES      | Employee who handled the order         |
| OrderDate     | date         | YES      | Date order was placed                  |
| ShipDate      | date         | YES      | Date order shipped                     |
| OrderStatus   | varchar(50)  | YES      | Status of order (Pending/Shipped/etc.) |
| ShipAddress   | varchar(255) | YES      | Shipping address                       |
| BillAddress   | varchar(255) | YES      | Billing address                        |
| Quantity      | int          | YES      | Quantity ordered                       |
| Sales         | int          | YES      | Total sales amount (Quantity x Price)  |
| CreationTime  | datetime2    | YES      | Timestamp of order creation            |

**Notes:**

* Join with `Customers`, `Employees`, and `Products`.
* Useful for revenue, delivery, and performance analysis.

---

#### 5. OrdersArchive

| Column        | Type         | Nullable | Description                     |
| ------------- | ------------ | -------- | ------------------------------- |
| OrderID       | int          | YES      | Archived order ID               |
| ProductID     | int          | YES      | Product sold                    |
| CustomerID    | int          | YES      | Customer who bought the product |
| SalesPersonID | int          | YES      | Employee who handled the order  |
| OrderDate     | date         | YES      | Original order date             |
| ShipDate      | date         | YES      | Original shipping date          |
| OrderStatus   | varchar(50)  | YES      | Original order status           |
| ShipAddress   | varchar(255) | YES      | Original shipping address       |
| BillAddress   | varchar(255) | YES      | Original billing address        |
| Quantity      | int          | YES      | Quantity ordered                |
| Sales         | int          | YES      | Total sales amount              |
| CreationTime  | datetime2    | YES      | Original creation timestamp     |

**Notes:**

* Contains historical data.
* Useful for year-over-year or archival reporting.

---

## Key Relationships

* `Orders.CustomerID` → `Customers.CustomerID`
* `Orders.ProductID` → `Products.ProductID`
* `Orders.SalesPersonID` → `Employees.EmployeeID`
* `Employees.ManagerID` → `Employees.EmployeeID` (self-join)
* `OrdersArchive` mirrors `Orders` for historical analysis

---

## Usage Overview

* Analyze sales per product, category, employee, or customer.
* Track historical orders via `OrdersArchive`.
* Build reports using joins, aggregations, window functions, and CTEs.
* Detect trends, customer behavior, and performance metrics.

---

# SQL Practice Roadmap

This repository contains a **structured SQL practice roadmap** from **Difficulty 3 to Difficulty 7**, designed for interview preparation and real-world analytics skills.

---

## Difficulty 3 — Basics & Filters (1–50)

### Focus

* Basic `SELECT`
* `WHERE`, `ORDER BY`
* Simple aggregations
* NULL handling

### Questions

1. List all customers from the `Customers` table.
2. Show only `FirstName` and `Country` of all customers.
3. Find customers where `Country = 'USA'`.
4. Get customers with `Score > 80`.
5. List employees working in the `Sales` department.
6. Display employee names and salaries only.
7. Find employees with salary greater than 50000.
8. List all products with price less than 100.
9. Show all orders with `OrderStatus = 'Shipped'`.
10. Get orders placed after `2024-01-01`.
11. Display all customers ordered by `Score` ascending.
12. List products ordered by price descending.
13. Find employees whose `Gender = 'M'`.
14. Show distinct countries from `Customers`.
15. Count total number of customers.
16. Count how many employees exist.
17. Find the highest salary among employees.
18. Find the lowest product price.
19. Calculate the average employee salary.
20. Show total sales value from `Orders`.
21. List orders with quantity greater than 5.
22. Show customers whose score is NULL.
23. Show employees with no manager assigned.
24. List orders where `ShipDate` is NULL.
25. Show top 5 highest-paid employees.
26. Get first 10 orders sorted by `OrderDate`.
27. Show products in category `Electronics`.
28. Find customers not from `Germany`.
29. List employees born after 1990.
30. Display orders with sales greater than 1000.
31. Show all archived orders.
32. Count number of archived orders.
33. List orders created today.
34. Show customers with score between 50 and 80.
35. List employees whose salary is between 40k and 60k.
36. Find products with price IN (50, 100, 150).
37. Show orders with status IN ('Pending', 'Processing').
38. Display employees sorted by last name.
39. Find customers whose first name starts with 'A'.
40. Find products ending with the word 'Pro'.
41. Show orders shipped after order date.
42. List all columns from `Employees`.
43. Find customers with score not equal to 100.
44. Display orders where sales = quantity × price.
45. Show employees with salary divisible by 5.
46. Find customers with missing last names.
47. List products with price greater than average price.
48. Show employees earning exactly 60000.
49. Count orders per status.
50. Show today’s date using SQL.

### Answers
```sql
-- 1. List all customers from the Customers table.
SELECT * FROM Sales.Customers;

-- 2. Show only FirstName and Country of all customers.
SELECT FirstName, Country FROM Sales.Customers;

-- 3. Find customers where Country = 'USA'.
SELECT * FROM Sales.Customers WHERE Country = 'USA';

-- 4. Get customers with Score > 80.
SELECT * FROM Sales.Customers WHERE Score > 80;

-- 5. List employees working in the Sales department.
SELECT * FROM Sales.Employees WHERE Department = 'Sales';

-- 6. Display employee names and salaries only.
SELECT CONCAT(FirstName, ' ', LastName) AS EmpName, Salary FROM Sales.Employees;

-- 7. Find employees with salary greater than 50000.
SELECT * FROM Sales.Employees WHERE Salary > 50000;

-- 8. List all products with price less than 100.
SELECT * FROM Sales.Products WHERE Price < 100;

-- 9. Show all orders with OrderStatus = 'Shipped'.
SELECT * FROM Sales.Orders WHERE OrderStatus = 'Shipped';

-- 10. Get orders placed after 2024-01-01.
SELECT * FROM Sales.Orders WHERE OrderDate > '2024-01-01';

-- 11. Display all customers ordered by Score ascending.
SELECT CustomerID, CONCAT(FirstName, ' ', LastName) AS CustomerName, Country, Score
FROM Sales.Customers
ORDER BY Score ASC;

-- 12. List products ordered by price descending.
SELECT ProductID, Product, Category, Price FROM Sales.Products ORDER BY Price DESC;

-- 13. Find employees whose Gender = 'M'.
SELECT EmployeeID, CONCAT(FirstName, ' ', LastName) AS EmployeeName FROM Sales.Employees WHERE Gender = 'M';

-- 14. Show distinct countries from Customers.
SELECT DISTINCT Country FROM Sales.Customers;

-- 15. Count total number of customers.
SELECT COUNT(DISTINCT CustomerID) AS TotalCustomers FROM Sales.Customers;

-- 16. Count how many employees exist.
SELECT COUNT(DISTINCT EmployeeID) AS TotalEmployees FROM Sales.Employees;

-- 17. Find the highest salary among employees.
SELECT MAX(Salary) AS HighestSalary FROM Sales.Employees;

-- 18. Find the lowest product price.
SELECT MIN(Price) AS LowestProductPrice FROM Sales.Products;

-- 19. Calculate the average employee salary.
SELECT AVG(Salary) AS AverageSalary FROM Sales.Employees;

-- 20. Show total sales value from Orders.
SELECT SUM(Sales) AS TotalSales FROM Sales.Orders;

-- 21. List orders with quantity greater than 5.
SELECT * FROM Sales.Orders WHERE Quantity > 5;

-- 22. Show customers whose score is NULL.
SELECT * FROM Sales.Customers WHERE Score IS NULL;

-- 23. Show employees with no manager assigned.
SELECT EmployeeID, CONCAT(FirstName, ' ', LastName) AS EmployeeName FROM Sales.Employees WHERE ManagerID IS NULL;

-- 24. List orders where ShipDate is NULL.
SELECT * FROM Sales.Orders WHERE ShipDate IS NULL;

-- 25. Show top 5 highest-paid employees.
SELECT TOP 5 EmployeeID, CONCAT(FirstName, ' ', LastName) AS EmployeeName FROM Sales.Employees ORDER BY Salary DESC;

-- 26. Get first 10 orders sorted by OrderDate.
SELECT TOP 10 * FROM Sales.Orders ORDER BY OrderDate ASC;

-- 27. Show products in category Electronics.
SELECT * FROM Sales.Products WHERE Category = 'Electronics';

-- 28. Find customers not from Germany.
SELECT * FROM Sales.Customers WHERE Country != 'DE';

-- 29. List employees born after 1990.
SELECT * FROM Sales.Employees WHERE YEAR(BirthDate) > 1990;

-- 30. Display orders with sales greater than 1000.
SELECT * FROM Sales.Orders WHERE Sales > 1000;

-- 31. Show all archived orders.
SELECT OrderID, CustomerID, OrderDate, OrderStatus FROM Sales.Orders WHERE LOWER(OrderStatus) = 'archived';

-- 32. Count number of archived orders.
SELECT COUNT(OrderID) AS TotalArchivedOrders FROM Sales.Orders WHERE LOWER(OrderStatus) = 'archived';

-- 33. List orders created today.
SELECT OrderID, CustomerID, OrderDate, OrderStatus FROM Sales.Orders
WHERE CreationTime >= CAST(GETDATE() AS DATE) AND CreationTime < DATEADD(DAY, 1, CAST(GETDATE() AS DATE));

-- 34. Show customers with score between 50 and 80.
SELECT CustomerID, CONCAT(FirstName, ' ', LastName) AS CustomerName, Score FROM Sales.Customers WHERE Score BETWEEN 50 AND 80;

-- 35. List employees whose salary is between 40k and 60k.
SELECT EmployeeID, CONCAT(FirstName, ' ', LastName) AS EmployeeName, Department, Salary FROM Sales.Employees WHERE Salary BETWEEN 40000 AND 60000;

-- 36. Find products with price IN (50, 100, 150).
SELECT ProductID, Product, Category, Price FROM Sales.Products WHERE Price IN (50, 100, 150);

-- 37. Show orders with status IN ('Pending', 'Processing').
SELECT OrderID, ProductID, OrderDate, ShipDate, OrderStatus, ShipAddress, BillAddress, Quantity, Sales FROM Sales.Orders WHERE OrderStatus IN ('Pending', 'Processing');

-- 38. Display employees sorted by last name.
SELECT EmployeeID, CONCAT(FirstName, ' ', LastName) AS EmployeeName, Department, Salary, ManagerID FROM Sales.Employees ORDER BY LastName ASC;

-- 39. Find customers whose first name starts with 'A'.
SELECT CustomerID, CONCAT(FirstName, ' ', LastName) AS CustomerName, Score FROM Sales.Customers WHERE FirstName LIKE 'A%';

-- 40. Find products ending with the word 'Pro'.
SELECT ProductID, Product, Category, Price FROM Sales.Products WHERE Product LIKE '%Pro';

-- 41. Show orders shipped after order date.
SELECT OrderID, ProductID, OrderDate, ShipDate, OrderStatus FROM Sales.Orders WHERE OrderDate < ShipDate;

-- 42. List all columns from Employees.
SELECT COLUMN_NAME FROM INFORMATION_SCHEMA.COLUMNS WHERE TABLE_SCHEMA = 'Sales' AND TABLE_NAME = 'Employees';

-- 43. Find customers with score not equal to 100.
SELECT CustomerID, CONCAT(FirstName, ' ', LastName) AS CustomerName, Score FROM Sales.Customers WHERE Score != 100;

-- 44. Display orders where sales = quantity × price.
SELECT O.OrderID, O.ProductID, O.Quantity, O.Sales, P.Price FROM Sales.Orders AS O
LEFT JOIN Sales.Products AS P ON O.ProductID = P.ProductID
WHERE O.Sales = O.Quantity * P.Price;

-- 45. Show employees with salary divisible by 5.
SELECT EmployeeID, FirstName, LastName, Salary FROM Sales.Employees WHERE Salary % 5 = 0;

-- 46. Find customers with missing last names.
SELECT CustomerID, FirstName, LastName FROM Sales.Customers WHERE LastName IS NULL OR LastName = '';

-- 47. List products with price greater than average price.
SELECT ProductID, Product, Category, Price FROM Sales.Products WHERE Price > (SELECT AVG(Price) FROM Sales.Products);

-- 48. Show employees earning exactly 60000.
SELECT * FROM Sales.Employees WHERE Salary = 60000;

-- 49. Count orders per status.
SELECT OrderStatus, COUNT(OrderStatus) AS OrdersCount FROM Sales.Orders GROUP BY OrderStatus;

-- 50. Show today's date using SQL.
SELECT CAST(GETDATE() AS DATE) AS TodaysDate;
```

---

## Difficulty 4 — Grouping & Simple Joins (51–100)

### Focus

* `GROUP BY`, `HAVING`
* INNER / LEFT JOIN
* Aggregations across tables

### Questions

51. Count customers per country.
52. Calculate average score per country.
53. Count employees per department.
54. Find max salary per department.
55. Show departments having more than 5 employees.
56. Count orders per order status.
57. Calculate total sales per customer.
58. Calculate total quantity sold per product.
59. Find total sales per salesperson.
60. Join `Orders` with `Customers` to show customer names per order.
61. Join `Orders` with `Products` to show product names.
62. Display order date, product name, and quantity.
63. Find customers who have placed at least one order.
64. Find customers who never placed an order.
65. Show employees who handled orders.
66. Count orders per day.
67. Find sales per month.
68. Join employees with their managers.
69. Show employee name and manager name.
70. Find average sales per order.
71. Show customers with more than 3 orders.
72. List top 5 customers by total sales.
73. Show top-selling product.
74. Find employee with highest total sales.
75. Count archived orders per year.
76. Compare current vs archived order counts.
77. Show orders with delayed shipping.
78. Calculate average delivery time.
79. Find products never ordered.
80. Find customers who ordered multiple categories.
81. Show total sales per country.
82. Find salesperson with no orders.
83. List employees older than average employee age.
84. Show customers with highest score per country.
85. Rank products by price.
86. Show duplicate customer first names.
87. Count orders per customer per year.
88. Show employees whose salary is above department average.
89. Find last order date per customer.
90. Find first order per customer.
91. Calculate running total of sales.
92. Show orders with sales above monthly average.
93. Find customers inactive for last 6 months.
94. Compare employee salary vs manager salary.
95. Show product revenue contribution percentage.
96. Identify peak sales day.
97. Show orders placed on weekends.
98. Detect orders shipped before order date.
99. Calculate cumulative sales per customer.
100. Identify repeat customers.

```sql
-- 51. Count customers per country.
SELECT
	Country,
	COUNT(CustomerID) AS TotalCustomers
FROM Sales.Customers
GROUP BY Country
ORDER BY TotalCustomers DESC;

-- 52. Calculate average score per country.
SELECT
	Country,
	AVG(Score) AS AverageScore
FROM Sales.Customers
GROUP BY Country
ORDER BY AverageScore DESC;

-- 53. Count employees per department.
SELECT
	Department,
	COUNT(EmployeeID) AS TotalEmployees
FROM Sales.Employees
GROUP BY Department
ORDER BY TotalEmployees DESC;

-- 54. Find max salary per department.
SELECT
	Department,
	MAX(Salary) AS Highest_Salary
FROM Sales.Employees
GROUP BY Department;

-- 55. Show departments having more than 5 employees.
SELECT
	Department,
	COUNT(EmployeeID) AS TotalUsers
FROM Sales.Employees
GROUP BY Department
HAVING COUNT(EmployeeID) > 5;

-- 56. Count orders per order status.
SELECT
	OrderStatus,
	COUNT(OrderID) AS TotalOrders
FROM Sales.Orders
GROUP BY OrderStatus;

-- 57. Calculate total sales per customer.
SELECT
	CustomerID,
	SUM(Sales) AS TotalSales
FROM Sales.Orders
GROUP BY CustomerID;

-- 58. Calculate total quantity sold per product.
SELECT
	ProductID,
	SUM(Quantity) AS TotalQuantity
FROM Sales.Orders
GROUP BY ProductID;

-- 59. Find total sales per salesperson.
SELECT
	SalesPersonID,
	SUM(Sales) AS TotalSales
FROM Sales.Orders
GROUP BY SalesPersonID;

-- 60. Join Orders with Customers to show customer names per order.
SELECT
	O.OrderID,
	O.CustomerID,
	CONCAT(FirstName, ' ', LastName) AS Name
FROM Sales.Orders AS O
JOIN Sales.Customers AS C
	ON O.CustomerID = C.CustomerID;

-- 61. Join Orders with Products to show product names.
SELECT
	O.OrderID,
	P.ProductID,
	P.Product,
	P.Category,
	P.Price
FROM Sales.Orders AS O
JOIN Sales.Products AS P
	ON O.ProductID = P.ProductID;

-- 62. Display order date, product name, and quantity.
SELECT
	O.OrderDate,
	P.Product,
	O.Quantity
FROM Sales.Orders AS O
JOIN Sales.Products AS P
	ON O.ProductID = P.ProductID;

-- 63. Find customers who have placed at least one order.
SELECT
	C.CustomerID,
	CONCAT(C.FirstName, ' ', C.LastName) AS Name,
	COUNT(O.OrderID) AS TotalOrders
FROM Sales.Orders AS O
INNER JOIN Sales.Customers AS C
	ON O.CustomerID = C.CustomerID
GROUP BY 
	C.CustomerID, 
	C.FirstName, 
	C.LastName
HAVING COUNT(O.OrderID) >= 1;

-- 64. Find customers who never placed an order.
SELECT
    C.CustomerID,
    C.FirstName,
    C.LastName,
    C.Country,
    C.Score
FROM Sales.Customers AS C
LEFT JOIN Sales.Orders AS O
    ON C.CustomerID = O.CustomerID
WHERE O.CustomerID IS NULL;

-- 65. Show employees who handled orders.
SELECT
	DISTINCT E.EmployeeID,
	E.FirstName,
	E.LastName
FROM Sales.Orders AS O
INNER JOIN Sales.Employees AS E
	ON O.SalesPersonID = E.EmployeeID;

-- 66. Count orders per day.
SELECT
	OrderDate,
	COUNT(OrderID) AS TotalOrders
FROM Sales.Orders
GROUP BY OrderDate;

-- 67. Find sales per month.
SELECT
	YEAR(OrderDate)AS Year,
	MONTH(OrderDate) AS Month,
	SUM(Sales) AS TotalOrdersPerMonth
FROM Sales.Orders
GROUP BY 
	YEAR(OrderDate),
	MONTH(OrderDate)
ORDER BY 
	Year,
	Month;

-- 68. Join employees with their managers.
SELECT
    E1.EmployeeID        AS EmployeeID,
    E1.FirstName         AS EmployeeFirstName,
    E1.LastName          AS EmployeeLastName,
    E2.EmployeeID        AS ManagerID,
    E2.FirstName         AS ManagerFirstName,
    E2.LastName          AS ManagerLastName
FROM Sales.Employees AS E1
LEFT JOIN Sales.Employees AS E2
    ON E1.ManagerID = E2.EmployeeID;

-- 69. Show employee name and manager name.
SELECT
    E1.EmployeeID,
    CONCAT(E1.FirstName, ' ', E1.LastName) AS EmployeeName,
    COALESCE(E2.FirstName + ' ' + E2.LastName, 'No Manager') AS ManagerName
FROM Sales.Employees E1
LEFT JOIN Sales.Employees E2
    ON E1.ManagerID = E2.EmployeeID;

-- 70. Find average sales per order.
SELECT
	ROUND(AVG(Sales), 2) AS AvgSales
FROM Sales.Orders;

-- 71. Show customers with more than 3 orders.
SELECT
	CustomerID,
	COUNT(OrderID) AS TotalOrders
FROM Sales.Orders
GROUP BY 
	CustomerID
HAVING COUNT(OrderID) > 3;

-- 72. List top 5 customers by total sales.
SELECT TOP 5
	CustomerID,
	SUM(Sales) AS TotalSales
FROM Sales.Orders
GROUP BY 
	CustomerID
ORDER BY TotalSales DESC;

-- 73. Show top-selling product.
SELECT TOP 1
	ProductID,
	COUNT(OrderID) AS TotalOrders
FROM Sales.Orders
GROUP BY ProductID
ORDER BY TotalOrders DESC;

-- 74. Find employee with highest total sales.
SELECT TOP 1
	SalesPersonID,
	SUM(Sales) AS TotalSales
FROM Sales.Orders
GROUP BY SalesPersonID
ORDER BY TotalSales DESC;

-- 75. Count archived orders per year.
SELECT
    YEAR(OrderDate) AS OrderYear,
    COUNT(*) AS ArchivedOrders
FROM Sales.OrdersArchive
GROUP BY YEAR(OrderDate)
ORDER BY OrderYear;

-- 76. Compare delivered vs shipped order counts.
SELECT
	OrderStatus,
	COUNT(*) AS OrderStatusCount
FROM Sales.Orders
WHERE LOWER(OrderStatus) IN ('delivered', 'shipped')
	AND OrderStatus IS NOT NULL
GROUP BY OrderStatus;

SELECT
	SUM(CASE WHEN OrderStatus = 'Delivered' 
		THEN 1 ELSE 0 END) AS DeliveredOrders,
	SUM(CASE WHEN OrderStatus = 'Shipped'
		THEN 1 ELSE 0 END) AS ShippedOrders
FROM Sales.Orders;

-- 77. Show orders with delayed shipping.
SELECT
    'Delayed' AS OrderStatus,
    COUNT(*) AS DelayedOrderCount
FROM Sales.Orders
WHERE OrderStatus = 'Delayed';

-- 78. Calculate average delivery time.
SELECT
	AVG(DATEDIFF(DAY, OrderDate, ShipDate)) AS AvgDeliveryDays
FROM Sales.Orders
WHERE OrderStatus = 'Delivered'
	AND OrderDate IS NOT NULL
	AND ShipDate IS NOT NULL;

-- 79. Find products never ordered.
-- Using 'LEFT JOIN + NULL filtering' 
SELECT 
	P.ProductID,
	P.Product,
	P.Category,
	P.Price
FROM Sales.Products AS P
LEFT JOIN Sales.Orders AS O
	ON P.ProductID = O.ProductID
WHERE O.ProductID IS NULL;

-- Using 'NOT EXISTS'
SELECT
	P.ProductID,
	P.Product,
	P.Category,
	P.Price
FROM Sales.Products P
WHERE NOT EXISTS(
	SELECT 1
	FROM Sales.Orders O
	WHERE O.ProductID = P.ProductID
);

-- Using 'NOT IN'
SELECT
	*
FROM Sales.Products
WHERE ProductID NOT IN
(
	SELECT
		ProductID
	FROM Sales.Orders
	WHERE ProductID IS NOT NULL
);

-- 80. Find customers who ordered products from multiple categories
SELECT
    O.CustomerID,
    CONCAT(C.FirstName, ' ', C.LastName) AS CustomerName,
    COUNT(DISTINCT P.Category) AS CategoryCount
FROM Sales.Orders AS O
JOIN Sales.Products AS P
    ON O.ProductID = P.ProductID
JOIN Sales.Customers AS C
    ON O.CustomerID = C.CustomerID
GROUP BY O.CustomerID, C.FirstName, C.LastName
HAVING COUNT(DISTINCT P.Category) > 1;

-- 81. Show total sales per country.
SELECT
	C.Country,
	SUM(O.Sales) AS TotalSalesByCountry
FROM Sales.Orders AS O
LEFT JOIN Sales.Customers AS C
	ON O.CustomerID = C.CustomerID
	AND C.Country IS NOT NULL
GROUP BY C.Country
ORDER BY TotalSalesByCountry DESC;

-- 82. Find salesperson with no orders.
WITH SalespersonsWithOrders AS (
    SELECT DISTINCT
        SalesPersonID
    FROM Sales.Orders
    WHERE SalesPersonID IS NOT NULL
)
SELECT
    E.EmployeeID,
    E.FirstName,
    E.LastName
FROM Sales.Employees AS E
LEFT JOIN SalespersonsWithOrders AS S
    ON E.EmployeeID = S.SalesPersonID
WHERE S.SalesPersonID IS NULL;

-- 83.  employees older than average employee age.
WITH EmployeesAge AS
(SELECT
	EmployeeID,
	CONCAT(FirstName, ' ', LastName) AS Name,
	BirthDate,
	DATEDIFF(YEAR, BirthDate, GETDATE()) - CASE WHEN DATEADD(YEAR, DATEDIFF(YEAR, BirthDate, GETDATE()), BirthDate) > GETDATE() THEN 1 ELSE 0 END AS Age
FROM Sales.Employees)
SELECT
	*
FROM EmployeesAge
WHERE Age > (SELECT AVG(Age) FROM EmployeesAge);

-- 84. Show customers with highest score per country.
WITH HighestScoreCustomers AS
(SELECT
	Country,
	CustomerID,
	CONCAT(FirstName, ' ', LastName) AS Name,
	Score,
	RANK() OVER(PARTITION BY Country ORDER BY Score DESC) AS rn
FROM Sales.Customers)
SELECT
	Country,
	CustomerID,
	Name
FROM HighestScoreCustomers
WHERE rn = 1;

-- 85. Rank products by price.
SELECT
	ProductID,
	Product,
	Category,
	Price,
	RANK() OVER(ORDER BY Price DESC) AS rnk
FROM Sales.Products;

-- 86. Show duplicate customer first names.
WITH DuplicateNames AS (
    SELECT FirstName
    FROM Sales.Customers
    GROUP BY FirstName
    HAVING COUNT(*) > 1
)
SELECT *
FROM Sales.Customers
WHERE FirstName IN (SELECT FirstName FROM DuplicateNames);

-- 87. Count orders per customer per year.
SELECT
	CustomerID,
	YEAR(OrderDate) AS Year,
	COUNT(*) AS TotalOrders,
	SUM(Sales) AS TotalSales
FROM Sales.Orders
GROUP BY CustomerID, YEAR(OrderDate);

-- 88. Show employees whose salary is above department average.
WITH DepartmentAvgSalary AS
(
SELECT
	Department,
	AVG(Salary) AS AvgSalary
FROM Sales.Employees
GROUP BY Department
)
SELECT
	E.EmployeeID,
	CONCAT(E.FirstName, ' ', E.LastName) As Name,
	E.Department,
	E.Salary,
	D.AvgSalary
FROM Sales.Employees E
LEFT JOIN DepartmentAvgSalary AS D
	ON E.Department = D.Department
WHERE E.Salary > D.AvgSalary
ORDER BY E.Department ASC, E.Salary DESC;
```
---

## Difficulty 5 — Joins, Subqueries & Business Logic (101–200)

### Focus

* Multi-table joins
* Subqueries & EXISTS
* Business logic
* Data validation

101. Show order ID, customer first name, and order date.
     *Join `Orders` with `Customers` using CustomerID.*

102. Display product name and total quantity sold.
     *Join Orders + Products and aggregate.*

103. Show employee name and number of orders handled.
     *Measures employee workload.*

104. List orders with customer country information.
     *Join Orders → Customers.*

105. Show product category for each order.
     *Join Orders → Products.*

106. Display orders with salesperson full name.
     *Join Orders → Employees.*

107. List customers and the products they purchased.
     *Many-to-many relationship.*

108. Show orders with both shipping and billing addresses.
     *Data completeness check.*

109. List orders where customer and salesperson are from the same country.
     *Multi-table conditional join.*

110. Display employees who sold products in the “Electronics” category.
     *Filtering through joins.*

111. Calculate total sales per product category.
     *Category-level revenue.*

112. Find average order sales per customer.
     *Customer value analysis.*

113. Show total quantity sold per salesperson.
     *Sales efficiency.*

114. Calculate total revenue generated by each employee.
     *Performance measurement.*

115. Find number of customers per country who placed orders.
     *Active customers per region.*

116. Show number of orders per product.
     *Product popularity.*

117. Find customers with highest total purchase value.
     *High-value customers.*

118. Calculate average product price per category.
     *Pricing analysis.*

119. Show total sales per year.
     *Time-based aggregation.*

120. Find daily total sales.
     *Daily revenue trend.*

121. Find customers whose score is above the average score.
     *Scalar subquery.*

122. Show employees earning more than the average salary.
     *Common HR analysis.*

123. Find products priced higher than average product price.
     *Price comparison.*

124. List customers who placed orders above average order sales.
     *Subquery in WHERE.*

125. Find employees whose salary is greater than their manager’s salary.
     *Correlated subquery.*

126. Show customers who placed the maximum order value.
     *MAX subquery logic.*

127. Find orders with the highest quantity sold.
     *Extreme-value filtering.*

128. List products never ordered.
     *NOT EXISTS logic.*

129. Show customers who placed orders in both current and archive tables.
     *Set-based thinking.*

130. Find employees who never handled an order.
     *Anti-join logic.*

131. Find customers who have at least one order.
     *EXISTS usage.*

132. Find customers with no orders.
     *NOT EXISTS usage.*

133. Show products that appear in archived orders.
     *Archive data check.*

134. List employees who appear as managers.
     *Self-reference EXISTS.*

135. Find customers who placed orders after 2024.
     *Date-based EXISTS.*

136. Show orders where shipping took more than 7 days.
     *DATEDIFF logic.*

137. Find orders shipped on the same day they were ordered.
     *Operational efficiency.*

138. Display customers with more than 5 orders.
     *HAVING condition.*

139. Show employees who handled more than average number of orders.
     *Comparative aggregation.*

140. Find products contributing more than 10% of total sales.
     *Percentage logic.*

141. Show employee name and manager name.
     *Self JOIN.*

142. List managers with number of subordinates.
     *Hierarchy aggregation.*

143. Find employees reporting to a manager in the same department.
     *Organizational structure.*

144. Show employees whose manager earns less than them.
     *Comparison across rows.*

145. Find top-level managers (no ManagerID).
     *Hierarchy root.*

146. Find month with highest sales.
     *Time-based ranking.*

147. Show average sales per weekday.
     *Pattern analysis.*

148. List customers who ordered only in 2023.
     *Date filtering.*

149. Find customers who ordered in multiple years.
     *Loyalty behavior.*

150. Calculate order aging (today − order date).
     *Aging analysis.*

151. Find orders where Sales ≠ Quantity × Product Price.
     *Data inconsistency detection.*

152. Detect duplicate customers (same first + last name).
     *Data cleansing.*

153. Show employees with missing gender values.
     *NULL validation.*

154. Find orders missing shipping address.
     *Data completeness.*

155. Identify customers without country information.
     *Incomplete profiles.*

156. Rank employees by salary.
     *RANK() introduction.*

157. Show top 3 highest-priced products per category.
     *PARTITION BY logic.*

158. Calculate running total of sales per day.
     *Cumulative analytics.*

159. Find each customer’s first order date.
     *MIN window logic.*

160. Find each customer’s latest order.
     *MAX window logic.*

161. Find salesperson who generated the highest revenue.
     *Performance leader.*

162. Show customers whose last order was more than 6 months ago.
     *Churn detection.*

163. Find employees who never sold products above $500.
     *Filtering with joins.*

164. Show customers with increasing order values over time.
     *Trend detection.*

165. Identify products with declining sales trend.
     *Time comparison.*

166. Combine current and archived orders into one result set.
     *UNION usage.*

167. Find customers who appear only in archived orders.
     *Historical-only customers.*

168. Compare total sales in Orders vs OrdersArchive.
     *Performance comparison.*

169. Show products sold only in the past (archive only).
     *Product lifecycle.*

170. Find orders moved to archive in the last year.
     *Archival logic.*

171. Find top 5 customers by lifetime value.
     *LTV calculation.*

172. Find bottom 5 products by revenue.
     *Underperformers.*

173. Calculate average basket size per order.
     *Sales efficiency.*

174. Find employee whose sales vary the most month-to-month.
     *Variance analysis.*

175. Identify peak sales hour using CreationTime.
     *Time-of-day analysis.*

176. Rewrite a subquery using JOIN.
     *Query optimization.*

177. Rewrite JOIN logic using EXISTS.
     *Alternative logic.*

178. Identify redundant joins in a query.
     *Performance awareness.*

179. Find customers with exactly one order.
     *Exact count logic.*

180. Show employees who handled orders from all categories.
     *Division problem.*

181. Show cumulative sales per customer ordered by time.
     *Running totals.*

182. Find products with sales above category average.
     *Correlated subquery.*

183. Rank customers by total spending within each country.
     *Partition ranking.*

184. Show month-over-month sales growth.
     *Trend calculation.*

185. Identify sales drop-off points.
     *Analytics thinking.*

186. Find customers who placed orders on consecutive days.
     *Date sequence logic.*

187. Identify employees who improved sales year over year.
     *Growth detection.*

188. Find products whose price never changed (assume static).
     *Data reasoning.*

189. Show orders contributing to top 20% of revenue.
     *Pareto analysis.*

190. Find customers responsible for 80% of sales.
     *80/20 rule.*

191. Detect suspicious orders with unusually high quantity.
     *Anomaly detection.*

192. Find employee with longest gap between two orders handled.
     *Time gap analysis.*

193. Identify products ordered by all customers.
     *Relational division.*

194. Show customers with declining purchase frequency.
     *Churn pattern.*

195. Find best-selling product per month.
     *Window aggregation.*

196. Identify seasonality in sales.
     *Time-series logic.*

197. Compare weekday vs weekend sales.
     *Behavior analysis.*

198. Detect order spikes (outliers).
     *Statistical logic.*

199. Identify customers upgrading purchase value over time.
     *Lifecycle analysis.*

200. Find customers who stopped ordering after a specific date.
     *Churn cutoff.*


## Difficulty 6 — Advanced SQL & Analytics (201–300)

### Focus

* Window functions
* LAG / LEAD
* Percentiles
* Time-series analytics
* Correlated subqueries


201. Rank employees by salary within each department.
     *Uses `RANK() OVER (PARTITION BY Department)`.*

202. Assign row numbers to orders ordered by `OrderDate`.
     *Sequential ordering.*

203. Show running total of sales per customer ordered by date.
     *Cumulative sum logic.*

204. Find highest-value order per customer.
     *Window MAX per partition.*

205. Show second-highest salary in each department.
     *Ranking + filtering.*

206. Rank products by price within category.
     *Partition ranking.*

207. Calculate average order value per customer using windows.
     *Window AVG.*

208. Show difference between each order’s sales and customer’s average sales.
     *Deviation analysis.*

209. Identify top 3 products by sales per category.
     *Ranking with partition.*

210. Calculate percent contribution of each order to customer total sales.
     *Percentage window.*

211. Compare each order’s sales with the previous order by the same customer.
     *LAG function.*

212. Calculate day-over-day sales change.
     *Time comparison.*

213. Identify customers whose order value increased compared to previous order.
     *Growth detection.*

214. Find products with declining month-over-month sales.
     *LEAD / LAG trend.*

215. Show time gap between consecutive orders per customer.
     *DATEDIFF + LAG.*

216. Detect sudden sales spikes per day.
     *Anomaly detection.*

217. Compare employee sales performance between consecutive months.
     *Period comparison.*

218. Identify customers with decreasing purchase frequency.
     *Frequency trend.*

219. Show first and last order sales for each customer.
     *LAG/LEAD boundary logic.*

220. Calculate cumulative average sales per month.
     *Running average.*

221. Find employees earning more than their department average.
     *Correlated subquery.*

222. Show customers whose total sales exceed country average.
     *Nested aggregation.*

223. Find products whose price is above category average.
     *Correlated pricing.*

224. Identify orders whose sales exceed the customer’s average order value.
     *Per-customer comparison.*

225. Show employees who generated more sales than their manager.
     *Correlated comparison.*

226. Find customers with orders in every year available.
     *Division logic.*

227. Identify products sold in every country.
     *Relational division.*

228. Find customers with increasing order value trend.
     *Correlation + time.*

229. Find salesperson with highest average order value.
     *Multi-level aggregation.*

230. Identify employees whose salary is in top 10% company-wide.
     *Percentile logic.*

231. Calculate median employee salary.
     *Percentile function.*

232. Find 90th percentile of order sales.
     *Outlier threshold.*

233. Identify customers in top 5% by total spending.
     *High-value segmentation.*

234. Segment customers into quartiles by score.
     *NTILE logic.*

235. Categorize employees into salary bands.
     *Distribution grouping.*

236. Show month-over-month sales growth rate.
     *Percentage change.*

237. Calculate rolling 3-month average sales.
     *Moving average.*

238. Identify best-performing quarter each year.
     *Quarter aggregation.*

239. Compare sales in first half vs second half of year.
     *Period comparison.*

240. Detect seasonal patterns in product sales.
     *Seasonality detection.*

241. Identify customers ordering only in peak months.
     *Time behavior.*

242. Calculate average delivery time per month.
     *Logistics analysis.*

243. Show longest delivery delay per year.
     *Delivery performance.*

244. Find days with zero sales.
     *Gap detection.*

245. Detect sudden drops in daily sales.
     *Trend break.*

246. Find employees who sold all product categories.
     *Division with joins.*

247. Identify customers who bought from all categories.
     *Complete coverage.*

248. Find products ordered by all customers.
     *Relational division.*

249. Show customers who bought from the same salesperson repeatedly.
     *Relationship analysis.*

250. Find employees whose customers never returned.
     *Churn responsibility.*

251. Identify orders shipped before order date.
     *Data error detection.*

252. Find orders with negative or zero sales.
     *Invalid data.*

253. Detect employees reporting to themselves.
     *Hierarchy validation.*

254. Identify customers with conflicting country data.
     *Consistency check.*

255. Find duplicate orders (same customer, date, product).
     *Deduplication.*

256. Calculate customer lifetime value (LTV).
     *Total historical sales.*

257. Identify churned customers (no orders in last X months).
     *Churn logic.*

258. Calculate repeat purchase rate.
     *Customer behavior.*

259. Compute average revenue per user (ARPU).
     *SaaS metric.*

260. Find customers with high order frequency but low value.
     *Behavior segmentation.*

261. Build employee management hierarchy.
     *Self-join or recursive CTE.*

262. Find maximum depth of management tree.
     *Hierarchy depth.*

263. Identify managers with highest revenue teams.
     *Team performance.*

264. Show employees with no subordinates.
     *Leaf nodes.*

265. Identify manager-employee salary inversions.
     *Pay structure validation.*

266. Rewrite correlated subquery using JOIN + window.
     *Query optimization.*

267. Replace subquery with EXISTS.
     *Performance tuning.*

268. Identify expensive aggregations in a query.
     *Execution awareness.*

269. Suggest indexes for common queries.
     *Index strategy.*

270. Compare execution plans of JOIN vs EXISTS.
     *Performance tradeoffs.*

271. Identify customers contributing to top 80% of revenue.
     *Pareto principle.*

272. Detect product cannibalization trends.
     *Product overlap analysis.*

273. Find customers switching product categories over time.
     *Behavior shift.*

274. Identify plateauing sales trends.
     *Growth analysis.*

275. Detect long-term declining customers.
     *Churn early warning.*

276. Find customers with consistent monthly spending.
     *Stability metric.*

277. Identify best salesperson per quarter.
     *Time-based ranking.*

278. Calculate rolling customer retention rate.
     *Cohort analysis.*

279. Detect abnormal employee performance changes.
     *Anomaly detection.*

280. Identify customers who returned after long inactivity.
     *Reactivation analysis.*

281. Find orders responsible for revenue spikes.
     *Event attribution.*

282. Identify products driving seasonal peaks.
     *Seasonal drivers.*

283. Detect sudden price-sensitivity changes.
     *Elasticity logic.*

284. Compare performance before vs after promotions (assumed).
     *A/B logic.*

285. Identify employees with inconsistent sales patterns.
     *Stability check.*

286. Find products with stable long-term demand.
     *Demand consistency.*

287. Identify customers upselling over time.
     *Cross-sell analysis.*

288. Detect order batching behavior.
     *Operational behavior.*

289. Identify peak load times using CreationTime.
     *Capacity planning.*

290. Find customers ordering across multiple time zones (assumed).
     *Global behavior.*

291. Calculate average order processing time.
     *Operational KPI.*

292. Identify orders stuck in processing.
     *Bottleneck detection.*

293. Detect suspiciously fast deliveries.
     *Fraud/data error.*

294. Identify customers placing orders outside normal hours.
     *Behavior anomaly.*

295. Find salespersons with volatile performance.
     *Statistical variance.*

296. Identify customer cohorts by first order month.
     *Cohort analysis.*

297. Track cohort revenue over time.
     *Cohort retention.*

298. Identify best cohort by lifetime value.
     *Cohort comparison.*

299. Detect sales saturation points.
     *Market maturity.*

300. Build a full customer analytics dashboard query.
     *End-to-end analytics.*

---

## Difficulty 7 — CTEs, Recursion & Multi-Stage Analytics (301–400)

### Focus

* Complex CTE pipelines
* Recursive queries
* Data warehousing logic
* KPI modeling
* Executive-level analytics

301. Build a CTE to calculate total sales per customer, then rank customers by that value.
     *Multi-step aggregation + ranking.*

302. Use CTEs to compute monthly sales, then calculate month-over-month growth.
     *Chained analytics.*

303. Create a CTE to calculate employee sales, then filter top 10%.
     *Performance segmentation.*

304. Build a pipeline to identify customers contributing to 80% of revenue.
     *Pareto logic.*

305. Create a CTE to calculate average order value per month.
     *Time-based metric.*

306. Use CTEs to find products with declining sales for 3 consecutive months.
     *Trend detection.*

307. Build layered CTEs to detect churned customers.
     *Customer lifecycle modeling.*

308. Calculate rolling 6-month revenue using CTEs.
     *Moving window logic.*

309. Identify best salesperson per quarter using CTEs.
     *Time-based ranking.*

310. Build a reusable CTE for active customers.
     *Reusability & clarity.*

311. Build an employee hierarchy using recursive CTEs.
     *Org tree modeling.*

312. Find the management chain for a given employee.
     *Upward recursion.*

313. Calculate hierarchy depth per employee.
     *Org complexity.*

314. Identify top-level managers with most descendants.
     *Team size analysis.*

315. Detect circular reporting relationships.
     *Data integrity check.*

316. Flatten employee hierarchy into parent-child pairs.
     *Normalization.*

317. Find all employees under a given manager.
     *Recursive traversal.*

318. Compute total salary cost under each manager.
     *Hierarchical aggregation.*

319. Identify managers whose teams generate the most revenue.
     *Team performance.*

320. Find employees without managers (root nodes).
     *Hierarchy roots.*

321. Use CTEs to calculate customer lifetime value (LTV).
     *Lifetime aggregation.*

322. Create a cohort analysis by customer first order month.
     *Cohort definition.*

323. Track cohort revenue over time using CTEs.
     *Cohort retention.*

324. Identify best-performing cohort by revenue.
     *Cohort comparison.*

325. Build a churn risk score using order frequency and recency.
     *Predictive feature engineering.*

326. Detect declining customers using rolling averages.
     *Early churn detection.*

327. Identify customers with seasonal buying patterns.
     *Seasonality analysis.*

328. Build a funnel: customers → orders → repeat orders.
     *Funnel modeling.*

329. Compute customer retention rate month-over-month.
     *Retention analytics.*

330. Calculate reactivation rate for dormant customers.
     *Lifecycle analytics.*

331. Rank orders per customer by sales using CTE + window.
     *Partition ranking.*

332. Identify each customer’s peak spending month.
     *Time-based max.*

333. Calculate cumulative sales per customer using CTEs.
     *Running totals.*

334. Detect abnormal order values using z-score logic.
     *Statistical anomaly detection.*

335. Identify customers with consistent month-over-month growth.
     *Trend consistency.*

336. Compare employee performance before and after promotion date (assumed).
     *Event comparison.*

337. Find top 3 products per category per month.
     *Multi-dimensional ranking.*

338. Identify declining product categories.
     *Category trend.*

339. Detect sales volatility per employee.
     *Stability analysis.*

340. Identify peak sales days using moving averages.
     *Peak detection.*

341. Allocate order revenue across employees proportionally.
     *Revenue attribution.*

342. Detect cannibalization between product categories.
     *Product overlap.*

343. Identify customers migrating to premium products.
     *Upsell detection.*

344. Compute weighted average delivery time.
     *Logistics KPI.*

345. Detect operational bottlenecks in shipping.
     *Process optimization.*

346. Identify customers with abnormal buying cycles.
     *Behavior anomaly.*

347. Build a customer health score.
     *Multi-metric scoring.*

348. Detect fraudulent orders using rule-based logic.
     *Fraud heuristics.*

349. Identify sales spikes driven by single customers.
     *Concentration risk.*

350. Compare weekday vs weekend conversion rates.
     *Behavioral analysis.*

351. Find customers who bought from every category.
     *Relational division.*

352. Identify employees who sold all products in a category.
     *Complete coverage.*

353. Find products purchased by all high-value customers.
     *Intersection logic.*

354. Detect customers loyal to one salesperson.
     *Exclusive relationship.*

355. Identify cross-sell opportunities.
     *Association analysis.*

356. Build a fact table view for orders.
     *Fact modeling.*

357. Build dimension views for customers, products, employees.
     *Dimension modeling.*

358. Create a star schema query for reporting.
     *OLAP-style query.*

359. Simulate slowly changing dimension (Type 2) logic.
     *Historical tracking.*

360. Build snapshot tables using SQL.
     *Point-in-time data.*

361. Optimize multi-CTE queries.
     *Query refactoring.*

362. Identify redundant scans in execution plans.
     *Performance diagnosis.*

363. Replace nested subqueries with window functions.
     *Efficiency improvement.*

364. Partition large tables logically for reporting.
     *Scalability strategy.*

365. Identify queries suitable for materialized views.
     *Caching logic.*

366. Build a full executive sales dashboard query.
     *End-to-end analytics.*

367. Identify leading indicators of churn.
     *Predictive insight.*

368. Detect early signs of product decline.
     *Lifecycle monitoring.*

369. Build an automated anomaly detection query.
     *Advanced analytics.*

370. Compute rolling cohort LTV.
     *Cohort economics.*

371. Identify customers contributing to revenue volatility.
     *Risk analysis.*

372. Compare sales performance across regions.
     *Geographical analytics.*

373. Detect saturation in product demand.
     *Market maturity.*

374. Identify employee burnout signals using order patterns.
     *Operational risk.*

375. Build a reusable KPI layer in SQL.
     *Analytics engineering.*

376. Create SQL tests for data quality checks.
     *Data reliability.*

377. Validate archive vs current data consistency.
     *Audit logic.*

378. Track data freshness metrics.
     *Pipeline monitoring.*

379. Simulate backfilled data corrections.
     *Historical adjustments.*

380. Build a SQL-based monitoring alert.
     *Operational alerting.*

381. Identify customers with erratic spending behavior.
     *Behavior volatility.*

382. Detect abnormal delivery times per region.
     *Logistics anomaly.*

383. Find products with price elasticity changes.
     *Pricing analytics.*

384. Identify employees whose performance depends on seasonality.
     *Seasonal performance.*

385. Build a SQL-only forecasting baseline.
     *Predictive groundwork.*

386. Track KPI drift over time.
     *Metric stability.*

387. Detect customer lifecycle transitions.
     *State modeling.*

388. Build an explainable churn model using SQL features.
     *Model feature prep.*

389. Identify long-term value creators.
     *Strategic insight.*

390. Build a fully documented SQL analytics pipeline.
     *Production readiness.*

391. Design a full sales analytics mart in SQL.
     *Data architecture.*

392. Build reusable SQL macros (conceptual).
     *Code abstraction.*

393. Refactor analytics SQL for readability and reuse.
     *Clean code.*

394. Identify hidden assumptions in business metrics.
     *Critical thinking.*

395. Validate KPIs against business rules.
     *Data governance.*

396. Simulate missing data scenarios.
     *Resilience testing.*

397. Build SQL-based unit tests.
     *Data testing.*

398. Detect silent data corruption.
     *Reliability engineering.*

399. Build a production-ready analytics SQL model.
     *Industry-grade SQL.*

400. Explain your SQL design choices to stakeholders.
     *Communication skill.*

---

## How to Use This Repository

* Solve **Difficulty 3–4** → Junior SQL / Foundations
* Solve **Difficulty 5–6** → Data Analyst / Senior SQL
* Solve **Difficulty 7** → Analytics Engineer / Data Scientist

---

Happy querying 🚀
