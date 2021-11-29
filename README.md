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

