-- 1. Show how many medal counts present for entire data
select medal, count(medal) as medalcount
from olympics1
where medal <> 'Nomedal'
group by medal;
![image](https://github.com/seema95/seema95/assets/165120254/5f8932b4-6de9-456a-9d6e-92346e23f7db)

 
-- 2. Show count of unique sports present in Olympics1
select Sport, count(distinct(Sport)) from olympics1
group by Sport;
 
-- 3. Show how many different medals won by team India
select Team, medal, count(medal) as medalcount
from olympics1
where Team= 'India' AND medal <> 'Nomedal'
group by Team, medal;
 

-- 4. Show event wise medals won by India show from highest to lowest medals won in order
select Team, Event, medal, count(medal) as medalcount
from olympics1
where Team = 'India' AND medal <> 'Nomedal'
group by Team, Event, medal
order by medalcount desc;
 
-- 5. Show event wise medals won by India in order of year
select event, year,medal, Team from olympics1
where Team='India' AND Medal <> 'Nomedal'
group by event, year, medal
order by Year;
 
-- 6. show country who won maximum medals.
select Team, medal, count(medal) as medalcount
from olympics1
where medal <> 'Nomedal'
group by Team,medal
order by medalcount desc;
 
-- 7.show top 10 countries whowon gold
select Team, medal, count(medal) as medalcount
from olympics1
where medal = 'Gold'
group by Team, medal
order by medalcount desc
limit 10;
 
--  8. show in which year did United states won most gold medal
select Team, year, medal, count(medal) as medalcount from olympics1
where Team='United States' AND medal = 'Gold'
group by year, medal
order by medalcount desc;
 


-- 9. In which sports United States has most medals.
select Team,Sport,Medal, count(medal) as medalcount from olympics1
where Team='United States' AND Medal <> 'Nomedal'
group by Team, Sport, Medal
order by medalcount desc;
 
-- 10. Find top three players who won most medals along with their sports and country
select name,sport,team, count(medal) as medalcount from olympics1
where Medal <> 'Nomedal'
group by name,sport,medal,team
order by medalcount desc
limit 3;
 






-- 11. Find player with most gold medals in cycling along with his country.
select name, medal ,sport,Team, count(medal) as medalcount from olympics1
where sport='Cycling' AND medal = 'Gold'
group by name, medal ,sport,Team
order by medalcount desc
limit 1;
 

-- 12.Find player with most medals (Gold+Silver+Bronze) in Basketball also show his country.
select Team,name, sport,medal, count(medal) as medalcount from olympics1
where sport= 'basketball' and medal <> 'Nomedal'
group by Team,name, sport,medal
order by medalcount desc;
 
-- 13. Find out the count of different medals of the top basketball player Teresa Edwards
select name, sport,medal, count(medal) from olympics1
where sport= 'basketball' and name='Teresa Edwards'
group by name, sport,medal;
 

-- 14. Find out medals won by male,female each year , Export this data and plot graph in excel
select Sex, year, medal, count(medal) from olympics1
where Medal <> 'Nomedal'
group by sex, year, medal
order by sex, year, medal;
 

