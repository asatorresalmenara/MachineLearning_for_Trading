# MachineLearning_for_Trading

Proyecto en el que estudio la implementaci�n de un sistema inteligente capaz de realizar inversiones en el mercado de FOREX.

La idea b�sica del proyecto se puede dividir en varias fases:

- Dise�o de un sistema predictivo del precio
- Dise�o de un agente inteligente que realice la operativa de entradas en corto-largo en un par forex dado (ej. eur-usd)
- Dise�o de una interfaz con el terminal del broker para obtener el data-feed en tiempo real y el estado de la cuenta / operaciones.

Como gu�a de desarrollo, estoy utilizando como lenguaje PYTHON y estas librer�as m�s representativas:

- scikit-learn : utilidades ML varias (cross-validation, GridSearch, LinearRegressores, ...)
- tensorflow   : librer�a deep learning de bajo nivel
- keras        : front-end de tensorflow (nivel de aplicaci�n)
- featurestools: feature engineering
- deap		   : implementaci�n de algoritmos gen�ticos

De momento estoy centrado en la implementaci�n de la 1� fase (red predictiva) para la que he dise�ado una red LSTM de varias capas a la que alimento con los precios OHLC, varios indicadores t�cnicos y detectores de patrones de velas �nicamente.

Para la siguiente fase, la idea es utilizar una red A3C (aprendizaje por refuerzo) para que utilice la predicci�n de la red LSTM junto con el estado de la cuenta en el broker y los estados de las operaciones en curso, para decidir qu� hacer (mantener la posici�n, abrir en corto o en largo).
  
## Changelog

----------------------------------------------------------------------------------------------
##### 05.12.2018 ->commit:"Dise�ando gym-environment"
- [x] Inicio el desarrollo del Gym-env que me sirva de referencia para evaluar al agente A3C.
- [x] Clono varios repos en ./gym 

----------------------------------------------------------------------------------------------
##### 04.12.2018 ->commit:"Iniciando dise�o A3C-LSTM"
- [x] Descarto filtro post-predictor ya que no introduce ninguna mejora.
- [x] Creo notebook para generar dataframe de predicciones y generar CSV para el Agente A3C
- [x] Inicio el notebook de implementaci�n del agente A3C-LSTM
- [x] Creo RAR files para archivos CSV pesados y extraigo los CSV de la copia de backup

----------------------------------------------------------------------------------------------
##### 03.12.2018 ->commit:"Descarto RFR y reorganizo directorios"
- [x] Descarto el RFR, reorganizo la estructura interna de los directorios y contin�o con el filtro post-predictor.

----------------------------------------------------------------------------------------------
##### 30.11.2018 ->commit:"Implementaci�n del RandomForestRegressor"
- [x] Implemenento el RFC y estoy a la espera de que termine el 'fitting' para luego evaluarlo. Lleva ya m�s de 30 horas...

----------------------------------------------------------------------------------------------
##### 28.11.2018 ->commit:"Realizaci�n de estudios de mejora LSTM"

- [x] Incluyo diversos estudios (notebooks) para mejorar el rendimiento de la red predictiva LSTM. Ver notebooks "Study X...."

----------------------------------------------------------------------------------------------
##### 27.11.2018 ->commit:"Terminado desarrollo LSTM"

- [x] Finalizo el desarrollo de la red LSTM que predecir� los precios HIGH-LOW de la siguiente sesi�n en base a las 4 �ltimas sesiones.


----------------------------------------------------------------------------------------------
##### 26.11.2018 ->commit:"Score 0.99"

- [x] Tengo un score del 99.5% lo que me "chirr�a" bastante. Revisar los datos por si hay algo que se me est� escapando.


----------------------------------------------------------------------------------------------
##### 24.11.2018 ->commit:"Incluyo indicadores y patrones de vela"

- [x] Incluyo indicadores t�cnicos de la librer�a TA-Lib (todos los que son viables)
- [x] Incluyo todos los patrones de velas que aportan informaci�n v�lida
- [!] El resultado del Algoritmo gen�tico no ha sido como esperaba. Tengo un score de un 50%. Tengo que replantear los 'features' de entrada.

----------------------------------------------------------------------------------------------
##### 16.11.2018 ->commit:"Score 0.99"

- [x] Implemento clase con Algoritmo gen�tico basado en la librer�a 'deap' para realizar una selecci�n de los mejores hiper-par�metros de la red.


----------------------------------------------------------------------------------------------
##### 6.11.2018 ->commit:"Score 0.99"

- [x] Agrupo todas las funcionalidades del notebook de trabajo en el m�dulo PredictiveNet.py


----------------------------------------------------------------------------------------------
##### 5.11.2018 ->commit:"Resumen �ltimo mes"

- [x] Incluyo un resumen de todos los commits hechos desde el d�a 19 de octubre:
- [x] Mas pruebas con diferentes configuraciones
- [x] Actualizo pesos nosuffle_bs128
- [x] Actualizado test-predicci�n. Verificando opci�n nosuffle_bs128
- [x] Corregida inserci�n de row en dataframe
- [x] A�adiendo filas al df
- [x] Verificando test recursivo
- [x] Probar sin shuffle, mayor batch_size. Implementar prueba recursiva
- [x] Incluyo archivo test_fourier.csv
- [x] Actualizado walk-forward. Probar con funci�n seno para descartar alg�n fallo oculto en los datos.
- [x] Comentando Fintech_LSTM. De momento acc=0.68
- [x] Actualizo proceso de entrenamiento
- [x] Probando fintech_test con nuevos features
- [x] Trabajando en fintech_tester
- [x] Probando con fourier multivariate
- [x] Incluyo csv eurusd en M30

