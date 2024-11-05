## Miembros Grupo:

Garcia Maiztegui	Agustin,
Rojas	Curulla Martin César,
Rosso	Luis
Rojas	Luana
Tomas	Schulteis 
Tomas Arrigo

# Sistema de Autenticación Seguro

# Mockup
https://xd.adobe.com/view/788666e5-3f93-42b3-91e1-e9249a475fc0-2dd5/grid

## Descripción
Este proyecto es una simulación de un sistema de autenticación de usuarios (login) con roles de usuario y administrador, incluyendo funciones de registro, login, y recuperación de contraseñas. Se ha desarrollado bajo las mejores prácticas de seguridad DevSecOps.

## Requisitos
- PHP 7.4+
- MySQL 5.7+
- Servidor Apache/Nginx

## Instalación
1. Clonar el repositorio.
2. Crear la base de datos usando las sentencias incluídas en el archivo 'db.sql' (ubicado en la carpeta raíz del proyecto).
3. Configurar en /model/model.php la conexion a la DB
5. Asegurar el file model.php no sea accesible, solo de manera local.
5. Asegúrese de que las configuraciones de seguridad del servidor web estén implementadas según las recomendaciones.

## Consideraciones de Seguridad
- Validación de contraseñas seguras.
- Uso de consultas preparadas para prevenir inyección SQL.
- Tokens CSRF en formularios para prevenir ataques CSRF.
- Protección contra XSS mediante el uso de `htmlspecialchars`.
- Configuración de headers de seguridad.
- Gestión de sesiones segura.
  
## Ejecutar la Aplicación
1. Asegúrese de que su servidor esté ejecutándose.
2. Navegue a `index.php` en su navegador.
3. Regístrese, inicie sesión y utilice las funciones del sistema.
 
## Consideraciones funcionales:

A - Para comenzar las pruebas, se detalla la creación de los usuarios en el archivo db.sql
Admin - 14276579, pass Mano+1986
User - 123, pass pepeApe88.

B - El sistema cuenta con en su página inicial los campos para incluir usuario y password.
Luego de ingesar los datos, el sistema valildará que no haya usuarios ni correos duplicados.
Al ingresar una nueva cuenta, se validarán las condiciones específicas para las contraseñas
(Mínimo 8 letras, incluyendo 1 mayúscula, 1 minúscula, 1 número y un caracter especial), 
adicionalmente requerirá ciertos datos para su ingreso: 

- DNI
- NOMBRE
- APELLIDO
- FECHA DE NACIMENTO
- CORREO ELECTRONICO
- CONTRASEÑA
- REPETIR CONTRASEÑA

En caso de no cumplir las condiciones de seguridad en la password, el sistema arrojará un error.
Una vez realizadas las validaciones, queda guardado en la base de datos.
Habiendo ingresado con el usuario NO administrador, el sistema lo dirigirá a una página que contiene
diversas imágenes sobre la carrera de ciberseguridad.

Al ingresar con un usuario administrador, detallamos las siguientes funcionalidades:

1 - ingresar un correo electrónico para buscar todos sus accesos al sistema, detallando su ID, e-mail y fecha de acceso.
2 - Posibilidad de desbloquear aquel usuario que haya ingresado más de 2 veces una contraseña incorrecta.
3 - El usuario administrador puede eliminar un usuario seleccionado.
