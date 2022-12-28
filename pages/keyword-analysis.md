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
    sum(lower(concat_ws(' ', title, url, text)) regexp '\\bweb3\\b') AS count,
    DATE_FORMAT(FROM_UNIXTIME(time), '%Y-%m-01') AS date
FROM items
WHERE dead = 0 and deleted = 0
GROUP BY 2
ORDER BY 2 ASC;
```
<LineChart data = {web3_per_month} y=count x=date  />


```hadoop_vs_sql
SELECT
    sum(lower(concat_ws(' ', title, url, text)) regexp '\\bsql\\b') AS sql_cnt,
    sum(lower(concat_ws(' ', title, url, text)) regexp '\\bhadoop\\b') AS hadoop_cnt,
    DATE_FORMAT(FROM_UNIXTIME(time), '%Y-%m-01') AS date
FROM items
WHERE dead = 0 and deleted = 0
GROUP BY 3
ORDER BY 3 ASC;
```

<LineChart data = {hadoop_vs_sql} y={["sql_cnt", "hadoop_cnt"]} x=date  />


```k8s_vs_docker
SELECT
    sum(lower(concat_ws(' ', title, url, text)) regexp '\\bk8s\\b|\\bkubernetes\\b') AS k8s_cnt,
    sum(lower(concat_ws(' ', title, url, text)) regexp '\\bdocker\\b') AS docker_cnt,
    DATE_FORMAT(FROM_UNIXTIME(time), '%Y-%m-01') AS date
FROM items
WHERE dead = 0 and deleted = 0
GROUP BY 3
ORDER BY 3 ASC;
```
<LineChart data = {k8s_vs_docker} y={["k8s_cnt", "docker_cnt"]} x=date  />

```mysql_vs_postgres
SELECT
    sum(lower(concat_ws(' ', title, url, text)) regexp '\\bmysql\\b') AS mysql_cnt,
    sum(lower(concat_ws(' ', title, url, text)) regexp '\\bpostgres\\b|\\bpostgresql\\b') AS pg_cnt,
    sum(lower(concat_ws(' ', title, url, text)) regexp '\\bmongodb\\b') AS mongo_cnt,
    DATE_FORMAT(FROM_UNIXTIME(time), '%Y-%m-01') AS date
FROM items
WHERE dead = 0 and deleted = 0
GROUP BY 4
ORDER BY 4 ASC;
```

<LineChart data = {mysql_vs_postgres} y={["mysql_cnt", "pg_cnt", "mongo_cnt"]} x=date  />


# how many times is hn.algolia.com mentioned?

```hn_algolia_per_month
SELECT
    SUM(
      LOWER(
        CONCAT_WS(' ', title, url, text)
      ) REGEXP 'hn.algolia.com'
    ) AS count,
    DATE_FORMAT(FROM_UNIXTIME(time), '%Y-%m-01') AS date
FROM items
WHERE dead = 0 AND deleted = 0
GROUP BY 2
ORDER BY 2 ASC;
```
<LineChart data = {hn_algolia_per_month} y=count x=date  />

# how many times is metaverse mentioned?

```metaverse_per_month
SELECT
    SUM(
      LOWER(
        CONCAT_WS(' ', title, url, text)
      ) REGEXP 'metaverse'
    ) AS count,
    DATE_FORMAT(FROM_UNIXTIME(time), '%Y-%m-01') AS date
FROM items
WHERE dead = 0 AND deleted = 0
GROUP BY 2
ORDER BY 2 ASC;
```
<LineChart data = {metaverse_per_month} y=count x=date  />
