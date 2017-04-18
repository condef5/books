# Install ruby in linux using rvm

Con rvm podemos manjear multiples versiones con ruby, esto hace que las diferentes versiones no colicionen puesto que 
tienen gemfiles separados.

Usaremos gpg que es una aplicacion para generar llaves publicas de encriptación utilizando opengpgp como protocolo, 
rvm nos pide utilizar una clave publica entonces copiamos y pegamos la llave publica que nos proporciona [rvm](http://rvm.io/rvm/install) 

`gpg --keyserver hkp://keys.gnupg.net --recv-keys 409B6B1796C275462A1703113804BB82D39DC0E3`

Ahora procedemos a instalar rvm

`\curl -sSL https://get.rvm.io | bash`

Una vez finalize este proceso para poder proceder a utilizar rvm tenemos que activarlo usando el siguiente comando
 
`source /home/condef5/.rvm/scripts/rvm`

En el comando anterior cambia `condef5` por el nombre de tu user.

Ahora podemos listar las versiones disponibles de ruby con el siguiente comando `rvm list known` y podemos darnos cuenta que existen
muchas versiones disponibles, nosotros instalaremos las versión más estable:

`rvm install ruby-head` 

Para poder listar las versiones disponibles de ruby podemos utilizar `rvm list` 

Para poder usar una versión en especial `rvm use 2.4.1`

Para poder establecer una versión por defecto en nuestra terminal `rvm --default use 2.4.1`

Para poder usar la ultima version `rvm use ruby --latest`









