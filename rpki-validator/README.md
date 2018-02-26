# rpki-validator

Como validador de ROAs utilizamos el RIPE NCC RPKI Validator version 2.24 

1. Creamos una imagen para docker a partir del archivo Dockerfile definido para el rpki-validator
```sh
$ mkdir mydockerbuild_rpki-validator
$ cd mydockerbuild_rpki-validator
$ wget 
$ sudo docker build -t rpki-validator .
```
2. imagen
```sh
$ docker images

```
3. Ejecutamos el contenedor teniendo en cuenta que los puertos 8080 y 8282 son mapeados en el host para su acceso externo. En el puerto 8080 se ejecuta la interfaz web del validador y en el puerto 8282 se accede al repositorio de ROAs. 
```sh
$ sudo docker run --name rpki-validator -dit --restart unless-stopped -p 8080:8080 -p 8282:8282 rpki-validator
```
5. 
```sh
$ sudo docker exec -it rpki-validator /bin/bash
```
6. 
