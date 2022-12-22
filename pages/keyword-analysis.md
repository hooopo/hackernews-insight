# how many times is SQL mentioned on hackernews

```sql_per_month
SELECT
    COUNT(*) AS count,
    DATE_FORMAT(FROM_UNIXTIME(time), '%Y-%m-01') AS date
FROM items
WHERE LOWER(url) LIKE '%sql%' OR LOWER(title) LIKE '%sql%' OR LOWER(text) LIKE '%sql%'
GROUP BY 2
ORDER BY 2 ASC;
```
<LineChart data = {sql_per_month} y=count x=date  />