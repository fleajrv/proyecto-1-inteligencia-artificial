# Predicción de rendimiento de cultivo

## Índice de contenidos
- [1. Descripción del problema](#1-descrición-del-problema)

- [2. Dataset](#2-dataset)

- [3. Modelo Seleccionado](#3-modelo-seleccionado)

    - [3.1. Motivo](#31-motivo)

    - [3.2. Ventajas](#32-ventajas)

    - [3.3. Limitaciones](#33-limitaciones)


## 1. Descrición del problema

En los ultimos años, la implementación de tecnología en el sector agrícola ha ido en aumento debido a sus beneficios tanto en el cuidado como en la estimación de producción de los cultivos.

Bajo este contexto, conocer las condiciones ideales para plantar y producir ciertos cultivos se ha vuelto crítico para la toma de decisiones de los agricultores, dado que en un mercado tan competitivo, ser consciente de qué tanto provecho se le puede sacar al suelo en base a sus características es clave para pode obtener la mayor cantidad de ganancias, al elegir conscientemente qué tipo de cultivos es mejor cosechar.

## 2. Dataset
En el presente proyecto, se pretende demostrar a través de un modelo predictivo el fruto mas apto para cultivar en un terreno particular según de distintos factores que incluyen la composición química de la tierra y datos históricos del clima.
El dataset seleccionado (["Crop Recommendation Dataset"](https://www.kaggle.com/datasets/atharvaingle/crop-recommendation-dataset/data)) recopila datos de distintos datasets provenientes de India y cuenta con los siguientes campos:

- **N** - proporción del contenido de nitrógeno en el suelo

- **P** - proporción del contenido de fósforo en el suelo

- **K** - proporción del contenido de potasio en el suelo

- **temperature** - temperatura en grados Celsius

- **humidity** - humedad relativa en %

- **ph** - valor de ph del suelo

- **rainfall** - precipitaciones en mm

- **label** - Tipo de cultivo

Sus dimensiones son 2.200 de entradas y 8 columnas, con las cuales se busca predecir el cultivo mas apto entre 22 opciones, entre las cuales se encuentran disponibles:
- **rice**: Arroz
- **maize**: Maíz
- **chickpea**: Garbanzos
- **kidneybeans**: Frijoles
- **pigeonpeas**: Guandules
- **mothbeans**: Frijoles moth
- **mungbean**: Frijoles mungo
- **blackgram**: Lentejas negras
- **lentil**: Lentejas
- **pomegranate**: Granada
- **banana**: Plátano
- **mango**: Mango
- **grapes**: Uvas
- **watermelon**: Sandía
- **muskmelon**: Melón
- **apple**: Manzana
- **orange**: Naranja
- **papaya**: Papaya
- **coconut**: Coco
- **cotton**: Algodón
- **jute**: Yute
- **coffee**: Café

## 3. Modelos Seleccionados

Para abordar este problema de clasificación multiclase, se propone la evaluación comparativa de tres algoritmos. Para asegurar una búsqueda de hiperparámetros robusta y evitar el sobreajuste espacial, la optimización de los modelos se realizará mediante validación cruzada utilizando GridSearchCV. En esta etapa experimental, se propone evaluar el rendimiento guiándose por tres métricas principales: **accuracy** para observar la exactitud global del modelo, **f1_macro** para asegurar un rendimiento equitativo que no discrimine a los cultivos con características más complejas y el área bajo la curva ROC en un enfoque one-over-rest que resulta ideal para clasificaciones múltiples **roc_auc_ovr**.

## Regresión logística
Dadas las condiciones del dataset, y que se plantea un modelo de predicción clasificador, se optó por utilizar un modelo de regresión logística. Para su implementación se diseñará un Pipeline que incluye un escalador para normalizar los datos y se entrenará usando regularización ElasticNet en el proceso.

#### Motivo
Como se mencionó, dado que se busca la creación de un modelo clasificador, la primera opción a considerar sería la de una regresión logística para empezar a probar por un modelo simple, dada la hipótesis de que varios de los atributos que considera el set de datos poseen una correlación considerable entre sí, tanto positiva como negativa. Se propone el uso de penalización con ElasticNet dado que toma ambos criterios Lasso y Rdige, que para el dataset trabajado podría ser de utilidad y de alta eficiencia.

#### Ventajas
- Costo de cómputo bajo
- Interpretabilidad fácil del modelo
- Ideal para la clasificación en base a probabilidades, dados pocos atributos con los que trabajar

#### Limitaciones
- Asume fronteras lineales, por lo que no puede capturar relaciones complejas.
- Es sensible a outliers / valores atípicos, lo que afectaría a la generalización del modelo.

## K-Nearest Neighbors
El segundo modelo considerado para este estudio se basa en el algoritmo de K-Nearest Neighbors. Al basarse enteramente en el cálculo matemático de distancias entre las muestras, este modelo también requerirá estar encapsulado en un pipeline con un escalador para asegurar que todas las métricas (desde el pH hasta los milímetros de lluvia) operen bajo la misma escala.
Se considerarán múltiples números de vecinos (K) y distintas métricas de distancia para encontrar el modelo más eficiente para el dataset.

#### Motivo
El uso de KNN se justifica por la lógica del dominio agrícola y justamente el objetivo de este estudio: **terrenos que comparten características químicas y climáticas similares tienden a ser aptos para el mismo tipo de cultivo**. KNN agrupa y clasifica basándose exactamente en la "similitud de vecindad", lo que permitirá contrastar los resultados de los otros modelos y capturar agrupaciones de condiciones ideales que no sigan un patrón puramente paramétrico.

#### Ventajas
- Es muy eficiente para modelar fronteras no lineales / complejas.
- Interpretabilidad fácil del modelo
- Al ser un modelo no paramétrico, no hace suposiciones previas sobre la distribución de los datos.

#### Limitaciones
- Presenta un costo computacional elevado al predecir, debido a la necesidad de calcular distancias para clasificar.
- La complejidad del entrenamiento depende altamente de los numeros de vecinos ($k_i$) y las métrica de distancias (euclideana, manhattan y minkowski).

## Decision Tree

#### Motivo

#### Ventajas

#### Limitaciones


## Random Forest


#### Motivo

#### Ventajas

#### Limitaciones
