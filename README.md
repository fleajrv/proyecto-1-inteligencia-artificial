# Predicción de rendimiento de cultivo

## Descrición del probelma

En los ultimos años, la implementación de tecnología en el area agrícola ha ido en aumento debido a sus beneficios tanto en el cuidado como en la estimación de producción de los cultivos.
Bajo este contexto, conocer las condiciones ideales para plantar y producir ciertos cultivos se ha vuelto crítico para la toma de decisiones de los agricultores.

## Dataset
En el presente proyecto, se pretende demostrar a través de un modelo predictivo el fruto mas apto para cultivar en un terreno particular según de distintos factores que incluyen la composición química de la tierra y datos históricos del clima.
El dataset seleccionado (["Crop Recommendation Dataset"](https://www.kaggle.com/datasets/atharvaingle/crop-recommendation-dataset/data)) recopila datos de distintos datasets provenientes de India y cuenta con los siguientes campos:

- N - proporción del contenido de nitrógeno en el suelo

- P - proporción del contenido de fósforo en el suelo

- K - proporción del contenido de potasio en el suelo

- temperature - temperatura en grados Celsius

- humidity - humedad relativa en %

- ph - valor de ph del suelo

- rainfall - precipitaciones en mm

- label - Tipo de cultivo

Sus dimensiones son 2.200 de entradas y 8 columnas, con las cuales se busca predecir el cultivo mas apto entre 22 opciones.




