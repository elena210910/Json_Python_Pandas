# Json_Python_Pandas

Este proyecto tiene como objetivo transformar datos en bruto en formato JSON en un mapa completamente funcional, 
utilizando las bibliotecas ijson, Pandas, matplotlib y seaborn.

Trabajar con grandes conjuntos de datos en formato JSON puede ser un desafío significativo, especialmente si estos conjuntos no caben en la memoria. En tales casos, 
una forma efectiva de explorar y analizar estos datos es combinando instrucciones de línea de comandos y Python.

Para un ejemplo tenemos un conjunto de datos (Datatset) que contiene información sobre la vigilancia de la calidad del aire en la ciudad de Nueva York.

Lamentablemente, la estructura del archivo JSON no la conocemos de antemano. 
Primero, veremos las primeras líneas del archivo air_quality_nyc.
Dado que un archivo JSON es un archivo de texto común, podemos usar un comando de línea de comandos para esto.

![](https://github.com/elena210910/Json_Python_Pandas/blob/main/bash1.PNG)

Vemos que los datos están bien formateados. Ahora necesitamos obtener las claves de primer nivel.
 
![](https://github.com/elena210910/Json_Python_Pandas/blob/main/bash2.PNG)

Ahora que conocemos las claves principales donde pueden estar los datos que necesitamos, pasemos a Python y usemos las bibliotecas ijson y pandas.
Dado que suponemos que nuestro archivo no cabe en la memoria RAM, no podemos simplemente leerlo usando la biblioteca json. En su lugar, lo leeremos secuencialmente, ahorrando memoria.

Lo hare utilizando el paquete ijson, que analizará el archivo JSON de manera iterativa en lugar de cargarlo todo en la memoria de una vez. Esto es más lento que la lectura directa en memoria, pero me permite trabajar con los archivos grandes que no caben en la memoria.

[Aqui esta el codico de Python](https://github.com/elena210910/Json_Python_Pandas/blob/main/code_python) 

*RESUMEN del codico:*
Extraímos los nombres de las columnas: Usando la clave meta, obtuvimos los nombres de todas las columnas para saber qué datos están disponibles.
Seleccionamos las columnas necesarias: Decidimos cuáles columnas nos interesan para el análisis.
Leímos los datos línea por línea: Con ijson, leímos los datos de la clave data de manera secuencial para no cargar todo el archivo en la memoria.
Creamos un DataFrame: Convertimos los datos leídos en una tabla pandas para facilitar el análisis.
Analizamos los datos: Filtramos los datos para PM 2.5, encontramos el área más contaminada y calculamos los valores medios por área.
Construimos un gráfico: Visualizamos las 10 áreas más contaminadas usando matplotlib y seaborn.

![](https://github.com/elena210910/Json_Python_Pandas/blob/main/10_top.png)




