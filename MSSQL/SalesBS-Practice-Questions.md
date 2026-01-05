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
**📕 Difficulty 6 — Questions 201–300**
Focus areas:

* Window functions (core)
* Correlated subqueries
* Time-series analysis
* Advanced joins & ranking logic
* Business analytics patterns
---

# Difficulty 6 — Advanced SQL & Analytics (201–300)

---

## 🔹 Window Functions (Must-Know)

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

---

## 🔹 LAG / LEAD (Trend Analysis)

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

---

## 🔹 Correlated Subqueries (Interview Favorite)

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

---

## 🔹 Percentiles & Distribution

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

---

## 🔹 Advanced Time-Series Analysis

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

---

## 🔹 Advanced JOIN Logic

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

---

## 🔹 Data Integrity & Auditing

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

---

## 🔹 Complex Business Metrics

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

---

## 🔹 Recursive / Hierarchical Thinking

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

---

## 🔹 Performance & Optimization

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

---

## 🔹 Advanced Analytical Challenges

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

---

## 🔹 Final Difficulty-6 Challenges

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
**Difficulty 7 — Questions 301–400**
Focus areas:

* Complex CTE pipelines
* Recursive queries
* Multi-stage analytics
* Data warehousing logic
* Business KPI modeling

---

# Difficulty 7 — CTEs, Recursion & Multi-Stage Analytics (301–400)

---

## 🔹 Multi-CTE Pipelines

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

---

## 🔹 Recursive CTEs (Hierarchy & Sequences)

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

---

## 🔹 Advanced Analytical CTEs

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

---

## 🔹 Window Functions Inside CTEs

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

---

## 🔹 Complex Business Logic

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

---

## 🔹 Advanced Set Logic & Division

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

---

## 🔹 Data Warehousing Patterns

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

---

## 🔹 Performance & Scaling

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

---

## 🔹 Final Difficulty-7 Challenges

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

---

## 🔹 Boss-Level Endgame (Still Difficulty 7)

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
