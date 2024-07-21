# _***Prediccion de enfermedades cardiacas***_

Para este analisis se dispone de un conjunto de datos en formato `csv` que contiene la informacion de varias métricas de salud de pacientes cardíacos, este conjunto incluye datos como la edad, la presión arterial, la frecuencia cardíaca, colesterol, gleusemia entre otros.

Se realizara un modelo el cual hara la predicción de enfermedades cardiacas en una persona, para esto se tiene un conjunto de datos donde esta alojada la información de varias métricas de salud de pacientes cardíacos a la cual se le realizara una limpieza de datos para poder hacer calculos precisos para una prediccion optima, fuera de eso se implementaran las tecnicas de analisis exploratorio las cuales ayudaran a analizar los datos de una manera visual para entender los datos mas facil, luego se seleccionara el algoritmo de regresion el cual servira para entrenar el modelo de datos y de acuerdo a los resultados de las metricas calculadas por el modelo se analizara cual de los modelos es mas acertivo en la precicción.

Una vez se tiene el modelo de datos con mayor acertividad en las predicciones cardiopaticas se hara una simulación donde se le pasaran por parametro cada uno de los valores de las metricas de cada paciente, dichos valores son los campos que contiene el conjunto de datos y de acuerdo a dichas metricas el sistema dira si esa persona tiene o no problemas cardiacos.

## _***Fuente de datos***_

En la siguiente `URL` se encuentran alojados los datos de las personas con problemas cardiacos que ayudaran a hacer el analisis de la problematica. Esta `URL` pertenece a la plataforma GitHub y servira para cargar el conjunto de datos en el notebook.

```
https://raw.githubusercontent.com/GabrielCastro1221/csv_dataScience/main/heart1.csv
```

## _***Información sobre el conjunto de datos***_

CAMPO            | DESCRIPCION
-----------------|------------------------------------------------------------------------
_***AGE***_      | Edad del paciente
_***SEX***_      | Sexo del paciente: 0 = Hombre - 1 = Mujer
_***CP***_       | Tipo de dolor en el pecho: 0 = angina tipica - 1 = angina atipica - 2 dolor no anginoso - 3 = asintomatico
_***TRESTBPS***_ | Presión arterial en reposo en mm Hg
_***CHOL***_     | Colesterol sérico en mg/dl
_***FBS***_      | Nivel de azúcar en la sangre en ayunas, clasificado como superior a 120 mg/dl: 1 = Verdadero - 0 = Falso
_***RESTECG***_  | Resultados electrocardiográficos en reposo: 0 = Normal - 1 = Tener anomalía de la onda ST-T - 2 = Mostrando hipertrofia ventricular izquierda probable o definitiva.
_***THALACH***_  | Frecuencia cardíaca máxima alcanzada durante una prueba de esfuerzo
_***EXANG***_    | Angina inducida por el ejercicio: 1 = Si - 0 = No
_***OLDPEAK***_  | Depresión del ST inducida por el ejercicio en relación con el reposo
_***SLOPE***_    | Pendiente del segmento ST del ejercicio máximo: 0 = pendiente ascendente - 1 = Plana - 2 = pendiente descendente
_***CA***_       | Número de vasos principales (0-4) coloreados por fluoroscopia
_***THAL***_     | Resultado de la prueba de esfuerzo con talio: 0 = Normal - 1 = Defecto solucionado - 2 = defecto reversible - 3 = No descrito
_***TARGET***_   | Estado de enfermedad cardíaca: 0 = Sano - 1 = Enfermo

## _***Librerias utilizadas en el Notebook***_

+ `Warnings`: se utiliza para controlar los mensajes de advertencia
+ `Pandas`: permite trabajar con datos estructurados de manera eficiente.
+ `Numpy`: Permite crear vectores y matrices grandes multidimensionales, junto con una gran colección de funciones matemáticas de alto nivel.
+ `MatplotLib`: Permite generar gráficos en dos dimensiones, a partir de datos contenidos en listas o diccionarios de datos.
+ `seaborn`: Proporciona una interfaz de alto nivel para crear gráficos estadísticos informativos.

## _***Metodos Utilizados en el Notebook***_

+ `pd.read_csv`: Este metodo de la libreria `pandas` permite cargar el conjunto de datos proveniente de la URL de github en el proyecto.
+ `info`: Este metodo de la libreria `pandas` proporciona información detallada del conjunto de datos.
+ `astype`: Este metodo de la libreria `pandas` permite hacer tranformaciones de datos sobre el conjunto de datos en el que se esta trabajando.
+ `describe`: Este metodo de la libreria `pandas` muestra los datos estadisticos de los datos numericos del conjunto de datos.
+ `describe(include="object")`: Este metodo de la libreria `pandas` muestra el resultado de los datos categoricos del conjunto de datos.
+ `plt.subplots`: Este metodo de la libreria `MatPlotLib` le asigna las dimensiones a la visualización
+ `np.floor & np.ceil`: Este metodo de la libreria `numpy` asigna un rango de columnas y celdas a las visualizaciones generadas.
+ `sns.histplot`: Este metodo de la libreria `seaborn` permite crear una visualizacion tipo histograma.
+ `plt.suptitle`: Este metodo de la libreria `MatPlotLib` permite agregarle un subtitulo alucivo a lo que se representa en los graficos.
+ `plt.tight_layout`: Este metodo de la libreria `MatPlotLib` permite automatizar la distribucion de los datos en la visualización
+ `plt.subplots_adjust`: Este metodo de la libreria `MatPlotLib` permite agregar espaciado perzonalido a las visualizaciones.
+ `plt.show`: Este metodo de la libreria `MatPlotLib` permite mostrar el grafico en el notebook.
+ `difference`: Este metodo de la libreria `pandas` permite hacer la diferencia de entre conjuntos de datos.
+ `value_counts`: Este metodo de la libreria `pandas` se utiliza para contar la frecuencia de valores unicos en una serie de datos.
+ `sort_values`: Este metodo de la libreria `pandas` Sirve pa ordenar valores de una o mas columnas.
+ `set_palette`: Este metodo de la  libreria `seaborn` Sirve pa asignar colores personalizados a las visualizaciones.
+ `sns.barplot`: Este metodo de la libreria `seaborn` permite crar una visualización de barras.
+ `sns.kdeplot`: Este metodo de la libreria `seaborn` permite ajustar la apariencia del grafico segun la probabilidad de las variables basadas en la serie de datos.

## _***Glosario***_

1. _***Data wrangling***_ `Limpieza de datos`: también conocido como data munging, es el proceso de limpiar, estructurar y enriquecer conjuntos de datos crudos en formatos más utilizables para análisis. Implica transformar datos en diferentes formatos, fusionar conjuntos de datos, detectar y corregir errores en los datos, así como manejar valores faltantes y asegurar que los datos estén en el formato adecuado para su análisis.

2. _***Datos categoricos***_: son un tipo de datos que representan características y cualidades, en lugar de cantidades numéricas. Estos datos se dividen en categorías o grupos discretos y finitos.

3. _***Datos continuos***_: son otro tipo de datos que representan valores numéricos que pueden tomar cualquier valor dentro de un intervalo específico.

4. _***Exploratory data analysis***_ `EDA`: Es una etapa fundamental en el proceso de análisis de datos, donde se utilizan técnicas estadísticas y gráficas para explorar y entender los datos antes de aplicar métodos más avanzados o realizar inferencias.

5. _***Analisis univariado***_: Es una técnica estadística que se centra en analizar una sola variable a la vez. Es decir, examina las características y propiedades de una variable sin considerar otras variables simultáneamente. Este tipo de análisis es fundamental en estadística descriptiva y suele ser el primer paso en la exploración de datos.

6. _***Analisis bivariado***_: Es una técnica estadística que se centra en estudiar la relación entre exactamente dos variables al mismo tiempo. A diferencia del análisis univariado, que se enfoca en una sola variable a la vez, el análisis bivariado explora cómo varía una variable en relación con otra.

7. _***IQR***_: Medida estadística utilizada para describir la dispersión de un conjunto de datos. Es especialmente útil para identificar y manejar valores atípicos.

8. _***Transformacion Box-Cox***_: La transformación Box-Cox es un método poderoso para estabilizar la varianza y hacer que los datos se parezcan más a una distribución normal. Es particularmente útil cuando no estás seguro de la naturaleza exacta de la distribución con la que estás tratando, ya que puede adaptarse a la mejor transformación de energía. Sin embargo, la transformación Box-Cox solo funciona para datos positivos, por lo que se debe tener cuidado al aplicarla a entidades que contienen ceros o valores negativos.

9. _***RobustScaler***_: Es una técnica de preprocesamiento de datos utilizada en la normalización de características en un conjunto de datos. Es particularmente útil cuando los datos contienen valores atípicos, ya que el RobustScaler utiliza la mediana y los cuartiles en lugar de la media y la desviación estándar, lo que lo hace más resistente a los outliers.

10. _***Codificación one-hot***_: Es una técnica utilizada en el procesamiento de datos y el aprendizaje automático para representar datos categóricos. Consiste en representar cada categoría como un vector binario donde un único elemento tiene el valor 1 y todos los demás elementos tienen el valor 0. Por ejemplo, si tienes una lista de colores ["rojo", "verde", "azul"], la codificación `one-hot` para "verde" sería [0, 1, 0]. Esta técnica es útil para trabajar con algoritmos de aprendizaje automático que requieren entradas numéricas, ya que permite representar datos categóricos de una manera que el modelo pueda entender.

11. _***Variables nominales:***_ Son variables sin orden inherente. Deben tener codificacion one-hot porque usarlos como números podría introducir un orden no deseado en el modelo.

12. _***Variables ordinales:***_ estas variables tienen un orden inherente. No es necesario que tengan codificacion one-hot, ya que su orden puede proporcionar información significativa al modelo.

13. _***Fuga de datos***_: La fuga de datos se refiere a un error en el preprocesamiento de datos en el que se utiliza información externa al conjunto de datos de entrenamiento para transformar o entrenar el modelo.

14. _***Validacion cruzada***_: Es una técnica utilizada en el aprendizaje automático y en estadística para evaluar la capacidad de generalización de un modelo predictivo. Esta técnica permite utilizar un conjunto de datos de manera más eficiente y proporciona una estimación más precisa del rendimiento del modelo en datos no vistos.

15. _***GridSearchCV***_ es una técnica utilizada para el ajuste de hiperparámetros en el aprendizaje automático, particularmente en el contexto de algoritmos de aprendizaje supervisados.

16. _***StratifiedKFold***_ es una técnica de validación cruzada, particularmente útil cuando se trata de problemas de clasificación. La validación cruzada es esencial para evaluar el rendimiento de un modelo de aprendizaje automático y para ajustar los hiperparámetros sin sobreajustar los datos de entrenamiento.

17. _***Muestreo estratificado***_: Es una técnica de muestreo utilizada para mejorar la representatividad de una muestra al dividir los datos en grupos homogéneos, llamados estratos, y luego seleccionar muestras aleatorias de cada uno de estos estratos. Esto asegura que cada subgrupo de datos esté adecuadamente representado en la muestra.
