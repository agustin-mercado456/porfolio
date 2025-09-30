# Descripción del dataset estudiado

 dataset analizado corresponde a los registros históricos de asistencia de clientes al gimnasio, abarcando desde el **1 de enero de 2023** hasta el **17 de julio de 2025**. La información incluye variables relacionadas con datos demográficos, antigüedad de cliente en el gimnasio, entre otras, que servirán de base para el análisis exploratorio y el modelado posterior.
a continuación se presenta el dataset en una tabla para su mayor comprensión:

| Variable                 | Descripción                                                                      |
| ------------------------ | -------------------------------------------------------------------------------- |
| id_cliente               | numero de documento del cliente                                                  |
| apellido_cliente         | ---                                                                              |
| nombre_cliente           | ---                                                                              |
| telefono_cliente_1       | ---                                                                              |
| edad_cliente             | edad del cliente                                                                 |
| tiempo_membresia_cliente | tiempo que lleva el cliente registrado en el gimnasio desde su primer asistencia |
| direccion_cliente        | ---                                                                              |
| localidad_cliente        | ---                                                                              |
| provincia_cliente        | --                                                                               |
| sexo_cliente             | sexo del cliente                                                                 |
| activado_cliente         | si el cliente esta activo                                                        |
| razon                    | a la sucursal que asistio                                                        |
| nombre_actividad         | la actividad que fue a realizar                                                  |
| fecha_registro_cliente   | la fecha en que asistió a realizar la actividad en ele gimnasio                  |
| hora_registro_cliente    | la hora que asistio                                                              |


dicho dataset contiene **264208 registros por 15 variables**

**observaciones:**
-  No se pudo realizar un **análisis por sexo de los clientes** porque los datos estaban incompletos o contaminados.
- No se pudo calcular la **distancia de los clientes a cada sucursal** debido a que la información de ubicación no era confiable ni consiste

# Abandono

Mediante el análisis de datos se detectó que, hasta el **17/07/2025**, un total de **3.100 clientes** han abandonado. A continuación, se detallan las condiciones de abandono según el segmento de clientes:

| segmento         | Definición resumida                                     | Cantidad |
| ---------------- | ------------------------------------------------------- | -------- |
| `perdido_2025`   | Clientes que asistieron en 2023 y 2024, pero no en 2025 | 697      |
| `no_volvio_2023` | Clientes que solo asistieron en 2023                    | 1547     |
| `ganado_2024`    | Clientes que asistieron solo en 2024                    | 856      |

los datos de abandono se distribuyen de la siguiente manera:

| segmento       | Jóvenes | Adultos Jóvenes | Adultos Medios | Adultos Mayores | Seniors |
| -------------- | ------- | --------------- | -------------- | --------------- | ------- |
| ganado_2024    | 428     | 252             | 137            | 34              | 5       |
| no_volvio_2023 | 736     | 455             | 311            | 51              | 4       |
| perdido_2025   | 296     | 228             | 153            | 20              | 0       |
en términos porcentuales:

| segmento         | Jóvenes | Adultos Jóvenes | Adultos Medios | Adultos Mayores | Seniors | Total % fila |
| ---------------- | ------- | --------------- | -------------- | --------------- | ------- | ------------ |
| ganado\_2024     | 13.8%   | 8.12%           | 4.41%          | 1.09%           | 0.16%   | 27.61%       |
| no\_volvio\_2023 | 23.61%  | 14.55%          | 9.97%          | 1.61%           | 0.16%   | 49.90%       |
| perdido\_2025    | 9.61%   | 7.19%           | 5.03%          | 0.65%           | 0.00%   | 22.48%       |
| Total % columna  | 47.09%  | 29.83%          | 19.38%         | 3.38%           | 0.29%   | 100%         |

#### Observaciones por segmento


- **`no_volvio_2023`** representa **49,9%** del total de clientes perdidos, siendo el segmento más afectado.
    
- **`ganado_2024`** contribuye con **27,6%**, mientras que **`perdido_2025`** aporta **22,4%**.
    
- Esto indica que **casi la mitad de los abandonos proviene de clientes que no repiten asistencia al año siguiente**.

#### Observaciones por franja etaria

- Los **jóvenes** concentran **47,0%** de los clientes perdidos.
    
- Les siguen los **adultos jóvenes** con **29,8%** y los **adultos medios** con **19,3%**.
    
- Los **adultos mayores** (3,38%) y **seniors** (0,29%) presentan un impacto menor.
#### Interpretación general

- La pérdida se concentra en segmentos con **menor fidelidad histórica**, es decir, clientes recientes o que asistieron solo un año.
    
- Esta información sugiere la necesidad de **estrategias de retención diferenciadas** enfocadas en **fidelizar a clientes jóvenes y recién incorporados**.
  
### Análisis de asistencias de los clientes que abandonaron

De los clientes que abandonaron, se contabilizó un total de **50.783 registros de asistencia**. A continuación se presentan los valores absolutos y porcentajes por segmento y franja etaria:

| segmento       | Jóvenes | Adultos Jóvenes | Adultos Medios | Adultos Mayores | Seniors |
| -------------- | ------- | --------------- | -------------- | --------------- | ------- |
| ganado_2024    | 2326    | 1917            | 1037           | 312             | 67      |
| no_volvio_2023 | 5939    | 5807            | 4919           | 654             | 39      |
| perdido_2025   | 9988    | 9496            | 7011           | 1271            | 0       |


| segmento        | Jóvenes | Adultos Jóvenes | Adultos Medios | Adultos Mayores | Seniors | Total % fila |
| --------------- | ------- | --------------- | -------------- | --------------- | ------- | ------------ |
| ganado_2024     | 4.58    | 3.77            | 2.04           | 0.61            | 0.13    | 11.13        |
| no_volvio_2023  | 11.69   | 11.43           | 9.69           | 1.29            | 0.08    | 34.18        |
| perdido_2025    | 19.67   | 18.70           | 13.81          | 2.5             | 0       | 54.68        |
| Total % columna | 36      | 33.9            | 25.54          | 4.4             | 0.21    | 100.000000   |


### Observaciones

**1. Distribución de la pérdida por segmento**

- El segmento **`perdido_2025`** concentra la mayor parte de los registros de asistencia de los clientes que abandonaron, representando **54,68%** del total.
    
- Le sigue **`no_volvio_2023`** con **34,18%** y **`ganado_2024`** con **11,13%**.
    

Esto indica que la mayoría de los clientes que se perdieron habían tenido una **fidelidad relativamente alta**, especialmente aquellos que estuvieron presentes en varios años.

**2. Distribución por franja etaria**


- Los **jóvenes** representan **36%** de los registros totales, siendo la franja más activa entre los clientes perdidos.
    
- Los **adultos jóvenes** aportan **33,9%**, y los **adultos medios** **25,54%**.
    
- Las franjas **adultos mayores** y **seniors** tienen una incidencia mucho menor, con **4,4%** y **0,21%**, respectivamente.
    

Esto confirma que la pérdida se concentra principalmente en **clientes más activos y de menor edad**, lo que podría tener un mayor impacto en la facturación.

### Valor económico de los clientes perdidos

Considerando que cada pase al gimnasio para realizar una actividad tiene un valor aproximado de **900 pesos argentinos**, podemos estimar la pérdida económica derivada del abandono de clientes durante **2024 y 2025**, suponiendo que cada cliente habría continuado asistiendo a la misma actividad y con la misma ocurrencia.

La pérdida estimada se calcula mediante la siguiente fórmula:

$$

\text{Perdida estimada por abandono} = a \cdot \sum_{i=1}^n p \cdot c_i

$$

donde:

- $\Huge a$ → Cantidad de años que el cliente estuvo ausente.
    
- $\Huge p$ → Precio unitario del pase para ingresar al gimnasio y realizar la actividad.
    
- $\Huge c_i$ → Cantidad de pases que el cliente habría registrado en cada uno de los años ausentes ($i = 1, 2, \dots, n$).


La pérdida estimada por abandono, calculada por segmento, es la siguiente:

- **Segmento `no_volvio_2023`**: $31.244.400
    
- **Segmento `ganado_2024`**: $5.093.100
    
- **Segmento `perdido_2025`**: $24.898.400
    

**Total estimado por abandono:** **$61.326.900**

>Esta cifra refleja el impacto económico de **no aplicar estrategias de retención**, resaltando la importancia de implementar técnicas de fidelización.


### Puntos a destacar

- El segmento `no_volvio_2023` es el más crítico, representando casi el 50% de los abandonos.
    
- Los jóvenes son la franja etaria con mayor abandono (47%), seguidos por adultos jóvenes (29.8%).
    
- El impacto económico es significativo ($61.3 millones)

### Fieles


Mediante el análisis de datos se detectó que, hasta el **17/07/2025**, un total de **2349 clientes** nos eligen. A continuación, se detallan las condiciones de abandono según el segmento de clientes:

| segmento           | Definición resumida                                | Cantidad |
| ------------------ | -------------------------------------------------- | -------- |
| `fiel`             | Clientes presentes en 2023, 2024 y 2025            | 1158     |
| `ganado_2025`      | Clientes que asistieron solo en 2025               | 582      |
| `ganado_2024_2025` | Clientes ganados en 2024 y que siguen en 2025      | 418      |
| `intermitente`     | Clientes presentes en 2023 y 2025, pero no en 2024 | 191      |
los datos se distribuyen de la siguiente manera:

| segmento         | Jóvenes | Adultos Jóvenes | Adultos Medios | Adultos Mayores | Seniors |
| ---------------- | ------- | --------------- | -------------- | --------------- | ------- |
| fiel             | 414     | 404             | 275            | 62              | 3       |
| ganado_2024_2025 | 205     | 115             | 78             | 15              | 5       |
| ganado_2025      | 277     | 178             | 101            | 21              | 5       |
| intermitente     | 104     | 54              | 26             | 7               | 0       |
en términos porcentuales:

| segmento         | Jóvenes | Adultos Jóvenes | Adultos Medios | Adultos Mayores | Seniors | Total_C |
| ---------------- | ------- | --------------- | -------------- | --------------- | ------- | ------- |
| fiel             | 17.62   | 17.20           | 11.71          | 2.64            | 0.13    | 49.30   |
| ganado_2024_2025 | 8.73    | 4.90            | 3.32           | 0.64            | 0.21    | 17.79   |
| ganado_2025      | 11.79   | 7.58            | 4.30           | 0.89            | 0.21    | 24.78   |
| intermitente     | 4.43    | 2.30            | 1.11           | 0.30            | 0.00    | 8.13    |
| **Total_F**      | 42.57   | 31.97           | 20.43          | 4.47            | 0.55    | 100.00  |

### Observaciones por segmento

- **Fiel**: 49.3% de la base que se mantuvo son clientes presentes los tres años (2023, 2024, 2025) mucho muy importante quiere decir que estos clientes nos eligen siempre

- **Ganado_2025** (clientes nuevos de 2025): 24.7%.

- **Ganado_2024_2025**: 17.7%, lo que indica un aporte importante de nuevas incorporaciones recientes.

- **Intermitentes** (2023 y 2025, pero ausentes en 2024): 8.1%, un pequeño porcentaje que retorna tras una ausencia importante retenerlo, porque indican que abandonan las actividades físicas y cuando vuelven nos eligen 

  
### Observaciones por franja etaria

La retención de clientes muestra una marcada concentración en los grupos más jóvenes:

- **Jóvenes**: representan el **42.5%** de la base retenida, siendo el segmento más numeroso y con mayor fidelidad.
    
- **Adultos jóvenes**: aportan el **31.9%**, conformando junto con los Jóvenes más del 70% de los clientes que se mantienen activos.
    
- **Adultos medios**: suponen el **20.4%**, un grupo relevante pero significativamente menor que los dos primeros.
    
- **Adultos mayores**: constituyen el **4.5%**, lo que refleja una menor presencia en la retención.
    
- **Seniors**: apenas el **0.5%**, evidenciando una participación casi marginal en la continuidad del servicio.
    


### Conexión con el abandono

- En los datos de abandono, los jóvenes también son el grupo que más pierde clientes (47%).

- Aunque son la base más numerosa de clientes activos, también son los que más se van si no hay estrategias de fidelización específicas.

- El segmento **fiel** representa casi la mitad de la base activa, pero los clientes “nuevos” de uno o dos años (**Ganado_2025** y **Ganado_2024_2025**) suman más del 42% de la base.

- Si no se retienen, pasarán a engrosar las filas del abandono en los próximos periodos.

  
### Interpretación general

- Fuerte dependencia de las franjas jóvenes para sostener el volumen de clientes.

- Alta rotación: casi la mitad de la base activa no tiene más de dos años de antigüedad.

- El mayor riesgo está en **no consolidar a los nuevos clientes para que pasen a ser fieles**, ya que ahí se concentra la estabilidad de la base.

### Análisis de asistencias de los clientes que no abandonaron

De los clientes que no abandonaron, se contabilizó un total de **209651 registros de asistencia**. A continuación se presentan los valores absolutos y porcentajes por segmento y franja etaria:


| segmento         | Jóvenes | Adultos Jóvenes | Adultos Medios | Adultos Mayores | Seniors |
| ---------------- | ------- | --------------- | -------------- | --------------- | ------- |
| fiel             | 52,605  | 63,031          | 53,028         | 13,281          | 961     |
| ganado_2024_2025 | 6,911   | 5,370           | 4,346          | 617             | 275     |
| ganado_2025      | 1,910   | 1,382           | 971            | 401             | 20      |
| intermitente     | 1,922   | 1,834           | 541            | 245             | 0       |


| segmento         | Jóvenes | Adultos Jóvenes | Adultos Medios | Adultos Mayores | Seniors | TotalC |
| ---------------- | ------- | --------------- | -------------- | --------------- | ------- | ------ |
| fiel             | 25.09   | 30.06           | 25.29          | 6.33            | 0.46    | 87.24  |
| ganado_2024_2025 | 3.30    | 2.56            | 2.07           | 0.29            | 0.13    | 8.36   |
| ganado_2025      | 0.91    | 0.66            | 0.46           | 0.19            | 0.01    | 2.23   |
| intermitente     | 0.92    | 0.87            | 0.26           | 0.12            | 0.00    | 2.17   |
| **TotalF**       | 30.22   | 34.16           | 28.09          | 6.94            | 0.60    | 100.00 |



### Observaciones por segmento

- **Fiel**: Con **186.407 asistencias** (87.24% del total), es lógico que concentre la mayor cantidad de registros, ya que corresponde a clientes activos en todos los años analizados.
    
- **Ganado_2024_2025**: Aporta **17.562 asistencias** (8.36%), lo que refleja una incorporación reciente pero significativa.
    
- **Ganado_2025**: Representa **4.697 asistencias** (2.23%), siendo clientes nuevos del último año.
    
- **Intermitente**: Registra **4.552 asistencias** (2.17%), mostrando un patrón de retorno tras un período de inactividad.

### Observaciones por franja etaria

- **Jóvenes**: 30.22% de las asistencias, primer grupo en volumen.
    
- **Adultos jóvenes**: 34.16%, el segmento con mayor proporción dentro de los clientes activos.
    
- **Adultos medios**: 28.09%, con una participación también relevante.
    
- **Adultos mayores**: 6.94%, con menor peso en la distribución total.
    
- **Seniors**: 0.6%, presencia casi marginal en el total de registros.

### Interpretación general

Más del 60% de las asistencias provienen de clientes menores de 40 años (Jóvenes + Adultos jóvenes), lo que evidencia una fuerte concentración en segmentos etarios más jóvenes y abre la oportunidad de fortalecer estrategias para atraer y retener a los grupos de mayor edad.

# Conclusión General

El análisis revela una base activa de **2.349 clientes** al 17/07/2025, con una fuerte concentración en segmentos jóvenes: **más del 74%** tiene menos de 40 años, y el **42.5%** pertenece al grupo “Jóvenes”. Esta estructura etaria es una fortaleza para el presente, pero también un riesgo para el futuro si no se diversifica la captación hacia segmentos de mayor edad.

La **fidelidad** es un factor crítico: el segmento **fiel** (clientes presentes los tres últimos años) representa el **49.3% de la base activa** y concentra el **87% de las asistencias**, confirmando que los clientes consolidados son quienes más usan el servicio. Sin embargo, **casi la mitad de la base actual** corresponde a clientes de **uno o dos años de antigüedad** (Ganado_2025 y Ganado_2024_2025), lo que refleja **alta rotación** y dependencia de incorporaciones recientes.

Los datos de abandono muestran que los **jóvenes son el grupo que más se gana, pero también el que más se pierde** (47% del abandono). Esto implica que sin estrategias de fidelización específicas para este segmento, el flujo constante de altas y bajas puede erosionar la estabilidad de la base.

En términos de uso, se registraron **209.651 asistencias** entre los clientes activos. El patrón es claro: a mayor antigüedad, mayor frecuencia de asistencia. Los nuevos e intermitentes participan menos, lo que indica que la vinculación inicial y la reactivación requieren programas más sólidos para que evolucionen hacia el perfil “fiel”.

**En síntesis**, el negocio se sostiene actualmente sobre tres pilares:

1. **Clientes fieles** que aportan volumen y constancia.
    
2. **Alta captación de jóvenes** que mantiene la base pero con un riesgo elevado de abandono.
    
3. **Dependencia de nuevos clientes** para sostener el crecimiento, lo que obliga a diseñar estrategias de conversión rápida hacia la fidelidad.
    

El desafío estratégico inmediato es **reducir la rotación**, **consolidar a los nuevos clientes** y **ampliar la captación hacia segmentos de mayor edad** para diversificar riesgos. Sin esto, el crecimiento podría estancarse y la base actual volverse frágil ante fluctuaciones de retención.
