# toba-docker-template

## Levantar el stack
```bash
docker compose up -d
```


## Ingresar al contenedor
```bash
docker exec -it toba_docker bash
```
## Instalar toba
```bash
bin/toba instalacion instalar
```
Nota: en la instalación en referencia a la base de datos ingresar:
```bash
PostgreSQL - Ubicaci�n (ENTER utilizar� localhost): pg
PostgreSQL - Puerto (ENTER utilizar�: 5432): 5432
PostgreSQL - Usuario (ENTER utilizar� postgres): postgres
PostgreSQL - Clave  (ENTER para usar sin clave): postgres
```

```bash
ln -s /var/local/docker-data/toba_docker-instalacion/toba.conf /etc/apache2/conf.d/toba.conf
```

Hace falta reiniciar apache en el contenedor

Navegar al editor : http://localhost:7008/toba_editor/3.4/


## Cargar proyecto

El directorio  "/var/local/docker-data/proyecto"  se encuentra montado,  se puede descargar el proyecto desde el contenedor (tiene el git instalado) o desde el SO anfitrión.
```bash
source entorno_toba.env
```
toba proyecto cargar -p proyecto_toba -d '/var/local/docker-data/proyecto/proyecto_toba'

Verificar permisos correspondientes en los directorios:

/var/local/docker-data/proyecto

/usr/local/build/vendor/


## Base de datos
Acceso:  localhost:7432

## Bajar stack
```bash
docker compose down
```
