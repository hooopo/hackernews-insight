
# Most Shared Website Domains

```top_domain
SELECT 
  Substring_index(Substring_index(Substring_index(Substring_index(url, '/', 3), '://', -1), '/', 1), '?', 1) AS domain,
  Count(*) as count
FROM   hackernews
WHERE  url IS NOT NULL
GROUP  BY 1
ORDER  BY 2 DESC
LIMIT  20
```

<DataTable
    data={top_domain} 
    rows=20
    rowNumbers=false
/>

# The number of github website is shared per month 

```github_stories_per_month
SELECT 
  count(*) as count, 
  DATE_FORMAT(FROM_UNIXTIME(time), '%Y-%m-01') as date 
FROM hackernews 
WHERE type = 'story' and url like '%github.com%'
GROUP BY 2 
ORDER BY 2 ASC;
```
<LineChart data = {github_stories_per_month} y=count x=date  />