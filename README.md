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

