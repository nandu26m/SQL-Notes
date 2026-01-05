# Difficulty 3 — Basics & Filters (50 Questions)

1. List all customers from the `Customers` table.
   *Tests basic SELECT and table usage.*

2. Show only `FirstName` and `Country` of all customers.
   *Column selection practice.*

3. Find customers where `Country = 'USA'`.
   *Simple WHERE condition.*

4. Get customers with `Score > 80`.
   *Numeric filtering.*

5. List employees working in the `Sales` department.
   *Filtering text columns.*

6. Display employee names and salaries only.
   *Selective projection.*

7. Find employees with salary greater than 50000.
   *Comparison operator.*

8. List all products with price less than 100.
   *Basic condition on products.*

9. Show all orders with `OrderStatus = 'Shipped'`.
   *Status-based filtering.*

10. Get orders placed after `2024-01-01`.
    *Date comparison.*

11. Display all customers ordered by `Score` ascending.
    *ORDER BY basics.*

12. List products ordered by price descending.
    *Sorting practice.*

13. Find employees whose `Gender = 'M'`.
    *Character filtering.*

14. Show distinct countries from `Customers`.
    *DISTINCT usage.*

15. Count total number of customers.
    *Basic aggregation.*

16. Count how many employees exist.
    *Row counting.*

17. Find the highest salary among employees.
    *MAX function.*

18. Find the lowest product price.
    *MIN function.*

19. Calculate the average employee salary.
    *AVG aggregation.*

20. Show total sales value from `Orders`.
    *SUM aggregation.*

21. List orders with quantity greater than 5.
    *Numeric condition.*

22. Show customers whose score is NULL.
    *NULL handling.*

23. Show employees with no manager assigned.
    *NULL condition logic.*

24. List orders where `ShipDate` is NULL.
    *Pending shipments.*

25. Show top 5 highest-paid employees.
    *LIMIT / TOP usage.*

26. Get first 10 orders sorted by `OrderDate`.
    *Pagination basics.*

27. Show products in category `Electronics`.
    *Category filtering.*

28. Find customers not from `Germany`.
    *NOT condition.*

29. List employees born after 1990.
    *Date filtering.*

30. Display orders with sales greater than 1000.
    *Revenue filtering.*

31. Show all archived orders.
    *Archive table usage.*

32. Count number of archived orders.
    *Basic counting.*

33. List orders created today.
    *Date function usage.*

34. Show customers with score between 50 and 80.
    *BETWEEN operator.*

35. List employees whose salary is between 40k and 60k.
    *Range filtering.*

36. Find products with price IN (50, 100, 150).
    *IN operator.*

37. Show orders with status IN ('Pending', 'Processing').
    *Multiple-value filtering.*

38. Display employees sorted by last name.
    *Alphabetical ordering.*

39. Find customers whose first name starts with 'A'.
    *LIKE operator.*

40. Find products ending with the word 'Pro'.
    *Pattern matching.*

41. Show orders shipped after order date.
    *Logical date comparison.*

42. List all columns from `Employees`.
    *Wildcard usage.*

43. Find customers with score not equal to 100.
    *Inequality operators.*

44. Display orders where sales = quantity × price (logical check).
    *Expression logic.*

45. Show employees with salary divisible by 5.
    *Modulo logic.*

46. Find customers with missing last names.
    *NULL checks.*

47. List products with price greater than average price.
    *Subquery intro.*

48. Show employees earning exactly 60000.
    *Exact match.*

49. Count orders per status.
    *GROUP BY intro.*

50. Show today’s date using SQL.
    *System function awareness.*

---

# Difficulty 4 — Grouping & Simple Joins (50 Questions)

51. Count customers per country.
    *GROUP BY fundamentals.*

52. Calculate average score per country.
    *Grouped aggregation.*

53. Count employees per department.
    *Department-level analysis.*

54. Find max salary per department.
    *Grouped MAX.*

55. Show departments having more than 5 employees.
    *HAVING clause.*

56. Count orders per order status.
    *Operational insight.*

57. Calculate total sales per customer.
    *Customer contribution.*

58. Calculate total quantity sold per product.
    *Sales volume analysis.*

59. Find total sales per salesperson.
    *Performance metrics.*

60. Join `Orders` with `Customers` to show customer names per order.
    *Basic INNER JOIN.*

61. Join `Orders` with `Products` to show product names.
    *Foreign key joins.*

62. Display order date, product name, and quantity.
    *Multi-table SELECT.*

63. Find customers who have placed at least one order.
    *JOIN + DISTINCT.*

64. Find customers who never placed an order.
    *LEFT JOIN logic.*

65. Show employees who handled orders.
    *Employee–order relationship.*

66. Count orders per day.
    *Date grouping.*

67. Find sales per month.
    *Time-series aggregation.*

68. Join employees with their managers.
    *Self join.*

69. Show employee name and manager name.
    *Hierarchy queries.*

70. Find average sales per order.
    *Order performance.*

71. Show customers with more than 3 orders.
    *HAVING + COUNT.*

72. List top 5 customers by total sales.
    *Ranking logic.*

73. Show top-selling product.
    *Aggregate + ORDER.*

74. Find employee with highest total sales.
    *Performance ranking.*

75. Count archived orders per year.
    *Historical data analysis.*

76. Compare current vs archived order counts.
    *Multi-table aggregation.*

77. Show orders with delayed shipping.
    *Date difference logic.*

78. Calculate average delivery time.
    *DATEDIFF usage.*

79. Find products never ordered.
    *Anti-join.*

80. Find customers who ordered multiple categories.
    *Join + GROUP BY.*

81. Show total sales per country.
    *Geographical analysis.*

82. Find salesperson with no orders.
    *LEFT JOIN filtering.*

83. List employees older than average employee age.
    *Subquery logic.*

84. Show customers with highest score per country.
    *Window logic intro.*

85. Rank products by price.
    *ROW_NUMBER / RANK intro.*

86. Show duplicate customer first names.
    *Data quality checks.*

87. Count orders per customer per year.
    *Multi-column grouping.*

88. Show employees whose salary is above department average.
    *Correlated subquery.*

89. Find last order date per customer.
    *MAX with grouping.*

90. Find first order per customer.
    *MIN aggregation.*

91. Calculate running total of sales.
    *Window function intro.*

92. Show orders with sales above monthly average.
    *Advanced subqueries.*

93. Find customers inactive for last 6 months.
    *Date filtering.*

94. Compare employee salary vs manager salary.
    *Self join logic.*

95. Show product revenue contribution percentage.
    *Ratio calculations.*

96. Identify peak sales day.
    *MAX grouping.*

97. Show orders placed on weekends.
    *Date functions.*

98. Detect orders shipped before order date.
    *Data validation.*

99. Calculate cumulative sales per customer.
    *Window functions.*

100. Identify repeat customers.
     *Business insight.*

---

**Difficulty 5** — **100 questions**
Focus areas:

* Multi-table JOINs
* Subqueries
* Aggregations with conditions
* Real business logic
* Data validation patterns

---

# Difficulty 5 — Joins, Subqueries & Business Logic (Questions 101–200)

---

### 🔹 JOIN-Centric Queries

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

---

### 🔹 Aggregation + JOIN

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

---

### 🔹 Subqueries (Core Interview Topic)

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

---

### 🔹 EXISTS / NOT EXISTS

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

---

### 🔹 Advanced Filtering Logic

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

---

### 🔹 Self Joins & Hierarchies

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

---

### 🔹 Date & Time Analysis

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

---

### 🔹 Data Quality & Validation

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

---

### 🔹 Window Function Introduction (Light)

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

---

### 🔹 Mixed Real-World Scenarios

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

---

### 🔹 Set Operations & Archives

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

---

### 🔹 Interview-Style Thinking

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

---

### 🔹 Logic & Optimization

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

---

### 🔹 Advanced Aggregation Patterns

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

---

### 🔹 Final Challenge (Difficulty 5)

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

---
