# CUSTOMER-SPENDING-PREDICTION

La necesidad de prever y optimizar el gasto de sus usuarios ha llevado a una empresa de comercio electrónico a buscar soluciones innovadoras. Como científicos de datos, hemos sido convocados para desarrollar un modelo de machine learning que pueda predecir con precisión cuánto gastará un usuario al visitar dicho sitio web.

# ANÁLISIS DE NUESTRA VARIABLE OBJETIVO

* Observamos que la cantidad de personas que consumieron al visitar la página web es mínima comparado con las personas que no consumieron nada.
* Esto nos indica que nuestra data está muy desbalanceada.

![image](https://github.com/davidcarrillo10288/CUSTOMER-SPENDING-PREDICTION/assets/104275645/f7c6c740-70d2-43fa-b3e0-266b06a48908)


![image](https://github.com/davidcarrillo10288/CUSTOMER-SPENDING-PREDICTION/assets/104275645/5b9834c3-0192-430f-ad07-42a1bbea6ce4)

* En la gráfica de dispersión, notamos que casi todos nuestros datos de esta variable se sitúan en el valor cero.
* Esto nos indica que la mayor cantidad de personas que visitan la página web no concretan la compra.
* Las personas que realizan un gasto elevado, es mínimo.

# MODELOS SELECCIONADOS PARA EL ANÁLISIS DE PREDICCIÓN
1. MODELO LGBoost
2. MODELO XGBoost
3. MODELO RANDOM FOREST
4. MODELO LINEAR REGRESSION

# MÉTRICAS OBTENIDAS EN LAS EVALUACIONES DE LOS MODELOS

![image](https://github.com/davidcarrillo10288/CUSTOMER-SPENDING-PREDICTION/assets/104275645/50ea06c7-1254-44f0-949d-88920c8774e8)

# CONCLUSIONES

* Construimos 4 modelos de regresión con la finalidad de predecir las personas que generan compras luego de visitar una página web (LGBoost, XGBosst, Random Forest y Linear Regression)
* Las principales métricas analizadas para los modelos fueron el R2, RMSE y MAE. Luego de analizar estas métricas, concluimos que el R2 no es tan relevante ya que poseemos casi todos los valores de transacciones en cero, y al estar muy dirigido para un lado, este valor no nos aporta lo necesario como para determinar una variabilidad como tal. Por el contrario el RMSE y MAE, los consideramos de mucha valía, ya que al representarnos la diferencia de los valores reales y predichos, al conseguir menores valores de estos, nos acercaríamos a valores más certeros.
* Si solo nos enfocaramos en estas dos métricas, de acuerdo a nuestro gráfico de comparativo de Métricas, El modelo que consiguió menores valores fue el Random Forest.
* Sin embargo, no quisimos quedarnos solo con estos dos parámetros, es por eso que decidimos realizar una Visualización de los Residuos. Luego de observar los residuos, notamos en los histogramas que si bien muchos valores estan cerca al cero, indicandonos que los valores predichos y reales, no tienen tanta diferencia, tambien hay varios valores que nos indican una gran diferencia en los pronósticos. Es asi, que despues de analizar estos residuos, deducimos que el Random Forest y XGBosst, son los que consiguieron mejores respuestas en diferencias de residuos.
* El último análisis que realizamos fue la Predicción de resultados - Valores diferentes de cero. Para esto hicimos uso de la Binarización de los valores reales y predichos, de esta forma conseguimos realizar una clasificación Binaria donde pudimos hallar los valores de Accuracy, recall, AUC, entre otros, los cuales nos ayudan a entender también como se esta generando el modelo. Es así que notamos que ningún modelo tiene excelentes resultados, sin embargo, el modelo que nos aporta un valor predicho y un valor real más exacto, por lo menos en la clase 0 (Es cuando se tiene valor cero de consumo), es el Random Forest. Si bien, presenta errores para predecir los valores de la clase 1, es el que menor falso negativo y positivo posee de todos los modelos analizados, asimismo es el que obtuvo mejor accuracy de entre todos.
* Para finalizar, Luego de realizar multiples análisis, nos decantamos por el Modelo Random Forest, el cual nos demuestra que consiguió los mejores resultados. Cabe precisar, que esto podríamos mejorarlo si tuvieramos muchos más datos de la clase 1, ya que esto para bien o para mal, nos genera un sesgo en el modelo.
