TUTORIAL 1

# Tutorial 1

## Paso 1

   echo sql Hello

## Paso 2

   psql --username=freecodecamp --dbname=postgres

Puedes obtener un historial de los comandos ejecutados en una terminal con el comando history.(PARA MAC , LINUX)

Importante. POSTGRES SQL si hace diferencia entre minuscula y mayúscula.

COMANDOS:
\c nombre_de_base_de_datos: Conecta a una base de datos específica
\c students
\d: Lista todas las tablas y vistas en la base de datos actual.
\d 
\l: Lista todas las bases de datos disponibles
\l 
\q: Sale de la consola psql y regresa al sistema operativo.
\q
\?: Muestra la lista de comandos disponibles y una breve descripción de cada uno.
\?
\du: Lista todos los roles (usuarios) en el servidor PostgreSQL, junto con sus atributos y pertenencia a grupos.
\du
\conninfo: Muestra información sobre la conexión actual, como la dirección IP y el puerto del servidor.
\conninfo
\i ruta/al/archivo.sql: Ejecuta comandos SQL desde un archivo específico.
\i /home/usuario/scripts/mi_script.sql





Otros comandos útiles
Salir de psql: \q
Ayuda en psql: \?
Ver todas las bases de datos: \l
Conectar a una base de datos: \c nombre_de_base_de_datos

CONSULTAS:

CREATE TABLE basedatos

ALTER TABLE students ADD COLUMN firs_name VARCHAR(50) NOT NULL

ALTER TABLE students ADD COLUMN major VARCHAR(50) NOT NULL

ALTER TABLE students ADD COLUMN major_id INT

ALTER TABLE
ADD COLUMN
VARCHAR()
NOT NULL
INT: Tipo de dato que representa un número entero.
SERIAL: Tipo de dato específico en PostgreSQL para autonumeración, generalmente implementado como INT con una secuencia asociada.
PRIMARY KEY: Restricción que garantiza la unicidad y no nulidad de una columna (o conjunto de columnas), típicamente utilizada para identificar de manera única cada fila en una tabla.
FOREIGN KEY: Restricción que establece y mantiene la integridad referencial entre dos tablas, relacionando una columna en una tabla hija con la clave primaria o única en una tabla padre.
REFERENCES: Cláusula utilizada para especificar la tabla y la columna a la que se hace referencia cuando se define una FOREIGN KEY.



touch insert_data.sh comando para crear un archivo sh.
chmod +x insert_data.sh agregar permiso de ejecución.

#!/bin/bash Para indicar que este archivo ejecute archivo bash.
# Script to insert data from courses.csv and students.csv into students database
cat courses.csv esto es u texto.
./insert_data.sh  Este comando ejecuta el archivo insert_data.sh.


cat courses.csv | while read MAJOR COURSE
do
  echo $MAJOR
done

// con esta imprimia solo la primera palabra de la tabla major

declare -p IFS

This variable is used to determine word boundaries. It defaults to spaces, tabs, and 
new lines. This is why the MAJOR variable was set to only the first word on each line 
from the data. Between the while and read commands, set the IFS to a comma like this: IFS=
","

cat courses.csv | while IFS="," read MAJOR COURSE
do
  echo $MAJOR
done

// este me imprime hasta donde esta la coma de la tabla major



cat courses.csv | while IFS="," read MAJOR COURSE
do
  echo $MAJOR $COURSE
done

// en esta  linea se va a imprimir el major y el course una al lado de la otra sin coma solamente un espacio.


cat courses.csv | while IFS="," read MAJOR COURSE
do
  # get major_id
  # if not found
  # insert major
  # get new major_id
  # get course_id
  # if not found
  # insert course
  # get new course_id
  # insert into majors_courses

done


You used the psql command to log in and interact with the database. You can use it to just run a single command and exit. Above your loop, add a PSQL variable that looks like this: PSQL="psql -X --username=freecodecamp --dbname=students --no-align --tuples-only -c". This will allow you to query your database from your script. The important parts are the username, dbname, and the -c flag that is for running a single command and exiting. The rest of the flags are for formatting.

1. Add the suggested variable between your first comment and the loop

2. The suggested area should look like this:

PSQL="psql -X --username=freecodecamp --dbname=students --no-align --tuples-only -c"




PSQL="psql -X --username=freecodecamp --dbname=students --no-align --tuples-only -c"
cat courses.csv | while IFS="," read MAJOR COURSE
do
  # get major_id
  MAJOR_ID=$($PSQL "SELECT major_id FROM majors WHERE major='$MAJOR'")
  echo $MAJOR_ID
  # if not found
  # insert major
  # get new major_id
  # get course_id
  # if not found
  # insert course
  # get new course_id
  # insert into majors_courses

done
