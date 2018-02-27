# BIRD

Para ejecutar la version 2.0.1 de bird dentro de un contenedor de docker seguimos los siguientes pasos

1. Creamos una imagen de docker a partir del archivo [Dockerfile](Dockerfile)
```sh
$ mkdir mydockerbuild_bird
$ cd mydockerbuild_bird
$ wget https://github.com/sancolo/rpki-lab/bird/Dockerfile
$ sudo docker build -t bird-2.0.1 .
```
2. Verificamos que la imagen esta creada en el host
```sh
$ docker images
REPOSITORY                  TAG                 IMAGE ID            CREATED             SIZE
bird-2.0.1                  latest              6c4040cd8d28        11 days ago         392MB
```
3. Creamos el directorio rbird1 y copiamos el archivo bird.conf de este repositorio en el directorio
```sh
$ mkdir $HOME/rbird1
$ cd $HOME/rbird1
$ wget https://github.com/sancolo/rpki-lab/blob/lunes/bird/rbird1.conf
$ ln -s rbird1.conf bird.conf
```
4. Ejecutamos el contenedor a partir de la imagen creada y montando el directorio local donde se encuentra el archivo de configuracion bird.conf para BIRD
```sh
$ sudo docker run -d --privileged --name rbird1 -v `$HOME/rbird1:/etc/bird:rw bird-2.0.1
```
5. Verificamos que el contenedor se esta ejecutando
```sh
$ docker ps
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS        PORTS        NAMES
1611c3c34128        bird-2.0.1          "/bin/sh -c 'bird -c…"   6 days ago          Up 6 days     179/tcp      rbird1
```
6. Para entrar al contenedor ejecutamos
```sh
$ sudo docker exec -it rbird1 /bin/bash
root@1611c3c34128:~# birdc
BIRD 2.0.1 ready.
bird> show status
BIRD 2.0.1
Router ID is 172.17.0.3
Current server time is 2018-02-26 22:05:01.227
Last reboot on 2018-02-20 15:46:49.565
Last reconfiguration on 2018-02-21 21:07:36.712
Daemon is up and running
bird>     
```
