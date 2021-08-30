# Codecademy -- Trends-in-Startups

/*checking how many columns are in the file*/
select * from startups;
/*There are 10 columns in this file*/

/*calculate the total number of companies in the table*/
select count(*) from startups;

/*calculate the sum of the valuation column*/
select sum(valuation) 
from starups;

/*return the maximum amount of money based on raised column*/
select max(raised) from startups;

/*return the maximum amount of money raised during seed stage*/
select max(raised) from startups
where stage = 'Seed';

/*the oldest year on the founded list*/
select min(founded) from startups;

/*return the average valuation*/
select avg(valuation)
from startups;

/*return the average valuation in each category*/
select category, avg(valuation) 
from startups
group by category;

/*return the average valuation in each category - round the averages to two decimal places*/
select category, round(avg(valuation), 2)
from startups
group by category;

/*return the average valuation in each category - round the average to two decimal places and order the list from highest averages to lowest*/
select category, round(avg(valuation), 2)
from startups
group by 1
order by 2 desc;

/*return the name of each category with the total number of companies that belong to it*/
select category, count(*)
from startups
group by category;

/*filter the result to include only categories that have more than three companies*/
select category, count(*)
from startups
group by category
having count(*) > 3;

/*average size of a startup in each location*/
select location, avg(employees)
from startups
group by location;

/*average size of a startup in each location, sizes above 500*/
select location, avg(employees)
from startups
group by location
having avg(employees) > 500;
