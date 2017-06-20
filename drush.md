# Drush
Para instalar drush in linux 

```sh
$ composer global require drush/drush
```

Para instalar un nuevo sitio con drush

```sh 
drush dl --select 
```

Por defecto nos muestra las versiones para drupal 8, si queremos crear un sitio con drupal 7 tenemos que especificarlo de la sgt manera:

```sh
drush dl drupal7 --select
```

## Hacks

Para recuperar contraseñas con drush

```sh 
drush upwd "user_name" --password=new-password 
```

