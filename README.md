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

Podemos probar que todo funcione correctamente corriendo el comando:

```docker-compose up -d --build server```

Posteriormente en nuestro navegador debemos de acceder a la siguiente dirección y deberíamoss de poder ver la pantalla de inicio de Laravel:

__http://localhost:8000/__

La bandera **--build** es opcional, puedes correrla sin problema pero si realizamos alguna modificación en los dockerfiles siempre debemos de añadirla.

**Nota:** Si llegamos a obtener un error de este tipo:

__The stream or file "/var/www/html/storage/logs/laravel.log" could not be opened in append mode: Failed to open stream: Permission denied__

Ejecutamos el siguiente comando:

```docker exec -it laravel-project_server_1 chmod 777 -R /var/www/html```

Una vez levantados los contenedores, para correr comandos de artisan usamos el comando siguiente:

```docker-compose run --rm artisan [COMANDO]```

Para correr un comando de npm usamos:

```docker-compose run --rm npm [COMANDO]```