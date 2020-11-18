# Crud en Laravel 8

## Instalar laravel
* En la carpeta /laravel/, ejecutar
`composer create-project --prefer-dist laravel/laravel laravel8_crud`

## Configurar base de datos

### /.env

```
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=laravel_crud
DB_USERNAME=root
DB_PASSWORD=
```

## Crear migración

`php artisan make:migration create_students_table --create=students`

* Habrá creado el archivo /database/migrations/....create_students_table. Introducir 

```
$table->string('first_name');
$table->string('last_name');
$table->string('address');
```

* Ejecutar `php artisan migrate`. Asegurarse de haber creado la base de datos antes en phpMyAdmin

## Crear resource route en el fichero web.php

