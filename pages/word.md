# how many times is SQL mentioned in the title of stories

```sql
select count(*) as cnt
from hackernews
where lower(title) like '%sql%'
```

<BigValue 
    data={sql} 
    value='cnt' 
    title="SQL mentioned in the title of stories"
/> 