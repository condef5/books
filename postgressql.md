# Intalar PGADMIN IV en ubuntu

Primero necesitamos instalar python, pip y algunos otros packages en nuestro sistema operativo:

```sh
sudo apt-get install build-essential libssl-dev libffi-dev libgmp3-dev virtualenv python-pip libpq-dev python-dev
```

## 1. Crear un entorno virtual

Crearemos un entorno virtual con python, esto lo hacemos para evitar conflictos entre versiones de nuestros 
paquetes o dependencias al momento de trabajar con python, más acerca de los entornos virtuales 
(aquí)[https://docs.python.org.ar/tutorial/3/venv.html].

```sh
cd /opt/
sudo mkdir enviromentpy
cd enviromentpy/
sudo virtualenv pgadmin4
cd pgadmin4
source bin/activate
```

## 2. Descargar e instalar PGADMIN IV

```sh
wget https://ftp.postgresql.org/pub/pgadmin/pgadmin4/v1.3/pip/pgadmin4-1.3-py2.py3-none-any.whl
pip install pgadmin4-1.3-py2.py3-none-any.whl 
```

## 3. Crear archivo de configuración

Crearemos un archivo local de configuración para PGADMIN IV

```sh
cd lib/python2.7/site-packages/pgadmin4
sudo touch config_local.py
```

Para configurar PGAdmin 4 para que se ejecute en modo de usuario único, agreguamos la siguiente linea:

```sh
sudo echo "SERVER_MODE = False" >> config_local.py
```

## 4. Ejecutar PGADMIN 4

Ejecutamos el siguiente comando

```sh
cd /opt/enviromentpy/pgadmin4
python lib/python2.7/site-packages/pgadmin4/pgAdmin4.py
```
En la consola nos dice que debemos ir a la ruta [http://localhost:5050](http://localhost:5050).

## 5. Agregar una conexión

Ahora simplemente le damos click en Server -> Create -> Server 

En la pestaña general agregamos un nombre y una descripción. En la otra pestaña conexión agregamos en host:localhost y agregamos nuestro user y password,
como en la siguiente imagen:

![Consola](images/pgadmin.png)

Nota: Si tienes problemas al agregar un server con las credenciales de autentificación, puedes hacer esto: 

```sh
sudo -u postgres psql
ALTER USER "postgres" WITH PASSWORD 'postgres';
```
Nota2: Puedes automatizar los pasos para iniciar el PGADMIN de la sgt manera:

* Crea un archivo en el home de tú sistema : `cd ~ && touch pgadmin.sh`
* Edita el archivo : `nano pgadmin.sh`
* Agrega el siguiente codigo: 
```sh
#!/bin/bash
source /opt/pgadmin4/bin/activate
python /opt/pgadmin4/lib/python2.7/site-packages/pgadmin4/pgAdmin4.py
```
  Presiona ctrl + x y guarda los cambios.
  
* Agrega el permiso de ejecución: `sudo chmod +x ~/pgadmin.sh`
* Para iniciar PGADMIN4 bastará con ejecutar: `cd ~ && ./pgadmin.sh` 

