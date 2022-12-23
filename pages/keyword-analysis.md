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


# how many times is React mentioned on hackernews

```react_per_month
SELECT
    COUNT(*) AS count,
    DATE_FORMAT(FROM_UNIXTIME(time), '%Y-%m-01') AS date
FROM items
WHERE LOWER(url) LIKE '% react %' OR LOWER(title) LIKE '% react %' OR LOWER(text) LIKE '% react %'
GROUP BY 2
ORDER BY 2 ASC;
```
<LineChart data = {react_per_month} y=count x=date  />

# how many times is Vue mentioned on hackernews

```vue_per_month
SELECT
    COUNT(*) AS count,
    DATE_FORMAT(FROM_UNIXTIME(time), '%Y-%m-01') AS date
FROM items
WHERE LOWER(url) LIKE '% vue %' OR LOWER(title) LIKE '% vue %' OR LOWER(text) LIKE '% vue %'
GROUP BY 2
ORDER BY 2 ASC;
```
<LineChart data = {vue_per_month} y=count x=date  />


# how many times is Pytorch mentioned on hackernews

```pytorch_per_month
SELECT
    COUNT(*) AS count,
    DATE_FORMAT(FROM_UNIXTIME(time), '%Y-%m-01') AS date
FROM items
WHERE LOWER(url) LIKE '% pytorch %' OR LOWER(title) LIKE '% pytorch %' OR LOWER(text) LIKE '% pytorch %'
GROUP BY 2
ORDER BY 2 ASC;
```
<LineChart data = {pytorch_per_month} y=count x=date  />


# how many times is tensorflow mentioned on hackernews

```tensorflow_per_month
SELECT
    COUNT(*) AS count,
    DATE_FORMAT(FROM_UNIXTIME(time), '%Y-%m-01') AS date
FROM items
WHERE LOWER(url) LIKE '% tensorflow %' OR LOWER(title) LIKE '% tensorflow %' OR LOWER(text) LIKE '% tensorflow %'
GROUP BY 2
ORDER BY 2 ASC;
```
<LineChart data = {tensorflow_per_month} y=count x=date  />

# how many times is Serverless mentioned on hackernews

```serverless_per_month
SELECT
    COUNT(*) AS count,
    DATE_FORMAT(FROM_UNIXTIME(time), '%Y-%m-01') AS date
FROM items
WHERE LOWER(url) LIKE '%serverless%' OR LOWER(title) LIKE '%serverless%' OR LOWER(text) LIKE '%serverless%'
GROUP BY 2
ORDER BY 2 ASC;
```
<LineChart data = {serverless_per_month} y=count x=date  />

# how many times is Web3 mentioned on hackernews

```web3_per_month
SELECT
    COUNT(*) AS count,
    DATE_FORMAT(FROM_UNIXTIME(time), '%Y-%m-01') AS date
FROM items
WHERE LOWER(url) LIKE '%web3%' OR LOWER(title) LIKE '%web3%' OR LOWER(text) LIKE '%web3%'
GROUP BY 2
ORDER BY 2 ASC;
```
<LineChart data = {web3_per_month} y=count x=date  />