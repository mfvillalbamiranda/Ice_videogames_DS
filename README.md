# Ice_videogames_DS

Ice es una tienda online que vende videojuegos por todo el mundo. Las reseñas de usuarios y expertos, los géneros, las plataformas (por ejemplo, Xbox o PlayStation) y los datos históricos sobre las ventas de juegos están disponibles en fuentes abiertas. Se deben identificar patrones que determinen si un juego tiene éxito o no. Esto te permitirá detectar proyectos prometedores y planificar campañas publicitarias.
<!--
Los datos se remontan a 2016, se encuentran en la planeación de una campaña para el 2017. El dataset contiene una columna "rating" que almacena la clasificación ESRB de cada juego. El Entertainment Software Rating Board (la Junta de clasificación de software de entretenimiento) evalúa el contenido de un juego y asigna una clasificación de edad como Adolescente o Adulto.

# Instrucciones para completar el proyecto
Paso 1. Abre el archivo de datos y estudia la información general 

Ruta de archivo:

/datasets/games.csv . Descarga el dataset

Paso 2. Prepara los datos

Reemplaza los nombres de las columnas (ponlos en minúsculas).
Convierte los datos en los tipos necesarios.
Describe las columnas en las que los tipos de datos han sido cambiados y explica por qué.
Si es necesario, elige la manera de tratar los valores ausentes:
Explica por qué rellenaste los valores ausentes como lo hiciste o por qué decidiste dejarlos en blanco.
¿Por qué crees que los valores están ausentes? Brinda explicaciones posibles.
Presta atención a la abreviatura TBD: significa "to be determined" (a determinar). Especifica cómo piensas manejar estos casos.
Calcula las ventas totales (la suma de las ventas en todas las regiones) para cada juego y coloca estos valores en una columna separada.
Paso 3. Analiza los datos

Mira cuántos juegos fueron lanzados en diferentes años. ¿Son significativos los datos de cada período?
Observa cómo varían las ventas de una plataforma a otra. Elige las plataformas con las mayores ventas totales y construye una distribución basada en los datos de cada año. Busca las plataformas que solían ser populares pero que ahora no tienen ventas. ¿Cuánto tardan generalmente las nuevas plataformas en aparecer y las antiguas en desaparecer?
Determina para qué período debes tomar datos. Para hacerlo mira tus respuestas a las preguntas anteriores. Los datos deberían permitirte construir un modelo para 2017.
Trabaja solo con los datos que consideras relevantes. Ignora los datos de años anteriores.
¿Qué plataformas son líderes en ventas? ¿Cuáles crecen y cuáles se reducen? Elige varias plataformas potencialmente rentables.
Crea un diagrama de caja para las ventas globales de todos los juegos, desglosados por plataforma. ¿Son significativas las diferencias en las ventas? ¿Qué sucede con las ventas promedio en varias plataformas? Describe tus hallazgos.
Mira cómo las reseñas de usuarios y profesionales afectan las ventas de una plataforma popular (tu elección). Crea un gráfico de dispersión y calcula la correlación entre las reseñas y las ventas. Saca conclusiones.
Teniendo en cuenta tus conclusiones compara las ventas de los mismos juegos en otras plataformas.
Echa un vistazo a la distribución general de los juegos por género. ¿Qué se puede decir de los géneros más rentables? ¿Puedes generalizar acerca de los géneros con ventas altas y bajas?
Paso 4. Crea un perfil de usuario para cada región

Para cada región (NA, UE, JP) determina:

Las cinco plataformas principales. Describe las variaciones en sus cuotas de mercado de una región a otra.
Los cinco géneros principales. Explica la diferencia.
Si las clasificaciones de ESRB afectan a las ventas en regiones individuales.
Paso 5. Prueba las siguientes hipótesis:

— Las calificaciones promedio de los usuarios para las plataformas Xbox One y PC son las mismas.

— Las calificaciones promedio de los usuarios para los géneros de Acción y Deportes son diferentes.

Establece tu mismo el valor de umbral alfa.

Explica:

— Cómo formulaste las hipótesis nula y alternativa.

— Qué criterio utilizaste para probar las hipótesis y por qué.

Paso 6. Escribe una conclusión general

Formato: Completa la tarea en Jupyter Notebook. Inserta el código de programación en las celdas code y las explicaciones de texto en las celdas markdown. Aplica formato y agrega encabezados.

# Descripción de datos
— Name (Nombre)

— Platform (Plataforma)

— Year_of_Release (Año de lanzamiento)

— Genre (Género) 

— NA_sales (ventas en Norteamérica en millones de dólares estadounidenses) 

— EU_sales (ventas en Europa en millones de dólares estadounidenses) 

— JP_sales (ventas en Japón en millones de dólares estadounidenses) 

— Other_sales (ventas en otros países en millones de dólares estadounidenses) 

— Critic_Score (máximo de 100) 

— User_Score (máximo de 10) 

— Rating (ESRB)

Es posible que los datos de 2016 estén incompletos.
-->

## Objetivo de negocio
El objetivo principal es identificar los patrones clave que determinan el éxito comercial de un videojuego a nivel global y regional, utilizando datos históricos hasta el año 2016. Esto permitirá a la tienda online Ice tomar decisiones basadas en datos para:
- Detectar proyectos y plataformas emergentes más prometedoras para el año 2017
- Optimizar la asignación del presupuesto publicitario mediante campañas de marketing focalizadas
- Maximizar los ingresos adaptando la oferta de videojuegos según el perfil de consumo y las preferencias específicas de cada región geográfica (Norteamérica, Europa y Japón).

## Descripción del dataset
El conjunto de datos contiene el histórico de ventas de videojuegos en diferentes regiones, junto con sus clasificaciones y calificaciones. Tras un análisis exploratorio de datos (EDA), las variables principales son:
- name: Nombre del videojuego
- platform: Plataforma de lanzamiento (ej. PS4, XOne, PC, 3DS)
- year_of_release: Año en que se lanzó el juego al mercado
- genre: Categoría o género del videojuego (Acción, Deportes, Shooter, etc.)
- na_sales, eu_sales, jp_sales, other_sales: Ventas en millones de dólares (USD) para Norteamérica, Europa, Japón y el resto del mundo respectivamente
- total_sales: Columna calculada que representa la suma global de las ventas de un juego en todas las regiones
- critic_score: Puntuación otorgada por la crítica especializada (escala de 0 a 100)
- user_score: Puntuación otorgada por los usuarios (escala de 0 a 10; procesando los valores "TBD" como ausentes para no sesgar el análisis)
- rating: Clasificación por edades otorgada por la ESRB (E, T, M, E10+, etc.).

## Metodología
Para resolver el problema, se siguió un pipeline estructurado de análisis de datos:
- Preparación y Limpieza de Datos: Conversión de los nombres de columnas a minúsculas, corrección de tipos de datos (como user_score a tipo flotante) y manejo de valores nulos o indeterminados ("TBD"). Creación de la métrica agregada total_sales.
- EDA: Determinación del ciclo de vida promedio de las consolas (identificado en aproximadamente 7-10 años) y definición del período relevante (2012-2016) para proyectar el año 2017.
  - Análisis de la distribución de ventas mediante diagramas de caja (boxplots) para comparar el rendimiento de las plataformas líderes (PS4, Xbox One, 3DS).
  - Evaluación del impacto de las reseñas sobre las ventas mediante gráficos de dispersión y coeficientes de correlación de Pearson.
- Perfilado de Usuarios por Región: Segmentación geográfica para identificar el Top 5 de plataformas y géneros, analizando también el impacto de la clasificación ESRB en cada mercado.
- Prueba de Hipótesis Estadísticas: Aplicación de pruebas inferenciales para validar supuestos sobre las calificaciones de los usuarios.

## Métricas
Las métricas clave empleadas para medir el éxito y validar los patrones fueron:
- Ventas Totales Brutas (en millones de USD): Métrica principal de éxito comercial.
- Mediana y Cuartiles de Ventas (vía Boxplots): Para entender el comportamiento del "juego promedio" frente a los grandes éxitos (outliers).
- Coeficiente de Correlación de Pearson ($r$): Para medir la fuerza y dirección de la relación lineal entre las puntuaciones de las reseñas (crítica/usuarios) y las ventas del juego.
- Valor P ($p\text{-value}$): Métrica de significancia estadística utilizada en las pruebas de hipótesis para aceptar o rechazar la hipótesis nula ($\alpha = 0.05$).

## Resultados
- Ciclo de Vida y Consolas Líderes: Se determinó que las plataformas tardan en promedio de 3 a 5 años en crecer y el mismo tiempo en desaparecer. Para el año 2017, las plataformas más rentables y en su fase de madurez son PS4 y Xbox One, mientras que la Nintendo 3DS sigue siendo sumamente relevante en el mercado asiático.
- Impacto de las Reseñas: Se encontró una correlación positiva moderada entre las calificaciones de los críticos y las ventas (los juegos con altas notas de la prensa tienden a vender más). Sorprendentemente, las calificaciones de los usuarios mostraron una correlación prácticamente nula con las ventas comerciales.
- Preferencias Regionales:
   - Norteamérica (NA) y Europa (EU): Comparten un perfil muy similar; sus consolas preferidas son PS4 y XOne, y su género predilecto es Action y Shooter. Los juegos clasificación M (Adultos) dominan el mercado.
   - Japón (JP): Rompe el patrón occidental por completo. La consola líder absoluta es la portátil Nintendo 3DS. El género más vendido es, por amplio margen, Role-Playing (RPG) y la clasificación ESRB tiene un impacto distinto debido a que muchos juegos locales no se rigen inicialmente por este sistema norteamericano (dejando muchos datos en blanco o favoreciendo clasificaciones aptas para adolescentes).

## Conclusiones
Las campañas de marketing deben enfocarse de forma diferenciada. Para el mercado occidental (NA y EU), los esfuerzos deben concentrarse en títulos de acción y disparos para PS4 y Xbox One. Para el mercado japonés, la inversión debe dirigirse a juegos de rol (RPG) para la familia de consolas de Nintendo.
A la hora de seleccionar qué juegos promocionar activamente en la tienda Ice, se debe priorizar aquellos que cuenten con un excelente Critic Score, ya que la opinión de la prensa especializada funciona como un predictor del volumen de ventas mucho más confiable que la opinión masiva de los usuarios.
Importancia del factor demográfico (ESRB): Los juegos con clasificación M (Mature) representan la mayor fuente de ingresos en Occidente, lo que demuestra que el público objetivo con mayor poder adquisitivo en estas regiones prefiere experiencias de juego más maduras y complejas.
