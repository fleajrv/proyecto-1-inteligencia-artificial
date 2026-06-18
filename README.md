# Predicción de rendimiento de cultivo

## Descrición del probelma

En los ultimos años, la implementación de tecnología en el sector agrícola ha ido en aumento debido a sus beneficios tanto en el cuidado como en la estimación de producción de los cultivos.

Bajo este contexto, conocer las condiciones ideales para plantar y producir ciertos cultivos se ha vuelto crítico para la toma de decisiones de los agricultores, dado que en un mercado tan competitivo, ser consciente de qué tanto provecho se le puede sacar al suelo en base a sus características es clave para pode obtener la mayor cantidad de ganancias, al elegir conscientemente qué tipo de cultivos es mejor cosechar.

## Dataset
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

## Modelo Seleccionado
Dadas las condiciones del dataset, y que se plantea un modelo de predicción clasificador, se optó por plantear un modelo de regresión logística, haciendo uso previo de un escalador para normalizar los datos y luego obtener los resultados de clasificación, haciendo uso de ElasticNet en el proceso.

### Motivo
Como se mencionó, dado que se busca la creación de un modelo clasificador, la primera opción a considerar sería la de una regresión logística para empezar a probar por un modelo simple, dada la hipótesis de que varios de los atributos que considera el set de datos poseen una correlación considerable entre sí, tanto positiva como negativa. En la misma página, se opta por el uso de ElasticNet dado que toma lo mejor de los modelos de Lasso y Rdige, y ante un dataset directo como el que se trabaja en el proyecto presente, podría ser de utilidad y de alta eficiencia.

### Ventajas
- Costo de cómputo bajo
- Interpretabilidad fácil del modelo
- Ideal para la clasificación en base a probabilidades, dados pocos atributos con los que trabajar

## Limitaciones
- Podría generar overfitting
- Puede quedarse corto si se utiliza una mayor cantidad de clases posibles