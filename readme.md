# Información para iniciar el Tutorial SQL 1 

.-Ingresar al Gitpod
.- Buscar el proyecto donde quede en los tres puntos.
.-Buscar la barra de hamburguesa en el VSC dar en view, command palette y luego escribir CodeRoad:start
.- Se abre un panel de trabajo
.-El terminal esta abierto para iniciar
.-Colocar comando echo sql Hello
.-Luego el comando psql --username=freecodecamp --dbname=postgres
.- Continuar con el tutorial.

# Gitpod

Tutorial 1: https://github.com/Laboratoria/learn-sql-by-building-a-student-database-part-1

# Pasos para iniciar el Tutorial 1

Paso 1

  echo sql Hello

Paso 2

  psql --username=freecodecamp --dbname=postgres
   
Paso 3

	Buscar la barra de hamburguesa en el VSC: en view, command palette y luego escribir CodeRoad:start

# Comandos

Conecta a una base de datos específica: \c nombre_de_base_de_datos: 
Ejemplo: \c students
Lista todas las tablas y vistas en la base de datos actual: \d
Ejemplo: \d 
Lista todas las bases de datos disponibles: \l
Ejemplo: \l 
Sale de la consola psql y regresa al sistema operativo: \q
Ejemplo: \q
Muestra la lista de comandos disponibles y una breve descripción de cada uno: \?
Ejemplo: \?
Lista todos los roles (usuarios) en el servidor PostgreSQL, junto con sus atributos y pertenencia a grupos: \du 
Ejemplo: \du
Muestra información sobre la conexión actual, como la dirección IP y el puerto del servidor:\conninfo 
Ejemplo: \conninfo
Ejecuta comandos SQL desde un archivo específico: \i ruta/al/archivo.sql
Ejemplo: \i /home/usuario/scripts/mi_script.sql

## Información necesaria para entender SQL

CREATE TABLE basedatos: Se utiliza para crear una nueva tabla en una base de datos. 

CREATE TABLE: Es el comando que indica que deseas crear una nueva tabla.

ADD COLUMN: Se utiliza para añadir una nueva columna a una tabla existente.

VARCHAR(): Se utiliza para almacenar cadenas de texto de longitud variable. 

NOT NULL: Es una restricción que se utiliza para asegurar que una columna en una tabla no acepte valores nulos. Esto significa que cada fila en la tabla debe contener un valor válido para esa columna; no se permiten entradas vacías o nulas.

INT: Tipo de dato que representa un número entero.

SERIAL: Tipo de dato específico en PostgreSQL para autonumeración, generalmente implementado como INT con una secuencia asociada.

PRIMARY KEY: Restricción que garantiza la unicidad y no nulidad de una columna (o conjunto de columnas), típicamente utilizada para identificar de manera única cada fila en una tabla.

FOREIGN KEY: Restricción que establece y mantiene la integridad referencial entre dos tablas, relacionando una columna en una tabla hija con la clave primaria o única en una tabla padre.

REFERENCES: Cláusula utilizada para especificar la tabla y la columna a la que se hace referencia cuando se define una FOREIGN KEY.

Truncate:Se utiliza para eliminar todos los registros de una o más tablas de manera rápida y eficiente, sin eliminar la estructura de las tablas. A diferencia de DELETE, que elimina filas una por una y puede registrar cada eliminación (lo que puede hacerla más lenta), TRUNCATE elimina todas las filas de una tabla en una sola operación, a menudo sin registrar individualmente cada fila eliminada.

touch: Es para crear un archivo vacío o actualizar la fecha y hora de un archivo existente. 

touch insert_data.sh: Comando para crear un archivo sh.

chmod +x insert_data.sh agregar permiso de ejecución: Se utiliza para agregar permisos de ejecución a un archivo en sistemas Unix/Linux. 

"#!/bin/bash": Para indicar que este archivo ejecute archivo bash,se conoce como shebang o hashbang y es crucial en los scripts de shell en sistemas Unix/Linux. 

"# Script to insert data from courses.csv and students.csv into students database": En un archivo de script de shell indica que el propósito del script es insertar datos desde los archivos CSV courses.csv y students.csv en una base de datos llamada students.

cat courses.csv esto es u texto: Se utiliza para mostrar el contenido del archivo courses.csv en la línea de comandos.
cat: Es una abreviatura de "concatenate". Este comando se usa para leer y mostrar el contenido de archivos.
courses.csv: Es el nombre del archivo cuyo contenido deseas visualizar.

./insert_data.sh  Este comando ejecuta el archivo insert_data.sh: Se utiliza para ejecutar el archivo insert_data.sh en un sistema Unix/Linux. 


## Consultas realizadas en el tutorial I

CREATE TABLE basedatos

CREATE TABLE students

CREATE TABLE MAJORS

CREATE TABLE courses

ALTER TABLE students ADD COLUMN firs_name VARCHAR(50) NOT NULL

ALTER TABLE students ADD COLUMN major VARCHAR(50) NOT NULL

ALTER TABLE students ADD COLUMN major_id INT