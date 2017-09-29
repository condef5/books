# Introducción a docker

Docker es una plataforma de software que le permite crear, probar e implementar aplicaciones rápidamente. 
Docker empaqueta software en unidades estandarizadas llamadas contenedores que incluyen todo lo necesario 
para que el software se ejecute, incluidas bibliotecas, herramientas de sistema, código y tiempo de ejecución. 
Con Docker, puede implementar y ajustar la escala de aplicaciones rápidamente en cualquier 
entorno con la certeza de saber que su código se ejecutará.
 

## Instalar Docker en servidor linux

Para instalar docker en linux, ejecutamos el sgt comando:
```sh
curl -sSL https://get.docker.com/ | sh
```

Creamos un usuario `deploy` con privilegios Docker:
```sh
useradd --user-group --create-home --shell /bin/bash deploy
usermod -aG docker deploy 
```

Copiamos las llaves de root para el user `deploy`:
```sh
mkdir /home/deploy/.ssh
cp ~/.ssh/authorized_keys /home/deploy/.ssh/authorized_keys
chown deploy /home/deploy/.ssh/authorized_keys 
```

## Comandos para trabajar con docker

Listar imagenes:
```sh
$ docker images
```
Descargar imagenes:
```sh
$ docker pull <ID imagen> 
```
Borrar imagenes:
```sh
$ docker rmi  <ID imagen>
```

Listar contenedores:
```sh
$ docker ps
```

Listar contenedores activos:
```sh
$ docker ps -a
```
Iniciar un contenedor:
```sh
$ docker start <ID container>
```

Parar un contenedor activo:
```sh
$ docker stop <ID container>
```
 
Borrar un contenedor:
```sh
docker rm <ID container>
```

Parar y eliminar todos los contenedores:
```sh
docker stop $(docker ps -a -q)
docker rm $(docker ps -a -q)
// o
docker rm -f $(docker ps -a -q)
```

Para eliminar todas las imagenes:
```sh
docker rmi $(docker images -q)
```

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
