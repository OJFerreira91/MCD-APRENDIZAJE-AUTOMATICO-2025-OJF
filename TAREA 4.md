## Tarea #4
### Universidad Autonoma de Nuevo León - FCFM
#### Maestría en Ciencia de Datos - Aprendizaje Automatico

Se procesa el data set con los siguientes puntos:

- Aplica algún método de filtro a tus datos mediante el uso de SelectKBest
- Aplica los modelos de selección de características cuidando los supuestos de cada modelo
- Busca una o varias métricas para seleccionar características en literatura relacionada con tu problema (cita tus fuentes)
- Con base en tu investigación, determina las características más relevantes de tu conjunto de datos
- Discute por qué crees que las características seleccionadas son las más relevantes y por qué el resto quedaron excluidas en la selección

Link:
[Tarea4.ipynb](Tarea4.ipynb)

Se utilizaron enfoques de selección univariada (SelectKBest con F-test e Información Mutua), regularización L1 con LassoCV, métodos wrapper como RFE con regresión lineal, y un modelo no lineal basado en árboles con Permutation Importance.

Las variables smoker, age, bmi y children fueron consistentes entre múltiples enfoques y presentaron un impacto significativo en el desempeño predictivo.

El análisis de parsimonia indicó que k = 4 proporciona la mejor combinación de R², RMSE y AIC/BIC.

Variables seleccionadas:
- smoker_yes — mayor importancia en todos los modelos, coherente con literatura médica sobre tabaco y costos sanitarios
- age — incremento de costos por mayor riesgo de enfermedades crónicas
- bmi — relación con enfermedades metabólicas y cardiovasculares
- children — relevancia operativa en el costo del seguro por cobertura dependiente

Variables excluidas:
- sex_male → baja señal predictiva, no significativa por MI ni permutación
- region_* → efectos muy débiles respecto a la categoría base; mejoras mínimas en predicción

Estos hallazgos están alineados con investigaciones similares en seguros médicos, donde el tabaquismo y la edad son determinantes primarios del gasto sanitario.


Link:

- [SelectKBest / univariate selection / f_regression / MI](https://www.kaggle.com/datasets/mirichoi0218/insurance)
- [RFE](https://scikit-learn.org/stable/modules/generated/sklearn.feature_selection.RFE.html)
- [Lasso para selección](https://scikit-learn.org/stable/modules/generated/sklearn.linear_model.Lasso.html)
- [Permutation importance](https://scikit-learn.org/stable/modules/permutation_importance.html)
- [AIC/BIC](https://en.wikipedia.org/wiki/Akaike_information_criterion)