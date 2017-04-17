# Install rails in windows 10

Descargar el instalador de rails en el siguiente [enlace](http://railsinstaller.org/en)
Ejecutar el instalador, le damos siguiente a todas las opciones, asegurate de instalar git si no lo tienes en tu sistema y agregar ruby, rails y git al path de windows.

Actualizar la version de rails a la version 5.1 con el siguiente comando: 

`gem install rails -v 5.1.0.rc1 --no-ri --no-rdoc`

Creamos un proyecto con react usando webpacker de rails con el siguiente comando

`rails new app webpack=react`

Si estas trabajando con un framework diferente puedes usar las sugientes configuraciones [webpacker](https://github.com/rails/webpacker)

Bien ahora podemos crear nuestros componentes dentro de la carpeta app/javascript

Para porder usar nuestros componentes bastara agregar:
    <%= javascript_pack_tag 'my_component' %> 

Si ocurre algun error al renderizar nuestros componentes podemos agregar 
``document.addEventListener(" DOMContentLoaded ", () => {
  ReactDOM.render(...)
})``
