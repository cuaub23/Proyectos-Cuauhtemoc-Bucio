# Reconstrucción de energía de rayos gamma con redes neuronales

## Descripción

Este proyecto desarrolla modelos de redes neuronales para estimar la energía de rayos gamma detectados por el observatorio HAWC (*High-Altitude Water Cherenkov*).

El objetivo es predecir la variable `mc.logEnergy` utilizando características relacionadas con las cascadas de partículas producidas por los rayos gamma al interactuar con la atmósfera terrestre.

El proyecto fue desarrollado como parte de mi formación académica en aprendizaje automático, análisis de datos y física computacional.

## Objetivos

- Analizar datos relacionados con eventos detectados por HAWC.
- Seleccionar variables relevantes para la predicción.
- Preprocesar y normalizar las características.
- Entrenar redes neuronales para resolver un problema de regresión.
- Comparar diferentes configuraciones de modelos.
- Evaluar el desempeño mediante métricas de error.

## Tecnologías utilizadas

- Python
- Jupyter Notebook
- Pandas
- NumPy
- Scikit-learn
- TensorFlow
- Keras
- Matplotlib

## Estructura del proyecto

```text
Proyectos-Cuauhtemoc-Bucio/
├── README.md
├── notebooks/
│   └── proyecto_HAWC_BRJC.ipynb
├── src/
│   ├── data_loader.py
│   ├── preprocessing.py
│   └── model.py
├── requirements.txt
├── data/
│   └── README.md
├── results/
│   └── graficas/
└── .gitignore
```

### Descripción de las carpetas y archivos

| Ruta | Descripción |
|---|---|
| `notebooks/` | Contiene la notebook principal con el análisis y los resultados. |
| `src/data_loader.py` | Carga el dataset y verifica que exista. |
| `src/preprocessing.py` | Selecciona, transforma y normaliza las variables. |
| `src/model.py` | Define y entrena los modelos de redes neuronales. |
| `data/` | Carpeta local para los datos utilizados en el proyecto. |
| `results/graficas/` | Contiene las gráficas finales del análisis. |
| `requirements.txt` | Lista de librerías necesarias para ejecutar el proyecto. |
| `.gitignore` | Evita subir archivos privados, temporales o innecesarios. |

## Datos

El proyecto utiliza un conjunto de datos relacionado con eventos de rayos gamma detectados por HAWC.

Los datos originales no se incluyen en este repositorio porque son privados o demasiado grandes para publicarse.

Para ejecutar el proyecto, se debe colocar localmente el dataset y configurar su ubicación mediante la variable de entorno `DATASET_PATH`.

Ejemplo:

```bash
export DATASET_PATH=/ruta/a/tu/dataset.csv
```

En Windows PowerShell:

```powershell
$env:DATASET_PATH="C:\ruta\a\tu\dataset.csv"
```

## Metodología

El proyecto se desarrolló mediante las siguientes etapas:

1. Carga del conjunto de datos.
2. Exploración inicial de las variables.
3. Selección de características.
4. Análisis de correlación.
5. Transformación de variables angulares.
6. División de los datos en entrenamiento, validación y prueba.
7. Normalización mediante `StandardScaler`.
8. Construcción de redes neuronales densas.
9. Entrenamiento con `EarlyStopping`.
10. Comparación y evaluación de los modelos.

La variable objetivo utilizada fue:

```text
mc.logEnergy
```

## Modelos

Se evaluaron diferentes arquitecturas de redes neuronales modificando:

- Número de capas ocultas.
- Número de neuronas.
- Funciones de activación.
- Regularización L2.
- Uso de dropout.
- Optimizadores.

La función de pérdida utilizada fue el error cuadrático medio:

```text
Mean Squared Error (MSE)
```

También se utilizó el error absoluto medio:

```text
Mean Absolute Error (MAE)
```

## Resultados

Durante el entrenamiento, algunos modelos alcanzaron valores de `MAE` cercanos a `0.26`.

La tabla siguiente deberá actualizarse con las métricas definitivas calculadas sobre el conjunto de prueba:

| Modelo | Características | MAE | MSE | RMSE |
|---|---|---:|---:|---:|
| Modelo 1 | Características base | Pendiente | Pendiente | Pendiente |
| Modelo 2 | Características base con regularización | Pendiente | Pendiente | Pendiente |
| Modelo 3 | Características base con dropout | Pendiente | Pendiente | Pendiente |
| Modelo final | Mejor configuración | Pendiente | Pendiente | Pendiente |

## Visualizaciones

Las gráficas generadas durante el análisis se guardan en:

```text
results/graficas/
```

Cuando agregues una imagen, puedes mostrarla aquí utilizando:

```markdown
![Pérdida de entrenamiento y validación](results/graficas/loss_history.png)
```

Por ejemplo:

![Pérdida de entrenamiento y validación](results/graficas/loss_history.png)

## Cómo ejecutar el proyecto

Clona el repositorio:

```bash
git clone https://github.com/cuaub23/Proyectos-Cuauhtemoc-Bucio.git
cd Proyectos-Cuauhtemoc-Bucio
```

Instala las dependencias:

```bash
pip install -r requirements.txt
```

Configura la ruta del dataset:

```bash
export DATASET_PATH=/ruta/a/tu/dataset.csv
```

Abre Jupyter Notebook:

```bash
jupyter notebook
```

Después abre la notebook:

```text
notebooks/proyecto_HAWC_BRJC.ipynb
```

## Principales aprendizajes

- La normalización es necesaria cuando las variables tienen escalas diferentes.
- Las variables angulares pueden representarse mediante seno y coseno.
- `EarlyStopping` ayuda a evitar entrenamientos innecesarios y sobreajuste.
- La regularización puede ayudar a controlar la complejidad del modelo.
- La evaluación final debe realizarse sobre datos que no hayan sido utilizados durante el entrenamiento.

## Posibles mejoras

- Comparar las redes neuronales con modelos como Random Forest o Gradient Boosting.
- Agregar gráficas de energía real contra energía predicha.
- Incorporar intervalos de incertidumbre.
- Guardar el mejor modelo en formato `.keras`.
- Crear una interfaz para realizar predicciones.
- Automatizar el proceso de entrenamiento y evaluación.

## Autor

**Josué Cuauhtémoc Bucio Rivera**

- GitHub: [cuaub23](https://github.com/cuaub23)
