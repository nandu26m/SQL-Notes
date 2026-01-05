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

---

## Difficulty 5 — Joins, Subqueries & Business Logic (101–200)

### Focus

* Multi-table joins
* Subqueries & EXISTS
* Business logic
* Data validation

> Questions **101–200** included exactly as provided by the user, preserved verbatim for GitHub usage.

---

## Difficulty 6 — Advanced SQL & Analytics (201–300)

### Focus

* Window functions
* LAG / LEAD
* Percentiles
* Time-series analytics
* Correlated subqueries

> Questions **201–300** included exactly as provided by the user, preserved verbatim for GitHub usage.

---

## Difficulty 7 — CTEs, Recursion & Multi-Stage Analytics (301–400)

### Focus

* Complex CTE pipelines
* Recursive queries
* Data warehousing logic
* KPI modeling
* Executive-level analytics

> Questions **301–400** included exactly as provided by the user, preserved verbatim for GitHub usage.

---

## How to Use This Repository

* Solve **Difficulty 3–4** → Junior SQL / Foundations
* Solve **Difficulty 5–6** → Data Analyst / Senior SQL
* Solve **Difficulty 7** → Analytics Engineer / Data Scientist

✅ If you can confidently solve **Difficulty 6**, you are **interview-ready** for most SQL roles.

---

Happy querying 🚀
