# codeacademysqlproject1
World Populations SQL Practice

select SUM(population_years.population) as 'totalpop', countries.continent from population_years
JOIN countries ON
  population_years.country_id = countries.id
WHERE countries.continent LIKE "%oceania%"
AND population_years.year = 2005;

select ROUND(AVG(population_years.population),0) AS 'avgpop', countries.continent
from population_years
JOIN countries ON
population_years.country_id = countries.id
WHERE population_years.year = 2003 AND countries.continent = "South America";

select SUM(population_years.population) as 'totalpop', countries.name, countries.continent  from population_years
JOIN countries ON
  population_years.country_id = countries.id
WHERE population_years.year = 2007
GROUP BY countries.name
ORDER BY totalpop ASC
LIMIT 2;

select MIN(population_years.population) as 'minpop', countries.name, countries.continent  from population_years
JOIN countries ON
  population_years.country_id = countries.id
WHERE population_years.year = 2007;

select ROUND(AVG(population_years.population),0) AS 'polavgpop' from population_years
JOIN countries ON
  population_years.country_id = countries.id
WHERE countries.name LIKE "%poland%";

select COUNT(population_years.id) as 'numtot', countries.name from population_years
JOIN countries ON population_years.country_id = countries.id
WHERE countries.name LIKE '%the'
GROUP BY 2 ORDER BY 1;

select SUM(population_years.population) as 'totsum', countries.continent from population_years
JOIN countries ON population_years.country_id = countries.id
WHERE population_years.year = 2010
GROUP by countries.continent
ORDER by totsum DESC;
