# Predicción de rendimiento de cultivo

## Descrición del probelma

En los ultimos años, la implementación de tecnología en el area agrícola ha ido en aumento debido a sus beneficios tanto en la x como en la estimación de producción de los cultivos.
Bajo este contexto, la información respecto a los factores que influyen en la producción se han vuelto críticos, debido a esto, la falta de conocimiento puede impactar negativamente el desempeño de los cultivos.

## Dataset
En el presente proyecto, se pretende demostrar a través de un modelo predictivo el impacto que pueden tener dichos factores en la producción basandose en un dataset que contiene información de distintos cultivos y sus características historicamente, incluyendo tanto factores manipulables como no manipulables. 
La colección de nombre  ["Agriculture Crop Yield"](https://www.kaggle.com/datasets/samuelotiattakorah/agriculture-crop-yield) cuenta con los siguientes campos:


- **Region**: Región geográfica donde crece el cultivo (North, East, South, West).

- **Soil_Type**: Tipo de suelo donde el cultivo es plantado (Clay, Sandy, Loam, Silt, Peaty, Chalky).

- **Crop**: Tipo de cultivo que crece (Wheat, Rice, Maize, Barley, Soybean, Cotton).

- **Rainfall_mm**: La cantidad de lluvia recibida en milímetros durante la etapa de crecimiento del cultivo.

- **Temperature_Celsius**: La temperatura promedio durante el período de crecimiendo, medido en grados Celsius.

- **Fertilizer_Used**: Indica si se aplicó fertilizador (True = Si, False = No).

- **Irrigation_Used**: Indica si se usó riego durante el período de crecimiento (True = Si, False = No).

- **Weather_Condition**: La condición climática predominante durante la temporada de crecimiento. (Sunny, Rainy, Cloudy).

- **Days_to_Harvest**: El número de días que tarda la cosecha en ser cosechada después de la siembra.

- **Yield_tons_per_hectare**: El rendimiento total del cultivo producido, medido en toneladas por hectárea.

Sus dimensiones son 1.000.000 de entradas y 10 columnas.
Si bien el dataset contiene datos sintéticos que no provienen de estudios reales en un sector agrícola específico, esta basado en entendimientos generales que influyen en el rendimiento de cultivos.


