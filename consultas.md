## Consultas básicas:

- Encuentra el número total de registros en la tabla.
- Encuentra el número total de viajes realizados por cada proveedor de servicios (vendor_id).
- Encuentra la cantidad promedio de pasajeros por viaje.

## Consultas de filtrado y ordenamiento:

- Encuentra todos los viajes en los que la distancia del viaje (trip_distance) sea mayor a 10 millas.
- Encuentra los viajes que tuvieron una propina (tip_amount) mayor a $5 y ordena los resultados por la cantidad de propina de forma descendente.
- Encuentra los viajes que tuvieron un pago en efectivo (payment_type = 2) y ordena los resultados por la tarifa (fare_amount) de forma ascendente.

## Consultas de agrupamiento y agregación:

- Encuentra el total de ingresos generados por cada proveedor de servicios (vendor_id).
- Encuentra la distancia promedio de viaje y la tarifa promedio por cada proveedor de servicios.
- Encuentra el número de viajes realizados por día de la semana y ordena los resultados por el número de viajes de forma descendente.

##Consultas de unión:

Crea una nueva tabla en Hive que contenga información adicional sobre las ubicaciones (pu_location_id y do_location_id) utilizando datos externos.
Une la tabla "ny_taxi_test" con la tabla de ubicaciones basándote en los campos de ubicación y encuentra los viajes que tienen una ubicación de recogida y entrega en el mismo condado.
Consultas avanzadas:

Encuentra los cinco proveedores de servicios principales (vendor_id) en función del ingreso total.
Encuentra la tarifa promedio por milla (fare_amount / trip_distance) para cada proveedor de servicios y clasifícalos de forma ascendente.
Encuentra los días con los mayores ingresos totales y los días con los menores ingresos totales.
