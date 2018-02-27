### IPv6 en Docker

Para habilitar IPv6 en Docker es necesario indicarlo con la opcion `--ipv6` al momento de correr el contenedor o habilitar la opcion `ipv6:` en el archivo de configuración. 

Si la subred es un /64, podemos definir un /80 para asignar a cada contenedor

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
