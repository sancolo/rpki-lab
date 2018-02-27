### IPv6 en Docker

Para habilitar IPv6 en Docker es necesario indicarlo con la opcion `--ipv6` al momento de correr el contenedor o habilitar la opcion `ipv6:` en el archivo de configuración. 

Si queremos asignar un bloque fijo IPv6 a los contenedores, es necesario hacerlo en el archivo daemon.json utilizando la opcion `fixed-cidr-v6`.  
Por ejemplo, si la subred es un /64, podemos definir un /80 desde donde asignar direcciones IPv6 a cada contenedor

```sh
# cat /etc/docker/daemon.json
{
  "ipv6": true,
  "fixed-cidr-v6": "2800:db8:4000:::/80"
}
```

Los cambios en el archivo daemon.json requieren un reload del demonio docker 
```sh
$ systemctl reload docker
```
