# Total number of registered users

```total_users
SELECT COUNT(*) AS count
FROM users;
```
<BigValue 
    data={total_users}
    value="count"
/> 

# Number of new users per month

```users_per_month
SELECT DATE_FORMAT(FROM_UNIXTIME(created), "%Y-%m-01") AS date,
       COUNT(*) AS count
FROM users
GROUP BY 1
ORDER BY 1 ASC;
```

<BarChart 
    data={users_per_month} 
    x=date 
    y=count
/>

# What is the trend of total cumulative users per month?

```cumulative_total_users
WITH per_month AS (
    SELECT DATE_FORMAT(FROM_UNIXTIME(created), "%Y-%m-01") AS date,
           COUNT(*) AS count
    FROM users
    GROUP BY 1
    ORDER BY 1 ASC
)
SELECT date,
       SUM(count) OVER (ORDER BY date ASC) AS cumulative_count
FROM per_month
```

<LineChart 
    data={cumulative_total_users} 
    x=date 
    y=cumulative_count
/>

# What is the number of active users (who submitted story, comment) per year, per quarter, per month, per week?

```user_retention
SELECT 'YEAR Active Users' AS name, COUNT(DISTINCT `by`) AS value FROM items WHERE time > unix_timestamp(DATE_SUB(now(), INTERVAL 1 YEAR))
UNION
SELECT 'QUARTER Active Users' AS name, COUNT(DISTINCT `by`) AS value FROM items WHERE time > unix_timestamp(DATE_SUB(now(), INTERVAL 1 QUARTER))
UNION
SELECT 'MONTH Active Users' AS name, COUNT(DISTINCT `by`) AS value FROM items WHERE time > unix_timestamp(DATE_SUB(now(), INTERVAL 1 MONTH))
UNION
SELECT 'WEEK Active Users' AS name, COUNT(DISTINCT `by`) AS value FROM items WHERE time > unix_timestamp(DATE_SUB(now(), INTERVAL 1 WEEK))
```

<ECharts config={
        {
            tooltip: {
                formatter: '{b}: {c}'
            },
            series: [
                {
                type: 'funnel',
                data: user_retention,
                }
            ]
        }
    }
/>

# Users who submitted the most stories on hackernews

```most_submit_users
SELECT `by`, COUNT(*) AS count
FROM items
WHERE type = 'story'
GROUP BY 1
ORDER BY 2 DESC
LIMIT 20;
```

<DataTable
    data={most_submit_users} 
    rows=10
/>

# Users with the most comments submitted on hackernews

```most_comments_users
SELECT `by`, COUNT(*) AS count
FROM items
WHERE type = 'comment'
GROUP BY 1
ORDER BY 2 DESC
LIMIT 20;
```


<DataTable
    data={most_comments_users} 
    rows=10
/>

# Users who got the most voted on hackernews

```most_score_users
SELECT `by`, SUM(score) AS total_score
FROM items
GROUP BY 1
ORDER BY 2 DESC
LIMIT 20;
```

<DataTable
    data={most_submit_users} 
    rows=10
/>