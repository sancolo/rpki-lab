# BIRD

Para ejecutar la version 2.0.1 de bird dentro de un contenedor de docker seguimos los siguientes pasos

1. Creamos una imagen de docker a partir del archivo Dockerfile
```sh
$ mkdir mydockerbuild_bird
$ cd mydockerbuild_bird
$ vi DockerFile
$ sudo docker build -t bird-2.0.1 .
```
2. Verificamos que la imagen esta creada en el host
```sh
$ docker images
REPOSITORY                  TAG                 IMAGE ID            CREATED             SIZE
...
bird-2.0.1                  latest              6c4040cd8d28        11 days ago         392MB
...
```
3. Creamos el directorio rbird1 y copiamos el archivo bird.conf de este repositorio en el directorio
```sh
$ mkdir $HOME/rbird1
$ cd $HOME/rbird1
$ vi bird.conf
```
4. Ejecutamos el contenedor a partir de la imagen creada y montando el directorio local donde se encuentra el archivo de configuracion bird.conf para BIRD
```sh
$ sudo docker run -d --privileged --name rbird1 -v `$HOME/rbird1:/etc/bird:rw bird-2.0.1
```
5. Verificamos que el contenedor se esta ejecutando
```sh
$ docker ps
```
6. 
