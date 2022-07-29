# Trabajo Final. Análisis de Datos

## Informe Entrega 2

### Alumnos:

###  Domenje, Carlos R.

###  Fux, Santiago.

---

## DATASET: Uso de Taxis Yellow Cab en USA en el año 2020

**Problema.** La pregunta a responder es:

1. ¿Existe una manera de caracterizar los lugares más recurrentes para inicio / fin de viaje?


## Análisis de Datos

Consideraciones sobre las columnas. 

- La columna Vendor ID es una variable categórica que puede tener el valor 1 o 2 dependiendo del fabricante del equipo. Esta información no es relevante para el análisis que queremos hacer por lo cuál pretendemos eliminarla del dataset. 

- Para las columnas **tpep_pickup_datetime** y **tpep_dropoff_datetime**, debemos pasar este tipo de dato a Unix Time para poder eliminar las dos columnas y generar una nueva que se llame **Trip_duration** y sea la diferencia entre las dos y nos dé la información de la duración total del viaje. 

- La columna passenger_count que es de tipo float64, debe pasar a tipo int64 ya que solo serán números enteros los que válidos.

- La columna **Store_and_fwd_flag** tiene los valores Y/N, por lo cual se decide pasar a Y = 1 y N = 0

- La columna **Airport_fee** contiene todos sus datos nulos por lo que se decide eliminar la columna completa.

