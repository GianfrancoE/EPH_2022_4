# EPH_2022_4
Análisis de datos encuesta permanente de hogares 2022 último Q


# Presentación y uso del código 1ra parte: Análisis de datos
Con el código creado, se hace un análisis de datos realizado en un entorno de Colaboratory de Google. Comienza importando las bibliotecas necesarias, como pandas, numpy, matplotlib.pyplot, entre otros que son utilizadas para el análisis y visualización de datos.

A continuación, se carga un archivo CSV llamado "usu_individual_T422.csv" en un DataFrame de pandas llamado "df". Luego, se realizan algunas operaciones de limpieza y transformación en el DataFrame. Se renombran las columnas utilizando un diccionario de mapeo, se filtran y seleccionan solo las columnas de interés, y se realiza la transformación logarítmica de una columna específica (relacionada al ingreso)

Después de las operaciones de limpieza y transformación, se realizan diferentes visualizaciones de los datos utilizando gráficos de violín y gráficos de barras, para analizar las distribuciones y las relaciones entre variables. También se realiza un test de normalidad en una columna específica utilizando el test de normalidad de Shapiro-Wilk.

Posteriormente, se calculan estadísticas descriptivas como el ingreso medio por región, la desviación estándar por región y la desviación estándar total del dataframe. Además, se realiza una prueba t independiente para comparar los ingresos entre diferentes regiones.

Luego, se muestra un dotplot para representar la media de ingresos por edad y un gráfico de barras para representar la media de ingresos por deciles. Por último, se imprime la media de ingresos por decil.

Al final del código, se vuelve a cargar el archivo CSV original en otro DataFrame llamado "df" y se repiten las mismas operaciones de limpieza y transformación que se realizaron anteriormente.

# Presentación y uso del código 2da parte: Modelo de regresión
Este fragmento de código implementa un modelo de regresión utilizando el algoritmo Random Forest. Se dividen los datos en conjuntos de entrenamiento y prueba, se definen las variables predictoras y la variable objetivo. Se entrena el modelo y se realizan predicciones en el conjunto de prueba. Se evalúa el rendimiento mediante el cálculo del error cuadrático medio (RMSE) y se visualiza la importancia de las variables en un gráfico de barras. Además, se calcula el coeficiente de determinación (R^2) y se obtienen métricas adicionales. 

La sección final del código utiliza la técnica RFECV (Recursive Feature Elimination with Cross-Validation) junto con un modelo de Random Forest para seleccionar las variables más relevantes en un problema de regresión. El RFECV realiza una evaluación recursiva y validación cruzada para determinar qué variables tienen un mayor impacto en el modelo. Se imprimen las variables seleccionadas y se realizan predicciones en el conjunto de prueba utilizando solo esas variables. Luego, se calcula el error cuadrático medio (RMSE) entre las predicciones y los valores reales para evaluar el rendimiento del modelo. Este enfoque ayuda a identificar las características más importantes y simplifica el modelo al utilizar solo las variables clave para la predicción, lo que puede mejorar la eficiencia y la interpretación del modelo. Esto se utilizó porque el modelo presentaba mucho overfitting con la complejidad que tenía. De esta manera se redujo un poco el overfitting pero no se pudo corregir de la manera deseada.

# Conclusiones del análisis

*Distribución de ingresos por región*

El gráfico de violín muestra la distribución del monto de ingreso ocupación principal en función de la región.  El logaritmo del ingreso graficado es más interesante para mostrar porque ayuda a visualizar mejor las diferencias entre las regiones en términos de magnitud relativa de los ingresos. Al aplicar el logaritmo, los valores extremadamente altos o bajos se atenuarían, lo que permitiría una mejor comparación entre las regiones. Además, al utilizar una escala logarítmica, se pueden apreciar mejor las variaciones en los ingresos en un rango más amplio, lo que puede revelar patrones o tendencias ocultas en los datos. Tanto para aplicar la escala logarítmica de los ingresos como para visualizar mejor los datos previo a eso, se quitaron todos los ingresos iguales a cero.

![image](https://github.com/GianfrancoE/EPH_2022_4/assets/137568096/01b11afc-43b7-4140-831a-6f1f406322e7)
![image](https://github.com/GianfrancoE/EPH_2022_4/assets/137568096/3d44e717-837c-46fb-bb8b-157d8e36ae85)





