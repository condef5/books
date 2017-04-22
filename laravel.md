### Install laravel in linux


```sh
composer global require "laravel/installer"
```

Si te muestra un error puede que se deba a que composer no se haya agregado al path, puedes corregirlo abriendo 

`nano ~/.bashrc`

Y agregando la siguieten linea :

`export PATH=~/.composer/vendor/bin:$PATH`

Puedes reiniciar la terminal o escribir :

`source ~/.bashrc `

Nota: en algunos casos composer se encuentra en la carpeta `~/.config/composer` en vez de `~/.composer` asi que puedes agregar esta linea al path en vez de la de arriba :

`export PATH=~/.config/composer/vendor/bin:$PATH`


### Solucionando los problemas con laravel new

* The Zip PHP extension is not installed

Para solucionar este problema bastará con instalar zip con nuestra versión de php instalada

`sudo apt-get install php7.*-zip` 

Nota: reemplaza el * por tu versión de php si tienes php7.1 cambia el * por el 1 :) .

*  Problem 1

    - Installation request for laravel/framework v5.4.19 -> satisfiable by laravel/framework[v5.4.19].
    - laravel/framework v5.4.19 requires ext-mbstring * -> the requested PHP extension mbstring is missing from your system.
    
    Solución :
    
    `sudo apt-get install php-mbstring php7.1-mbstring php-gettext`
    
*  Problem 2
    - Installation request for phpunit/php-code-coverage 4.0.8 -> satisfiable by phpunit/php-code-coverage[4.0.8].
    - phpunit/php-code-coverage 4.0.8 requires ext-dom * -> the requested PHP extension dom is missing from your system.
    
    Solución :
    
    `sudo apt-get install php-xml`
    
*  Problem 3
    - Installation request for phpunit/phpunit 5.7.19 -> satisfiable by phpunit/phpunit[5.7.19]. 
    
    Solución :
    
    ``

* Problem 4
    - laravel/framework v5.4.19 requires ext-mbstring * -> the requested PHP extension mbstring is missing from your system.
    - laravel/tinker v1.0.0 requires illuminate/console ~5.1 -> satisfiable by laravel/framework[v5.4.19].
    - Installation request for laravel/tinker v1.0.0 -> satisfiable by laravel/tinker[v1.0.0].
    
    Solución :
    
    ``



