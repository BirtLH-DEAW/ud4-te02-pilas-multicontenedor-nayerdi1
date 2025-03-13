# Crea la imagen intermedia
FROM ubuntu:latest as intermedia

# Instala git
RUN apt-get update \
    && apt-get -y install git

# Clona el repositorio desde Github
RUN git clone https://github.com/deaw-birt/UD4-despliegue-PHP.git 

# Crea la segunda capa de la imagen
FROM mysql:5.7

# Copia los scrips al directorio que queremos
# Les ponemos numero para que se ejecuten en orden
COPY --from=intermedia /UD4-despliegue-PHP/mysql/crearBBDD.sql /docker-entrypoint-initdb.d/1-crearBBDD.sql
COPY --from=intermedia /UD4-despliegue-PHP/mysql/InsertarDatos.sql /docker-entrypoint-initdb.d/2-insertarDatos.sql

# Expone el puerto 3306
EXPOSE 3306