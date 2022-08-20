# Parcial 1 - Gestión de Datos
# Andrés Leonardo Medina Quijano
 
# Desarrollo Parcial
## Punto 1 - Exploración de datos

La siguiente tabla presenta los campos del dataset y una breve caracterización y descripción de cada uno:

| Campo original              | Campo nuevo              | Tipo de dato | Tipo de dato Pandas | Descripción                                                                 | Valores nulos |
| --------------------------- | ------------------------ | ------------ | ------------------- | --------------------------------------------------------------------------- | ------------- |
| gender                      | GÉNERO                   | Alfabético   | object              | Género del estudiante (No binario, masculino o femenino)                    | SI            |
| race/ethnicity              | RAZA\_ETNIA              | Alfabético   | object              | Raza del estudiante (Grupos identificados por letras)                       | SI            |
| parental level of education | NIVEL\_EDUCACIÓN\_PADRES | Alfabético   | object              | Nivel de educación de los padres                                            | SI            |
| lunch                       | ALMUERZO                 | Alfabético   | object              | Tipo de almuerzo que tiene el estudiante                                    | SI            |
| test preparation course     | PREPARACION\_CURSO       | Alfabético   | object              | Identifica si el estudiante realizó una prueba de preparación para el curso | SI            |
| math score                  | MATEMATICAS              | Decimal      | float64             | Calificación de matemáticas                                                 | SI            |
| reading score               | LECTURA                  | Decimal      | float64             | Calificación de lectura                                                     | SI            |
| writing score               | ESCRITURA                | Decimal      | float64             | Calificación de escritura                                                   | SI            |

## Punto 2 - Limpieza de datos

El principal problema detectado, son campos vacíos, que pueden afectar el análisis, se definieron las siguientes estrategias para cada campo:
- Género: Reclasificar a "Otro"
- Raza: Omitir
- Nivel de educación padres: Eliminar filas vacías
- Almuerzo: Omitir
- Preparación curso: Eliminar filas vacías
- Calificación matemáticas: Eliminar filas vacías
- Calificación lectura: Eliminar filas vacías
- Calificación escritura: Eliminar filas vacías

Los casos de omitir se deben a que a pesar de los vacíos no afectan el análisis que se desea realizar

Con la limpieza de datos finalmente el DataFrame quedo con 772 filas para el análisis

## Punto 3 - Promedio por asignatura

La siguiente tabla presenta los promedios de los estudiantes por cada asignatura:

| ASIGNATURA  | CALIFICACIÓN PROMEDIO |
| ----------- | --------------------- |
| MATEMATICAS | 66,2616580            |
| LECTURA     | 69,5466321            |
| ESCRITURA   | 68.,207253            |

Se evidencia claramente que hay un puntaje promedio mayor en lectura, sin embargo, la diferencia entre las 3 es de poco más de 3 puntos, lo cuál es muy bajo y aún más si se compara con la desviación estándar: 1.37222. Por lo que se concluye que no hay un sesgo en los datos.

## Punto 4 - Correlación entre calificaciones

Se realizaron diferentes combinación de correlaciones utilizando las correlaciones de spearman y de pearson así:
### Entre las tres asignaturas

La correlación es bastante alta, siempre superando 0.8, esto se ve acentuado por el resultado del punto anterior y la cercanía entre dichos valores

Se realizaron las combinaciones de correlación entre dos asignaturas para ver que alguno estuviera generando una dependencia que no se notará en el análisis de las 3

### Matemáticas vs Lectura

La correlación es de 0.8 por lo que es bastante alta y respeta el resultado del análisis de las 3

### Matemáticas vs Escritura

La correlación está entre 0.77 y 0.8 por lo que a pesar de ser la más baja se mantiene cerca y respeta el resultado del análisis de las 3

### Escritura vs Lectura

Es la correlación más alta (0.94 y 0.95) y se mmantiene cerca al resultado del análisis de las 3, aunque es la correlación que lo mantiene elevado

### Conclusión

Se puede decir que existe una correlación entre los resultados de las 3 materias, y es positivo, esto significa que si el promedio de una materia aumenta lo más seguro es que en las demás también aumente, esto puede deberse a diversos factores pero con los datos obtenido se presume que puede ser debido a la preparación de los estudiantes

## Punto 5 - Promedio entre géneros

- Analizando los resultados por género en matemáticas se evidencia que la diferencia es muy poca, siendo de 4,72 la diferencia entre el máximo y el mínimo promedio, y con una desviación estándar de 2.34 entre los datos
- El género que obtuvo el mejor promedio general fue el femino con 69.88, seguido por el no-binario con 69.214

##Punto 6 - Por encima del percentil 85

Se evidencia que hubo 113 alumnos por encima del percentil 85 en escritura

La distribución del nivel de educación de los padres de estos estudiantes es la siguiente:

| Nivel de educación      |  %   |
| ----------------------- | ---- |
| Bachiller               | 11,8 |
| Preparatoria            | 19,8 |
| Algo de la preparatoria | 17   |
| Algo de la universidad  | 22,3 |
| Pregrado                | 22,4 |
| Maestría                | 6,7  |