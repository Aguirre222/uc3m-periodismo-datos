# Practica-4-historia-periodismo-datos

## Enlaces a las infografías

Contaminación acústica 18 de marzo: https://datawrapper.dwcdn.net/Gx1PL/3/

Contaminación acústica 18 de abril: https://datawrapper.dwcdn.net/6pxb0/2/


![Infografía 1](imagenes/imagen-01-practica-4.png)

![Infografía 2](imagenes/imagen-02-practica-4.png)

Estos diagramas de puntos (dot plot) permiten observar lo alejados que están unos de otros los niveles de ruido registrados en cada una de las 30 estaciones de la Red Fija de Vigilancia de la Contaminación Acústica. Con el eje x puedo localizar el valor numérico de los puntos y con el eje y puedo ubicar la estación de cada dato. La interactividad de la visualización también me permite ver específicamente los valores de cada uno de los puntos, que poseen un color rojo representativo de la bandera municipal y autonómica de Madrid.

## Memoria

### Proceso de selección y limpieza de datos


Para seleccionar la información de este trabajo acudí al portal “datos.gob.es” que es la plataforma en la que se organiza y categoriza el Catálogo Nacional de Datos Abiertos. En este trabajo decidí centrarme en la contaminación acústica dentro de la ciudad de Madrid y, finalmente, usando para acotar el periodo en el que quiero centrarme, busqué específicamente los niveles de contaminación acústica en la ciudad durante el primer año de la pandemia de COVID-19 (2020). El enlace del conjunto de datos que escogí finalmente es [este] (https://datos.gob.es/es/catalogo/l01280796-covid-19-contaminacion-acustica-datos-diarios-con-actualizacion-semanal).

Mi objetivo es comparar los niveles de contaminación acústica en la ciudad en dos días distintos (el 18 de marzo y el 18 de abril) y, por ende, escogí el archivo “.csv” de los datos diarios de contaminación acústica recogidos por las 30 estaciones de Red Fija de Vigilancia de la Contaminación Acústica (una serie de estaciones repartidas por la ciudad que se encargan de captar información relativa a la condición acústica de su entorno).
Una vez descargado el archivo, usé Openrefine para limpiar los datos y quedarme solo con los del 18 de marzo, en un primer archivo, y los del 18 de abril, en otro. Para ambos casos usé la siguiente configuración inicial:

![Imagen 1](imagenes/imagen-1-practica-4.png)

Dentro del proyecto usé las transformaciones comunes en la columna “Fechas” para que las celdas fueran leídas en formato fecha y, a continuación, usé la faceta de línea de tiempo y la selección mediante estrellas para borrar todos los datos anteriores al 18 de marzo de 2020. Para la visualización solo me interesaban los datos numéricos recogidos en la columna “LAeq24h”, que se refieren al “Nivel sonoro equivalente diario”, ya que me parecen los más representativos de toda la información recogida en toda una jornada. De manera que borré las columnas “Ld”, “Le” y “Ln” que se refieren, respectivamente, al “nivel sonoro continuo equivalente del periodo día”, “nivel sonoro continuo equivalente del periodo tarde” y “nivel sonoro continuo equivalente del periodo noche”. Después creo una nueva columna basada en “Estación”. La llamo “Estaciones” y en la caja de texto en lenguaje GREL escribo la expresión "Estación "+ value”. Así, cuando quiera crear la gráfica a partir de estas columnas las estaciones serán leídas como texto y no como número por Datawrapper. Finalmente borro la columna “Estación” para tener las 3 columnas con las que quiero trabajar:

![Imagen 2](imagenes/imagen-2-practica-4.png)

![Imagen 3](imagenes/imagen-3-practica-4.png)

Para el archivo con los datos del 18 de abril sigo exactamente los mismos pasos, pero borro los datos anteriores al 18 de abril.

### Proceso de creación de infografías


Tras subir el archivo a Datawrapper y esconder la columna de fechas de la visualización (pues no es adecuada para la infografía que pienso hacer) elijo el diagrama de puntos (dot plot) como forma de visualizar mi información y le pongo como título “Contaminación acústica (en db) de Madrid 18 de marzo/abril 2020”. Como la información se refiere a la contaminación acústica en Madrid elegí un color rojo oscuro para los puntos de ambos diagramas.

![Imagen 4](imagenes/imagen-4-practica-4.png)

![Imagen 5](imagenes/imagen-5-practica-4.png)

El formato de los números es 1,000[.00] como se ve en la imagen inferior. La etiqueta de “Estaciones” la alineo a la izquierda, en las anotaciones pongo mi nombre en la firma y vinculo el origen de los datos. Finalmente, publico la imagen y copio el enlace resultante.

![Imagen 6](imagenes/imagen-6-practica-4.png)


![Imagen 7](imagenes/imagen-7-practica-4.png)



### Historia de periodismo de datos (comentario de las infografías):

En estas dos infografías de diagrama de puntos podemos ver representados los niveles de ruido en dos días distintos recogidos por las 30 estaciones fijas en la ciudad de Madrid. Ambos días, 18 de marzo y abril, se enmarcan dentro del estado de alarma impuesto para frenar el avance del Covid-19. Durante este “confinamiento duro” la actividad cotidiana se detuvo y se restringió la libre circulación por las calles, por lo que el tráfico peatonal y vehicular se vio drásticamente reducido en este período (que arranca oficialmente el 15 de marzo). Esto último es relevante, pues el tráfico en Madrid es el culpable de más del [80% del ruido en la ciudad](https://www.europapress.es/madrid/noticia-trafico-causante-mas-80-contaminacion-acustica-madrid-20180424183441.html).

Así pues, como lo predecible es que se note un gran cambio en los niveles de ruido que se registran en la capital, es interesante comparar la información de ambas infografías con el ruido en Madrid antes de la pandemia. En la primera infografía, la del 18 de marzo, vemos que la mayoría de puntos se ubican en el rango entre los 50 y los 63 decibelios de ruido; en la segunda se registran menores niveles de ruido: ningún punto sobrepasa la línea de los 63 decibelios (como sí ocurría con 3 estaciones en marzo) y la mayoría de puntos se encuentra entre los 49 y los 59 db. De media, el 18 de marzo de 2020 se registró en Madrid capital un ruido de 57,52 db y el 18 abril el promedio fue de 55,78 db. Si los comparamos con los niveles de otros años vemos que el descenso en los niveles de ruido ha sido notable: la media de ruido [entre enero y julio de 2018 fue de 61,91](https://ecodiario.eleconomista.es/espana/noticias/9404771/09/18/Madrid-sobrepasa-un-27-los-limites-de-contaminacion-acustica-por-las-noches.html#:~:text=La%20contaminaci%C3%B3n%20ac%C3%BAstica%20en%20Madrid,en%202014%2C%202016%20y%202017) (e históricamente la media anual ha sido de 61,98). La media de ruido total de [abril de 2020 fue de 57,29,](https://www.lavanguardia.com/local/madrid/20200510/481066782790/madrid-registra-4-decibelios-menos-de-ruido-en-sus-calles-que-antes-del-confinamiento.html) una cifra bastante por debajo de la media anual histórica de la ciudad y que desciende en más de 3 db al registro de abril de 2019 (60,67db).

Estos datos superan el umbral marcado por [la Unión Europea](https://www.europapress.es/madrid/noticia-trafico-causante-mas-80-contaminacion-acustica-madrid-20180424183441.html) y por la [Ordenanza de Protección contra la Contaminación Acústica y Térmica madrileña](https://sede.madrid.es/sites/v/index.jsp?vgnextoid=0130511f3649e210VgnVCM2000000c205a0aRCRD&vgnextchannel=6b3d814231ede410VgnVCM1000000b205a0aRCRD), que establece un límite de ruido de 55 db de día y 45 de noche en zonas residenciales. En ambas infografías la mayoría de estaciones, tanto el 18 de marzo como en abril, registran niveles superiores a 55db: en el diagrama del 18 de marzo solo 8 estaciones registran un nivel de ruido medio inferior a 55db, en la infografía del 18 de abril este número asciende a 12 estaciones. Si bien la muestra de ambas visualizaciones se limita a un solo día en cada caso, teniendo en cuenta los promedios antes mencionados y los registros habituales de la ciudad, puedo afirmar que los efectos del confinamiento son visibles en estos dos diagramas de puntos.




