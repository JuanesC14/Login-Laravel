Laboratorio #2 – Implementación del Login en Laravel

Universidad Tecnológica de Panamá – Facultad de Ingeniería de Sistemas Computacionales
Curso: Ingeniería Web
Instructor: Ing. Irina Fong
Estudiante: Juan Carrión
Fecha de ejecución: 07/10/2025



Introducción

Este laboratorio tiene como finalidad implementar y documentar el módulo de Login utilizando el framework Laravel, aplicando el patrón Modelo-Vista-Controlador (MVC).
La arquitectura de Laravel se organiza de la siguiente forma:

Modelos (app/Models): Manejan la lógica de negocio y la comunicación con la base de datos.

Controladores (app/Http/Controllers): Procesan solicitudes, coordinan modelos y retornan vistas.

Vistas (resources/views): Contienen las interfaces generadas con Blade.

Rutas (routes/web.php): Definen las URL y sus controladores asociados.

Durante su desarrollo se configuró el archivo .env, se instalaron dependencias, se generaron migraciones y se integró el paquete Laravel UI para crear el sistema de autenticación.



Requisitos Previos
Tecnologías Utilizadas

PHP 8.2.26

Composer 2.8.12

Laravel 5.18.0

NPM

MySQL

WampServer

Visual Studio Code

Sistema Operativo Windows



Instalación y Configuración
1. Clonar el repositorio
git clone https://github.com/JuanesC14/Login-Laravel.git
cd Login_Lab
2. Instalar dependencias
composer install
npm install && npm run dev
3. Crear archivo de entorno
cp .env.example .env
4. Configurar base de datos en .env
DB_DATABASE=login_lab
DB_USERNAME=root
DB_PASSWORD=
5. Generar la key de Laravel
php artisan key:generate
6. Ejecutar migraciones
php artisan migrate



Implementación del Login (Laravel UI)

Para el login se utilizó el paquete Laravel UI.

Comandos utilizados:
composer require laravel/ui
php artisan ui bootstrap --auth
npm install && npm run dev

Laravel UI generó automáticamente:

Controladores de autenticación

Vistas en /resources/views/auth/

Estilos con Bootstrap

Rutas de autenticación en web.php

Migraciones necesarias para users



Base de Datos

El proyecto utiliza MySQL como motor de base de datos.
A través de migraciones se generaron las siguientes tablas:

users

password_resets

failed_jobs

migrations

personal_access_tokens

Comando ejecutado:
php artisan migrate




Respaldo de la Base de Datos

Se incluye un respaldo dentro del repositorio:

/database/backup/login_lab.sql

Este archivo contiene la estructura generada por las migraciones durante este laboratorio.


Dificultades y Soluciones
Problema	Solución aplicada
Error al migrar la base de datos	Se revisó la configuración del .env y se ejecutó php artisan migrate:fresh.
Error al compilar assets con npm	Se reinstalaron las dependencias con npm install.
Vistas de autenticación no aparecían	Se reinstaló Laravel UI con php artisan ui bootstrap --auth.
Clave APP_KEY ausente	Se generó nuevamente usando php artisan key:generate.



Comandos Principales Utilizados
composer install
composer require laravel/ui
php artisan ui bootstrap --auth
npm install && npm run dev
php artisan migrate
php artisan serve



Referencias

Laravel Documentation – Authentication
https://laravel.com/docs/8.x/authentication

Laravel/UI Package
https://github.com/laravel/ui

Composer Documentation
https://getcomposer.org/doc/


Información del Desarrollador

Este laboratorio ha sido desarrollado por el estudiante de la Universidad Tecnológica de Panamá:

Nombre: Juan Carrión
Correo: juan.carrion@utp.ac.pa
Curso: Ingeniería Web
Instructor del Laboratorio: Ing. Irina Fong



Fecha de Ejecución

07/10/2025
