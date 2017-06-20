# Drush
Para instalar drush in linux 
> composer global require drush/drush
Para instalar un nuevo sitio con drush
> drush dl --select 
Por defecto nos muestra las versiones para drupal 8, si queremos crear un sitio con drupal 7 tenemos que especificarlo de la sgt manera:
> drush dl drupal7 --select

## Hacks

Para recuperar contraseñas con drush

> drush upwd "user_name" --password=new-password 


