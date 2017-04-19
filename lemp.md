# Configure LEMP

LEMP es un grupo de software que se puede utilizar para servir páginas web dinámicas y aplicaciones web. Este es un acrónimo 
que describe un sistema operativo Linux, con un servidor web Nginx.
Los datos del backend se almacenan en la base de datos MySQL y el procesamiento dinámico es manejado por PHP.

## Nginx
```sh
sudo apt-get update
sudo apt-get install nginx
```
Permitir tráfico en el puerto 80.

Podemos habilitarlo escribiendo:

```sh
sudo ufw allow 'Nginx HTTP' 
```

Puede verificar el cambio escribiendo:

```sh
sudo ufw status 
```
## Mysql

