# ANÁLISIS DE DATOS DE ACTIVIDAD DE VUELOS Y FIDELIZACIÓN DE LOS CLIENTES
Este proyecto es un análisis de datos extraídos de dos fuentes diferentes. Por un lado, tenemos la actividad de vuelos de los clientes y por el otro, su historial de fidelidación. Este proyecto se ha llevado a cabo con el objetivo de obtener información sobre patrones de comportamiento de los clientes y profundizar en la información disponible.

# DATOS UTILIZADOS Y TRANSFORMACIONES REALIZADAS

A partir de dos archivos .csv, hemos hecho primero una exploración (EDA) de cada uno, para conocer los conjuntos de datos y saber con qué estábamos trabajando. El primer archivo tenía información sobre la distancia volada, los puntos acumulados, los puntos canjeable, los vuelos reservados y los vuelos acompañantes, además del número de fidelización correspondiente a cada cliente, en base al año y mes: por lo que había muchos número duplicados porque habían viajado en diferente año/mes, algo bastante común. 
Mientras que en el segundo archivo teníamos información acerca de los clientes, como su estado civil, país, ciudad, género, nivel educativo, salario y tipo de tarjetas de fidelización, año y mes de inscripción y si habían cancelado su afiliación.
Tras una primera exploración (EDA) de ambos conjuntos, se procedió a una serie de limpiezas y transformaciones necesarias:

- Se corrigieron los valores negativos en la columna de salario convirtiéndolos a positivos.
- Se eliminaron duplicados exactos para evitar ruido en el análisis.
- Se analizaron los valores nulos, en particular en las columnas de salario y fecha de cancelación.
En cuanto a los salarios faltantes, se observó que la mayoría de los valores nulos correspondían a clientes con educación "College". Por ello, se imputó la media salarial calculada dentro de este grupo en base a la media del grupo de estudios menor y el siguiente mayor a "College", para mantener coherencia con el perfil educativo.

Para las columnas de cancelación, se detectó que más del 87% de los registros no tenían año ni mes de cancelación. Dado que la mayoría de clientes no han cancelado su afiliación, se imputaron estos valores como 0. Además, se creó una nueva columna booleana ('Cancelado') para indicar de forma clara si un cliente ha cancelado o no su membresía.

A continuación hemos hecho un merge con el campo Loyalty Number como clave, a trvés de un left join, para poder conservar la iformación de todos los vuelos y agregar la información de cada perfil de cliente.

# VISUALIZACIONES

Después de haber unido nuestros .csv, hemos creado uno nuevo con los cambios para poder visualizar los datos y entender mejor el comportamiendo de los clientes y sus características. Hemos creado 6 tablas para responder a 6 preguntas. Donde destacamos que hay cierta estacionalidad en las reservas, habiendo una mayor cantidad de reservas de vuelos en los meses de verano y diciembre, aunque hay actividad todo el año.

Existe una relación positivo entre la distancia de los vuelos y una mayor cantidad de puntos acumulados. 

Respecto a los datos demográficos podemos ver que dentro del país Canadá, los clientes se concentran en las provincias de Ontario, British Columbia y Quebec, que hay una tendencia directa entre la educación y el salario, a mayor nivel educativo, mayor es el salario promedio del cliente. Y que la mayoría de los clientes están casados y hay una distribución equilibrada en el estado civil entre hombres y mujeres.
Estas gráficas nos han permitido identificar patrones y relaciones entre nuestros datos.
