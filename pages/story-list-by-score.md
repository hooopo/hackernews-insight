# Stories with most score

```new_items
select id,
  title, 
  score, 
  `by`,
  DATE_FORMAT(FROM_UNIXTIME(time), '%Y-%m-%d') as date
from items 
where type = 'story' and deleted = 0 and dead = 0
order by score desc 
limit 20;
```
{#each new_items as item}

* [{item.title}](https://news.ycombinator.com/item?id={item.id}) {item.date} ⬆ {item.score} by [{item.by}](https://news.ycombinator.com/user?id={item.by}) 

{/each}


# Stories with most score in 2022

```with_most_score_2022
select id,
  title, 
  score, 
  `by`,
  DATE_FORMAT(FROM_UNIXTIME(time), '%Y-%m-%d') as date
from items 
where type = 'story' and deleted = 0 and dead = 0 and DATE_FORMAT(FROM_UNIXTIME(time), '%Y') = '2022'
order by score desc 
limit 20;
```
{#each with_most_score_2022 as item}

* [{item.title}](https://news.ycombinator.com/item?id={item.id}) {item.date} ⬆ {item.score} by [{item.by}](https://news.ycombinator.com/user?id={item.by}) 

{/each}

# Stories with most score in 2021

```with_most_score_2021
select id,
  title, 
  score, 
  `by`,
  DATE_FORMAT(FROM_UNIXTIME(time), '%Y-%m-%d') as date
from items 
where type = 'story' and deleted = 0 and dead = 0 and DATE_FORMAT(FROM_UNIXTIME(time), '%Y') = '2021'
order by score desc 
limit 20;
```
{#each with_most_score_2021 as item}

* [{item.title}](https://news.ycombinator.com/item?id={item.id}) {item.date} ⬆ {item.score} by [{item.by}](https://news.ycombinator.com/user?id={item.by}) 

{/each}

# Stories with most score in 2020

```with_most_score_2020
select id,
  title, 
  score, 
  `by`,
  DATE_FORMAT(FROM_UNIXTIME(time), '%Y-%m-%d') as date
from items 
where type = 'story' and deleted = 0 and dead = 0 and DATE_FORMAT(FROM_UNIXTIME(time), '%Y') = '2020'
order by score desc 
limit 20;
```
{#each with_most_score_2020 as item}

* [{item.title}](https://news.ycombinator.com/item?id={item.id}) {item.date} ⬆ {item.score} by [{item.by}](https://news.ycombinator.com/user?id={item.by}) 

{/each}

# Stories with most score in 2019

```with_most_score_2019
select id,
  title, 
  score, 
  `by`,
  DATE_FORMAT(FROM_UNIXTIME(time), '%Y-%m-%d') as date
from items 
where type = 'story' and deleted = 0 and dead = 0 and DATE_FORMAT(FROM_UNIXTIME(time), '%Y') = '2019'
order by score desc 
limit 20;
```
{#each with_most_score_2019 as item}

* [{item.title}](https://news.ycombinator.com/item?id={item.id}) {item.date} ⬆ {item.score} by [{item.by}](https://news.ycombinator.com/user?id={item.by}) 

{/each}