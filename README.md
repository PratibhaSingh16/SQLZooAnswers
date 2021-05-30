# SQLZooAnswers
# This repository contains answers of all the SQL queries from https://sqlzoo.net/wiki/SELECT_from_Nobel_Tutorial


``1. Winners from 1950``


SELECT yr, subject, winner
  FROM nobel
 WHERE yr = 1950
 
 
 ``2. Show who won the 1962 prize for Literature.``
 
 SELECT winner
  FROM nobel
 WHERE yr = 1962
   AND subject = 'Literature'
   
   ``3. Show the year and subject that won 'Albert Einstein' his prize.``
   
   select yr, subject
from nobel
where winner = 'Albert Einstein'

``4. Give the name of the 'Peace' winners since the year 2000, including 2000.``

select winner
from nobel
where subject = 'Peace' and yr >= '2000'

``5. Show all details (yr, subject, winner) of the Literature prize winners for 1980 to 1989 inclusive.``

select yr, subject, winner
from nobel
where subject = 'Literature' and yr >= '1980' and yr <= '1989'

``6. Show all details of the presidential winners:``

* Theodore Roosevelt
* Woodrow Wilson
* Jimmy Carter
* Barack Obama

SELECT yr, subject, winner
FROM nobel
WHERE subject = 'Peace' and winner = 'Theodore Roosevelt' or winner = 'Woodrow Wilson' or winner = 'Jimmy Carter' or winner = 'Barack Obama'


``7. Show the winners with first name John``

SELECT winner
FROM nobel
where winner like 'John%'


``8.  Show the year, subject, and name of Physics winners for 1980 together with the Chemistry winners for 1984.``

select yr, subject, winner
from nobel 
where subject = 'Physics' and yr = '1980' or subject = 'Chemistry' and yr = '1984'

``9. Show the year, subject, and name of winners for 1980 excluding Chemistry and Medicine``

select yr, subject, winner
from nobel
where yr = '1980' and subject not in('Chemistry','Medicine')

``10. Show year, subject, and name of people who won a 'Medicine' prize in an early year (before 1910, not including 1910) together with winners of a 'Literature' prize in a later year (after 2004, including 2004)``

select yr, subject, winner
from nobel
where subject = 'Medicine' and yr < '1910' or subject = 'Literature' and yr >= '2004'

``11. Find all details of the prize won by PETER GRÜNBERG``

select *
from nobel
Where winner = 'PETER GRÜNBERG'

``12. Find all details of the prize won by EUGENE O'NEILL``

select *
from nobel
Where winner like 'EUGENE O%'

``13. List the winners, year and subject where the winner starts with Sir. Show the the most recent first, then by name order.``

select winner, yr, subject
from nobel
where winner like 'Sir%'
order by Yr desc, winner

``14. Show the 1984 winners and subject ordered by subject and winner name; but list Chemistry and Physics last.``

select winner, subject
from nobel
where yr = '1984'
order by ( case subject
           when 'Chemistry' then 1
           when 'Physics'   then 2
           else 0
           end), subject, winner






















