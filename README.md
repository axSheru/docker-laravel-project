# Acerca de.

En este proyecto se ejemplifica el uso de docker para un proyecto de laravel.
Se utilizan 6 contenedores:

* nginx
* php
* mysql
* composer
* artisan
* npm

# Instrucciones.

Para iniciar el proyecto con composer se debe de ejecutar el siguiente comando:

* docker-compose run --rm composer create-project --prefer-dist laravel/laravel .

Una vez que se termine de construir el proyecto, podremos verlo en la carpeta src.