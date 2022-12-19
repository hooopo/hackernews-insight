# Schema of hackernews datasets

```schema
desc items
```

<DataTable
    data={schema} 
    rows=20
    rowNumbers=false
/>

# Total number of datasets

```total_items
select 
count(*),
sum(dead) as dead_count
FROM items

```

<DataTable
    data={total_items} 
    rowNumbers=false
    rowLines=false
/>

# Number of items of each type

```items_per_type
select
  type,
  count(*) as count
FROM items
group by 1
order by 2 desc
```

<DataTable
    data={items_per_type} 
/>

# How many items created per month?

```items_per_month
SELECT 
  count(*) as count, 
  DATE_FORMAT(FROM_UNIXTIME(time), '%Y-%m-01') as date 
FROM items 
GROUP BY 2 
ORDER BY 2 ASC;
```
<LineChart data = {items_per_month} y=count x=date  />

# How many stories created per month?

```stories_per_month
SELECT 
  count(*) as count, 
  DATE_FORMAT(FROM_UNIXTIME(time), '%Y-%m-01') as date 
FROM items 
WHERE type = 'story'
GROUP BY 2 
ORDER BY 2 ASC;
```
<LineChart data = {stories_per_month} y=count x=date  />

# How many comments created per month?

```comments_per_month
SELECT 
  count(*) as count, 
  DATE_FORMAT(FROM_UNIXTIME(time), '%Y-%m-01') as date 
FROM items 
WHERE type = 'comment'
GROUP BY 2 
ORDER BY 2 ASC;
```
<LineChart data = {comments_per_month} y=count x=date  />


# How many URL stories created per month?

```url_stories_per_month
SELECT 
  count(*) as count, 
  DATE_FORMAT(FROM_UNIXTIME(time), '%Y-%m-01') as date 
FROM items 
WHERE type = 'story' and url is not null
GROUP BY 2 
ORDER BY 2 ASC;
```
<LineChart data = {url_stories_per_month} y=count x=date  />

# How many text stories created per month?

```text_stories_per_month
SELECT 
  count(*) as count, 
  DATE_FORMAT(FROM_UNIXTIME(time), '%Y-%m-01') as date 
FROM items 
WHERE type = 'story' and url is null
GROUP BY 2 
ORDER BY 2 ASC;
```
<LineChart data = {text_stories_per_month} y=count x=date  />

# How many dead stories created per month?

```dead_stories_per_month
SELECT 
  count(*) as count, 
  DATE_FORMAT(FROM_UNIXTIME(time), '%Y-%m-01') as date 
FROM items 
WHERE type = 'story' and dead = 1
GROUP BY 2 
ORDER BY 2 ASC;
```
<LineChart data = {dead_stories_per_month} y=count x=date  />