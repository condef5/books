## Instalación de docker en linux

* Instalar docker
```sh
$ curl -sSL https://get.docker.com/ | sh
```

* Instalar docker-compose
```sh
$ sudo curl -L https://github.com/docker/compose/releases/download/1.16.1/docker-compose-`uname -s`-`uname -m` -o /usr/local/bin/docker-compose
$ sudo chmod +x /usr/local/bin/docker-compose
$ docker-compose -v
```

## Instalación de docker en MacOS

* Primera opción: Instalar con [Docker Toolbox](https://docs.docker.com/toolbox/toolbox_install_mac/).

* Segunda opción: Instalar con [brew](https://pilsniak.com/how-to-install-docker-on-mac-os-using-brew).

## Despliegue del proyecto en local con docker

Es necesario tener instalado `docker` y `docker-compose`, clonamos el proyecto y ejecutamos docker-compose

```sh
$ git clone https://github.com/condef5/todo-hunter
$ cd todohunter
$ docker-compose up
```
El comando anterior creará e iniciará el contenedor `todohunter_web_1` que se estará ejecutando en http://localhost:2000 

### Flujo de trabajo en local
Creamos una cuenta en [docker-hub](https://hub.docker.com/) e iniciamos sesión en nuestra maquina:
```sh
$ docker login
```
Ahora cuando realicemos nuevos cambios en el código,  tenemos que registrar esos cambios en nuestra imagen.
Construimos la imagen y agregamos el tag todohunter:
```sh
$ docker build -t ${docker_user}/todohunter
```
Subimos la imagen a dockerhub
```sh
$ docker push ${docker_user}/todohunter
```
Nota: Reemplace el placeholder ${docker_user} por su `username` de docker hub. 

## Despliegue del proyecto en producción con docker

Instalamos `docker` en el servidor:
```sh
$ curl -sSL https://get.docker.com/ | sh
```

Creamos un nuevo usuario con Privilegios Docker:
```sh
$ useradd --user-group --create-home --shell /bin/bash deploy
$ usermod -aG docker deploy
```
Copiamos el archivo authorized_keys del usuario `root` al usuario `deploy`
```sh
$ mkdir /home/deploy/.ssh
$ cp ~/.ssh/authorized_keys /home/deploy/.ssh/authorized_keys
$ chown deploy /home/deploy/.ssh/authorized_keys 
```

Ahora cerramos la sesión, volvemos a conectarnos al servidor e iniciamos sesión en docker:
```sh
$ ssh deploy@${server_ip}
$ docker login
```
Descargamos la imagen desde docker-hub:
```sh
$ docker pull condef5/todohunter:latest
```

Eliminamos los contenedores antiguos si es que existen:
```sh
docker stop web || true
docker rm web || true
docker rmi condef5/todohunter:current || true
```
Actualizamos la nueva imagen:
```sh
docker tag condef5/todohunter:latest condef5/todohunter:current
```

Iniciamos el contenedor:
```sh
docker run -d --restart always --name web -p 80:80 condef5/todohunter:current
```
Y con esto el despliegue de la aplicación a finalizado.

 
