## Ruby on rails with react

## Instalar ruby

Para instalar ruby en linux podemos usar gestor de versiones como rvm(ruby versión manager) el cual nos permite manejar distintas versiones de ruby en un solo host, multiples entornos de interpretes y gemas.
Y si recién estas empezando te preguntarás como me puede ayudar rvm en comparación de la tipica instalación de ruby, imagina que estas trabajando un proyecto con rails 5.0 y ruby 2.4 y viene un cliente y quiere que le hagas unos cuantos cambios a un proyecto antiguo el cual se manejaba con las versión de rails 4.2 y ruby 2.1, para ello tendrías que volver a instalar asegurandote de cambiar el path y evitar que las versiones entren en conflicto, y para añadir la cereza al pastel de limón, imagina que quieres probar la ultima version de rails con webpack xd, para todo esto rvm es tu mejor solución.

## Rvm
Para instalar rvm en linux necesitarás seguir los siguientes pasos:
1. Dirigeté a la página de (rvm)[https://rvm.io/rvm/install] y agregamos la key publica en nuestra terminal, usaremos gpg que es una aplicacion para generar llaves publicas de encriptación utilizando opengpgp como protocolo, rvm nos pide utilizar una clave publica entonces copiamos y pegamos la llave publica que nos proporciona rvm

`pg --keyserver hkp://keys.gnupg.net --recv-keys 409B6B1796C275462A1703113804BB82D39DC0E3`

2. Instalamos la versión de rvm

`\curl -sSL https://get.rvm.io | bash`

Una vez finalize este proceso para poder proceder a utilizar rvm tenemos que activarlo usando el siguiente comando

`source /home/condef5/.rvm/scripts/rvm`

nota: cambia "condef5" por el nombre de tu user

3. Instalar una versión de ruby

Ahora podemos listar las versiones disponibles de ruby con el siguiente comando :

`rvm list known `

Y podemos darnos cuenta que existen muchas versiones disponibles, nosotros instalaremos las versión más estable:

`rvm install ruby-head`

4. Establecer una versión en nuestro sistema

Para poder listar las versiones disponibles de ruby podemos utilizar 

`rvm list`

Para poder usar una versión en especial 

`rvm use 2.4.1`

Para poder establecer una versión por defecto en nuestra terminal 

`rvm --default use 2.4.1`

Para poder usar la última version que usamos con ruby 

`rvm use ruby --latest`


## Instalar Rails 

Para instalar rails debemos fijarnos en que versión de ruby estamos y dependiendo de eso podemos instalar la versión adecuada de rails de forma local. 

Si deseas la versión beta mas reciente o la versión candidata, puedes instalarlo con --pre

```sh
$ gem install rails --pre 
$ rails -v
```

Si deseas la version estable más estable

```sh
$ gem install rails
$ rails -v
```

## Crear proyecto con rails y react

Tan simple como ejecutar

`rails new myapp --webpack=react`

#### Patrocinado por 

* Facebook => [https://www.facebook.com/drupvon/](https://www.facebook.com/drupvon/) 
* Youtube =>  [https://www.youtube.com/channel/UCTZN5u1Ad12nGBe2R9ssCmQ(https://www.youtube.com/channel/UCTZN5u1Ad12nGBe2R9ssCmQ)  
* Twitter => [https://twitter.com/drupvon](https://twitter.com/drupvon)  
