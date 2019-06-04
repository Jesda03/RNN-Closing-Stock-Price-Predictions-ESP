# RNN-Closing-Stock-Price-Predictions-ESP
En este repositorio se encuenta todo el contenido asociado a la entrega del proyecto U4 (redes recurrentes), perteneciente al curso de posgrado Fundamentos de Deep Learning de la Universidad de Antioquia.

El objetivo de este proyecto es elaborar generar y un modelo que permita predecir el precio de cierre de las acciones de BANCOLOMBIA en la bolsa de valores de Colombia (Bvc). Para este fin, se descargaron los valores históricos de precio de cierre diario y sus indicadores asociados desde el 01 de enero de 2008 hasta el 16 de marzo de 2019 (aproximadamente 10 años).

Tomando como guía un trabajo de predicción de precios de acciones de Goldman Sachs (NYSE: GS), decidimos incluir distintos datos de entrada: datos de precio de cierre de acciones de varias empresas del sector financiero colombiano, indicadores técnicos calculados a partir del precio de cierre de las acciones de Bancolombia, Transformadas de Fourier para extraer direcciones de tendencias generales, información de un modelo ARIMA e indicadores asociados al comportamiento de la economía en colombia (COLCAP).
Todo esto, con el fin de contar con la mayor cantidad de datos posible para la realización de buenas predicciones.

Datos históricos de precios de acciones en la Bvc: https://www.bvc.com.co/pps/tibco/portalbvc/Home/Empresas/Listado+de+Emisores

Link de interés: 
https://github.com/borisbanushev/stockpredictionai

A continuación se detalla el contenido de cada notebook:

# U4.01 – Inicial

### Descarga y caracterización inicial del conjunto de datos: 
Antes de explorar el contenido de este proyecto, es necesario ejecutar completamente este notebook.

## Contenido

1. Carga inicial de los datos
2. Procesamiento inicial de los datos históricos de Bancolombia
3. Procesamiento de datos COLCAP
4. Precio de cierre de empresas del sector
5. Indicadores técnicos de los datos de Bancolombia
6. Transformada de Fourier
7. ARIMA

# U4.02 - Series de tiempo cierre acciones con arquitecturas RNN

En este notebook, se crean diferentes arquitectura de redes neuronales recurrentes (RNN) para evaluar cuál es la que mejor predice los movimientos del precio de cierre de las acciones. Los tipos de arquitectura RNN que serán implementadas LSTM y Encoders-Decoders, con las cuales se crean difentes modelos donde varia el número de neuronas de la capa LSTM y el lookback. Al final se seleccionan los modelos LSTM y Encoders-Decoders de menor pérdida para realizar las predicciones y compararlas con el precio de cierre original.

## Contenido

1. Importación de librerías y cargue del dataset
2. Definión funciones de creación de dataset y gráficos de los modelos
3. LSTM
4. Encoder-Decoder
5. Encoder-Decoder version 2

# U4.03 LSTM con 512 células y lookback de 30 (6000 épocas)

En este notebook, se lleva a cabo el entrenamiento de una red LSTM con 512 células y lookback de 30. Para esto, se hace uso de la herramienta Google Colaboratory. Se guarda el modelo y su error cuadrático médio en diferentes puntos del entrenamiento (cada 200 épocas). Finalmente, se comparan los mse y se grafícan las predicciones del modelo con menor mse. A partir de las 4000 épocas, se cambia el optimizador de Adam a RMSProp y se agrega el parámetro tamaño de batch = 64. Se obtiene un mse de 0.175097 para los datos escalado.

## Contenido

1. Importación de librerías y cargue del dataset
2. Herramientas de Google para guardar modelos en Drive
3. Definión funciones de creación de dataset y gráficos de los modelos
4. Creación y entrenamiento del modelo LSTM-512C-30Lb
5. Comparación del modelo y gráfico de predicciones

# U4.04 Series de tiempo cierre acciones - LSTM y PCA

Con la ayuda de Principal Component Analysis (PCA) se analizarán las características del dataset, con el fin de revisar su variabilidad y la posibiidad de reducir sus características. Luego, se crearán diferentes tipos de modelos de arquitectura LSTM, donde varia el número de neuronas de la capa LSTM y el lookback para realizar el mismo ejercicio de los anteriores notebooks: Entrenamiento de los modelos, selección del mejor modelo y predicciones con éste último.

## Contenido

1. Importación de librerías y cargue del dataset
2. PCA
3. Definión funciones de creación de dataset y gráficos de los modelos
4. LSTM

## Modelos entrenados

Los modelos que fueron entrenados y exportados en los notebooks, se encuentran disponibles en los siguientes enlaces:

U4.02: https://www.dropbox.com/sh/pnaw4tx2h0wdb96/AACCi8wep96-Lg8k28gjI8y5a

U4.03: https://drive.google.com/drive/folders/1eY3rBhjQQRWVB10M5Mc0O8W1HQLd_5zQ?usp=sharing
