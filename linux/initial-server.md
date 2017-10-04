Crear un usuario con permisos root
```sh
adduser sammy
usermod -aG sudo sammy
```

Asumimos que ya generaste tu clave ssh, Imprimimos en nuestra maquina local la llave ssh
```sh
cat ~/.ssh/id_rsa.pub
```
Y la copiamos en nuestro clipboard.

En nuestro server:
```sh
su - sammy
mkdir ~/.ssh
chmod 700 ~/.ssh
nano ~/.ssh/authorized_keys
chmod 600 ~/.ssh/authorized_keys
exit
```
Ahora podemos acceder a nuestro servidor de la siguiente manera : `ssh sammy@${server_ip}`

