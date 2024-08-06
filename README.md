# Power-Bi-and-MySQL-project
Project build using Power Bi and MySql

----------MySQL Workbench Query --------
with bike as (
SELECT * FROM bike_share_yr_0
UNION ALL 
SELECT * FROM bike_share_yr_1)

select 
dteday,
season,
a.yr,
mnth,
hr,
holiday,
weekday,
riders,
rider_type,
price,
COGS,
riders*price as Revenue,
riders*price - COGS*riders as profit
from bike as a
left join cost_table as b
on a.yr = b.yr;
