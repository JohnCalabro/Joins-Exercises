
# PART 1:

# 1:

SELECT * FROM owners
FULL OUTER JOIN vehicles
ON owners.id = vehicles.owner_id;

# 2: 

SELECT first_name, last_name, 
COUNT(owner_id) FROM owners
JOIN vehicles  ON  owners.id= vehicles.owner_id 
GROUP BY (first_name, last_name)
ORDER BY first_name;


# 3:

SELECT first_name, last_name,
COUNT(owner_id) AS count, AVG(price) AS average FROM owners
JOIN vehicles ON owners.id = vehicles.owner_id
GROUP BY (first_name, last_name) 
HAVING COUNT(owner_id) > 1 AND AVG(price) > 10000 
ORDER BY first_name DESC;


# SQL ZOO

# Tutorial 6

# 1

SELECT matchid, player FROM goal 
  WHERE teamid = 'GER'

# 2:

SELECT id,stadium,team1,team2
  FROM game WHERE id = 1012;

# 3:
SELECT player, teamid, stadium, mdate
  FROM game JOIN goal ON (id=matchid)
WHERE teamid = 'GER'

# 4:

SELECT team1, team2, player FROM game JOIN goal ON id=matchid
WHERE player LIKE 'Mario%'

# 5:

SELECT player, teamid, coach, gtime
  FROM goal JOIN eteam on teamid=id
 WHERE gtime<=10

# 6:

SELECT mdate, teamname FROM
game JOIN eteam ON (team1 = eteam.id)
WHERE coach = 'Fernando Santos'

# 7:

SELECT player FROM game 
JOIN goal ON matchid = id
WHERE stadium = 'National Stadium, Warsaw'

# 8:

SELECT DISTINCT player FROM 
game JOIN goal ON (id = matchid)
WHERE (team1 = 'GER' OR team2 = 'GER') 
AND teamid <> 'GER' 


# 9:

SELECT teamname, COUNT(teamid) FROM 
goal JOIN eteam ON (teamid = id)
GROUP BY teamname

# 10:

SELECT stadium, COUNT(*) FROM
game JOIN goal ON (id = matchid)
GROUP BY stadium

# 11:

SELECT matchid, mdate, COUNT(*) FROM
	game JOIN goal ON (id = matchid)
	WHERE team1 = 'POL' OR team2 = 'POL'
	GROUP BY matchid, mdate 
# 12:

SELECT matchid, mdate, COUNT (*)
FROM game JOIN goal ON (id = matchid)
WHERE teamid = 'GER'
GROUP BY matchid, mdate

# 13: 
couldn’t understand it. 


# Tutorial 7

# 1:
SELECT id, title, yr
 FROM movie
 WHERE yr=1962

# 2:

SELECT yr FROM movie
WHERE title = 'Citizen Kane'

# 3:

SELECT id, title, yr FROM movie
WHERE title LIKE '%Star Trek%'
ORDER BY YR

# 4:

SELECT id FROM actor
WHERE name =  'Glenn Close'

# 5:

SELECT id FROM movie
WHERE title = 'Casablanca'

# 6:

SELECT name FROM actor
JOIN casting ON casting.actorid = id
WHERE casting.movieid = 27

# 7:

SELECT name FROM actor
JOIN casting ON casting.actorid = id
WHERE casting.movieid = 35

# 8:

SELECT title
FROM movie
JOIN casting
ON movieid = id
JOIN actor
ON actor.id = actorid
WHERE name = 'Harrison Ford';

# 9:

SELECT title
FROM movie
JOIN casting
ON movieid = id
JOIN actor
ON actor.id = actorid
WHERE name = 'Harrison Ford'
AND ord <> 1

# 10:

SELECT title, name
FROM movie
JOIN casting
ON movieid = id
JOIN actor
ON actor.id = actorid
WHERE yr = 1962
AND ord = 1





 