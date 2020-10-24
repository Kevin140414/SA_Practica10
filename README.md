# Software Avanzado Practica 11

Esta practica consiste en la creación de 4 contenedores, para formar un conjunto de microservicios de un restaurante, un repartidor y un cliente, los cuales se comunican por medio de un esb. Para montar esta configuración de contenedores se hace uso de docker-compose.

## Construcción de las imagenes utilizando Dockerfiles
Se deben constuir las imagenes de docker, para ello se deben ejecutar las siguientes instrucciones en la raiz de este proyecto, y en la carpeta correspondiente.

```
$ sudo docker build -t cliente .
$ sudo docker build -t repartidor .
$ sudo docker build -t restaurante .
$ sudo docker build -t esb .
```

## Crear los contenedores con el uso de docker-compose
Una vez ya se tienen las imagenes de docker creadas, se utilizara docker-compose para crear una red de contenedores para la comunicacion entre el contenedor del servidor web y el contenedor de la base de datos. Para crear esta red se debe ejecutar el siguiente comando:

```
$ sudo docker-compose up
```
## Configuración de un reverse proxy, para que los servicios se encuentren en el puerto 80 bajo distintas carpetas del proxy
### Ejemplo de configuración
location /restaurante/ {
	proxy_pass http://restaurante:3001;
}

## Link del video
- https://youtu.be/YpAO8V5F3JQ
