# toba-docker-template

## Levantar el stack
docker compose up -d

## Ingresar al contenedor

docker exec -it toba_docker bash

## Instalar toba

bin/toba instalacion instalar

ln -s /var/local/docker-data/toba_docker-instalacion/toba.conf /etc/apache2/conf.d/toba.conf

Hace falta reiniciar apache en el contenedor

Navegar al editor : http://localhost:7008/toba_editor/3.4/


## Cargar proyecto

El directorio  "/var/local/docker-data/proyecto"  se encuentra montado,  se puede descargar el proyecto desde el contenedor (tiene el git instalado) o desde el SO anfitrión.

source entorno_toba.env

toba proyecto cargar -p proyecto_toba -d '/var/local/docker-data/proyecto/proyecto_toba'

Verificar permisos correspondientes en los directorios:

/var/local/docker-data/proyecto

/usr/local/build/vendor/


## Base de datos
Se puede acceder por localhost:7432

## Bajar stack
docker compose down

