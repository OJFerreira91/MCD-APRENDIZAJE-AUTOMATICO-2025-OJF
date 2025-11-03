## Tarea #3
### Universidad Autonoma de Nuevo León - FCFM
#### Maestría en Ciencia de Datos - Aprendizaje Automatico

Se procesa el data set con los siguientes puntos:

- Comprueba si tus variables de interés son conjuntos de datos paramétricos o no paramétricos
- Calcula estadísticos descriptivos básicos para tus datos
- Haz una matriz de correlación de tus datos y escribe algunas interpretaciones de la misma
- Realiza alguna prueba de hipótesis a partir de las conclusiones que hayas sacado de la matriz de correlación
- Presenta tus resultados gráficamente

Se aplicó la prueba de Shapiro-Wilk a las variables numéricas.
El nivel de significancia utilizado fue α = 0.05.
De acuerdo con los p-values obtenidos:

- Si p > 0.05 → no se rechaza la normalidad → datos paramétricos

- Si p ≤ 0.05 → se rechaza la normalidad → datos no paramétricos
Todas las interpretaciones se realizaron según esta regla.

Todas las variables numéricas evaluadas presentan una distribución NO normal (p ≤ 0.05), por lo que se consideran NO paramétricas. Esto implica que, para análisis estadísticos inferenciales y correlaciones, deberán utilizarse métodos no paramétricos

Link:
[Tarea3.ipynb](Tarea3.ipynb)