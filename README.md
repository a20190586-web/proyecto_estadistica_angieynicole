# Desigualdad digital y empleabilidad en jóvenes peruanos (18–29 años) 2022–2023

##  Descripción del proyecto
Este proyecto analiza cómo el **acceso a Internet influye en la probabilidad de tener un empleo formal** entre jóvenes peruanos (18–29 años) durante el periodo **pospandemia (2022–2023)**.  
La investigación utiliza datos de la **Encuesta Nacional de Hogares (ENAHO)** del **INEI**, disponibles en: [https://proyectos.inei.gob.pe/microdatos/](https://proyectos.inei.gob.pe/microdatos/).

> Por razones de tamaño, los archivos originales de ENAHO no se incluyen en este repositorio. Solo se sube la data limpia y el archivo `.Rmd` en la carpeta "códigos", donde se detalla el proceso completo de limpieza y análisis.

##  Objetivo
Evaluar si el acceso a Internet en el hogar aumenta la probabilidad de acceder a un empleo formal, controlando por educación, género y zona geográfica.

##  Marco teórico
- **Desarrollo humano (Sen, 1999):** el acceso digital amplía capacidades y oportunidades.  
- **Capital digital (Van Dijk, 2005):** las habilidades tecnológicas mejoran la empleabilidad.  
- **Desigualdad estructural (Castells, 2000):** la brecha digital reproduce desigualdades sociales.  

##  Metodología
- **Base de datos:** ENAHO 2022–2023 (módulos de empleo y TIC).  
- **Unidad de análisis:** jóvenes ocupados de 18–29 años.  
- **Método:** regresión logística binaria.  
- **Variables clave:** acceso a Internet, empleo formal, educación, género, zona.  

##  Diccionario de datos
| Módulo | Variable original | Nuevo nombre | Tipo | Descripción | Valores principales |
|:--|:--|:--|:--|:--|:--|
| Todos | ubigeo | ubigeo | chr | Código geográfico del distrito (6 dígitos) | Ej. “150101” = Lima-Cercado |
| Todos | conglome | conglome | int | Identificador del conglomerado ENAHO | Numérico |
| Todos | vivienda | vivienda | int | Número de vivienda dentro del conglomerado | Numérico |
| Todos | hogar | hogar | int | Identificador del hogar en la vivienda | Numérico |
| Hogar | p1144 | interh | factor | Hogar con acceso a Internet | 1 = Sí, 2 = No |
| Individuo | p207 | sexo | factor | Sexo del individuo | 1 = Hombre, 2 = Mujer |
| Individuo | p208a | edad | int | Edad en años cumplidos | Numérico |
| Individuo | p209 | estciv | factor | Estado civil | 1 = Soltero, 2 = Casado, 3 = Conviviente, etc. |
| Educación | p300a | lengua | factor | Primera lengua aprendida | 1 = Castellano, 2 = Quechua, 3 = Aymara, etc. |
| Educación | p301a | ultani | int | Último año o grado aprobado | Escala ordinal |
| Educación | p313 | razest | factor | Motivo por el que no estudia | 1 = Económica, 2 = Falta de interés, etc. |
| Empleo | p501 | trabsp | factor | Trabajó la semana pasada | 1 = Sí, 2 = No |
| Empleo | p507 | catocu | factor | Categoría ocupacional | 1 = Empleado, 2 = Independiente, etc. |
| Empleo | p511a | tipcon | factor | Tipo de contrato | 1 = Indefinido, 2 = Temporal, etc. |
| Empleo | p514 | otrtra | factor | Tiene otro trabajo | 1 = Sí, 2 = No |

##  Contenido del Repositorio
- data_limpia: `data_jovenes_22.csv`, `data_jovenes_23.csv` y `data_limpia.csv`  
- `códigos`: limpieza, merge y análisis estadístico.
