# Stories with most comments

```with_most_comments
select id,
  title, 
  score, 
  `by`, 
  descendants,
  DATE_FORMAT(FROM_UNIXTIME(time), '%Y-%m-%d') as date 
from items 
where type = 'story' and deleted = 0 and dead = 0
order by descendants desc 
limit 20;
```
{#each with_most_comments as item}

* [{item.title}](https://news.ycombinator.com/item?id={item.id}) {item.date} 💬 {item.descendants} by [{item.by}](https://news.ycombinator.com/user?id={item.by})

{/each}

# Stories with most comments in 2022

```with_most_comments_2022
select id,
  title, 
  score, 
  `by`, 
  descendants,
  DATE_FORMAT(FROM_UNIXTIME(time), '%Y-%m-%d') as date 
from items 
where type = 'story' and deleted = 0 and dead = 0 and DATE_FORMAT(FROM_UNIXTIME(time), '%Y') = '2022'
order by descendants desc 
limit 20;
```
{#each with_most_comments_2022 as item}

* [{item.title}](https://news.ycombinator.com/item?id={item.id}) {item.date} 💬 {item.descendants} by [{item.by}](https://news.ycombinator.com/user?id={item.by})

{/each}

# Stories with most comments in 2021

```with_most_comments_2021
select id,
  title, 
  score, 
  `by`, 
  descendants,
  DATE_FORMAT(FROM_UNIXTIME(time), '%Y-%m-%d') as date 
from items 
where type = 'story' and deleted = 0 and dead = 0 and DATE_FORMAT(FROM_UNIXTIME(time), '%Y') = '2021'
order by descendants desc 
limit 20;
```
{#each with_most_comments_2021 as item}

* [{item.title}](https://news.ycombinator.com/item?id={item.id}) {item.date} 💬 {item.descendants} by [{item.by}](https://news.ycombinator.com/user?id={item.by})

{/each}

# Stories with most comments in 2020

```with_most_comments_2020
select id,
  title, 
  score, 
  `by`, 
  descendants,
  DATE_FORMAT(FROM_UNIXTIME(time), '%Y-%m-%d') as date 
from items 
where type = 'story' and deleted = 0 and dead = 0 and DATE_FORMAT(FROM_UNIXTIME(time), '%Y') = '2020'
order by descendants desc 
limit 20;
```
{#each with_most_comments_2020 as item}

* [{item.title}](https://news.ycombinator.com/item?id={item.id}) {item.date} 💬 {item.descendants} by [{item.by}](https://news.ycombinator.com/user?id={item.by})

{/each}

# Stories with most comments in 2019

```with_most_comments_2019
select id,
  title, 
  score, 
  `by`, 
  descendants,
  DATE_FORMAT(FROM_UNIXTIME(time), '%Y-%m-%d') as date 
from items 
where type = 'story' and deleted = 0 and dead = 0 and DATE_FORMAT(FROM_UNIXTIME(time), '%Y') = '2019'
order by descendants desc 
limit 20;
```
{#each with_most_comments_2019 as item}

* [{item.title}](https://news.ycombinator.com/item?id={item.id}) {item.date} 💬 {item.descendants} by [{item.by}](https://news.ycombinator.com/user?id={item.by})

{/each}