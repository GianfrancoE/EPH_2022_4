**Para ver el código entren a "Análisis_de_datos.ipynb" y abran el collab.También van a necesitar el archivo que dice "usu_individual_T422.csv". Súbanlo al content y todo debería funcionar si se corren las cosas en orden.**

# Presentación
### Problema
El problema en este estudio de caso consiste en analizar y predecir los ingresos ocupacionales principales basados en diversas características demográficas y educativas. El conjunto de datos contiene información sobre los ingresos, edades, regiones, niveles educativos y otros factores de los individuos. El objetivo es comprender las relaciones entre estas variables, identificar características importantes para predecir los ingresos y desarrollar un modelo de regresión que pueda estimar con precisión los ingresos de las personas en función de sus características.

### Resumen de las conclusiones
El análisis reveló importantes conclusiones sobre los ingresos y su distribución. Los ingresos por región muestran diferencias significativas entre sí, reflejando las desigualdades en Argentina. El nivel educativo también es destacado como un factor clave, mostrando que la educación es un mecanismo para superar la pobreza.
Las estadísticas de ingresos por región revelan variaciones significativas, con la Patagonia teniendo el ingreso promedio más alto y el Nordeste el más bajo. La desviación estándar también varía, reflejando la heterogeneidad dentro de cada región.
Se utilizó un modelo de regresión Random Forest que obtuvo un alto coeficiente de determinación en el conjunto de entrenamiento, pero mostró un rendimiento deficiente en el conjunto de prueba debido al sobreajuste. El análisis de importancia destacó la influencia de la "Edad", "Nivel educativo más alto" y "Región" en la predicción de los ingresos.

### Possibilidades de mejora en base a conclusiones
El análisis revela que existen disparidades regionales significativas en los ingresos, lo cual puede abordarse mediante políticas que fomenten la competitividad y el desarrollo económico en las regiones rezagadas. Esto implica invertir en infraestructura, facilitar la inversión y promover la creación de empleo en áreas con menores ingresos.

Además, se destaca la importancia del nivel educativo para los ingresos. Para promover la movilidad económica, es fundamental fomentar la educación de calidad y orientada hacia las necesidades del mercado laboral. Esto puede lograrse mediante asociaciones público-privadas, programas de capacitación profesional y políticas que incentiven la participación del sector empresarial en la educación.

El análisis también resalta la desigualdad en la distribución de ingresos incluso en zonas con altos niveles de empleo público. Esto indica que en lugar de políticas de redistribución forzada, se puede optar por un enfoque que estimule la creación de oportunidades y el emprendimiento. Esto implica reducir la carga impositiva a las empresas y promover políticas que faciliten la creación de empleo y el crecimiento económico sostenible.

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

## Análisis estadístico 

### Distribución de ingresos por región

El gráfico de violín muestra la distribución del monto de ingreso ocupación principal en función de la región.  El logaritmo del ingreso graficado es más interesante para mostrar porque ayuda a visualizar mejor las diferencias entre las regiones en términos de magnitud relativa de los ingresos. Al aplicar el logaritmo, los valores extremadamente altos o bajos se atenuarían, lo que permitiría una mejor comparación entre las regiones. Además, al utilizar una escala logarítmica, se pueden apreciar mejor las variaciones en los ingresos en un rango más amplio, lo que puede revelar patrones o tendencias ocultas en los datos. Tanto para aplicar la escala logarítmica de los ingresos como para visualizar mejor los datos previo a eso, se quitaron todos los ingresos iguales a cero.

![image](https://github.com/GianfrancoE/EPH_2022_4/assets/137568096/01b11afc-43b7-4140-831a-6f1f406322e7)
![image](https://github.com/GianfrancoE/EPH_2022_4/assets/137568096/3d44e717-837c-46fb-bb8b-157d8e36ae85)

### Test de normalidad del logaritmo del ingreso

Se realizó un test de normalidad en la columna "Log_Monto" del conjunto de datos utilizando el código proporcionado. El objetivo era determinar si la distribución de los datos seguía una distribución normal. Este test es estadísticamente relevante para verificar los supuestos de normalidad en diversos métodos y modelos estadísticos. El resultado del test mostró un estadístico de prueba de 1311.97 y un valor p extremadamente pequeño (1.2860113698269532e-285), lo que indica que los datos no seguían una distribución normal. El test realizado fue el de Shapiro-Wilk.

### Ingresos por región: Estadísticos
Se calculó el ingreso promedio y la desviación estándar del ingreso por región utilizando el dataframe "df". Los resultados se imprimieron en pantalla.

Los resultados muestran que el ingreso promedio por región varía significativamente. En la región de Patagonia, el ingreso promedio es de $126,886.70, seguida por Gran Buenos Aires con $107,105.39 y Pampeana con $89,563.84. Nordeste tiene el ingreso promedio más bajo con $67,647.38.

La desviación estándar del ingreso también presenta diferencias por región. Patagonia tiene la mayor variabilidad en los ingresos con una desviación estándar de $127,199.77, mientras que Nordeste tiene la menor variabilidad con $50,213.70. Esto indica que en Patagonia hay una mayor dispersión de los ingresos, posiblemente debido a diferencias económicas y laborales en esa región.

La desviación estándar total del conjunto de datos es de $78,232.36, lo que refleja la variabilidad general de los ingresos en todas las regiones consideradas.

### Test de significancia
Se realizó la prueba t independiente para comparar los ingresos de cada región con los ingresos de todas las demás regiones. Esto es estadísticamente relevante para determinar si existían diferencias significativas en los ingresos entre las regiones. Se utilizó el test t de Student para comparar las medias de dos grupos.

Los resultados de las pruebas t mostraron que todas las regiones tenían valores p muy bajos, lo que indicaba que había diferencias estadísticamente significativas en los ingresos entre las regiones. Esto implicaba que los ingresos variaban de manera considerable entre las diferentes regiones. Por ejemplo, la región de Patagonia tuvo un valor p extremadamente bajo, lo que sugirió que los ingresos en esta región diferían significativamente de los ingresos en las demás regiones.


### Ingreso medio por edad

Se realizó el cálculo de la media de ingresos por edad y se generó un dotplot para visualizar los resultados. Esto es estadísticamente importante para comprender la relación entre la edad y los ingresos.

El dotplot mostró que el ingreso promedio era menor a 50mil pesos en las edades más jóvenes (menores a 25 años), y luego aumentaba gradualmente hasta alcanzar una media de entre 90 a 120 mil pesos en el rango de edad de 50 a 60 años. Posteriormente, se observó un descenso en la media de ingresos, aunque con mayor variabilidad de resultados debido a la menor cantidad de personas de edad avanzada en la base de datos.

![image](https://github.com/GianfrancoE/EPH_2022_4/assets/137568096/67a16bbe-57c7-4c6d-a678-bcbc855dcd3f)

### Ingreso medio por decil

Se realizó el cálculo de la media de ingresos por deciles y se creó un gráfico de barras utilizando seaborn. Esto es importante para comprender la distribución de los ingresos en diferentes segmentos económicos de la población.

El gráfico de barras muestra las medias de ingresos por decil, donde se observó un aumento gradual en los ingresos a medida que se avanzaba en los deciles. El decil 1 tenía una media de 13,960.72 pesos, mientras que el decil 10 tenía la media más alta con 271,218.55 pesos. Esto indica una distribución pobre de los ingresos en nuestro país.

Estos resultados proporcionan una visión general de la desigualdad de ingresos y pueden ser útiles para comprender la estructura socioeconómica de la muestra estudiada.

![image](https://github.com/GianfrancoE/EPH_2022_4/assets/137568096/306c4a1e-1a21-454a-902c-0d8a1f9a2317)

## Análisis: Modelo de regresión
Se realizó un modelo de regresión utilizando Random Forest para predecir el ingreso ocupacional principal basado en varias características. Se dividió el conjunto de datos en entrenamiento y prueba, se entrenó el modelo y se realizaron predicciones en el conjunto de prueba. Se calculó el error (RMSE) y se evaluaron el coeficiente de determinación (R^2) en ambos conjuntos.

Los resultados muestran que se utilizaron 1,566 datos para el entrenamiento y 14,101 datos para el error, lo que corresponde a una proporción de datos de entrenamiento del 9.99% y una proporción de datos de error del 90.01%. El coeficiente de determinación (R^2) en el conjunto de entrenamiento fue de 0.89, indicando un buen ajuste del modelo a los datos de entrenamiento. Sin embargo, en el conjunto de prueba, el coeficiente de determinación (R^2) fue de 0.22, lo que sugiere un rendimiento inferior del modelo en datos no vistos.

El gráfico de barras de importancia de variables muestra la contribución relativa de cada característica en la predicción del ingreso. Se observa que las variables "Edad" y "Nivel_más_alto_de_educación" tienen una mayor importancia en el modelo.

![image](https://github.com/GianfrancoE/EPH_2022_4/assets/137568096/41de67ba-f270-4858-b494-0ad8345ff66c)


Esta diferencia sugiere que el modelo presenta un caso de overfitting. El coeficiente de determinación alto en el conjunto de entrenamiento indica que el modelo se ajusta muy bien a los datos de entrenamiento, pero su rendimiento se reduce significativamente cuando se evalúa en datos no vistos (conjunto de prueba). El bajo coeficiente de determinación en el conjunto de prueba indica que el modelo no generaliza bien y tiene dificultades para hacer predicciones precisas en nuevos datos. Para corregir el overfitting, se pueden considerar técnicas como la regularización, la reducción de características o el ajuste de los hiperparámetros del modelo.


