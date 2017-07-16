## Instalar laravel en linux

```sh
composer global require "laravel/installer"
```

Si te muestra un error puede que se deba a que composer no se haya agregado al path de tu S.O., puedes corregirlo abriendo 

`nano ~/.bashrc`

Copia esta linea al principio:
 
`export PATH=~/.config/composer/vendor/bin:$PATH`

Presiona `ctrl + x ` y guarda los cambios con la tecla `y`

Puedes reiniciar la terminal o escribir:

`source ~/.bashrc `

Ahora escribe en la terminal: `laravel --version`

Nota: Si el comando anterior te da error, significa que composer se encuentra en la carpeta `~/.composer` en vez de `~/.config/composer` asi que puedes agregar esta linea al path en vez de la de arriba :

`export PATH=~/.composer/vendor/bin:$PATH`

Ahora ya estás ready para comenzar a desarrollar con laravel, crea tu primer proyecto:

```sh
laravel new myapp
cd myapp
php artisan serve
```
Si no tienes ningun error, tu aplicación estará corriendo en http://localhost:8000/

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
    
### Instalar valet in linux 

Valet es muy parecido a laragon en windows para la creación de host virtuales y nos evita estár ejecutando el  archimegaconocido `php artisan serve`. 

Instalar valet in linux es fácil [valet in linux](https://github.com/cpriego/valet-linux)
   
   `composer global require cpriego/valet-linux`
   
   Si tienes algun problema con curl puedes solucionarlo asi
   `sudo apt-get install php7.1-curl`
   
   Para iniciar valet puedes usar `valet install` esto es automatico y no require volverlo a instalar
   
   
   


