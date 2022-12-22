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


# how many times is Hadoop mentioned on hackernews

```hadoop_per_month
SELECT
    COUNT(*) AS count,
    DATE_FORMAT(FROM_UNIXTIME(time), '%Y-%m-01') AS date
FROM items
WHERE LOWER(url) LIKE '%hadoop%' OR LOWER(title) LIKE '%hadoop%' OR LOWER(text) LIKE '%hadoop%'
GROUP BY 2
ORDER BY 2 ASC;
```
<LineChart data = {hadoop_per_month} y=count x=date  />

# how many times is docker mentioned on hackernews

```docker_per_month
SELECT
    COUNT(*) AS count,
    DATE_FORMAT(FROM_UNIXTIME(time), '%Y-%m-01') AS date
FROM items
WHERE LOWER(url) LIKE '%docker%' OR LOWER(title) LIKE '%docker%' OR LOWER(text) LIKE '%docker%'
GROUP BY 2
ORDER BY 2 ASC;
```
<LineChart data = {docker_per_month} y=count x=date  />