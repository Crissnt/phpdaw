# Instalar laravel

1. instalar composer
2. composer global require laravel/installer
3. Crear carpeta 'laravel' en xampp/htdocs/
4. laravel new nombreProyecto
5. Con Visual Studio Code, abrir la carpeta del proyecto
6. Introducir `php artisan serve` en la consola de Visual Studio (esto arranca la aplicación)

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

* ##### Crear base de datos (con nombre blog, por ejemplo)

# Configurar bases de datos
* Archivo *.env* en raíz del proyecto

* Ejecutar `php artisan migrate`. Esto creará una serie de tablas en la base de datos 'blog'.
* En database/migrations/ se encuentran los esquemas de las tablas creadas con migrate

#### app/models/
* user.php

# Eloquent
## Crear modelo y migración
* Ejecutar *php artisan make:model Nota -m*
Ahora tenemos un nuevo archivo en database/migrations. Dentro de él, pegar
```
    $table->string('nombre');
    $table->text('descripcion');
```

debajo de $table->id en la función *Up*

* También tenemos un nuevo modelo en /app/models llamado nota.php
* Ejecutamos de nuevo `php artisan migrate` para copiar la base a phpMyAdmin

### Entrar en routes/web.php
Añadimos una vista con el siguiente codigo

`Route::view('contactos', 'contact')->name('contact');`

Luego, creamos la vista en *resources/views/* con el nombre contact.blade.php

Añadimos otra vista en routes/web.php

`Route::view('acerca-de', 'about')->name('about');`

Y creamos el documento de la vista en *resources/views* con el nombre about.blade.php

Añadimos controladores en el archivo web.php

```
    Route::get('blog', 'BlogController@index')->name('blog.index');
    Route::get('blog/(post:slug)', 'BlogController@show')->name('blog');
```

Se crean las vistas en views/
* about.blade.php
* blog.blade.php
* home.blade.php
* layout.blade.php

Código vistas:
```
@extends('layout')

@section('content')

<h1>Home</h1>

@endsection
```

Código layout.blade.php

```
<Menu>
    <ul>
    <li><a href="{{ route('home') }}">Home</a></li>
    <li><a href="{{ route('about') }}">Acerca de</a></li>
    <li><a href="{{ route('blog.index')}}">Blog</a></li>
    <li><a href="{{ route('contact') }}">Contactos</a></li>
    </ul>
    </Menu>

    <div>
    @yield('content')
    </div>
```
## Crear registros falsos en la tabla

# Comandos importantes

* php artisan serve - Arranca el servidor

* php artisan key:generate