# Trabajo Final. Análisis de Datos

## Informe Entrega 1

### Alumnos:

###  Domenje, Carlos R.

###  Fux, Santiago.

---

## DATASET: Uso de Taxis Yellow Cab en USA en el año 2020

**Problema.** Intentaremos responder las siguientes preguntas:

1. ¿Existe una manera de caracterizar los lugares más recurrentes para inicio / fin de viaje?

2. ¿Cómo son los viajes típicamente en distancia y tiempo?

3. ¿Podremos segmentar los viajes de alguna manera? (clusterización)


## 1. Obtención de datos

Para importar los datos, buscamos en la página web brindada por la cátedra:

- [Yellow Cab - Dataset](https://www1.nyc.gov/site/tlc/about/tlc-trip-record-data.page)

**Nota**: El dataset utilizado será el del año 2020 y será descargado en una carpeta llamada "data" dentro de la carpeta contenedora del proyecto.

Se realizó la importación del dataset tomado del mes de Julio del año 2020. 

El archivo del dataset tiene como formato **.parquet**, el cual es un archivo que esta orientado a columnas, por lo cual, al importar pandas, utilizamos la funcion ```read_parquet() ``` para poder leer el dataset en un variable y así comenzar con su análisis. 

En primer lugar ser realizó un reconocimiento de cada una de las variables del dataset, realizando una descripción del significado y ejemplo de sus valores. 

### Descripción de Columnas del Dataset.

- **VendorID**: Proveedor de servicios de tecnologias en taxis (T-PEP)

    - 1: Creative Mobile Technologies, LLC
    - 2: VeriFone Inc.
--- 
- **tpep_pickup_datetime**: Fecha y hora en el cual el reloj fue activado al iniciar un viaje.

    - Ejemplo del dato en el dataset: 2020-07-01 00:25:32
---
- **tpep_dropoff_datetime**: Fecha y hora en el cual el reloj fue desactivador al finalizar un viaje.

    - Ejemplo del dato en el dataset: 2020-07-01 00:33:39

---
- **Passenger_count**: El número de pasajeros en el vehiculo. (Es un dato que lo ingresa el conductor.)

    - Ejemplo del dato en el dataset: 1.0

---
- **Trip_distance**: La distancia del viaje transcurrido en millas reportada por el taxímetro. 

    - Ejemplo del dato en el dataset: 1.50

---
- **PULocationID**: TLC Zona en la que el taxímetro se activó.

    - Ejemplo del dato en el dataset: 238

---
- **DOLocationID**: TLC Zona en la que el taxímetro se desactivó.

    - Ejemplo del dato en el dataset: 75
---
- **RateCodeID**:  El código de tarifa final vigente al final del viaje.

    - 1= Standard rate
    - 2= JFK 
    - 3= Newark
    - 4= Nassau or Westchester
    - 5= Negotiated fare
    - 6= Group ride
---
- **Store_and_fwd_flag**:  Este flag indica si el registro de viaje se llevó a cabo en la memoria del dispositivo del vehiculo antes de enviar al proveedor, también conocido como "almacenar y reenviar", porque el vehiculo no tenia conexion al servidor.

    - Y= Almacenar y reenviar informacion.
    - N= No almacenar y enviar informacion.
---
- **Payment_type**: Un código numérico que significa cómo el pasajero pagó por el viaje.

    - 1= Credit card
    - 2= Cash
    - 3= No charge
    - 4= Dispute
    - 5= Unknown
    - 6= Voided trip
---
- **Fare_amount**: La tarifa de tiempo y distancia calculada por el taxímetro.

    - Ejemplo del dato en el dataset: 8.0
---
- **Extra**: Varios extras y recargos. Actualmente, esto solo incluye los cargos de $0.50 y $1 por la hora pico y por la noche.

    - Ejemplo del dato en el dataset: 0.5
---
- **MTA_tax**: Impuesto MTA de $0.50 que se activa automáticamente según la tasa de uso del medidor.

    - Ejemplo del dato en el dataset: 0.5
---
- **Improvement_surcharge**: Recargo de mejora de $ 0.30 en viaje en el descenso de bandera. El recargo por mejora comenzó a cobrarse en 2015.

    - Ejemplo del dato en el dataset: 0.3

---
- **Tip_amount**: Importe de la propina: este campo se completa automáticamente para las propinas de tarjetas de crédito. Las propinas en efectivo no están incluidas.

    - Ejemplo del dato en el dataset: 0.00
---
- **Tolls_amount**: Importe total de todos los peajes pagados en el viaje.

    - Ejemplo del dato en el dataset: 0.00
---
- **Total_amount**: El monto total cobrado a los pasajeros. No incluye propinas en efectivo.

    - Ejemplo del dato en el dataset: 9.30
---
- **Congestion_Surcharge**: Importe total recaudado en el viaje por el recargo por congestión del Estado de Nueva York.

    - Ejemplo del dato en el dataset: 0.00
---
- **Airport_fee**: $1.25 para recoger solo en los aeropuertos LaGuardia y John F. Kennedy

    - Ejemplo del dato en el dataset: None


