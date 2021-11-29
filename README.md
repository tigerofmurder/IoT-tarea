# IoT-tarea

Alumnos:
  Cueva Flores, Jonathan Brandon
  
  Garcia Diaz, German Flavio
  
  Montesinos Apaza, Sergio


# PASOS A SEGUIR
## Antes de iniciar el docker
Verificar si no esta corriendo mysql en su maquina
```
sudo netstat -nlpt |grep 3306
```
Si hay un proceso en ejecucion detener
```
sudo service mysql stop
```
## Ejecutar nuestro archivo .yml
### Crear red interna
```
docker network create <<nombre de red>>
```
para nuestro caso:
```
docker network create iot-network
```
### Inicializar nuestro docker
```
docker-compose up
```
### Ingresamos a nuestro contenedor o VM
```
docker exec -it <<nombre-asignado-por-docker>> bash
```
En nuestro caso
```
docker exec -it iotsecond_mysql_1 bash
```
### Ingresamos a Mysql
```
mysql -u root -p
```
la contraseña de nuestro mysql la especificamos en nuestro archivo .yml para nuestro caso es "password"
### Ingresando a la base de datos "TimeSeries"
```
use TimeSeries
```
### Creando la tabla en nuestra BD
```
CREATE TABLE thingData ( id INT NOT NULL AUTO_INCREMENT PRIMARY KEY, topic varchar(1024), payload varchar(2048), timestamp varchar(15), deleted binary(1) ) 
```
