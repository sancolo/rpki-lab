# rpki-validator

Como validador de ROAs utilizamos el RIPE NCC RPKI Validator version 2.24 

1. 

2.
```sh
$ mkdir mydockerbuild_rpki-validator
$ cd mydockerbuild_rpki-validator
$ wget 
$ sudo docker build -t rpki-validator .
```
3.

4. 
```sh
$ sudo docker run --name rpki-validator -dit --restart unless-stopped -p 8080:8080 -p 8282:8282 rpki-validator
```
5. 
```sh
$ sudo docker exec -it rpki-validator /bin/bash
```
6. 
