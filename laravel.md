# Instalar laravel

1. instalar composer
2. composer global require laravel/installer
3. Crear carpeta 'laravel' en xampp/htdocs/
4. laravel new nombreProyecto
5. Con Visual Studio Code, abrir la carpeta del proyecto
6. Introducir php artisan serve en la consola de Visual Studio (esto arranca la aplicación)

<hr>


### public/
* Fichero htaccess

### resources/
#### views/
##### welcome.blade.php
Las lineas que empiezan con '@' son código 'blade'

## app/
### http/
#### controllers/

## routes/
* web.php

##### Crear base de datos (con nombre blog, por ejemplo)

# Configurar bases de datos
* Archivo *.env* en raíz del proyecto

* Ejecutar *php artisan migrate*. Esto creará una serie de tablas en la base de datos 'blog'.
* En database/migrations/ se encuentran los esquemas de las tablas creadas con migrate

#### models/
* user.php

# Eloquent
## Crear modelo y migración
* Ejecutar php artisan make:model Nota -m