# Most Shared Website Domains

```top_domain
SELECT
    SUBSTRING_INDEX(SUBSTRING_INDEX(SUBSTRING_INDEX(SUBSTRING_INDEX(url, '/', 3), '://', -1), '/', 1), '?', 1) AS domain,
    COUNT(*) AS count
FROM items
WHERE url IS NOT NULL
GROUP BY 1
ORDER BY 2 DESC
LIMIT 20
```

<DataTable
    data={top_domain} 
    rows=20
    rowNumbers=false
/>

# The number of github website is shared per month

```github_stories_per_month
SELECT
    COUNT(*) AS count,
    DATE_FORMAT(FROM_UNIXTIME(time), '%Y-%m-01') AS date
FROM items
WHERE type = 'story' AND url LIKE '%github.com%'
GROUP BY 2
ORDER BY 2 ASC;
```

<LineChart data = {github_stories_per_month} y=count x=date  />

# What is the TLD(Top Level Domain) that is most used by the shared sites

```top_tld_domain
SELECT
    SUBSTRING_INDEX(
        SUBSTRING_INDEX(SUBSTRING_INDEX(SUBSTRING_INDEX(SUBSTRING_INDEX(url, '/', 3), '://', -1), '/', 1), '?', 1),
        '.',
        -1
    ) AS tld,
    COUNT(*) AS count
FROM items
WHERE url IS NOT NULL
GROUP BY 1
ORDER BY 2 DESC
LIMIT 10
```

<DataTable
    data={top_tld_domain} 
    rows=10
    rowNumbers=false
/>

# What is the TLD(Top Level Domain) that got the most avg score

```avg_score_of_tld_domain
SELECT
    SUBSTRING_INDEX(
        SUBSTRING_INDEX(SUBSTRING_INDEX(SUBSTRING_INDEX(SUBSTRING_INDEX(url, '/', 3), '://', -1), '/', 1), '?', 1),
        '.',
        -1
    ) AS tld,
    AVG(score) AS avg_score,
    COUNT(*)
FROM items
WHERE url IS NOT NULL
GROUP BY 1
HAVING COUNT(*) > 50
ORDER BY 2 DESC
LIMIT 10
```

<DataTable
    data={avg_score_of_tld_domain} 
    rows=10
    rowNumbers=false
/>
