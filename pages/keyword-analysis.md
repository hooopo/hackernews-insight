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


# how many times is ChatGPT mentioned?

```chatgpt_per_month
SELECT
    SUM(
      LOWER(
        CONCAT_WS(' ', title, url, text)
      ) LIKE '%chatgpt%'
    ) AS count,
    DATE_FORMAT(FROM_UNIXTIME(time), '%Y-%m-01') AS date
FROM items
WHERE dead = 0 AND deleted = 0
GROUP BY 2
ORDER BY 2 ASC;
```
<LineChart data = {chatgpt_per_month} y=count x=date  />

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
    sum(lower(concat_ws(' ', title, url, text)) LIKE '%web3%') AS count,
    DATE_FORMAT(FROM_UNIXTIME(time), '%Y-%m-01') AS date
FROM items
WHERE dead = 0 and deleted = 0
GROUP BY 2
ORDER BY 2 ASC;
```
<LineChart data = {web3_per_month} y=count x=date  />


# how many times is Cloud Native mentioned on hackernews

```cloud_native_per_month
SELECT
    sum(lower(concat_ws(' ', title, url, text)) LIKE '%cloud native%') AS count,
    DATE_FORMAT(FROM_UNIXTIME(time), '%Y-%m-01') AS date
FROM items
WHERE dead = 0 and deleted = 0
GROUP BY 2
ORDER BY 2 ASC;
```
<LineChart data = {cloud_native_per_month} y=count x=date  />

# how many times is Database mentioned on hackernews

```database_per_month
SELECT
    sum(lower(concat_ws(' ', title, url, text)) LIKE '%database%') AS count,
    DATE_FORMAT(FROM_UNIXTIME(time), '%Y-%m-01') AS date
FROM items
WHERE dead = 0 and deleted = 0
GROUP BY 2
ORDER BY 2 ASC;
```
<LineChart data = {database_per_month} y=count x=date  />

# how many times is Lowcode mentioned on hackernews

```lowcode_per_month
SELECT
    sum(lower(concat_ws(' ', title, url, text)) LIKE '%lowcode%') AS count,
    DATE_FORMAT(FROM_UNIXTIME(time), '%Y-%m-01') AS date
FROM items
WHERE dead = 0 and deleted = 0
GROUP BY 2
ORDER BY 2 ASC;
```
<LineChart data = {lowcode_per_month} y=count x=date  />


# how many times is AI mentioned on hackernews

```ai_per_month
SELECT
    sum(lower(concat_ws(' ', title, url, text)) LIKE '%artificial intelligence%') AS count,
    DATE_FORMAT(FROM_UNIXTIME(time), '%Y-%m-01') AS date
FROM items
WHERE dead = 0 and deleted = 0
GROUP BY 2
ORDER BY 2 ASC;
```
<LineChart data = {ai_per_month} y=count x=date  />

# how many times is WebAssembly mentioned on hackernews

```webassembly_per_month
SELECT
    sum(lower(concat_ws(' ', title, url, text)) LIKE '%webassembly%') AS count,
    DATE_FORMAT(FROM_UNIXTIME(time), '%Y-%m-01') AS date
FROM items
WHERE dead = 0 and deleted = 0
GROUP BY 2
ORDER BY 2 ASC;
```
<LineChart data = {webassembly_per_month} y=count x=date  />


# how many times is SSG mentioned on hackernews

```ssg_per_month
SELECT
    sum(lower(concat_ws(' ', title, url, text)) LIKE '%ssg%') AS count,
    DATE_FORMAT(FROM_UNIXTIME(time), '%Y-%m-01') AS date
FROM items
WHERE dead = 0 and deleted = 0
GROUP BY 2
ORDER BY 2 ASC;
```
<LineChart data = {ssg_per_month} y=count x=date  />

# how many times is GraphQL mentioned on hackernews

```graphql_per_month
SELECT
    sum(lower(concat_ws(' ', title, url, text)) LIKE '%graphql%') AS count,
    DATE_FORMAT(FROM_UNIXTIME(time), '%Y-%m-01') AS date
FROM items
WHERE dead = 0 and deleted = 0
GROUP BY 2
ORDER BY 2 ASC;
```
<LineChart data = {graphql_per_month} y=count x=date  />


# how many times is hn.algolia.com mentioned?

```hn_algolia_per_month
SELECT
    SUM(
      LOWER(
        CONCAT_WS(' ', title, url, text)
      ) LIKE '%hn.algolia.com%'
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
      ) LIKE '%metaverse%'
    ) AS count,
    DATE_FORMAT(FROM_UNIXTIME(time), '%Y-%m-01') AS date
FROM items
WHERE dead = 0 AND deleted = 0
GROUP BY 2
ORDER BY 2 ASC;
```
<LineChart data = {metaverse_per_month} y=count x=date  />

# how many times is microservice mentioned?

```microservice_per_month
SELECT
    SUM(
      LOWER(
        CONCAT_WS(' ', title, url, text)
      ) LIKE '%microservice%'
    ) AS count,
    DATE_FORMAT(FROM_UNIXTIME(time), '%Y-%m-01') AS date
FROM items
WHERE dead = 0 AND deleted = 0
GROUP BY 2
ORDER BY 2 ASC;
```
<LineChart data = {microservice_per_month} y=count x=date  />

# how many times is vercel mentioned?

```vercel_per_month
SELECT
    SUM(
      LOWER(
        CONCAT_WS(' ', title, url, text)
      ) LIKE '%vercel%'
    ) AS count,
    DATE_FORMAT(FROM_UNIXTIME(time), '%Y-%m-01') AS date
FROM items
WHERE dead = 0 AND deleted = 0
GROUP BY 2
ORDER BY 2 ASC;
```
<LineChart data = {vercel_per_month} y=count x=date  />

# how many times is cloudflare mentioned?

```cloudflare_per_month
SELECT
    SUM(
      LOWER(
        CONCAT_WS(' ', title, url, text)
      ) LIKE '%cloudflare%'
    ) AS count,
    DATE_FORMAT(FROM_UNIXTIME(time), '%Y-%m-01') AS date
FROM items
WHERE dead = 0 AND deleted = 0
GROUP BY 2
ORDER BY 2 ASC;
```
<LineChart data = {cloudflare_per_month} y=count x=date  />


# how many times is planetscale mentioned?

```planetscale_per_month
SELECT
    SUM(
      LOWER(
        CONCAT_WS(' ', title, url, text)
      ) LIKE '%planetscale%'
    ) AS count,
    DATE_FORMAT(FROM_UNIXTIME(time), '%Y-%m-01') AS date
FROM items
WHERE dead = 0 AND deleted = 0
GROUP BY 2
ORDER BY 2 ASC;
```
<LineChart data = {planetscale_per_month} y=count x=date  />

# how many times is edge function mentioned?

```edge_function_per_month
SELECT
    SUM(
      LOWER(
        CONCAT_WS(' ', title, url, text)
      ) LIKE '%edge function%'
    ) AS count,
    DATE_FORMAT(FROM_UNIXTIME(time), '%Y-%m-01') AS date
FROM items
WHERE dead = 0 AND deleted = 0
GROUP BY 2
ORDER BY 2 ASC;
```
<LineChart data = {edge_function_per_month} y=count x=date  />


# how many times is cloudflare workers mentioned?

```cloudflare_workers_per_month
SELECT
    SUM(
      LOWER(
        CONCAT_WS(' ', title, url, text)
      ) LIKE '%cloudflare workers%'
    ) AS count,
    DATE_FORMAT(FROM_UNIXTIME(time), '%Y-%m-01') AS date
FROM items
WHERE dead = 0 AND deleted = 0
GROUP BY 2
ORDER BY 2 ASC;
```
<LineChart data = {cloudflare_workers_per_month} y=count x=date  />

# how many times is drizzle mentioned?

```drizzle_per_month
SELECT
    SUM(
      LOWER(
        CONCAT_WS(' ', title, url, text)
      ) LIKE '%drizzle%'
    ) AS count,
    DATE_FORMAT(FROM_UNIXTIME(time), '%Y-%m-01') AS date
FROM items
WHERE dead = 0 AND deleted = 0
GROUP BY 2
ORDER BY 2 ASC;
```
<LineChart data = {drizzle_per_month} y=count x=date  />

# how many times is prisma mentioned?

```prisma_per_month
SELECT
    SUM(
      LOWER(
        CONCAT_WS(' ', title, url, text)
      ) LIKE '%prisma%'
    ) AS count,
    DATE_FORMAT(FROM_UNIXTIME(time), '%Y-%m-01') AS date
FROM items
WHERE dead = 0 AND deleted = 0
GROUP BY 2
ORDER BY 2 ASC;
```
<LineChart data = {prisma_per_month} y=count x=date  />

# how many times is nextjs mentioned?

```nextjs_per_month
SELECT
    SUM(
      LOWER(
        CONCAT_WS(' ', title, url, text)
      ) LIKE '%nextjs%'
    ) AS count,
    DATE_FORMAT(FROM_UNIXTIME(time), '%Y-%m-01') AS date
FROM items
WHERE dead = 0 AND deleted = 0
GROUP BY 2
ORDER BY 2 ASC;
```
<LineChart data = {nextjs_per_month} y=count x=date  />

# how many times is wordpress mentioned?

```wordpress_per_month
SELECT
    SUM(
      LOWER(
        CONCAT_WS(' ', title, url, text)
      ) LIKE '%wordpress%'
    ) AS count,
    DATE_FORMAT(FROM_UNIXTIME(time), '%Y-%m-01') AS date
FROM items
WHERE dead = 0 AND deleted = 0
GROUP BY 2
ORDER BY 2 ASC;
```
<LineChart data = {wordpress_per_month} y=count x=date  />









