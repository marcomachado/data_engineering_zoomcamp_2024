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
(not finished)
select "DOLocationID" as local_inicial, sum(total_amount) as total
from green_trip_data
where DATE(lpep_pickup_datetime)='2019-09-18'
group by local_inicial
order by total desc

74, 75, 166

Question 6. Largest tip
(not finished)

