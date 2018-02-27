### IPv6 en Docker

Si la subred es un /64, podemos definir un /80 para asignar a cada contenedor

```sh
# cat /etc/docker/daemon.json
{
  "ipv6": true,
  "fixed-cidr-v6": "2800:db8:4000:::/80"
}
