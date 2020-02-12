# Tutorial de LARAVEL

## Contenido

1. [Instalando lo necesario (Windows)](#instalando-lo-necesario)
2. [Estructura de directorios](#estructura-de-directorios)

## Instalando lo necesario

1. [Laragon](https://laragon.org): Instala lo necesario de modo que solo nos ocupemos de lo importante... `{ crear software }`
2. [nodejs](https://nodejs.org/es/)
3. [npm](https://www.npmjs.com/)
4. [visual studio code](https://code.visualstudio.com/)
5. Instalar Laravel: Para poder usar los comandos de laravel en la consola, debemos instalarlo a través de [composer](https://getcomposer.org) y con ejecutando las siguientes líneas en nuestra terminal: \
`composer global require laravel/installer`\

## Estructura de directorios

### app

Contiene el código fuente de la aplicación o lógica de negocios. Los directorios se usan para:

- **Console** : se usa para almacenar nuestros propios comandos
- **Exceptions** : en esta se encuentra el manejador de excepciones, es aquí donde se almacenan las excepciones personalizadas
- **Http** : Contiene los `controladores, middelware y kernel`, este último se usa para registrar los middelware
- **Providers**: Contiene los service provider de la aplicación

### bootstrap

Cuenta con el archivo **app.php** que es el encargado de iniciar o cargar todas las dependencias de la aplicación o framework y el directorio **cache** que es donde se almacenan los archivos generados por laravel y almacenados de modo que no se tengan que volve a generar, por ejemplo los archivos css y js procesados

### config

Almacena todas las configuraciones de la aplicación, ahora:
>todo cambio que deseemos hacer en esos archivos deben registrarse en el archivo env

### database

Contiene todos los archivos requeridos para usar code first como método para gestionar la base de datos

### public

Contiene el archivo **`index.php`** que es el punto de entrada de todas la peticiones que se hacen a la aplicación.

Este es el único punto accesible a nuestra aplicación, por esta razón es aquí donde son almacenados los archivos `css, js, svg, img, etc.` Archivos que deseamos que estén disponibles en nuestra aplicación

### resources

Contiene las `vistas o views` de nuestra aplicación, junto con los archivos `sass, js y css` no compilados y también los archivos de traducción.

### routes

- **web.php** : en este se definen todas las rutas de nuestra aplición
- **api.php** : en este se definen las rutas de una api, este no contiene cookies, ni otros elementos propios de una página web
- **console.php** : se usa para agregar comandos fácilmente
- **chanels.php** : en este se definen los canales o broadcast que nuestra aplicación soporta

### storage

Contiene las vistas compiladas, logs autogenerados por laravel, archivos en cache entre otros. Inicialmente se generan los siguientes directorios, y estos son sus usos

- **app** : se usa para almacenar los archivos generados por nuestra aplicación
  - public : puede ser usada para almacenar archivos generados por el usuario, por ejemplo, imagenes de perfil que deben ser accesibles públicamente. Sin embargo, como se dijo anteriormente los archivos que se ven públicamente están almacenados en la carpeta [public](#public). Entonces para poder acceder a los archivos de esta carpeta, hay que crear un simbolic link desde la carpeta public a la carpeta storage y esto se hace con el comando de artisan `php artisan storage:link`
- **framework** : lo usa laravel para guardar los archivos compilados como las vistas, cache, sesiones, etc
- **logs** : contiene información detallada sobre los errores que ocurren en la aplicación

### test

En esta se almacenan las pruebas unitarias

### vendor

Contiene todas las dependencias de composer, y no se debe tocar sino para leer lo que necesitemos

## Lecciones
