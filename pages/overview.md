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
SELECT
    COUNT(*),
    SUM(dead) AS dead_count
FROM items

```

<DataTable
    data={total_items} 
    rowNumbers=false
    rowLines=false
/>

# Number of items of each type

```items_per_type
SELECT
    type,
    COUNT(*) AS count
FROM items
GROUP BY 1
ORDER BY 2 DESC
```

<DataTable
    data={items_per_type} 
/>

# How many items created per month?

```items_per_month
SELECT
    COUNT(*) AS count,
    DATE_FORMAT(FROM_UNIXTIME(time), '%Y-%m-01') AS date
FROM items
GROUP BY 2
ORDER BY 2 ASC;
```
<LineChart data = {items_per_month} y=count x=date  />

# How many stories created per month?

```stories_per_month
SELECT
    COUNT(*) AS count,
    DATE_FORMAT(FROM_UNIXTIME(time), '%Y-%m-01') AS date
FROM items
WHERE type = 'story'
GROUP BY 2
ORDER BY 2 ASC;
```
<LineChart data = {stories_per_month} y=count x=date  />

# How many comments created per month?

```comments_per_month
SELECT
    COUNT(*) AS count,
    DATE_FORMAT(FROM_UNIXTIME(time), '%Y-%m-01') AS date
FROM items
WHERE type = 'comment'
GROUP BY 2
ORDER BY 2 ASC;
```
<LineChart data = {comments_per_month} y=count x=date  />


# How many URL stories created per month?

```url_stories_per_month
SELECT
    COUNT(*) AS count,
    DATE_FORMAT(FROM_UNIXTIME(time), '%Y-%m-01') AS date
FROM items
WHERE type = 'story' AND url IS NOT NULL
GROUP BY 2
ORDER BY 2 ASC;
```
<LineChart data = {url_stories_per_month} y=count x=date  />

# How many text stories created per month?

```text_stories_per_month
SELECT
    COUNT(*) AS count,
    DATE_FORMAT(FROM_UNIXTIME(time), '%Y-%m-01') AS date
FROM items
WHERE type = 'story' AND url IS NULL
GROUP BY 2
ORDER BY 2 ASC;
```
<LineChart data = {text_stories_per_month} y=count x=date  />

# How many dead stories created per month?

```dead_stories_per_month
SELECT
    COUNT(*) AS count,
    DATE_FORMAT(FROM_UNIXTIME(time), '%Y-%m-01') AS date
FROM items
WHERE type = 'story' AND dead = 1
GROUP BY 2
ORDER BY 2 ASC;
```
<LineChart data = {dead_stories_per_month} y=count x=date  />