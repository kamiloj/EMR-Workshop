## Consultas básicas:

- Para encontrar el número total de registros en la tabla:
```
SELECT COUNT(*) FROM ny_taxi_test;
```
- Para encontrar el número total de viajes realizados por cada proveedor de servicios (vendor_id):

```
SELECT vendor_id, COUNT(*) AS total_trips
FROM ny_taxi_test
GROUP BY vendor_id;
```
- Para encontrar la cantidad promedio de pasajeros por viaje:

```
SELECT AVG(passenger_count) AS average_passengers
FROM ny_taxi_test;
```
## Consultas de filtrado y ordenamiento:

- Para encontrar todos los viajes en los que la distancia del viaje (trip_distance) sea mayor a 10 millas:

```
SELECT *
FROM ny_taxi_test
WHERE trip_distance > 10;
```
- Para encontrar los viajes que tuvieron una propina (tip_amount) mayor a $5 y ordenar los resultados por la cantidad de propina de forma descendente:

```
SELECT *
FROM ny_taxi_test
WHERE tip_amount > 5
ORDER BY tip_amount DESC;
```
- Para encontrar los viajes que tuvieron un pago en efectivo (payment_type = 2) y ordenar los resultados por la tarifa (fare_amount) de forma ascendente:

```
SELECT *
FROM ny_taxi_test
WHERE payment_type = 2
ORDER BY fare_amount ASC;
```

## Consultas de agrupamiento y agregación:

- Para encontrar el total de ingresos generados por cada proveedor de servicios (vendor_id):

```
SELECT vendor_id, SUM(total_amount) AS total_income
FROM ny_taxi_test
GROUP BY vendor_id;
```
- Para encontrar la distancia promedio de viaje y la tarifa promedio por cada proveedor de servicios:

```
SELECT vendor_id, AVG(trip_distance) AS average_distance, AVG(fare_amount) AS average_fare
FROM ny_taxi_test
GROUP BY vendor_id;
```

- Para encontrar el número de viajes realizados por día de la semana y ordenar los resultados por el número de viajes de forma descendente:

```
SELECT DAYOFWEEK(lpep_pickup_datetime) AS day_of_week, COUNT(*) AS total_trips
FROM ny_taxi_test
GROUP BY DAYOFWEEK(lpep_pickup_datetime)
ORDER BY total_trips DESC;
```

## Consultas avanzadas:

Para encontrar los cinco proveedores de servicios principales (vendor_id) en función del ingreso total:

```
SELECT vendor_id, SUM(total_amount) AS total_income
FROM ny_taxi_test
GROUP BY vendor_id
ORDER BY total_income DESC
LIMIT 5;
```

- Para encontrar la tarifa promedio por milla (fare_amount / trip_distance) para cada proveedor de servicios y clasificarlos de forma ascendente:
```
SELECT vendor_id, AVG(fare_amount / trip_distance) AS fare_per_mile
FROM ny_taxi_test
GROUP BY vendor_id
ORDER BY fare_per_mile ASC;
```

- Para los días con los mayores ingresos
```
SELECT lpep_pickup_datetime, SUM(total_amount) AS total_income
FROM ny_taxi_test
GROUP BY lpep_pickup_datetime
ORDER BY total_income DESC
LIMIT 5; 
```

- Para los días con los menores ingresos
```
SELECT lpep_pickup_datetime, SUM(total_amount) AS total_income
FROM ny_taxi_test
GROUP BY lpep_pickup_datetime
ORDER BY total_income ASC
LIMIT 5; 
```
