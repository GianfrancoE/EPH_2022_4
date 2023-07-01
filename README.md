# EPH_2022_4
Análisis de datos encuesta permanente de hogares 2022 último Q


# Presentación y uso del código
Con el código creado, se hace un análisis de datos realizado en un entorno de Colaboratory de Google. Comienza importando las bibliotecas necesarias, como pandas, numpy, matplotlib.pyplot, entre otros que son utilizadas para el análisis y visualización de datos.
A continuación, se carga un archivo CSV llamado "usu_individual_T422.csv" en un DataFrame de pandas llamado "df". Luego, se realizan algunas operaciones de limpieza y transformación en el DataFrame. Se renombran las columnas utilizando un diccionario de mapeo, se filtran y seleccionan solo las columnas de interés, y se realiza la transformación logarítmica de una columna específica (relacionada al ingreso)

Después de las operaciones de limpieza y transformación, se realizan diferentes visualizaciones de los datos utilizando gráficos de violín y gráficos de barras, para analizar las distribuciones y las relaciones entre variables. También se realiza un test de normalidad en una columna específica utilizando el test de normalidad de Shapiro-Wilk.

Posteriormente, se calculan estadísticas descriptivas como el ingreso medio por región, la desviación estándar por región y la desviación estándar total del dataframe. Además, se realiza una prueba t independiente para comparar los ingresos entre diferentes regiones.

Luego, se muestra un dotplot para representar la media de ingresos por edad y un gráfico de barras para representar la media de ingresos por deciles. Por último, se imprime la media de ingresos por decil.

Al final del código, se vuelve a cargar el archivo CSV original en otro DataFrame llamado "df" y se repiten las mismas operaciones de limpieza y transformación que se realizaron anteriormente.

# Conclusiones del análisis
