# Información para iniciar el Tutorial SQL II

.-Ingresar al Gitpod
.-Buscar el proyecto donde quede en los tres puntos.
.-Buscar la barra de hamburguesa en el VSC dar en view, command palette y luego escribir CodeRoad:start
.-Se abre un panel de trabajo
.-El terminal esta abierto para iniciar
.-Colocar comando echo sql Hello
.-Luego el comando psql --username=freecodecamp --dbname=postgres
.-Continuar con el tutorial.

# Gitpod

Tutorial 2: https://github.com/Laboratoria/learn-sql-by-building-a-student-database-part-1

Paso 1

    echo sql Hello

Paso 2

    psql --username=freecodecamp --dbname=postgres
   
Paso 3

	Buscar la barra de hamburguesa en el VSC: en view, command palette y luego escribir CodeRoad:start

# Comandos y cláusulas

* SELECT: Se utiliza para consultar y recuperar datos de una base de datos. Permite seleccionar columnas específicas de una o más tablas y, a menudo, se utiliza en combinación con otras cláusulas para filtrar, ordenar y agrupar datos.
* "*": Selecciona todas las columnas.
* FROM: Especifica la tabla de la que se deben recuperar los datos.
* WHERE: Condición (Opcional). Filtra los registros que cumplen con la condición especificada.
* ORDER BY: Ordena los resultados.
* HAVING: Filtra grupos de datos.
* COUNT: Se utiliza para contar el número de filas en un conjunto de resultados. Puedes contar todas las filas o solo las filas que cumplen con una condición.
* SUM: Se utiliza para sumar los valores de una columna numérica en un conjunto de resultados.
* MAX: Se utiliza para encontrar el valor máximo en una columna numérica o de fecha en un conjunto de resultados.
* MIN: Se utiliza para encontrar el valor mínimo en una columna numérica o de fecha en un conjunto de resultados.
* JOIN: Combina datos de múltiples tablas.
* LIMIT: Limita el número de resultados.
* INNER JOIN: Se utiliza para combinar filas de dos o más tablas basadas en una condición de coincidencia. Solo se devuelven las filas que tienen coincidencias en ambas tablas.
* FULL JOIN: Se utiliza para combinar filas de dos tablas y devuelve todas las filas cuando hay una coincidencia en una de las tablas. Si no hay coincidencia, devuelve NULL para las columnas de la tabla que no tiene coincidencia.
* USING: Se utiliza en los JOIN para simplificar la condición de combinación cuando las columnas de las dos tablas tienen el mismo nombre.
* AS: Asigna un nombre alternativo (alias) a la columna en el resultado.
* ON: La cláusula ON se utiliza en las sentencias JOIN para especificar la condición de combinación entre dos tablas.
* DISTINCT:La cláusula DISTINCT en SQL se utiliza para eliminar duplicados de los resultados de una consulta, devolviendo solo valores únicos en el conjunto de resultados.
* INSERT: Inserta nuevos datos en una tabla.
* UPDATE: Modifica datos existentes en una tabla.
* DELETE: Elimina datos de una tabla.
* CREATE TABLE: Crea una nueva tabla en la base de datos.
* DROP TABLE: Elimina una tabla de la base de datos.

# Ejemplos de select realizados en el tutorial 2

* SELECT * FROM students;
* SELECT * FROM students WHERE major='Data Science';
* SELECT * FROM students WHERE major='Data Science' ORDER BY name ASC;
* SELECT major_id, COUNT(*) AS number_of_students FROM students GROUP BY major_id;
* SELECT major_id FROM students GROUP BY major_id;
* SELECT major_id, COUNT(*) FROM students GROUP BY major_id;
* SELECT major_id, MIN(gpa) FROM students GROUP BY major_id;
* SELECT major_id, MIN(gpa), MAX(gpa) FROM students GROUP BY major_id;
* SELECT major_id, MIN(gpa), MAX(gpa) FROM students GROUP BY major_id HAVING MAX(gpa) = 4.0
* SELECT major_id, MIN(gpa) AS min_gpa, MAX(gpa) FROM students GROUP BY major_id HAVING MAX(gpa)=4.0;
* SELECT major_id, MIN(gpa) AS min_gpa, MAX(gpa) AS max_gpa FROM students GROUP BY major_id HAVING MAX(gpa) = 4.0;
* SELECT major_id, COUNT(*) AS number_of_students FROM students GROUP BY major_id HAVING COUNT(*) < 8;
* SELECT * FROM students FULL JOIN majors ON students.major_id = majors.major_id;
* SELECT major FROM students INNER JOIN majors ON students.major_id= majors.major_id;
* SELECT DISTINCT(major) FROM students INNER JOIN majors ON students.major_id = majors.major_id;
* SELECT * FROM students RIGHT JOIN majors ON students.major_id = majors.major_id;
* SELECT * FROM students RIGHT JOIN majors ON students.major_id= majors.major_id;
* SELECT * FROM students RIGHT JOIN majors ON students.major_id = majors.major_id WHERE student_id IS NULL;
* SELECT * FROM students LEFT JOIN majors ON students.major_id=majors.major_id;
* SELECT * FROM students LEFT JOIN majors ON students.major_id=majors.major_id WHERE major='Data Science' OR gpa>=3.8;
* SELECT * FROM students FULL JOIN majors ON students.major_id = majors.major_id WHERE first_name LIKE '%ri%' OR major LIKE '%ri%'; 
* SELECT students.major_id FROM students FULL JOIN majors AS m ON students.major_id= m.major_id;
* SELECT s.major_id FROM students AS s FULL JOIN majors AS m ON s.major_id = m.major_id;
* SELECT * FROM students FULL JOIN majors USING(major_id) FULL JOIN majors_courses USING(major_id) FULL JOIN courses USING(course_id);