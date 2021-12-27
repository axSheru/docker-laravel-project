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

```docker-compose run --rm composer create-project --prefer-dist laravel/laravel .```

Una vez que se termine de construir el proyecto, podremos verlo en la carpeta src.
Posteriormente debemos de ir al archivo **src/.env** y actualizar la sección de la conexión a la DB
con los datos que tengamos en el archivo **env/mysql.env** . Debe de verse de esta forma:

```
DB_CONNECTION=mysql
DB_HOST=mysql
DB_PORT=3306
DB_DATABASE=homestead
DB_USERNAME=homestead
DB_PASSWORD=secret
```