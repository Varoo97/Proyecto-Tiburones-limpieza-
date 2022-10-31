# Proyecto-Tiburones-limpieza-
![iron-jaws](https://user-images.githubusercontent.com/114336696/199124364-c5d1a0cd-acb8-4c5d-abca-c29d02ea850f.jpg)




Para este proyecto vamos a limpiar una base de datos de ataques de tiburones, para poder sacar datos congruentes.

Nos hemos puesto como objetivo en esta práctica analizar los años con mayor número de incidentes registrados, el sexo con mayor número de incidencias, el país donde encontramos mayor registro de ataques, las actividades que realizaban los sujetos en el momento del ataque así como si estos ataques fueron fatales o no.

Para la limpieza de datos, empezamos importando pandas y numpy

Nos paramos un momento a observar las dimensiones de nuestro DataFrame, el tipo de dato que encontramos, así como el espacio que ocupa en nuestra memoria.

Antes de nada, podemos observar que existen filas con todo valores nulos y por esto mismo y al estar repetidas, procedemos a eliminar los duplicados.

Tras esto, revisamos el numero de nulos por columna y sacamos el porcentaje

Pintamos una grafíca con todos los valores nulos del DataFrame

Eliminamos las columnas con más de un 80% de valores nulos

Volvemos a revisar que efectivamente el gráfico de nulos a cambiado, así cpmo las dimensiones de nuestro DataFrame

Al solo haber un nulo en la columna 'Case Number', y es un dato que podemos deducir por las otras columnas, lo reemplazamos por el dato correcto

Tras esto, creamos una lista2 con todas las filas donde el valor de la columna 'Date' sea nulo, para que acontinuación pasemos a eliminar esta lista, y por lo tanto eliminemos 9 filas.

Para seguir deshaciendonos de valores nulos, hemos rellenado todos los valores nulos de la columna 'Name' por la palabra 'Unknown'

A continuación, para la columna 'Year' hemos seguido los mismos pasos que para la primera columna de 'Case Number'

Finalmente, para el resto de valores nulos del DataFrame hemos rellenado los valores nulos con 'Unknown'

Volvemos a pintar los valores nulos del DataFrame, para así comprobar que efectivamente hemos conseguido eliminar todos los valores que no nos interesaban

Una vez nos hemos deshecho de todos los nulos, nos disponemos a limpiar las columnas, centrándonos en aquellas que nos son realmente útiles para nuestro objetivo.

Tanto la columna de 'Sex' y de 'Fatal (Y/N)', usamos la función replace, para pasarle nosotros los valores que nos interesa que lleven, y así arreglar el problema.

Tras esto, nos damos cuenta que en la columna 'Species' hay un dato incongruente (invalid), que se repite en 103 filas y por lo tanto, nos es inútil mantenerlas, por lo que las eliminamos.

Además, observamos que existen 4 columnas con la misma información, por lo que limpiamos la primera de ellas 'Case Number', mendiante regex, pasándole el filtro que queremos que pase y una vez hemos conseguido esto sobreescribimos las otras 3. (No borramos columnas)

De la misma manera, aplicando regex, filtramos la columna de 'Activity'

Acto seguido, convertimos la columna 'Year' a integer, para así eliminar los decimales que contiene.

Y finalmente realizamos 'crosstab' para poder ver de manera clara los diferentes valores que se van repitiendo en nuestros parámetros, llegando así a nuestro objetivo y pudiendo sacar conclusiones.
