# how many times is SQL mentioned on hackernews

```sql_per_month
SELECT 
  count(*) as count, 
  DATE_FORMAT(FROM_UNIXTIME(time), '%Y-%m-01') as date 
FROM hackernews 
WHERE lower(url) like '%sql%' or lower(title) like '%sql%' or lower(text) like '%sql%'
GROUP BY 2 
ORDER BY 2 ASC;
```
<LineChart data = {sql_per_month} y=count x=date  />