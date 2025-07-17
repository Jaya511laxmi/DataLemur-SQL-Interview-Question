## Q1 – Histogram of Tweets Twitter SQL Interview Question
```sql
SELECT 
  tweets_num 	 AS tweet_bucket, 
  COUNT(user_id) AS users_num 
FROM (
    SELECT 
      user_id, 
      COUNT(tweet_id) AS tweets_num 
    FROM tweets 
    WHERE tweet_date BETWEEN '2022-01-01' AND '2022-12-31' 
    GROUP BY user_id
) AS total_tweets 
GROUP BY tweets_num;



## Q2 – Data Science Skills (LinkedIn SQL Interview Question)

```sql
SELECT
  candidate_id
FROM candidates
WHERE 
  skill IN ('Python', 'Tableau', 'PostgreSQL')
GROUP BY candidate_id
HAVING COUNT(DISTINCT skill) = 3
ORDER BY candidate_id ASC;

## Q3 – Page With No Likes Facebook SQL Interview Question
```sql
SELECT pg.page_id
FROM pages pg
LEFT OUTER JOIN page_likes pl 
ON pg.page_id = pl.page_id
WHERE pl.page_id IS NULL
ORDER BY pg.page_id;


## Q4 - Unfinished Parts Tesla SQL Interview Question
```sql
SELECT DISTINCT part, assembly_step
FROM parts_assembly
WHERE finish_date IS NULL;
