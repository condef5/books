# Drupal console

Para instalar drupal console en linux basta con descargar el ejecutable 

```sh
$ curl https://drupalconsole.com/installer -L -o drupal.phar
$ mv drupal.phar /usr/local/bin/drupal
$ chmod +x /usr/local/bin/drupal
```
Para actualizar la drupalConsole

```sh
drupal self-update
```

## notes

Para instalar un drupal8 desde la DC basta con el comando `drupal site:install`, [documentación del comando](https://hechoendrupal.gitbooks.io/drupal-console/content/en/commands/site-install.html
