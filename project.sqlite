-- find the most popular Hacker News stories
SELECT title, score
FROM hacker_news
ORDER BY score DESC
LIMIT 5;

-- find the total score of all the stories
SELECT SUM(score)
FROM hacker_news;

-- pinpoint the users who have accumulated a lot of points across their stories
SELECT user, SUM(score)
FROM hacker_news
GROUP BY user
HAVING SUM(score) > 200
ORDER BY 2 DESC;

-- add these users’ scores together and divide by the total to get the percentage
SELECT (517 + 309 + 304 + 282) / 6366.0;

-- how many times has each offending user posted this link
SELECT user, COUNT(*)
FROM hacker_news
WHERE url LIKE "https://www.youtube.com/watch?v=dQw4w9WgXcQ"
GROUP BY user
ORDER BY COUNT(*) DESC;

-- how many times has each offending user posted this link
SELECT user, COUNT(*)
FROM hacker_news
WHERE url LIKE "https://www.youtube.com/watch?v=dQw4w9WgXcQ"
GROUP BY user
ORDER BY COUNT(*) DESC;

-- which of these sites feed Hacker News the most
SELECT CASE
    WHEN url LIKE "%github.com%" THEN "GitHub"
    WHEN url LIKE "%medium.com%" THEN "Medium"
    WHEN url LIKE "%nytimes.com%" THEN "New York Times"
    ELSE "Other"
    END AS 'Source'
FROM hacker_news;

-- What’s the best time of the day to post a story on Hacker News
SELECT timestamp
FROM hacker_news
LIMIT 10;

-- returns the hour, HH, of the timestamp column
SELECT strftime('%H', timestamp) AS "Hour",
-- average score for each hour
      ROUND(AVG(score),1) AS 'Average Score',
-- count of stories for each hour
      COUNT(*) AS 'Number of Stories'
FROM hacker_news
WHERE timestamp IS NOT NULL
GROUP BY 1
ORDER BY 2 DESC;
