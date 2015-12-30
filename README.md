<h1 align="center"><font color="#DF0101"><b>INSTITUTO POLITÉCNICO NACIONAL</b></font></h1>
<h2 align="center"><font color="#00FF00">U.P.I.I.C.S.A.</font></h2>
<br><br/>
<h3 align="center"><b>ALMACENAMIENTO DE DATOS Y SU ADMINISTRACIÓN</b></h3>
<h3 align="center">TAREA 7: ANÁLISIS DE DATOS Y PRESENTACIÓN DE RESULTADOS CON R</h3>
<br><br/>

#### **NOMBRE: JUAN JOSÉ LAIR MARTÍNEZ**
#### **BOLETA: B150848**

<br><br/>
<h4 align="left"><font color="##FF0000"><b>SINOPSIS O RESUMEN EJECUTIVO</b></font></h4>
El clima severo (Severe Weather) se define como una tormenta o clima destructivo. Se aplica generalmente a tormentas dañinas e intensas, a menudo perjudiciales como tormentas eléctricas, tormentas de granizo y tornados; pero también puede describir eventos como los sistemas tropicales, tormentas de nieve, "nor'easters" y "derechos".

Este trabajo contampla varios tipos de reportes de tormentas por estado, ciudad, fechas y tipos de eventos desde 1950 al presente. Para nuestro estudio, se obtuvieron los datos correspondientes a la década de los 70's extraídos de la base de datos de eventos de tormentas de la National Oceanic and Atmospheric Administration (NOAA) disponibles en formato "CSV" y que contiene los registros utilizados para documentar:

a) La ocurrencia de tormentas y otros fenómenos climatológicos que tienen la suficiente intensidad para causar perdidas de vida, lesiones, daños materiales y/o interrupción en el comercio;
b) raro, inusual, fenómenos climatológicos que generan atención de los medios de comunicación, tales como nevadas en el sur de Florida o en el área de la costa de San Diego, y
c) otros eventos metereológicos significativos, tales como máximo o mínimo de temperaturas o precipitaciones que ocurren en conexión con otros eventos.

<br></br>
<h4 align="left"><font color="##FF0000"><b>CARGA Y PROCESAMIENTO DE DATOS CRUDOS</b></font></h4>
De la base de datos de eventos de tormentas de la "National Climatic Data center" de la "National Oceanic and Atmospheric Administrator" http://www1.ncdc.noaa.gov/pub/data/swdi/stormevents/csvfiles/, obtenemos los archivos para los años de 1971 a 1980 para analizar los fenómenos climatológicos.

<br></br>
<h4 align="left"><font color="##FF0000"><b>ANALIZANDO LOS DATOS DEL AÑO 1971</b></font></h4>
Leemos los datos del archivo StormEvents_details-ftp_v1.0_d1971_c20150826.csv que se encuentra en formato delimitado por comas incluído en el archivo con extensión gz.

```{r}
Fatalities1971<-read.csv( "c:/AdmonDatos/Tarea6/StormEvents_details-ftp_v1.0_d1971_c20150826.csv", header=T, sep=",", na.strings="")
```

Procedemos a obtener el número de registros que contiene el archivo y se hace una exploración de algunos datos.

```{r}
head(Fatalities1971[, 9:15], n=5L)
head(Fatalities1971[, 21:29], n=5L)
nrow(Fatalities1971)
ncol(Fatalities1971)
colnames(Fatalities1971)
```

Realizando un análisis sobre las columnas más significativas nos encontramos con: 

a) Columna EVENT_TYPE que nos indica el tipo de fenómeno metereológico (tornado, granizo o tormenta de rayos),

```{r}
x0<-Fatalities1971$EVENT_TYPE
summary(x0)
```

b) Columna MONTH_NAME que es el mes en el cual sucedieron los eventos,

```{r}
x1<-Fatalities1971$MONTH_NAME
summary(x1)
```

c) Columnas INJURIES_DIRECT y INJURIES_INDIRECT que son las lesiones directas e indirectas; 

```{r}
x2<-Fatalities1971$INJURIES_DIRECT
summary(x2)
x3<-Fatalities1971$INJURIES_INDIRECT
summary(x3)
```

d) así como DEATHS_DIRECT y DEATHS_INDIRECT que son las muertes ocasionadas, directa o indirectamente por los fenómenos.

```{r}
x4<-Fatalities1971$DEATHS_DIRECT
summary(x4)
x5<-Fatalities1971$DEATHS_INDIRECT
summary(x5)
```

e) Columna STATE que es el estado en donde sucedieron los eventos y

```{r}
x6<-Fatalities1971$STATE
summary(x6)
```

f) Por último, los valores perdidos:

```{r}
mean(is.na(Fatalities1971))
```

<br></br>
<h4 align="left"><b>CONCLUSIONES DEL AÑO 1971</b></h4>
Se observa que se cuenta con un total de 3471 registros, el fenómeno natural con mayor número de eventos en el año son las tormentas eléctricas con 1544, el mes de junio es el de mayor eventos con 983, no existen muertes indirectas y el máximo de muertes directas en el año es de 30 y el estado con mayor número de eventos es Texas con un total de 483.

<br></br>
<h4 align="left"><font color="##FF0000"><b>ANALIZANDO LOS DATOS DEL AÑO 1972</b></font></h4>
Leemos los datos del archivo StormEvents_details-ftp_v1.0_d1972_c20150826.csv que se encuentra en formato delimitado por comas incluído en el archivo con extensión gz.

```{r}
Fatalities1972<-read.csv( "c:/AdmonDatos/Tarea6/StormEvents_details-ftp_v1.0_d1972_c20150826.csv", header=T, sep=",", na.strings="")
```

Procedemos a obtener el número de registros que contiene el archivo y se hace una exploración de algunos datos.

```{r}
head(Fatalities1972[, 9:15], n=5L)
head(Fatalities1972[, 21:29], n=5L)
nrow(Fatalities1972)
ncol(Fatalities1972)
colnames(Fatalities1972)
```

Realizando un análisis sobre las columnas más significativas nos encontramos con: 

a) Columna EVENT_TYPE que nos indica el tipo de fenómeno metereológico (tornado, granizo o tormenta de rayos),

```{r}
x0<-Fatalities1972$EVENT_TYPE
summary(x0)
```

b) Columna MONTH_NAME que es el mes en el cual sucedieron los eventos,

```{r}
x1<-Fatalities1972$MONTH_NAME
summary(x1)
```

c) Columnas INJURIES_DIRECT y INJURIES_INDIRECT que son las lesiones directas e indirectas; 

```{r}
x2<-Fatalities1972$INJURIES_DIRECT
summary(x2)
x3<-Fatalities1972$INJURIES_INDIRECT
summary(x3)
```

d) así como DEATHS_DIRECT y DEATHS_INDIRECT que son las muertes ocasionadas, directa o indirectamente por los fenómenos.

```{r}
x4<-Fatalities1972$DEATHS_DIRECT
summary(x4)
x5<-Fatalities1972$DEATHS_INDIRECT
summary(x5)
```

e) Columna STATE que es el estado en donde sucedieron los eventos y

```{r}
x6<-Fatalities1972$STATE
summary(x6)
```

f) Por último, los valores perdidos:

```{r}
mean(is.na(Fatalities1972))
```

<br></br>
<h4 align="left"><b>CONCLUSIONES DEL AÑO 1972</b></h4>
Se observa que se cuenta con un total de 2168 registros, el fenómeno natural con mayor número de eventos en el año son los tornados con 775, el mes de junio es el de mayor eventos con 371, no existen muertes indirectas y el máximo de muertes directas en el año es de 6 y el estado con mayor número de eventos es Texas con un total de 399.

<br></br>
<h4 align="left"><font color="##FF0000"><b>ANALIZANDO LOS DATOS DEL AÑO 1973</b></font></h4>
Leemos los datos del archivo StormEvents_details-ftp_v1.0_d1973_c20150826.csv que se encuentra en formato delimitado por comas incluído en el archivo con extensión gz.

```{r}
Fatalities1973<-read.csv( "c:/AdmonDatos/Tarea6/StormEvents_details-ftp_v1.0_d1973_c20150826.csv", header=T, sep=",", na.strings="")
```

Procedemos a obtener el número de registros que contiene el archivo y se hace una exploración de algunos datos.

```{r}
head(Fatalities1973[, 9:15], n=5L)
head(Fatalities1973[, 21:29], n=5L)
nrow(Fatalities1973)
ncol(Fatalities1973)
colnames(Fatalities1973)
```

Realizando un análisis sobre las columnas más significativas nos encontramos con: 

a) Columna EVENT_TYPE que nos indica el tipo de fenómeno metereológico (tornado, granizo o tormenta de rayos),

```{r}
x0<-Fatalities1973$EVENT_TYPE
summary(x0)
```

b) Columna MONTH_NAME que es el mes en el cual sucedieron los eventos,

```{r}
x1<-Fatalities1973$MONTH_NAME
summary(x1)
```

c) Columnas INJURIES_DIRECT y INJURIES_INDIRECT que son las lesiones directas e indirectas; 

```{r}
x2<-Fatalities1973$INJURIES_DIRECT
summary(x2)
x3<-Fatalities1973$INJURIES_INDIRECT
summary(x3)
```

d) así como DEATHS_DIRECT y DEATHS_INDIRECT que son las muertes ocasionadas, directa o indirectamente por los fenómenos.

```{r}
x4<-Fatalities1973$DEATHS_DIRECT
summary(x4)
x5<-Fatalities1973$DEATHS_INDIRECT
summary(x5)
```

e) Columna STATE que es el estado en donde sucedieron los eventos y

```{r}
x6<-Fatalities1973$STATE
summary(x6)
```

f) Por último, los valores perdidos:

```{r}
mean(is.na(Fatalities1973))

```
<br></br>
<h4 align="left"><b>CONCLUSIONES DEL AÑO 1973</b></h4>
Se observa que se cuenta con un total de 4453 registros, el fenómeno natural con mayor número de eventos en el año son las tormentas eléctricas con 2157, el mes de junio es el de mayor eventos con 934, no existen muertes indirectas y el máximo de muertes directas en el año es de 7 y el estado con mayor número de eventos es Texas con un total de 503.

<br></br>
<h4 align="left"><font color="##FF0000"><b>ANALIZANDO LOS DATOS DEL AÑO 1974</b></font></h4>
Leemos los datos del archivo StormEvents_details-ftp_v1.0_d1974_c20150826.csv que se encuentra en formato delimitado por comas incluído en el archivo con extensión gz.

```{r}
Fatalities1974<-read.csv( "c:/AdmonDatos/Tarea6/StormEvents_details-ftp_v1.0_d1974_c20150826.csv", header=T, sep=",", na.strings="")
```

Procedemos a obtener el número de registros que contiene el archivo y se hace una exploración de algunos datos.

```{r}
head(Fatalities1974[, 9:15], n=5L)
head(Fatalities1974[, 21:29], n=5L)
nrow(Fatalities1974)
ncol(Fatalities1974)
colnames(Fatalities1974)
```

Realizando un análisis sobre las columnas más significativas nos encontramos con: 

a) Columna EVENT_TYPE que nos indica el tipo de fenómeno metereológico (tornado, granizo o tormenta de rayos),

```{r}
x0<-Fatalities1974$EVENT_TYPE
summary(x0)
```

b) Columna MONTH_NAME que es el mes en el cual sucedieron los eventos,

```{r}
x1<-Fatalities1974$MONTH_NAME
summary(x1)
```

c) Columnas INJURIES_DIRECT y INJURIES_INDIRECT que son las lesiones directas e indirectas; 

```{r}
x2<-Fatalities1974$INJURIES_DIRECT
summary(x2)
x3<-Fatalities1974$INJURIES_INDIRECT
summary(x3)
```

d) así como DEATHS_DIRECT y DEATHS_INDIRECT que son las muertes ocasionadas, directa o indirectamente por los fenómenos.

```{r}
x4<-Fatalities1974$DEATHS_DIRECT
summary(x4)
x5<-Fatalities1974$DEATHS_INDIRECT
summary(x5)
```

e) Columna STATE que es el estado en donde sucedieron los eventos y

```{r}
x6<-Fatalities1974$STATE
summary(x6)
```

f) Por último, los valores perdidos:

```{r}
mean(is.na(Fatalities1974))

```
<br></br>
<h4 align="left"><b>CONCLUSIONES DEL AÑO 1974</b></h4>
Se observa que se cuenta con un total de 5375 registros, el fenómeno natural con mayor número de eventos en el año son las tormentas eléctricas con 2599, el mes de junio es el de mayor eventos con 1501, no existen muertes indirectas y el máximo de muertes directas en el año es de 36 y el estado con mayor número de eventos es Texas con un total de 424.

<br></br>
<h4 align="left"><font color="##FF0000"><b>ANALIZANDO LOS DATOS DEL AÑO 1975</b></font></h4>
Leemos los datos del archivo StormEvents_details-ftp_v1.0_d1975_c20150826.csv que se encuentra en formato delimitado por comas incluído en el archivo con extensión gz.

```{r}
Fatalities1975<-read.csv( "c:/AdmonDatos/Tarea6/StormEvents_details-ftp_v1.0_d1975_c20150826.csv", header=T, sep=",", na.strings="")
```

Procedemos a obtener el número de registros que contiene el archivo y se hace una exploración de algunos datos.

```{r}
head(Fatalities1975[, 9:15], n=5L)
head(Fatalities1975[, 21:29], n=5L)
nrow(Fatalities1975)
ncol(Fatalities1975)
colnames(Fatalities1975)
```

Realizando un análisis sobre las columnas más significativas nos encontramos con: 

a) Columna EVENT_TYPE que nos indica el tipo de fenómeno metereológico (tornado, granizo o tormenta de rayos),

```{r}
x0<-Fatalities1975$EVENT_TYPE
summary(x0)
```

b) Columna MONTH_NAME que es el mes en el cual sucedieron los eventos,

```{r}
x1<-Fatalities1975$MONTH_NAME
summary(x1)
```

c) Columnas INJURIES_DIRECT y INJURIES_INDIRECT que son las lesiones directas e indirectas; 

```{r}
x2<-Fatalities1975$INJURIES_DIRECT
summary(x2)
x3<-Fatalities1975$INJURIES_INDIRECT
summary(x3)
```

d) así como DEATHS_DIRECT y DEATHS_INDIRECT que son las muertes ocasionadas, directa o indirectamente por los fenómenos.

```{r}
x4<-Fatalities1975$DEATHS_DIRECT
summary(x4)
x5<-Fatalities1975$DEATHS_INDIRECT
summary(x5)
```

e) Columna STATE que es el estado en donde sucedieron los eventos y

```{r}
x6<-Fatalities1975$STATE
summary(x6)
```

f) Por último, los valores perdidos:

```{r}
mean(is.na(Fatalities1975))

```
<br></br>
<h4 align="left"><b>CONCLUSIONES DEL AÑO 1975</b></h4>
Se observa que se cuenta con un total de 4975 registros, el fenómeno natural con mayor número de eventos en el año son las tormentas eléctricas con 2639, el mes de junio es el de mayor eventos con 1006, no existen muertes indirectas y el máximo de muertes directas en el año es de 7 y el estado con mayor número de eventos es Texas con un total de 497.

<br></br>
<h4 align="left"><font color="##FF0000"><b>ANALIZANDO LOS DATOS DEL AÑO 1976</b></font></h4>
Leemos los datos del archivo StormEvents_details-ftp_v1.0_d1976_c20150826.csv que se encuentra en formato delimitado por comas incluído en el archivo con extensión gz.

```{r}
Fatalities1976<-read.csv( "c:/AdmonDatos/Tarea6/StormEvents_details-ftp_v1.0_d1976_c20150826.csv", header=T, sep=",", na.strings="")
```

Procedemos a obtener el número de registros que contiene el archivo y se hace una exploración de algunos datos.

```{r}
head(Fatalities1976[, 9:15], n=5L)
head(Fatalities1976[, 21:29], n=5L)
nrow(Fatalities1976)
ncol(Fatalities1976)
colnames(Fatalities1976)
```

Realizando un análisis sobre las columnas más significativas nos encontramos con: 

a) Columna EVENT_TYPE que nos indica el tipo de fenómeno metereológico (tornado, granizo o tormenta de rayos),

```{r}
x0<-Fatalities1976$EVENT_TYPE
summary(x0)
```

b) Columna MONTH_NAME que es el mes en el cual sucedieron los eventos,

```{r}
x1<-Fatalities1976$MONTH_NAME
summary(x1)
```

c) Columnas INJURIES_DIRECT y INJURIES_INDIRECT que son las lesiones directas e indirectas; 

```{r}
x2<-Fatalities1976$INJURIES_DIRECT
summary(x2)
x3<-Fatalities1976$INJURIES_INDIRECT
summary(x3)
```

d) así como DEATHS_DIRECT y DEATHS_INDIRECT que son las muertes ocasionadas, directa o indirectamente por los fenómenos.

```{r}
x4<-Fatalities1976$DEATHS_DIRECT
summary(x4)
x5<-Fatalities1976$DEATHS_INDIRECT
summary(x5)
```

e) Columna STATE que es el estado en donde sucedieron los eventos y

```{r}
x6<-Fatalities1976$STATE
summary(x6)
```

f) Por último, los valores perdidos:

```{r}
mean(is.na(Fatalities1976))

```
<br></br>
<h4 align="left"><b>CONCLUSIONES DEL AÑO 1976</b></h4>
Se observa que se cuenta con un total de 3768 registros, el fenómeno natural con mayor número de eventos en el año son las tormentas eléctricas con 1742, el mes de marzo es el de mayor eventos con 744, no existen muertes indirectas y el máximo de muertes directas en el año es de 5 y el estado con mayor número de eventos es Texas con un total de 585.

<br></br>
<h4 align="left"><font color="##FF0000"><b>ANALIZANDO LOS DATOS DEL AÑO 1977</b></font></h4>
Leemos los datos del archivo StormEvents_details-ftp_v1.0_d1977_c20150826.csv que se encuentra en formato delimitado por comas incluído en el archivo con extensión gz.

```{r}
Fatalities1977<-read.csv( "c:/AdmonDatos/Tarea6/StormEvents_details-ftp_v1.0_d1977_c20150826.csv", header=T, sep=",", na.strings="")
```

Procedemos a obtener el número de registros que contiene el archivo y se hace una exploración de algunos datos.

```{r}
head(Fatalities1977[, 9:15], n=5L)
head(Fatalities1977[, 21:29], n=5L)
nrow(Fatalities1977)
ncol(Fatalities1977)
colnames(Fatalities1977)
```

Realizando un análisis sobre las columnas más significativas nos encontramos con: 

a) Columna EVENT_TYPE que nos indica el tipo de fenómeno metereológico (tornado, granizo o tormenta de rayos),

```{r}
x0<-Fatalities1977$EVENT_TYPE
summary(x0)
```

b) Columna MONTH_NAME que es el mes en el cual sucedieron los eventos,

```{r}
x1<-Fatalities1977$MONTH_NAME
summary(x1)
```

c) Columnas INJURIES_DIRECT y INJURIES_INDIRECT que son las lesiones directas e indirectas; 

```{r}
x2<-Fatalities1977$INJURIES_DIRECT
summary(x2)
x3<-Fatalities1977$INJURIES_INDIRECT
summary(x3)
```

d) así como DEATHS_DIRECT y DEATHS_INDIRECT que son las muertes ocasionadas, directa o indirectamente por los fenómenos.

```{r}
x4<-Fatalities1977$DEATHS_DIRECT
summary(x4)
x5<-Fatalities1977$DEATHS_INDIRECT
summary(x5)
```

e) Columna STATE que es el estado en donde sucedieron los eventos y

```{r}
x6<-Fatalities1977$STATE
summary(x6)
```

f) Por último, los valores perdidos:

```{r}
mean(is.na(Fatalities1977))

```
<br></br>
<h4 align="left"><b>CONCLUSIONES DEL AÑO 1977</b></h4>
Se observa que se cuenta con un total de 3728 registros, el fenómeno natural con mayor número de eventos en el año son las tormentas eléctricas con 1723, el mes de mayo es el de mayor eventos con 874, no existen muertes indirectas y el máximo de muertes directas en el año es de 22 y el estado con mayor número de eventos es Texas con un total de 379.

<br></br>
<h4 align="left"><font color="##FF0000"><b>ANALIZANDO LOS DATOS DEL AÑO 1978</b></font></h4>
Leemos los datos del archivo StormEvents_details-ftp_v1.0_d1978_c20150826.csv que se encuentra en formato delimitado por comas incluído en el archivo con extensión gz.

```{r}
setwd("c:/AdmonDatos/Tarea6/")
Fatalities1978<-read.csv( "StormEvents_details-ftp_v1.0_d1978_c20150826.csv", header=T, sep=",", na.strings="")
```

Procedemos a obtener el número de registros que contiene el archivo y se hace una exploración de algunos datos.

```{r}
head(Fatalities1978[, 9:15], n=5L)
head(Fatalities1978[, 21:29], n=5L)
nrow(Fatalities1978)
ncol(Fatalities1978)
colnames(Fatalities1978)
```

Realizando un análisis sobre las columnas más significativas nos encontramos con: 

a) Columna EVENT_TYPE que nos indica el tipo de fenómeno metereológico (tornado, granizo o tormenta de rayos),

```{r}
x0<-Fatalities1978$EVENT_TYPE
summary(x0)
```

b) Columna MONTH_NAME que es el mes en el cual sucedieron los eventos,

```{r}
x1<-Fatalities1978$MONTH_NAME
summary(x1)
```

c) Columnas INJURIES_DIRECT y INJURIES_INDIRECT que son las lesiones directas e indirectas; 

```{r}
x2<-Fatalities1978$INJURIES_DIRECT
summary(x2)
x3<-Fatalities1978$INJURIES_INDIRECT
summary(x3)
```

d) así como DEATHS_DIRECT y DEATHS_INDIRECT que son las muertes ocasionadas, directa o indirectamente por los fenómenos.

```{r}
x4<-Fatalities1978$DEATHS_DIRECT
summary(x4)
x5<-Fatalities1978$DEATHS_INDIRECT
summary(x5)
```

e) Columna STATE que es el estado en donde sucedieron los eventos y

```{r}
x6<-Fatalities1978$STATE
summary(x6)
```

f) Por último, los valores perdidos:

```{r}
mean(is.na(Fatalities1978))

```
<br></br>
<h4 align="left"><b>CONCLUSIONES DEL AÑO 1978</b></h4>
Se observa que se cuenta con un total de 3657 registros, el fenómeno natural con mayor número de eventos en el año son las tormentas eléctricas con 1758, el mes de mayo es el de mayor eventos con 770, no existen muertes indirectas y el máximo de muertes directas en el año es de 16 y el estado con mayor número de eventos es Texas con un total de 496.

<br></br>
<h4 align="left"><font color="##FF0000"><b>ANALIZANDO LOS DATOS DEL AÑO 1979</b></font></h4>
Leemos los datos del archivo StormEvents_details-ftp_v1.0_d1979_c20150826.csv que se encuentra en formato delimitado por comas incluído en el archivo con extensión gz.

```{r}
Fatalities1979<-read.csv( "c:/AdmonDatos/Tarea6/StormEvents_details-ftp_v1.0_d1979_c20150826.csv", header=T, sep=",", na.strings="")
```

Procedemos a obtener el número de registros que contiene el archivo y se hace una exploración de algunos datos.

```{r}
head(Fatalities1979[, 9:15], n=5L)
head(Fatalities1979[, 21:29], n=5L)
nrow(Fatalities1979)
ncol(Fatalities1979)
colnames(Fatalities1979)
```

Realizando un análisis sobre las columnas más significativas nos encontramos con: 

a) Columna EVENT_TYPE que nos indica el tipo de fenómeno metereológico (tornado, granizo o tormenta de rayos),

```{r}
x0<-Fatalities1979$EVENT_TYPE
summary(x0)
```

b) Columna MONTH_NAME que es el mes en el cual sucedieron los eventos,

```{r}
x1<-Fatalities1979$MONTH_NAME
summary(x1)
```

c) Columnas INJURIES_DIRECT y INJURIES_INDIRECT que son las lesiones directas e indirectas; 

```{r}
x2<-Fatalities1979$INJURIES_DIRECT
summary(x2)
x3<-Fatalities1979$INJURIES_INDIRECT
summary(x3)
```

d) así como DEATHS_DIRECT y DEATHS_INDIRECT que son las muertes ocasionadas, directa o indirectamente por los fenómenos.

```{r}
x4<-Fatalities1979$DEATHS_DIRECT
summary(x4)
x5<-Fatalities1979$DEATHS_INDIRECT
summary(x5)
```

e) Columna STATE que es el estado en donde sucedieron los eventos y

```{r}
x6<-Fatalities1979$STATE
summary(x6)
```

f) Por último, los valores perdidos:

```{r}
mean(is.na(Fatalities1979))

```
<br></br>
<h4 align="left"><b>CONCLUSIONES DEL AÑO 1979</b></h4>
Se observa que se cuenta con un total de 4279 registros, el fenómeno natural con mayor número de eventos en el año son las tormentas eléctricas con 2046, el mes de junio es el de mayor eventos con 939, no existen muertes indirectas y el máximo de muertes directas en el año es de 42 y el estado con mayor número de eventos es Texas con un total de 726.

<br></br>
<h4 align="left"><font color="##FF0000"><b>ANALIZANDO LOS DATOS DEL AÑO 1980</b></font></h4>
Leemos los datos del archivo StormEvents_details-ftp_v1.0_d1980_c20150826.csv que se encuentra en formato delimitado por comas incluído en el archivo con extensión gz.

```{r}
Fatalities1980<-read.csv( "c:/AdmonDatos/Tarea6/StormEvents_details-ftp_v1.0_d1980_c20150826.csv", header=T, sep=",", na.strings="")
```

Procedemos a obtener el número de registros que contiene el archivo y se hace una exploración de algunos datos.

```{r}
head(Fatalities1980[, 9:15], n=5L)
head(Fatalities1980[, 21:29], n=5L)
nrow(Fatalities1980)
ncol(Fatalities1980)
colnames(Fatalities1980)
```

Realizando un análisis sobre las columnas más significativas nos encontramos con: 

a) Columna EVENT_TYPE que nos indica el tipo de fenómeno metereológico (tornado, granizo o tormenta de rayos),

```{r}
x0<-Fatalities1980$EVENT_TYPE
summary(x0)
```

b) Columna MONTH_NAME que es el mes en el cual sucedieron los eventos,

```{r}
x1<-Fatalities1980$MONTH_NAME
summary(x1)
```

c) Columnas INJURIES_DIRECT y INJURIES_INDIRECT que son las lesiones directas e indirectas; 

```{r}
x2<-Fatalities1980$INJURIES_DIRECT
summary(x2)
x3<-Fatalities1980$INJURIES_INDIRECT
summary(x3)
```

d) así como DEATHS_DIRECT y DEATHS_INDIRECT que son las muertes ocasionadas, directa o indirectamente por los fenómenos.

```{r}
x4<-Fatalities1980$DEATHS_DIRECT
summary(x4)
x5<-Fatalities1980$DEATHS_INDIRECT
summary(x5)
```

e) Columna STATE que es el estado en donde sucedieron los eventos y

```{r}
x6<-Fatalities1980$STATE
summary(x6)
```

f) Por último, los valores perdidos:

```{r}
mean(is.na(Fatalities1980))

```
<br></br>
<h4 align="left"><b>CONCLUSIONES DEL AÑO 1980</b></h4>
Se observa que se cuenta con un total de 6136 registros, el fenómeno natural con mayor número de eventos en el año son las tormentas eléctricas con 3179, el mes de junio es el de mayor eventos con 1429, no existen muertes indirectas y el máximo de muertes directas en el año es de 5 y el estado con mayor número de eventos es Texas con un total de 772.

<br><br/>
<h4 align="left"><font color="##FF0000"><b>CONCLUSIONES DÉCADA 70's</b></font></h4>
A continuación se muestra, en números, las conclusiones acerca de la década de los 70's con respecto a este estudio de fenómenos climatológicos:

```{r}
setwd("c:/AdmonDatos/Tarea6/")

FILES<-list("StormEvents_details-ftp_v1.0_d1971_c20150826.csv","StormEvents_details-ftp_v1.0_d1972_c20150826.csv","StormEvents_details-ftp_v1.0_d1973_c20150826.csv","StormEvents_details-ftp_v1.0_d1974_c20150826.csv","StormEvents_details-ftp_v1.0_d1975_c20150826.csv","StormEvents_details-ftp_v1.0_d1976_c20150826.csv","StormEvents_details-ftp_v1.0_d1977_c20150826.csv","StormEvents_details-ftp_v1.0_d1978_c20150826.csv","StormEvents_details-ftp_v1.0_d1979_c20150826.csv","StormEvents_details-ftp_v1.0_d1980_c20150826.csv")

for( files in FILES ){
    if( !exists("Fatalities" ) ) {
        Fatalities<-read.csv( files, header=T, sep=",", na.strings="")
    } else {
        data<-read.csv(files, header=T, sep=",", na.strings="")
        Fatalities<-rbind(Fatalities,data)
    }
}

print(paste("Total de registros: ", nrow(Fatalities), sep = " "))
```

ESTADOS CON MÁS EVENTOS EN TODO EL AÑO:

```{r}
y0<-Fatalities$STATE
summary(y0)
```

FENÓMENO CLIMATOLÓGICO CON MÁS EVENTOS EN TODO EL AÑO:

```{r}
y1<-Fatalities$EVENT_TYPE
summary(y1)
```

CIUDADES CON MÁS EVENTOS EN TODO EL AÑO:

```{r}
y2<-Fatalities$CZ_NAME
summary(y2)
```

MAYOR NÚMERO DE MUERTES DIRECTAS EN LA DÉCADA

```{r}
max(Fatalities$DEATHS_DIRECT)
```

MAYOR NÚMERO DE LESIONES DIRECTAS EN LA DÉCADA

```{r}
max(Fatalities$INJURIES_DIRECT)
```

<br><br/>
<h4 align="left"><font color="##FF0000"><b>BIBLIOGRAFÍA</b></font></h4>

[1] Roger D. Peng, "R Programming for Data Science"

[2] NOAA National Centers For Environmental Information - National Oceanic And Atmospheric Administration

Storm Events Database, Bulk Data Download

http://www1.ncdc.noaa.gov/pub/data/swdi/stormevents/csvfiles/