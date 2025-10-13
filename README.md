Laboratorio #2 – Implementación del Login en Laravel

Universidad Tecnológica de Panamá 
Facultad de Ingeniería de Sistemas Computacionales Licenciatura en Ingeniería de Software 
Curso: Ingeniería Web  
Instructora: Ing. Irina Fong  
Estudiante: Juan Carrion  
Fecha de ejecución:07/10/2025


Introducción

El presente laboratorio tiene como objetivo implementar y documentar el Login utilizando el framework Laravel, aplicando los principios del patrón Modelo-Vista-Controlador.

En Laravel, la arquitectura MVC se distribuyo de esta manera:

Modelos (app/Models): Se encargan de manejar la lógica de negocio y la comunicación con la base de datos.

Vistas (resources/views): Contienen la interfaz gráfica que ve el usuario (HTML, Blade).

Controladores (app/Http/Controllers) → Procesan las solicitudes HTTP, coordinan los modelos y retornan vistas o respuestas.

Rutas (routes/web.php): Definen las URL que responden a las acciones del usuario.

Durante este laboratorio realize migraciones, configuraciones en el archivo .env, al igual que la instalación de dependencias y personalización del módulo de autenticación de Laravel.


Requisitos Previos

PHP	8.2.26
Composer	2.8.12
Laravel 5.18.0
Entorno de Desarrollo	WampServer 
Servidor Web	Apache o Nginx
Base de Datos	MySQL
Editor de Código	Visual Studio Code
NPM	Para compilar los assets (Laravel Mix / Vite)
Sistema Operativo	Windows


Instalación y Configuración

a) Clonar el repositorio:
git clone https://github.com/usuario/Login_Lab.git
cd Login_Lab


b) Instalar las dependencias:
composer install
npm install && npm run dev


c) Crear el archivo de entorno:
cp .env.example .env


d) Configurar las credenciales de la base de datos en .env:
DB_DATABASE=login_lab
DB_USERNAME=root
DB_PASSWORD=


e) Generar la clave de la aplicación:
php artisan key:generate


f) Ejecutar las migraciones:
php artisan migrate

Implementación del Login (Laravel UI)

Para el login se empleó el paquete Laravel UI, que proporciona el scaffolding clásico de login, registro y recuperación de contraseña.

Comandos utilizados:

composer require laravel/ui
php artisan ui bootstrap --auth
npm install && npm run dev


Este flujo genera automáticamente:

Controladores de autenticación (Auth).

Vistas de login y registro (resources/views/auth).

Rutas configuradas en routes/web.php.

Migraciones para la tabla users.


Base de Datos

El sistema se conecta a una base de datos MySQL configurada en el archivo .env.

Tablas principales generadas mediante migraciones:

users

password_resets

failed_jobs

personal_access_tokens

migrations

Comandos ejecutados:

php artisan migrate


Dificultades y Soluciones
Error al ejecutar migraciones: Para solucionarlo verifique la conexión en .env y se ejecutó php artisan migrate:fresh.
Error en npm run dev	Se reinstalaron dependencias con npm install.
Problemas con vistas de autenticación	Se reinstaló Laravel UI y se regeneraron vistas con php artisan ui bootstrap --auth.
Clave de aplicación faltante	Se generó nuevamente con php artisan key:generate.


Comandos Clave Utilizados
composer install
composer require laravel/ui
php artisan ui bootstrap --auth
npm install && npm run dev
php artisan migrate
php artisan serve
