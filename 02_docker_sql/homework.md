Question 1. Docker tags
--rm

Question 2. Docker run: version of wheel
0.42.0

Question 3. Count records
15612

select count(*) from green_trip_data 
where lpep_pickup_datetime >= '2019-09-18 00:00:00' 
and lpep_dropoff_datetime <= '2019-09-18 23:59:59';

Question 4. Longest trip for each day
2019-09-26

select DATE(lpep_pickup_datetime) as data_viagem, max(trip_distance) as distancia
from green_trip_data
group by data_viagem
order by distancia desc;

Question 5. Three biggest pick up Boroughs

select z."Borough" as local_inicial, sum(total_amount) as total
from green_trip_data as g, zones as z
where DATE(lpep_pickup_datetime)='2019-09-18'
and g."PULocationID"=z."LocationID"
group by local_inicial
order by sum(total_amount) desc;

"Brooklyn"	96333.24000000028
"Manhattan"	92271.29999999944
"Queens"	78671.70999999956

Question 6. Largest tip
select g."DOLocationID" as drop_off_zone, max(g.tip_amount)
from green_trip_data as g, zones as z
where DATE(lpep_pickup_datetime)>='2019-09-01' 
and DATE(lpep_pickup_datetime)<='2019-09-30'
and z."Zone"='Astoria'
and g."PULocationID"=z."LocationID"
group by drop_off_zone
order by max(g.tip_amount) desc;

select * from zones where "LocationID"=132;

131	132	"Queens"	"JFK Airport"	"Airports"

