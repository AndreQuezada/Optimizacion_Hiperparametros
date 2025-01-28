# Optimizacion_Hiperparametros

# Optimización de Hiperparámetros con Random Forest

## 📌 Descripción
Este repositorio contiene un cuaderno Jupyter (`.ipynb`) donde se realiza la optimización de hiperparámetros de un modelo **Random Forest** utilizando `GridSearchCV` y `RandomizedSearchCV`. También se incluye el modelo entrenado (`.pkl`) para su uso posterior sin necesidad de reentrenamiento.

## 📊 Datos Utilizados
Se ha utilizado el conjunto de datos **Car Evaluation Dataset** de UCI Machine Learning Repository:
- URL: [https://archive.ics.uci.edu/ml/machine-learning-databases/car/car.data](https://archive.ics.uci.edu/ml/machine-learning-databases/car/car.data)
- Variables categóricas que describen las características de automóviles y su evaluación de aceptabilidad.

## ⚙️ Proceso de Optimización
1. **Cargamos y preprocesamos los datos**: Se codificaron las variables categóricas con `LabelEncoder`.
2. **Entrenamos un modelo base de Random Forest** para evaluar su rendimiento inicial.
3. **Aplicamos GridSearchCV** para encontrar los mejores hiperparámetros.
4. **Usamos RandomizedSearchCV** con 25 iteraciones para mejorar la búsqueda.
5. **Reentrenamos el modelo con los mejores hiperparámetros** encontrados.
6. **Evaluamos el modelo en datos de prueba** y guardamos el modelo final en un archivo `.pkl`.

## 📈 Resultados
- **Mejor modelo encontrado**:
  - `n_estimators = 50`
  - `max_depth = None`
  - `min_samples_split = 5`
- **Precisión obtenida en validación cruzada:** 96.23%

## 🚀 Uso del Modelo
Para reutilizar el modelo sin necesidad de reentrenarlo:
```python
import joblib
modelo_cargado = joblib.load("modelo_randomforest.pkl")
predicciones = modelo_cargado.predict(X_test)
```

## 📜 Licencia
Este proyecto está bajo la Licencia MIT. Consulta el archivo `LICENSE` para más detalles.
