# Clasificador de Dígitos con KNN

Este proyecto implementa y compara varias **técnicas de reducción de dimensionalidad** combinadas con un **clasificador K-Nearest Neighbors (KNN)** para el reconocimiento de dígitos escritos a mano.

El conjunto de datos utilizado es `digits` de **scikit-learn**, compuesto por imágenes de **8×8 píxeles (64 características)** que representan dígitos del 0 al 9.

El proyecto está desarrollado en **Google Colab** y se entrega como un notebook `.ipynb`, donde cada paso del análisis está claramente explicado y estructurado.

📄 Una explicación detallada de todo el desarrollo (teoría, implementación y resultados) se encuentra en el archivo **`Documentación.pdf`** incluido en el repositorio.

---

## ✨ Funcionalidades

- Análisis exploratorio y visualización de dígitos manuscritos
- Reducción de dimensionalidad mediante:
  - PCA
  - Truncated SVD
  - Kernel PCA
  - Análisis Discriminante Lineal (LDA)
- Clasificación usando K-Nearest Neighbors (KNN)
- Evaluación del rendimiento con validación cruzada
- Optimización de hiperparámetros mediante `GridSearchCV`
- Visualización de proyecciones y resultados de búsqueda

---

## 🛠️ Requisitos

- numpy  
- scikit-learn  
- matplotlib  
- pandas  

Instalación de dependencias:

```bash
pip install numpy scikit-learn matplotlib pandas
```

---

## 🚀 Cómo Ejecutar

1. Clona el repositorio:
```
git clone https://github.com/alvarobello33/ClasificadorKNN_Digitos.git
cd ClasificadorKNN_Digitos
```

2. Abre el notebook .ipynb en Google Colab o Jupyter Notebook.

3. Ejecuta las celdas secuencialmente para reproducir los resultados.

---

## 📌 Notas

- PCA, SVD y KernelPCA alcanzan la mayor precisión (~98.9%) en este conjunto de datos.
- Todos las iimplementacinoes están documentadas paso a paso en el notebook.

