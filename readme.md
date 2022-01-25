Construcción de una aplicación de gestión de proyectos en PHP y MySQL desde cero.

En este caso nos basamos en un tutorial que nos proporciona el código necesario, por lo que muchos de los pasos consisten en copiar y pegar el mismo.

1. Creación de una base de datos de gestión de proyectos:
Comenzaremos creando nuestra base de datos de gestión de proyectos. Las principales tablas que utilizaremos son:

Clientes : datos de la empresa del cliente
Contactos : datos de contacto del cliente. Un cliente puede tener uno o más contactos.
Proyectos — información del proyecto
Hitos — hito del proyecto
Tareas : tareas del proyecto
Horas : tiempo dedicado a cada tarea
Costos — costo de una tarea
Usuarios : datos del usuario; uno puede ser un empleado o un gerente

2. Mediante PhpMyAdmin creamos la base de datos e introducimos las tablas  con toda la información aportada por el tutorial.

3. A continuación replicamos la estructura de archivos y carpetas y el código de los mismos aportado por el creador del tutorial. Debemos asegurarnos de que las rutas esten adapatadas a nuestra estructura de carpetas y de que no haya ningún tipo de error.

4. Por último accedemos al archivo confg.php dentro de la carpeta phpGrid y adaptamos los datos de username, password y db name de acuerdo con nuestra configuración en phpMyadmin. En este caso quedaría de la siguiente manera:

/**/
define('PHPGRID_DB_HOSTNAME','localhost'); // database host name
define('PHPGRID_DB_USERNAME', 'root');     // database user name
define('PHPGRID_DB_PASSWORD', ''); // database password
define('PHPGRID_DB_NAME', 'simple_pm'); // database name
define('PHPGRID_DB_TYPE', 'mysql');  // database type
define('PHPGRID_DB_CHARSET','utf8'); // ex: utf8(for mysql),AL32UTF8 (for oracle), leave blank to use the default charset
/*

5. Una vez más nos aeguramos de que el código está escrito correcatamente y si es así la página ya deberia funcionar con normalidad, permitiendonos acceder a los apartados de "Login as manager" y "Login as employee"

-----------------------------------------------------------------------

6. Continuando con un nuevo proyecto, vamos a implementar un login de usuario y contraseña dentro de cada uno de los apartados (manager y employee).

7. Para ello vamos a reutilizar los 3 elementos de login que utilizamos en el proyecto "bootstrap-npm-starter". Estos son:

sesiones1_login.php
sesiones1_logout.php
sesiones1_principal.php

8. Los copiamos y pegamos en el directorio raiz de este proyecto y procedemos a enlazar de manera que cuando pulsamos en Login as employee accedamos al sesiones1_login.php y cuando pulsamos en login as employee accedamos a sesiones1_login2.php (el cual  ha sido creado para este proyecto en concreto). Estos cambios se van a realizar principalemnte en index.php, tasks.php,  clients.php, login y login2. Además copiamos el contenido del archivo sesiones1_principal.php al inicio de clients y tasks con el fin de que todo este correctamente conectado.

9. Por ultimo, para poder realizar el logout, cambiamos la "Location" que muestra por la de index.php y si está tambien correctamente inluido en clients y tasks nos debería permitir volver a la página de inicio para logearnos de nuevo.
