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