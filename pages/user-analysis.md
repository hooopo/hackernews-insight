# Total number of registered users

```total_users
select count(*) as count from users
```
<BigValue 
    data={total_users}
    value="count"
/> 

# Number of new users per month

```users_per_month
select DATE_FORMAT(from_unixtime(created),"%Y-%m-01") as date,
  count(*) as count
from users
group by 1
order by 1 asc
```

<BarChart 
    data={users_per_month} 
    x=date 
    y=count
/>

# What is the trend of total cumulative users per month?

```cumulative_total_users
with per_month as (
select DATE_FORMAT(from_unixtime(created),"%Y-%m-01") as date,
  count(*) as count
from users
group by 1
order by 1 asc
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

# Users who submitted the most stories on hackernews

```most_submit_users
select `by`, count(*) as count
FROM items 
where type = 'story'
group by 1 
order by 2 desc 
limit 10;
```

<BarChart 
    data={most_submit_users} 
    x=by 
    y=count 
    swapXY=true 
    fillColor=green
    fillOpacity=0.5
    yAxisTitle="Submits Count" 
/>

# Users with the most comments submitted on hackernews

```most_comments_users
select `by`, count(*) as count
FROM items 
where type = 'comment'
group by 1 
order by 2 desc 
limit 10;
```

<BarChart 
    data={most_comments_users} 
    x=by 
    y=count 
    swapXY=true 
    fillOpacity=0.5
    yAxisTitle="Comments Count" 
/>

# Users who got the most voted on hackernews

```most_score_users
select `by`, sum(score) as total_score
FROM items 
group by 1 
order by 2 desc 
limit 10;
```

<BarChart 
    data={most_score_users} 
    x=by 
    y=total_score
    swapXY=true 
    fillColor=red
    fillOpacity=0.5
    yAxisTitle="Total Score" 
/>