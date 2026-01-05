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

### JOIN-Centric Queries

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


### Aggregation + JOIN

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


### Subqueries (Core Interview Topic)

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


### EXISTS / NOT EXISTS

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


### Advanced Filtering Logic

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

### Self Joins & Hierarchies

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

### Date & Time Analysis

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


### Data Quality & Validation

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

### Window Function Introduction (Light)

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


### Mixed Real-World Scenarios

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


### Set Operations & Archives

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


### Interview-Style Thinking

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


### Logic & Optimization

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


### Advanced Aggregation Patterns

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

### Final Challenge (Difficulty 5)

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
