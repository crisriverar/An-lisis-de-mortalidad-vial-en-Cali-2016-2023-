# Analísis de mortalidad vial en Cali 2016 - 2023

Este repositorio contiene el análisis exploratorio de las muertes en accidentes de tránsito en Cali entre 2016 y abril de 2023, realizado con datos abiertos de la Alcaldía. El objetivo es entender quién muere (rol vial, edad, sexo) y cuándo muere (año, día de la semana, franja horaria) para generar hallazgos útiles en seguridad vial.

## Contenido del repositorio

El análisis se organiza en tres bloques:

1. Revisión de calidad de datos y limpieza
consolidado_muertes_en_accidente_de_transito_2016_al_2023.csv → base original de Datos Abiertos Cali (2,456 registros, 6 columnas).
accidentes_cali_limpio.csv → base resultante tras el pipeline de limpieza, con las variables derivadas.

2. Perfil de las víctimas
Distribución por rol vial (CONDICION), edad y sexo.
Cruces de sexo × rol vial y edad × rol vial (boxplot).

3. Patrones temporales
Tendencia anual 2016-2022 (2023 se excluye por estar incompleto).
Conteo por día de la semana y por franja horaria (madrugada, mañana, tarde, noche).

Notebook: analisis_accidentes_cali.ipynb → contiene todo el proceso, desde la carga hasta las visualizaciones.

## Objetivo del análisis

Identificar y documentar problemas de calidad de datos (codificación, valores centinela, rangos y unidades mezcladas en la edad, formatos de fecha, categorías duplicadas).
Construir un proceso de limpieza reproducible, con cada decisión justificada.
Crear variables derivadas: edad numérica, año, mes, día de la semana, hora, franja horaria y días hasta el fallecimiento (validado con el umbral internacional de 30 días).
Caracterizar el perfil de las víctimas por rol vial, edad y sexo.
Identificar en qué momentos (año, día, hora) se concentran las muertes.
Reconocer las limitaciones del dataset para no sobreinterpretar los resultados.

## Conclusiones y recomendaciones

Motociclistas (41.1%) y peatones (38.9%) concentran cerca del 80% de las muertes registradas, y la diferencia entre ambos es de solo dos puntos porcentuales. El problema no se reduce a las motos: los usuarios sin protección física, en conjunto, son la gran mayoría de las víctimas. Se recomienda que las estrategias de seguridad vial atiendan ambos grupos en paralelo y no solo uno.

Son dos poblaciones de víctimas distintas. La edad mediana del motociclista fallecido es de 29 años y la del peatón es de 66, y cerca del 81% de todas las víctimas son hombres. Esto sugiere que las medidas deberían diferenciarse: control de velocidad y cultura vial dirigidos a jóvenes en moto, e infraestructura y cruces seguros para adultos mayores. Además, se identificaron 4 peatones menores de 12 años, lo que señala que la seguridad peatonal infantil también requiere atención.

Las mujeres fallecen principalmente como peatonas (48.8%) y como parrilleras (24.1%), mientras que los hombres lo hacen sobre todo como motociclistas (45.7%). Los programas de prevención podrían considerar este patrón al segmentar sus mensajes.

Las muertes se concentran en fin de semana (sábado y domingo, aproximadamente 400 y 420 casos, frente a unos 275 de martes a jueves) y en la franja nocturna (621 casos, la más alta). Se propone, como hipótesis a validar, priorizar los operativos de control en noches y fines de semana.

Entre 2016 y 2022 no hay una tendencia clara a la baja: el total anual oscila entre 289 y 353 muertes. El descenso de 2019-2021 empezó antes de la pandemia, por lo que no puede atribuirse solo a ella. El dato de 2023 llega únicamente hasta el 9 de abril, por lo que su caída es un artefacto de la cobertura y no una mejora real.

##  Limitaciones importantes: 
Todas las cifras son conteos y proporciones de muertes registradas, no tasas de mortalidad, porque el dataset no incluye la población expuesta ni el volumen de tráfico. Además, la hora falta en cerca del 17% de los registros, y no se realizaron pruebas estadísticas de significancia.

## Próximos pasos
Analizar la distribución del tiempo hasta el fallecimiento por rol vial.
Aplicar pruebas estadísticas (ANOVA, chi-cuadrado) a las diferencias de edad y sexo entre roles viales.
Cruzar día de la semana con franja horaria.
Calcular tasas reales si se consiguen datos de parque automotor, población o aforos de tráfico.
Herramientas

Python (pandas, matplotlib), Jupyter Notebook / Google Colab.

## Fuente de datos

Datos Abiertos Cali: Consolidado de muertes en accidentes de tránsito 2016-2023 (datos.cali.gov.co).
