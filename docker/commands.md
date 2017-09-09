## Comandos

Detener todos los contenedores
```sh
$ docker stop $(docker ps -a -q)
```

Borrar todos los contenedores
```sh
$ docker rm $(docker ps -a -q)
```

Borrar todas las imagenes
```sh
$ docker rmi $(docker images -q)
```

Borra todos los contenedores y actualiza la cache
```sh
docker system prune -a 

```
