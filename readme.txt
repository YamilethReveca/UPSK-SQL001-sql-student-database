### TUTORIAL I


# COMANDOS:

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

# CONSULTAS:

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

