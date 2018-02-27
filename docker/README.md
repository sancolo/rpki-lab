### Docker commands and tips
- Listado de imagenes en el host
```sh
$ docker images
```
- Ver procesos contenedores corriendo en el host
```sh
$ docker ps
```
- Listado de dispositivos de red
```sh
$ docker network list
```
- Detalle de un dispositivo de red (Ej: bridge)
```sh
$ docker network inspect bridge
```
- Logs de un contenedor (Ej: rbird1)
```sh
$ docker logs --tail 20 rbird1
. . . . . 
bird: Reconfiguring
bird: Reloading channel bgp1.ipv4
bird: Reconfigured
bird: Accept unknown ROA 0.0.0.0/0 for ASN 65002
bird: Accept unknown ROA 192.168.0.0/16 for ASN 65002
bird: Ignore invalid ROA 86.49.0.0/17 for ASN 65002
bird: Accept unknown ROA 10.0.0.0/8 for ASN 65002
bird: Ignore invalid ROA 200.3.12.0/22 for ASN 65002
bird: Reconfiguring
bird: Reloading channel bgp1.ipv6
bird: Reconfigured
bird: Accept unknown ROA ::/0 for ASN 65002
bird: Accept unknown ROA 2001:db8:4000::/48 for ASN 65002
bird: Accept unknown ROA 2001:db8::/32 for ASN 65002
bird: Ignore invalid ROA 2001:13c7:7002::/48 for ASN 65002
bird: Accept unknown ROA 2000::/4 for ASN 65002
bird: Ignore invalid ROA 2001:13c7:7012::/49 for ASN 65002
. . . . .
```
- Parar un contenedor
```sh
$ docker stop rbird1
```
- Remover un contenedor
```
$ docker rm rbird1
```



