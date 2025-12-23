\# Clasificador KNN de Dígitos 



Este proyecto implementa y compara varias técnicas de reducción de dimensionalidad (PCA, SVD, KernelPCA, LDA) junto con un clasificador K-Nearest Neighbors (KNN) para la clasificación de dígitos escritos a mano utilizando el conjunto de datos `digits` de scikit-learn formado por imágenes de dígitos de 64px.



\## Contenido del Proyecto



El notebook está estructurado en las siguientes secciones:



1\.  \*\*Análisis del conjunto de datos\*\*: Carga y exploración inicial del dataset, incluyendo la visualización de dígitos individuales, la media y la desviación estándar de cada dígito.

2\.  \*\*División (train, test) y normalización\*\*: Se divide el conjunto de datos en entrenamiento y prueba, y se normalizan los datos utilizando `StandardScaler` de scikit-learn y manualmente.

3\.  \*\*Proyección de los componentes principales\*\*: Aplicación de PCA, SVD, KernelPCA y LDA para reducir la dimensionalidad de los datos, tanto con datos originales como con datos normalizados.

4\.  \*\*Visualización de la Proyección\*\*: Muestreo de los datos proyectados en 3D para observar la separación de las clases.

5\.  \*\*Predicción\*\*: Entrenamiento de modelos KNN con los datos transformados por cada técnica de reducción de dimensionalidad y evaluación de su rendimiento.

6\.  \*\*Análisis de resultados\*\*: Función para calcular la precisión mediante validación cruzada.

7\.  \*\*Búsqueda de algoritmo y valores óptimos\*\*: Implementación de `GridSearchCV` para encontrar los mejores hiperparámetros (número de componentes y número de vecinos `k` para KNN) para cada técnica de reducción de dimensionalidad, con y sin normalización.

8\.  \*\*Visualizar la evolución de la búsqueda\*\*: Graficación del rendimiento de cada pipeline en función del número de componentes y `n\_neighbors`.



\## Dependencias



Este proyecto requiere las siguientes librerías de Python:



\*   `numpy`

\*   `sklearn` (scikit-learn)

\*   `matplotlib`

\*   `pandas`



Para instalar las dependencias, puedes usar `pip`:



```bash

pip install numpy scikit-learn matplotlib pandas

```



\## Cómo Ejecutar el Proyecto



1\.  Clona este repositorio:

&nbsp;   ```bash

&nbsp;   git clone <URL\_DEL\_REPOSITORIO>

&nbsp;   cd <NOMBRE\_DEL\_REPOSITORIO>

&nbsp;   ```

2\.  Abre el notebook en Google Colab o en tu entorno de desarrollo Jupyter preferido.

3\.  Ejecuta las celdas del notebook secuencialmente para replicar el análisis y los resultados.



\## Resultados Clave del Análisis de GridSearchCV



La búsqueda de hiperparámetros óptimos reveló los siguientes mejores rendimientos:



\*   \*\*PCA\*\*: Best Score: 0.9889, Best Params: `{'kneighborsclassifier\_\_n\_neighbors': 1, 'pca\_\_n\_components': 35}`

\*   \*\*PCA\_SS (Standard Scaled)\*\*: Best Score: 0.9769, Best Params: `{'kneighborsclassifier\_\_n\_neighbors': 4, 'pca\_\_n\_components': 25}`

\*   \*\*SVD\*\*: Best Score: 0.9889, Best Params: `{'kneighborsclassifier\_\_n\_neighbors': 1, 'truncatedsvd\_\_n\_components': 35}`

\*   \*\*SVD\_SS (Standard Scaled)\*\*: Best Score: 0.9769, Best Params: `{'kneighborsclassifier\_\_n\_neighbors': 4, 'truncatedsvd\_\_n\_components': 25}`

\*   \*\*KPCA\*\*: Best Score: 0.9889, Best Params: `{'kernelpca\_\_n\_components': 35, 'kneighborsclassifier\_\_n\_neighbors': 1}`

\*   \*\*KPCA\_SS (Standard Scaled)\*\*: Best Score: 0.9769, Best Params: `{'kernelpca\_\_n\_components': 25, 'kneighborsclassifier\_\_n\_neighbors': 4}`

\*   \*\*LDA\*\*: Best Score: 0.9689, Best Params: `{'kneighborsclassifier\_\_n\_neighbors': 3, 'lineardiscriminantanalysis\_\_n\_components': 9}`

\*   \*\*LDA\_SS (Standard Scaled)\*\*: Best Score: 0.9689, Best Params: `{'kneighborsclassifier\_\_n\_neighbors': 3, 'lineardiscriminantanalysis\_\_n\_components': 9}`



Estos resultados muestran que PCA, SVD y KernelPCA alcanzaron la mayor precisión (0.9889) sin normalización, utilizando `n\_neighbors=1` y 35 componentes. LDA, aunque ligeramente inferior, también mostró un buen rendimiento, especialmente considerando que está limitado por la dimensionalidad intrínseca de las clases.

