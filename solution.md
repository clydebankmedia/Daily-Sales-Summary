# Solution Code - Daily Sales Summary
<details>
<summary>Step 1 Solution  - Preview the tickets data</summary>
    
```sql
SELECT purchase_date, price_paid
FROM tickets
LIMIT 5;
```
</details>
<details>
<summary>Step 2 Solution - Count how many tickets sold each day</summary>
    
```sql
SELECT 
    purchase_date, 
    COUNT(*) as total_tickets
FROM tickets
GROUP BY purchase_date;
    
-- Optional: ORDER BY total_tickets
SELECT 
    purchase_date, 
    COUNT(*) as total_tickets
FROM tickets
GROUP BY purchase_date
ORDER BY total_tickets DESC;
```
</details>
<details>
    
<summary>Step 3 Solution - Add the average ticket price</summary>
    
```sql
SELECT 
    purchase_date, 
    COUNT(*) as total_tickets,
    AVG(price_paid) AS avg_ticket_price
FROM tickets
GROUP BY purchase_date;
```
</details>
<details>
<summary>Step 4 Solution - Clean up the average for reporting</summary>

```sql
SELECT 
    purchase_date, 
    COUNT(*) as total_tickets,
    ROUND(AVG(price_paid), 2) AS avg_ticket_price
FROM tickets
GROUP BY purchase_date;
```
</details>
<details>
<summary>Step 5 Solution - Put the results in order<summary>
    
```sql
SELECT 
    purchase_date, 
    COUNT(*) as total_tickets,
    ROUND(AVG(price_paid), 2) AS avg_ticket_price
FROM tickets
GROUP BY purchase_date
ORDER BY purchase_date ASC;
```
</details>
<details>    
<summary>Step 6 Solution - (Optional) Narrow the focus</summary>
    
```sql
SELECT 
    purchase_date, 
    COUNT(*) as total_tickets,
    ROUND(AVG(price_paid), 2) AS avg_ticket_price
FROM tickets
WHERE price_paid >= 25
GROUP BY purchase_date
ORDER BY purchase_date ASC;
```
</details>
<details>    
<summary>Step 7 Solution - (Optional - Stretch): Look at daily revenue totals</summary>
    
```sql
SELECT 
    purchase_date, 
    COUNT(*) as total_tickets,
    ROUND(sum(price_paid), 2) AS daily_revenue
FROM tickets
GROUP BY purchase_date
ORDER BY daily_revenue DESC;
```
</details>
<details>
<summary>**Solution**</summary>
    
    ```sql
    SELECT purchase_date, price_paid
    FROM tickets
    LIMIT 5;
    ```
</details>
<details>    
<summary>**Solution**</summary>
    
```sql
SELECT 
    purchase_date, 
    COUNT(*) as total_tickets
FROM tickets
GROUP BY purchase_date;
    
-- Optional: ORDER BY total_tickets
SELECT 
    purchase_date, 
    COUNT(*) as total_tickets
FROM tickets
GROUP BY purchase_date
ORDER BY total_tickets DESC;
```
</details>
<details>    
<summary>**Solution**</summary>
    
```sql
SELECT 
    purchase_date, 
    COUNT(*) as total_tickets,
    AVG(price_paid) AS avg_ticket_price
FROM tickets
GROUP BY purchase_date;
```
</details>
<details>    
<summary>**Solution**</summary>
    
```sql
SELECT 
    purchase_date, 
    COUNT(*) as total_tickets,
    ROUND(AVG(price_paid), 2) AS avg_ticket_price
FROM tickets
GROUP BY purchase_date;
```
</details>
<details>    
<summary>**Solution**</summary>
    
```sql
SELECT 
    purchase_date, 
    COUNT(*) as total_tickets,
    ROUND(AVG(price_paid), 2) AS avg_ticket_price
FROM tickets
GROUP BY purchase_date
ORDER BY purchase_date ASC;
```
</details>
<details>    
<summary>**Solution**</summary>
    
```sql
SELECT 
    purchase_date, 
    COUNT(*) as total_tickets,
    ROUND(AVG(price_paid), 2) AS avg_ticket_price
FROM tickets
WHERE price_paid >= 10
GROUP BY purchase_date
ORDER BY purchase_date ASC;
```
</details>
<details>    
<summary>Step 7 Solution</summary>
    
```sql
SELECT 
    purchase_date, 
    COUNT(*) as total_tickets,
    ROUND(sum(price_paid), 2) AS daily_revenue
FROM tickets
GROUP BY purchase_date
ORDER BY daily_revenue DESC;
```
</details>
