### Visualizacion de datos
- Muestra una muestra de los registros cargados utilizando DUMP:

```
DUMP NY_TAXI;
````

### Transformaciones básicas:

- Filtra los registros que cumplan con cierta condición utilizando el operador FILTER:
```
filtered_data = FILTER NY_TAXI BY trip_distance > 10;
DUMP filtered_data;
```

- Proyecta solo las columnas necesarias utilizando el operador FOREACH:

```
projected_data = FOREACH NY_TAXI GENERATE vendor_id, lpep_pickup_datetime, trip_distance;
DUMP projected_data;
```
- Agrupa los registros por una columna específica utilizando el operador GROUP:

```
grouped_data = GROUP NY_TAXI BY vendor_id;
DUMP grouped_data;
```

### Operaciones de agregación:

- Calcula el promedio, la suma, el máximo o el mínimo de una columna utilizando operadores de agregación como AVG, SUM, MAX, MIN, etc. Por ejemplo, para calcular el promedio de la distancia de viaje (trip_distance) por proveedor (vendor_id):
```
avg_distance_by_vendor = FOREACH grouped_data GENERATE group AS vendor_id, AVG(NY_TAXI.trip_distance) AS average_distance;
DUMP avg_distance_by_vendor;
```

Aplica funciones de filtrado y transformación avanzadas utilizando expresiones regulares, funciones de cadena, funciones de fecha y hora, etc. Por ejemplo, para filtrar los registros que cumplan con cierta condición utilizando una expresión regular en la columna "lpep_pickup_datetime":
```
filtered_data = FILTER NY_TAXI BY lpep_pickup_datetime MATCHES '2019-.*';
DUMP filtered_data;
```
