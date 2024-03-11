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


## PUESTA EN PRODUCCIÓN

![image](https://github.com/davidcarrillo10288/CUSTOMER-SPENDING-PREDICTION/assets/104275645/3eb4a03e-d371-4e29-bd14-b689d04c3ba9)

* Observamos que los valores que predice tienen una diferencia de los valores originales, pero no es tan elevada.

Lo podemos observar en el Histograma de residuos

![image](https://github.com/davidcarrillo10288/CUSTOMER-SPENDING-PREDICTION/assets/104275645/d75fa979-5e98-4f15-9fed-1bfdb9f31f31)

* Notamos que la mayoria de residuos se concentran cerca al cero, lo que nos da un indicio de que no hay mucha diferencia entre los valores predichos y reales.

![image](https://github.com/davidcarrillo10288/CUSTOMER-SPENDING-PREDICTION/assets/104275645/034f706e-d25d-43db-88e3-7ef95e101bdf)

* Sin embargo, al analizar en un rango dado, sin considerar valores cercanos a cero de los residuos, notamos que si hay valores que estan más alejados, de diferencias grandes pero no son tantos como los que están más cerca a cero. Esto nos da un indicio que las predicciones por lo menos cuando se valida un consumo son adecuados.

Realizamos una Binarización de los valores y predichos, con la finalidad de poder observar que tan bien nuestro modelo predice si hay consumo o no, para esto notamos la matriz de confusión y los métricas de clasificación

![image](https://github.com/davidcarrillo10288/CUSTOMER-SPENDING-PREDICTION/assets/104275645/9ebcb9a7-e07c-456d-965d-9e65d9549963)


![image](https://github.com/davidcarrillo10288/CUSTOMER-SPENDING-PREDICTION/assets/104275645/647b51ef-3952-4241-ac96-2a28f759bb83)

* Si bien las métricas nos arrojan buenos datos, tambien notamos que aún tenemos deficiencias al momento de predecir datos de consumo, según nuestros datos, seguimos confundiendonos al predecir si hay o no hay consumo. Esto podríamos mejorarlo si nuestro dataset no fuera tan desbalanceado.


# CONCLUSIONES

* Construimos 4 modelos de regresión con la finalidad de predecir las personas que generan compras luego de visitar una página web (LGBoost, XGBosst, Random Forest y Linear Regression)
Las principales métricas analizadas para los modelos fueron el R2, RMSE y MAE. Luego de analizar estas métricas, concluimos que el R2 no es tan relevante ya que poseemos casi todos los valores de transacciones en cero, y al estar muy dirigido para un lado, este valor no nos aporta lo necesario como para determinar una variabilidad como tal. Por el contrario el RMSE y MAE, los consideramos de mucha valía, ya que al representarnos la diferencia de los valores reales y predichos, al conseguir menores valores de estos, nos acercaríamos a valores más certeros.
* Si solo nos enfocaramos en estas dos métricas, de acuerdo a nuestro gráfico de comparativo de Métricas, El modelo que consiguió menores valores fue el Random Forest.
* Sin embargo, no quisimos quedarnos solo con estos dos parámetros, es por eso que decidimos realizar una Visualización de los Residuos. Luego de observar los residuos, notamos en los histogramas que si bien muchos valores estan cerca al cero, indicandonos que los valores predichos y reales, no tienen tanta diferencia, tambien hay varios valores que nos indican una gran diferencia en los pronósticos. Es asi, que despues de analizar estos residuos, deducimos que el Random Forest y XGBosst, son los que consiguieron mejores respuestas en diferencias de residuos.
* El último análisis que realizamos fue la Predicción de resultados - Valores diferentes de cero. Para esto hicimos uso de la Binarización de los valores reales y predichos, de esta forma conseguimos realizar una clasificación Binaria donde pudimos hallar los valores de Accuracy, recall, AUC, entre otros, los cuales nos ayudan a entender también como se esta generando el modelo. Es así que notamos que ningún modelo tiene excelentes resultados, sin embargo, el modelo que nos aporta un valor predicho y un valor real más exacto, por lo menos en la clase 0 (Es cuando se tiene valor cero de consumo), es el Random Forest. Si bien, presenta errores para predecir los valores de la clase 1, es el que menor falso negativo y positivo posee de todos los modelos analizados, asimismo es el que obtuvo mejor accuracy de entre todos.
* Para finalizar, Luego de realizar multiples análisis, nos decantamos por el Modelo Random Forest, el cual nos demuestra que consiguió los mejores resultados.
* Cuando llevamos a producción nuestro modelo de Random Forest, notamos que efectivamente los resultados predichos de los reales no tienen una diferencia muy grande (Visualización de residuos). Si existe algunos pronosticos que escapan de esto, pero en general se comporta de buena manera.
* Sin embargo, si bien la precisión del modelo es buena, notamos en nuestra matriz de confusión de los datos reales, que aún tenemos dificultades para bajar los falsos positivos del modelo, por lo menos para nuestra clase 1, que es cuando detecta el modelo que hay consumo. Esto principalmente debido al alto grado de desbalance del modelo. Cabe precisar, que esto podríamos mejorarlo si tuvieramos muchos más datos de la clase 1, ya que esto para bien o para mal, nos genera un sesgo en el modelo.
