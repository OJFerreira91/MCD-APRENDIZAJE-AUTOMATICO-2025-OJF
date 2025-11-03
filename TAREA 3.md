## Tarea #3
### Universidad Autonoma de Nuevo León - FCFM
#### Maestría en Ciencia de Datos - Aprendizaje Automatico

Se procesa el data set con los siguientes puntos:

- Comprueba si tus variables de interés son conjuntos de datos paramétricos o no paramétricos
- Calcula estadísticos descriptivos básicos para tus datos
- Haz una matriz de correlación de tus datos y escribe algunas interpretaciones de la misma
- Realiza alguna prueba de hipótesis a partir de las conclusiones que hayas sacado de la matriz de correlación
- Presenta tus resultados gráficamente

Link:
[Tarea3.ipynb](Tarea3.ipynb)

# 1 Normalidad de datos

Se aplicó la prueba de Shapiro-Wilk a las variables numéricas.
El nivel de significancia utilizado fue α = 0.05.
De acuerdo con los p-values obtenidos:

- Si p > 0.05 → no se rechaza la normalidad → datos paramétricos

- Si p ≤ 0.05 → se rechaza la normalidad → datos no paramétricos
Todas las interpretaciones se realizaron según esta regla.

Todas las variables numéricas evaluadas presentan una distribución NO normal (p ≤ 0.05), por lo que se consideran NO paramétricas. Esto implica que, para análisis estadísticos inferenciales y correlaciones, deberán utilizarse métodos no paramétricos.

| Variable | Conclusión     |
| -------- | -------------- |
| age      | No paramétrica |
| bmi      | No paramétrica |
| children | No paramétrica |
| charges  | No paramétrica |

✅ Todas las variables numéricas mostraron distribuciones no normales, por lo que se utilizaron pruebas no paramétricas.

# 2 Estadística descriptiva

Se reportaron medidas de tendencia central y dispersión para las variables numéricas, y distribución porcentual para la variable categórica **smoker**.

# 3 Correlación de Spearman

|              | age       | bmi   | children | charges   |
| ------------ | --------- | ----- | -------- | --------- |
| **age**      | 1.000     | 0.108 | 0.057    | **0.534** |
| **bmi**      | 0.108     | 1.000 | 0.016    | 0.119     |
| **children** | 0.057     | 0.016 | 1.000    | 0.133     |
| **charges**  | **0.534** | 0.119 | 0.133    | 1.000     |

Los gastos médicos (charges) presentan una correlación positiva moderada con la edad (age) y muy débil con el BMI y número de hijos, indicando que la edad es un factor más asociado al costo sanitario.


# 4 Prueba de hipótesis: impacto del tabaquismo en los costos

- H₀: Los fumadores y no fumadores tienen el mismo costo médico (charges).

- H₁: Los fumadores tienen mayor costo médico que los no fumadores.

Se aplicó la prueba Mann–Whitney U (unilateral derecha):
| Estadístico      | Resultado |
| ---------------- | --------- |
| U                | 284,133   |
| p-value          | 0.000000  |
| Tamaño de efecto | -0.949    |

✅ Se rechaza H₀ → Los fumadores presentan costos significativamente mayores
🔥 Efecto extremadamente alto (|r_rb| ≈ 0.95)

# 5 Visualización

Se presentaron:

- Mapa de calor de correlaciones

- Boxplot de costos por condición de fumador

- Violin plot de distribuciones de charges en ambos grupos

Las gráficas muestran que el grupo fumador presenta una mayor dispersión y valores atípicos elevados, lo cual coincide con los resultados estadísticos.

# ✅ Conclusión Final

La edad y, de manera predominante, el tabaquismo son variables muy asociadas con el incremento del costo médico.

Link:
[Tarea3.ipynb](Tarea3.ipynb)