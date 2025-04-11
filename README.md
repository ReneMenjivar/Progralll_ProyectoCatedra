                                Sistema de Gestión de Inventarios
Bienvenido al Sistema de Gestión de Inventarios, una aplicación web diseñada para gestionar de manera eficiente clientes, productos, existencias, ventas,
usuarios, reportes y
configuraciones. Desarrollado con Laravel 5, MySQL y Vue.js, este sistema ofrece una interfaz intuitiva accesible
desde el navegador en inventory.test, ejecutándose localmente con Laragon.

                        Requisitos
---> Laragon: Entorno local para ejecutar el sistema.
---> PHP 7.4.33: Requerido por Laravel 5.
---> Node.js: Para procesar archivos JavaScript y CSS.
---> MySQL: Base de datos para almacenar la información.
---> Git: Para clonar el repositorio desde GitHub.

                        Instalación
Instalar dependencias previas:
---> Descarga e instala Laragon desde laragon.org.
---> Descarga e instala Node.js desde nodejs.org.
---> Descarga e instala Git desde git-scm.com.

Clonar el repositorio: Abre una terminal y ejecuta:

git clone https://github.com/ReneMenjivar/Progralll_ProyectoCatedra.git

Acceder al directorio del proyecto:

cd Progralll_ProyectoCatedra
Instalar dependencias:
Instala las dependencias de PHP:

composer install

Instala las dependencias de JavaScript: 

npm install

Configurar el entorno:
Copia el archivo .env.example a .env:
cp .env.example .env

Edita el archivo .env con los datos de tu base de datos MySQL:
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=db_inventory
DB_USERNAME=tu_usuario
DB_PASSWORD=tu_contraseña

Crear las tablas de la base de datos: Ejecuta las migraciones:
php artisan migrate

Compilar los assets: Prepara los archivos de diseño:

npm run dev

Iniciar Laragon:
Abre Laragon y asegúrate de que el servidor esté activo.
Accede al sistema desde el navegador en: http://inventory.test.

                Base de Datos
La base de datos db_inventory está estructurada con las siguientes tablas principales:

- users: Usuarios (nombre, correo, contraseña, rol).
- roles: Roles (Super Administrador, Gerente, Vendedor).
- customers: Clientes (nombre, correo, teléfono).
- products: Productos (nombre, categoría, proveedor, stock, precio).
- categories: Categorías de productos.
- vendors: Proveedores.
- stocks: Movimientos de inventario (entradas/salidas).
- sells: Ventas realizadas.
- sell_details: Detalles de ventas (productos vendidos, cantidades).
- payments: Pagos registrados.
- branches: Sucursales del negocio.
- companies: Información de la empresa.
- menus: Opciones de navegación.
- password_resets: Restablecimiento de contraseñas.
- migrations: Registro de cambios en la base de datos.


                Manual de Usuario
1. Iniciar Sesión
Abre http://inventory.test en tu navegador.
Ingresa tu correo y contraseña. Haz clic en "Iniciar sesión".

3. Gestión de Módulos
Clientes (Super Administrador, Gerente):
Agrega nuevos clientes con nombre, correo y teléfono. Edita o busca clientes existentes.

Productos (Todos los roles):
Gestiona categorías y proveedores. Registra productos con nombre, categoría, stock y precio.

Existencias (Todos los roles):
Registra entradas y salidas de inventario.

Ventas (Todos los roles):
Crea ventas seleccionando productos y cantidades. Registra pagos asociados.

Usuarios (Solo Super Administrador):
Agrega, edita o asigna roles a usuarios.

Reportes (Todos los roles):
Genera reportes por categoría, vendedor, producto, cliente o stock.
Filtra por sucursal o tipo de factura.

Configuración (Solo Super Administrador):
Actualiza datos de la empresa y sucursales. Cambia contraseñas.

5. Roles y Permisos
Super Administrador: Acceso completo a todos los módulos.
Gerente: Gestiona clientes, productos, existencias, ventas y reportes.
Vendedor: Gestiona productos, existencias, ventas y reportes de ventas.

            Tecnologías Utilizadas
Backend: Laravel 5, PHP, Blade.
Frontend: HTML, CSS, Less, JavaScript, Vue.js, CoffeeScript.
Base de datos: MySQL.
Build: Laravel Mix.
Entorno local: Laragon.
⚙ Configuración Avanzada
Compilar assets en tiempo real (desarrollo):

npm run watch

Limpiar caché:

php artisan cache:clear
php artisan config:clear

Regenerar claves (si es necesario):

php artisan key:generate

                    Seguridad
Usa contraseñas seguras para los usuarios.
Configura roles para limitar accesos según las necesidades.
En producción, habilita HTTPS y protege el archivo .env.

                    Notas
Asegúrate de que Laragon esté activo para acceder a inventory.test.
Revisa los logs en /storage/logs/laravel.log si encuentras errores.
Mantén las dependencias actualizadas con:

composer update
npm update

